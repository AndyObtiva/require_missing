# require_missing

Require missing gems by first checking if they are installed but not added to Bundler Gemfile, and if unavailable auto install and continue Ruby execution unhindered. 

Supports the idea of optional dependencies. In other words, requiring gems that are not declared in Bundler Gemfile and asking the user whether they want to install/use them or continue execution without them in the middle of running an application (presenting a GUI question if it is a Glimmer app, or otherwise just a command line prompt). Also, the ability to pre-configure require none, require all, or auto-answer prompts.

