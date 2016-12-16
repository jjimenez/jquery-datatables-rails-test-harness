# README

This test harness is a simple version of a rails application that includes the jquery-datatables-rails gem.
(https://github.com/rweng/jquery-datatables-rails)

In the Gemfile you can specifiy a particular version of the gem

It currently points to my fork of the gem which includes updates to the most recent dataTables files.

```ruby
gem 'jquery-datatables-rails', git:  'https://github.com/jjimenez/jquery-datatables-rails.git'
```

In this test harness the gem has been installed for responsive datatables as described on the original repo (https://github.com/rweng/jquery-datatables-rails).


After the standard setup for a rails application including installing ruby, rails, and bundle install, run the rails server for the application 

```bash
rails s
```

and navigate to your localhost:3000/test/index page

you should see a table setup with a couple of options to test.
  
 Selecting one of the options from the select will change the display:
 * default is a zero-configuration option for dataTables
 * responsive will adjust and hide columns in an expandable region for each row as the width of the display window gets smaller
 * responsive hide salary is the same as responsive except there will always be an expander and salary will always be in the expander
 

Some things to look for if you update / change the gem you are pointing to:

* look for images to be loaded for sorting
    * there is a rake task to update css url tags to use rails assets helpers
    * keep in mind that in order for these to work, css files have to have .scss extensions
* look in your javascript console for errors

That's right, I didn't create jasmine or other automated tests.

If you update your gem, test the generator by removing 

```
ruby

//= require dataTables/jquery.dataTables
//= require dataTables/extras/dataTables.responsive
```

from the application.js file and 

```
 *= require dataTables/extras/dataTables/responsive.dataTables
 *= require dataTables/jquery.dataTables
 ```
 from the application.css file and rerunning the install generator as per the original repository.
 
 Pull requests to add testing functionality will be accepted!
 
 