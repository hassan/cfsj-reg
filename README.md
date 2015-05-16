Registration
============

First pass at a generic web/email-based registration app for use with
Code for San Jose projects like the Road Closure Notification (RCN) app.

My intent is to keep functions for RCN separated into microservices as much
as possible: email registration, phone registration, preferences, notifications,
so each can be implemented independently (and not necessarily in Ruby on Rails).

Secondarily I want to figure out what CfSJ projects should include by default
(see Generic components and Generic services below).

### What this service will do

Phase 1: Allow people to register an email address to receive
alerts related to road closures in San Jose, based on TBD criteria (neighborhoods,
council districts, route end points).

Phase 2: Enable registration/alerting via SMS (text message).

### Generic components

* License
* Data attribution if public data used
* Privacy Policy
* Internationalization support (multi-language)

### Generic services

Need to explore the feasibility/appropriateness of using 3rd-party services e.g.

* email sending
* logging
* analytics
* others?

in the context of CfSJ projects.

Setup
-----
### Ruby on Rails

Initial config uses PostgreSQL for the database, but any supported DB will work.

### devise (authentication gem) setup instructions

```
Some setup you must do manually if you haven't yet:

  1. Ensure you have defined default url options in your environments files. Here
     is an example of default_url_options appropriate for a development environment
     in config/environments/development.rb:

       config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

     In production, :host should be set to the actual host of your application.
```
In this repo, the development mailer settings assume use of ```mailcatcher```
(below) and [pow](http://pow.cx/) as your dev server using the 'cfsj-reg.dev' hostname;
adjust as necessary for your environment.

Everything else for devise is already baked into the app as is.

### mailcatcher

For testing mail sending, install and run the [mailcatcher](http://mailcatcher.me/)
gem on your local dev machine. This is extremely useful for checking devise functions
like email confirmation, password reset, etc.
