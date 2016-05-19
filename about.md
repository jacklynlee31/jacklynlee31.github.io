<b>Setting up Laravel Valet</b>

You will need to install Homebrew (http://brew.sh/) in order to use Laravel Valet.

If Homebrew isn't already installed, paste this into the command line:
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

It may prompt you for a password during installation. Use the same password from your local computer.

Make sure you have the latest version: brew update

Install PHP 7.0 using Homebrew: brew install homebrew/php/php70

Install Valet with Composer: composer global require laravel/valet

The installation worked well for me. (And composer hates me, so that's saying something.)

Now: valet install

When I tried to install I got a 'command not found: valet' error. I fixed it by going into my bash profile and adding:

alias valet="~/.composer/vendor/bin/valet"

You may want to add an alias regardless if you don't have one. It should make working with valet a little easier.

Now it's time to make sure Valet is running.

Make a folder on your desktop and cd into it.
Use: valet park

Next, create a new Laravel project: laravel new example

Because my .bash_profile will never love me, I had to go through some hoops to get this set up. Regardless, if you need an alias for laravel:

alias laravel='~/.composer/vendor/bin/laravel'

Then you'll have to source your bash profile. For me, I use:
source ~/.bash_profile

It is probably different from yours.

At this point I used 'composer install'

Once your project is created, open it in your browser.
My project name was 'example' so I put example.dev in my browser.

Now, whenever you go to http://folder-name.dev you will be able to see the site. (WITHOUT SWITCHING IT IN MAMP!!)

You can also share your local instance: valet share

There will be links in there you can copy and send to whoever you want. They don't have to have valet installed on their computer for it to work.

NOTE: To share the site, your 'tunnel' must be open. If you Ctrl+C out of the 'valet share' screen, they won't be able to view your local instance.

My site is not fully set up, but when I used valet share I was able to see the HTTP Requests showing '500 Internal Server Error.'

Another thing to be excited about: valet logs

Now you can open the logs right in the command line.

Small note: Make sure to change '.env example' to 'env' and generate an Application key. That messed me up for a second.
