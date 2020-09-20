# require_missing

Require missing gems by first checking if they are installed but not added to Bundler Gemfile, and if unavailable auto-install and continue Ruby execution unhindered. 

Supports the idea of optional dependencies. In other words, requiring gems that are not declared in Bundler Gemfile and asking the user whether they want to install/use them or continue execution without them in the middle of running an application (presenting a GUI question if it is a Glimmer app, or otherwise just a command line prompt). Also, the ability to pre-configure require none, require all, or auto-answer prompts.

## Instructions

Simply use Ruby's `require` as usual. If users run an app without running `gem install` or `bundle install` first, require_missing will prompt the user whether they want to install the gem during runtime, and if yes, the app continues after install unhindered. During install, it will add the gem to `Gemfile` if the file exists and the gem is not there already. 

If you run the app with the environment variable `REQUIRE_MISSING_AUTOINSTALL=true`, then calling `require` on an unavailable gem will auto-install it regardless of whether it was installed or declared in Bundler. It will also auto-add it to `Gemfile` if the file exists (unless it is already there but not installed).
