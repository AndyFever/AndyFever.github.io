---
layout: post
title: "Setting up a test framework"
modified:
categories: blog
excerpt: "This shows how I set up Cucumber with Selenium using Ruby for automated testing on the mac"
tags: [cucumber, BDD, ruby, capybara, selenium]
date: 2017-08-17
---
As described [here](https://andyfever.github.io/Agile-Testing-with-Cucumber/"), I have got excellent results
from automated testing with BDD using a framework based on Cucumber.  This blog describes how I set up the framework
from scratch using my trusty MacBook pro and a few well written (not by me!) acceptance requirements.

### Requirements

This is the list of tools used in the framework:

- Cucumber
- Ruby Version Manager ([RVM is a environment manager for ruby)](https://rvm.io/ "RVM Link"))
- Ruby 2.3.x
- Ruby Gems ([Ruby Gems is a package manager for ruby ](https://github.com/rubygems/rubygems))
- Capybara ([Capybara helps you to automated BDD scenarios)](https://github.com/teamcapybara/capybara "Capybara Link"))
- Selenium
- Roo ([Roo is a gem for interfacing with spreadsheets ](https://github.com/roo-rb/roo "Link for the Roo gem"))
- Pry ([Pry is a great debugging tool for ruby](https://github.com/pry/pry "Pry Link"))

There are one or two other dependencies used like [Curl](http://macappstore.org/curl/) and [Homebrew](https://brew.sh/). If you haven't used them before then you should do a bit of background reading/setup before carrying on.

### Installing Ruby and Ruby Gems

To install the current development version of Ruby I tend to use Ruby Version Manager (RVM) to manage the Ruby environments - it gives you a lot more flexibility in the long term. In terminal, run the following commands:

	  gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

	  curl -sSL https://get.rvm.io | bash -s stable  
<p></p>
You know have both RVM and Ruby installed. Check it's all worked as expected:
    ruby -v

    ruby 2.3.1p112 (2016-04-26 revision 54768) [x86_64-darwin15]  
<p></p>
To install Ruby Gems, follow the installation instructions that can be found [here](https://github.com/rubygems/rubygems).

### Installing Cucumber

To install Cucumber, do the following:
    gem install cucumber  
<p></p>
That's all there is to that. To see the list of commands available to you now just type:

    cucumber --help  
<p></p>
For a simple example of what cucumber does we can initiate a project. Create a new directory and cd into it. Then type:

    cucumber --init  
<p></p>
Cucumber will then create the following files for you in the directory

    └── features
    ├── step_definitions
    └── support
        └── env.rb  
<p></p>
The features directory will contain all your requirements in the format that cucumber will be able to parse. The step definitions directory will contain all your code to implement the tests.  Finally the env.rb file contains everything Cucumber needs to setup your environment.  This includes selenium.  Talking of which...

### Selenium Setup

Most problems I experienced with this framework where in some way related to Selenium, but the installation process is again simple. Just use the following:

    gem install selenium-webdriver  
<p></p>
That should install the web driver, you still need to specific driver for the browser, in this case we generally used Chrome.  To install we use Homebrew again:

    brew install chromedriver  
<p></p>
This should setup everything you need for your tests to control a browser.

### Setting up your Gemfile

Going forward you will be managing your dependencies which will be stored in the root folder of your project. To create it, run the following while in the root directory of your project:

    echo "source 'https://rubygems.org'" > Gemfile  
<p></p>
You should now have the following setup.

    .
    ├── Gemfile
    └── features
      ├── step_definitions
      └── support
        └── env.rb  
<p></p>
Now in your gemfile, add the following lines.

gem 'selenium-webdriver', '>=3.0.5'
gem 'cucumber'
gem 'test-unit'
gem "minitest"
gem "minitest-reporters"
gem 'pry'
gem 'capybara'
gem 'capybara-screenshot'
gem 'rspec'
gem 'rake'
gem 'savon'
gem 'roo'

Back in your terminal, you can install or update all the gems any time you want by running

    bundle install  
<p></p>
### Setting up the env.rb file

In your IDE, open the env.rb file and save the following code:

    require 'capybara/cucumber'

    Capybara.register_driver :selenium do |app|
      capabilities = Selenium::WebDriver::Remote::Capabilities.chrome
    capabilities['chromeOptions'] = { prefs: $chrome_prefs }
      Capybara::Selenium::Driver.new(app, browser: $browser, desired_capabilities: capabilities)
    end

    Capybara.default_driver = :selenium
    Capybara.default_max_wait_time = 5
    Capybara.wait_on_first_by_default = true  
<p></p>
This will let Capybara know to use the chromedriver.

The next blog will describe creating your first test.
