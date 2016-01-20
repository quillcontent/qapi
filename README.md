QAPI - Quill Platform API published documentation.
========

Our docs are published at http://qapi-docs.quill-platform.com. We use the magic of gh-pages and slate to publish them.

Getting Started
------------------------------

### Prerequisites

You're going to need:

 - **Linux or OS X** — Windows may work, but is unsupported.
 - **Ruby, version 1.9.3 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

 1. Install all dependencies: `bundle install`
 2. Start the test server: `bundle exec middleman server`

You can now see the docs at <http://localhost:4567>.

### Publishing

To publish run 
```rake publish```
