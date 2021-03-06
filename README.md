This page is for installing and using Slate on the native OS, as opposed to using Vagrant or Docker.

## Dependencies

Minimally, you will need the following:

* [Ruby](https://www.ruby-lang.org/en/) >= 2.3
* [Bundler](https://bundler.io/)
* [NodeJS](https://nodejs.org/en/)

Please note, only Linux and macOS are officially supported at this time. While slate should work on Windows, it is unsupported.

See below for installation instructions for different OSes / distros.

### Installing Dependencies on Ubuntu 18.04+

Install Ruby, NodeJS, and tools for compiling native ruby gems:
```bash
sudo apt install ruby ruby-dev build-essential libffi-dev zlib1g-dev liblzma-dev nodejs patch
```

Update RubyGems and install bundler:

```bash
sudo gem update --system
sudo gem install bundler
```

### Installing Dependencies on macOS

First, install [homebrew](https://brew.sh/), then install xcode command line tools:

```bash
xcode-select --install
```

Agree to the Xcode license:

```bash
sudo xcodebuild -license
```
Install ruby:

```bash
brew install ruby
```

Install nodejs runtime:

```bash
brew install node
```


Update RubyGems and install bundler:

```bash
gem update --system
gem install bundler
```

## Getting Set Up
Install ruby gems for slate:

```shell
# either run this to run locally
bundle install
```

Note: if the above fails on installing nokogiri and using macOS see
[here](https://github.com/sparklemotion/nokogiri.org/blob/master/docs/tutorials/installing_nokogiri.md#macos)
for some helpful tips on things that might help.

## Running slate

You can run slate in two ways, either as a server process for development, or just build html files.

To do the first option, run:

```bash
bundle exec middleman server
```

and you should see your docs at http://localhost:4567. Whoa! That was fast!

The second option (building html files), run:

```bash
bundle exec middleman build
```
 
## What Now?

The next step is to [learn how to edit `source/index.md` to change the content of your docs](Markdown-Syntax). Once you're done, you might want to think about [deploying your docs](https://github.com/slatedocs/slate/wiki/Deploying-Slate).