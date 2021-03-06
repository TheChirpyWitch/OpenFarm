[![Coverage Status](https://img.shields.io/coveralls/openfarmcc/OpenFarm.svg)](https://coveralls.io/r/openfarmcc/OpenFarm)
[![Code Climate](https://codeclimate.com/github/openfarmcc/OpenFarm/badges/gpa.svg)](https://codeclimate.com/github/FarmBot/OpenFarm)
[![Issue Stats](http://issuestats.com/github/openfarmcc/openfarm/badge/pr)](http://issuestats.com/github/openfarmcc/openfarm)
[![Issue Stats](http://issuestats.com/github/openfarmcc/openfarm/badge/issue)](http://issuestats.com/github/openfarmcc/openfarm)
OpenFarm
========

[OpenFarm](http://openfarm.cc) is a free and open database and web application for farming and gardening knowledge. One might think of it as the Wikipedia or Freebase for growing plants, though it functions more like a cooking recipes site. The main content are Growing Guides: creative, crowd-sourced, single-author, structured documents that include all of the necessary information for a person or machine to grow a plant, i.e.: seed spacing and depth, watering regimen, recommended soil composition and companion plants, sun/shade requirements, etc.

Other use cases: a mobile app for home gardeners, Google providing &ldquo;One Box&rdquo; answers to search queries such as &ldquo;How do I grow tomatoes?&rdquo;, smart garden sensors, automated farming machines.

### Core Contributor Group

If you have any quick questions, ask them on [IRC on Freenode #openfarmcc](https://webchat.freenode.net/?channels=openfarmcc). If the room looks empty it's because our core team uses Slack, we have a bot piping messages back and forth - read on if you want to join that!

Sign up to [our Slack room](http://slack.openfarm.cc/)! We strongly recommend joining this group if you want to get involved and meet the other contributors. 

### Community Discussion Group

To discuss features, feature requests, and ideas, and to interface with our users at large (and contributors not on GitHub), please check out our public [discussion forum](https://www.loomio.org/g/yWm14fG6/openfarm-community-development-group).

## Development

### Getting Started (The Easy Way)

You should use Vagrant to get the OpenFarm system running on your computer. It will avoid having to install the things listed in The Hard Way below. 

1. Install [Vagrant](https://www.vagrantup.com/docs/installation/).
2. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads). 
3. Open your terminal.
4. `$ git clone https://github.com/openfarmcc/OpenFarm.git` - this tells your computer to fetch the data stored in this repository using git.
5. `$ cd OpenFarm` - change to the OpenFarm directory
6. `$ vagrant up` This will take a long time. We're downloading a whole bunch of stuff. Go make yourself a pot of coffee, or brew some tea. If something goes wrong at this point, reach out to Simon directly at [slack.openfarm.cc](http://slack.openfarm.cc/). Once Vagrant is set up on your system, you'll need to tell the server to start running. To do this:
8. `$ vagrant ssh` - this makes you access the new virtual server we just created to run OpenFarm on.
9. `cd /vagrant` - the `vagrant` directory is mirrored in your own computer. If you add a file there, you'll see it appear here. 
10. `rails s` - actually run the Rails server!
11. you should now be able to access OpenFarm on your local system at http://localhost:3000. If all went well, you will have a seeded database and can use the account `admin@admin.com` with password `admin123`. 

The above is still being patched, so please reach out to us if something went wrong!

### Getting Started (The Hard Way)

You will need to install [Ruby](http://www.ruby-lang.org/en/), [Rails](http://rubyonrails.org/), [ElasticSearch](http://www.elasticsearch.org/), and [Mongodb](http://docs.mongodb.org/manual/installation/) before you can get an OpenFarm server up and running on your local machine. Once you have these prerequisites to get started with a local copy of the project, run:

```bash
$ git clone https://github.com/openfarmcc/OpenFarm.git
$ cd OpenFarm
$ bundle install
$ rake db:setup
$ echo "ENV['SECRET_KEY_BASE'] = '$(rake secret)'" >> config/app_environment_variables.rb
$ rails s
```

Then, visit [http://127.0.0.1:3000/](http://127.0.0.1:3000/) in your browser to see the OpenFarm web application running on your local machine. If all went well, you will have a seeded database and can use the account `admin@admin.com` with password `admin123`.

Remember that `/vagrant` folder in the Vagrant VM is largely for convenience, and working in it can cause unexpected behavior with other tools - you should do your work in your own non-vagrant environment. Use the environment you're most familiar with to program, and Vagrant will do the rest.

**If you had any problems** installing bundles getting up and running etc see the [Common Issues Page](https://github.com/openfarmcc/OpenFarm/wiki/Common-Issues).

#### How to Contribute

Help us [translate the website](https://www.transifex.com/projects/p/openfarm/).

For code, have a look at our [contribution guidelines](https://github.com/openfarmcc/OpenFarm/blob/master/CONTRIBUTING.md).

Want to see the big picture? We have a [project roadmap](https://docs.google.com/spreadsheets/d/13_VQDOm8HpM49Ql3HyNfL9ut5JlqbLEDA9yEk5OqgqU/edit?usp=sharing) for that!

### FAQ

Have a look at the [FAQ](http://openfarm.cc/pages/faq) for some frequently asked questions about contributing (Angular, Issue Trackers, IRC Channels).

### User Flow

![User Flow Diagram] (http://i.imgur.com/YowIq1N.jpg)

![Information Architecture Diagram] (http://i.imgur.com/qZzF4OZ.jpg)

### Mockups

To view the most recent mockups, click [here](https://drive.google.com/open?id=0B-wExYzQcnp3cVZvZ3JXb3FDZTg&authuser=0).

### Contributors

We encourage everyone to contribute! From newbies, to pros, to people who don&#8217;t write software, to those with just a few ideas to share &mdash; we greatly appreciate everyone&#8217;s input and are happy to help you help us. We strive for diversity on our team and are dedicated to making a safe space and community for everyone. To help us ensure this, We have created and adopted a [Code of Conduct](https://openfarm.cc/pages/code_of_conduct?locale=en).

Here are our [current contributors](https://github.com/openfarmcc/OpenFarm/graphs/contributors) here on GitHub. But that's just people who contribute code. There's a whole host of people who contributed financially, and people contribute guides on the actual website too!

### Software License

The MIT License (MIT)

Copyright (c) 2014 Farmbot Project, et. al. [(http://go.farmbot.it/)](http://go.farmbot.it/).

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

### Data License

All data within the OpenFarm.cc database is in the [Public Domain (CC0)](creativecommons.org/publicdomain/zero/1.0/).
