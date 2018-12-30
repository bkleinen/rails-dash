# starting this app with RVM

    $ cd HelloRails
    ruby-2.5.1 - #gemset created /Users/kleinen/.rvm/gems/ruby-2.5.1@rails2018
    ruby-2.5.1 - #generating rails2018 wrappers.........

## as it's a new gemset, bundler is not found:
    /HelloRails (master)$ bundle install
    -bash: bundle: command not found

    /HelloRails (master)$  gem install bundler
    Fetching: bundler-1.17.3.gem (100%)
    Successfully installed bundler-1.17.3
    1 gem installed
    /HelloRails (master)$ bundle

bundler installs all gems and compiles nokogiri

## start rails

### Correct Gemset??

     HelloRails (master)$ rvm use
     Using /Users/kleinen/.rvm/gems/ruby-2.5.1 with gemset rails2018

    HelloRails (master)$ rails s

# Creating a new Rails app with RVM Gemsets

## Create the gemset and ruby-* files:

    /ruby-dash$ rvm use 2.5.1@rails2018 --create --ruby-version
    ruby-2.5.1 - #gemset created /Users/kleinen/.rvm/gems/ruby-2.5.1@rails2018
    ruby-2.5.1 - #generating rails2018 wrappers.........
    Using /Users/kleinen/.rvm/gems/ruby-2.5.1 with gemset rails2018
    19:33:48-kleinen~/mine/current/htw/ruby-dash$ ls -lart
    total 16
    drwxr-xr-x  49 kleinen  staff  1568 Dec 30 19:31 ..
    -rw-r--r--   1 kleinen  staff    10 Dec 30 19:33 .ruby-gemset
    drwxr-xr-x   4 kleinen  staff   128 Dec 30 19:33 .
    -rw-r--r--   1 kleinen  staff    11 Dec 30 19:33 .ruby-version
    19:33:51-kleinen~/mine/current/htw/ruby-dash$

## install Rails, create App, move ruby-* files down

    /ruby-dash$ gem install rails
    /ruby-dash$ rails new HelloRails
    /ruby-dash$ cd HelloRails

    /ruby-dash$ mv ../ruby-* .

# CDing in Dir makes rvm use right Gemset
can be checked like this:

    /HelloRails (master)$ cd ..
    /ruby-dash$ rvm use default
    Using /Users/kleinen/.rvm/gems/ruby-2.4.1

    /ruby-dash$ cd HelloRails/

    /ruby-dash/HelloRails (master)$ rvm use
    Using /Users/kleinen/.rvm/gems/ruby-2.5.1 with gemset rails2018


# Emptying the Gemset

     /HelloRails (master)$  rvm use
     Using /Users/kleinen/.rvm/gems/ruby-2.5.1 with gemset rails2018

     /HelloRails (master)$ ls $(rvm gemdir)/gems
     actioncable-5.2.2		byebug-10.0.2			listen-3.1.5			rack-test-1.1.0			spring-watcher-listen-2.0.1
     actionmailer-5.2.2		capybara-3.12.0			loofah-2.2.3			rails-5.2.2			sprockets-3.7.2
     actionpack-5.2.2		childprocess-0.9.0		mail-2.7.1			rails-dom-testing-2.0.3		sprockets-rails-3.2.1
     actionview-5.2.2		chromedriver-helper-2.1.0	marcel-0.3.3			rails-html-sanitizer-1.0.4	sqlite3-1.3.13
     activejob-5.2.2			coffee-rails-4.2.2		method_source-0.9.2		railties-5.2.2			thor-0.20.3
     activemodel-5.2.2		coffee-script-2.4.1		mimemagic-0.3.3			rake-12.3.2			thread_safe-0.3.6
     activerecord-5.2.2		coffee-script-source-1.12.2	mini_mime-1.0.1			rb-fsevent-0.10.3		tilt-2.0.9
     activestorage-5.2.2		concurrent-ruby-1.1.4		mini_portile2-2.4.0		rb-inotify-0.10.0		turbolinks-5.2.0
     activesupport-5.2.2		crass-1.0.4			minitest-5.11.3			regexp_parser-1.3.0		turbolinks-source-5.2.0
     addressable-2.5.2		erubi-1.8.0			msgpack-1.2.4			ruby_dep-1.5.0			tzinfo-1.2.5
     archive-zip-0.11.0		execjs-2.7.0			multi_json-1.13.1		rubyzip-1.2.2			uglifier-4.1.20
     arel-9.0.0			ffi-1.9.25			nio4r-2.3.1			sass-3.7.2			web-console-3.7.0
     bindex-0.5.0			globalid-0.4.1			nokogiri-1.9.1			sass-listen-4.0.0		websocket-driver-0.7.0
     bootsnap-1.3.2			i18n-1.3.0			public_suffix-3.0.3		sass-rails-5.0.7		websocket-extensions-0.1.3
     builder-3.2.3			io-like-0.3.0			puma-3.12.0			selenium-webdriver-3.141.0	xpath-3.2.0
     bundler-1.17.3			jbuilder-2.8.0			rack-2.0.6			spring-2.0.2


     HelloRails (master)$ rvm gemset empty
     Are you SURE you wish to remove the installed gems for /Users/kleinen/.rvm/gems/ruby-2.5.1@rails2018?
     (anything other than 'yes' will cancel) > yes
     installing gem /Users/kleinen/.rvm/gem-cache/gem-empty-1.1.2.gem --local --no-ri --no-rdoc.
     Successfully uninstalled actioncable-5.2.2
     .....

All gems deleted!

    /HelloRails (master)$ ls $(rvm gemdir)/gems
    /HelloRails (master)$

# installing all gems

    /HelloRails (master)$  rvm use
    Using /Users/kleinen/.rvm/gems/ruby-2.5.1 with gemset rails2018
    
    (if not in the right gemset: )
    
    /HelloRails (master)$ rvm use 2.5.1@rails2018
    Using /Users/kleinen/.rvm/gems/ruby-2.5.1 with gemset rails2018
    
    /HelloRails (master)$ bundle install
    
