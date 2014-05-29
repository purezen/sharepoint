# Sharepoint

Sharepoint is a Rails application that aims to be a simple interface for managing and
sharing files in a web browser. It lets users create folders and upload, download
and share files. Admins can manage users, groups and permissions.

Website:
http://purezen.github.io/sharepoint

Bug reports and feature requests:
https://github.com/purezen/sharepoint/issues/new


Requirements
------------
The requirements for running Boxroom are:

 * Ruby 2.1.1, 2.1.0, 2.0.0 or 1.9.3
 * Rails 4.1.1
 * A database (e.g. MySQL or SQLite)


Installation
------------
Follow these steps:

 1. Extract, checkout or clone Boxroom into a new folder
 2. `cd` into the new folder
 3. Install necessary gems: `$ bundle install`
 4. Run the install script: `$ bundle exec rake install`
 5. Start the server: `$ bundle exec rails server`
 6. Point your browser to http://localhost:3000/
 7. Enjoy!


Upgrading to Rails 4
--------------------
Follow these steps:

 1. Make a backup of your current `boxroom` folder (e.g. by renaming it to `boxroom.bak`)
 2. Extract, checkout or clone the Rails 4 version of Boxroom into a new folder
 3. Copy the `uploads` folder from your backed up version to the new version
 4. Copy `config/database.yml` from back up to the new version
 5. When using SQLite: copy `db/development.sqlite3` and/or `db/production.sqlite3` from back up to the new version
 6. Install necessary gems: `$ bundle install`
 7. Run the install script: `$ bundle exec rake install`

If you run into difficulties, please get in touch via the [issue tracker](https://github.com/purezen/sharepoint/issues/new).


Mail settings
-------------
Boxroom sends email on the following occasions:

 * When inviting new users
 * On a reset password request
 * When a file is shared

For the application to be able to send email, a few things have to be set up. Depending on the environment
you're working in, either open `config/environments/development.rb` or `config/environments/production.rb`.
Uncomment the following lines and fill in the correct settings of your mail server:

```ruby
config.action_mailer.delivery_method = :smtp
config.action_mailer.smtp_settings = {
  :address => 'mailhost',
  :port => 587,
  :user_name => 'user_name',
  :password => 'password',
  :authentication => 'plain'
}
```

Also uncomment the following and replace `localhost:3000` with the host name the app will be running under:

```ruby
config.action_mailer.default_url_options = { :host => 'localhost:3000' }
```

Lastly, you have to choose the address emails will be sent from. You can do
this by uncommenting and adjusting the following:

```ruby
ActionMailer::Base.default :from => 'Sharepoint <yourname@yourdomain.com>'
```

Credits
-------

Members:

Aditya Bhardwaj - aditya2204@gmail.com
Ishaana Rai - ishaana193@gmail.com
Shashank Salwan - shashanksalwan@gmail.com

Icons:

 * [Yusuke Kamiyamane](http://p.yusukekamiyamane.com/)


License
-------
Copyright (c) 2014 JIIT Students

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the
Software, and to permit persons to whom the Software is furnished to do so, subject
to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A
PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
