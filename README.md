# Week 4 Comprehensive Assessment

Fork this repository, update this file to include your answers, and submit a pull request. You may refer to any notes, past projects, or external resources you want. The questions do not have to be completed in order.

* The routes for the `Photo` resource should be nested under the `User` resource. What line should I put in `config/routes.rb` to create a complete set of nested RESTful routes for these resources?

[answer]resources :users do
          resources :photos
        end


* A `User` will have many `Articles`. I need to create a migration for the articles table that has a title, body and something to link it to the User that owns it. What should I run on the command line to get started?

[answer] $ rails g model Article title body user:references

* When do I use `has_many` vs `has_many :through`?

[answer] use "has_many" when there is a one to many relationship between resources, use "has_many :through" when you want to have a many to many relationship between resources.

* How can I I iterate through all of the articles associated with the current user? Write the code that would make this happen.

[answer] current_user.articles.each do |article|
            <insert stuff you want to do here>
         end


* How can I create a new article associated with a user who has_many articles?

[answer]current_user.articles << Article.create (title: "cool new article", body: "cool stuff")


* What method does Devise give us that represents a user who is logged in?

[answer]current_user


* What command runs my migrations on Heroku?

[answer]$ heroku run rake db:migrate


* What command will show the logs on Heroku?

[answer]$ heroku logs


* Describe the purpose of Heroku

[answer] to host applications (using postgres databases only) in the cloud, so they can be accessed by other people over the internet.

* Describe when you would use polymorphic relationships

[answer] when you want to associate a particular resource with multiple other resources in the same fashion as one another.
