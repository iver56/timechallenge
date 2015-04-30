# Setup

Create a postgres user and database for the project:

Fill out the following files.
Secret_token can be generated with ```rake secret```.
Get GitHub auth tokens from https://www.github.com.

- config/database.example.yml -> config/database.yml
- config/local_env.example.yml -> config/local_env.yml
- config/initializers/secret_token.example.yml -> config/initializers/secret_token.yml

Install gems ```bundle install```.

Set up the database ```rake db:reset``` (runs create, schema load, seed).

Run server ```rails server```.

# Production stuff

- Run migrations (RAILS_ENV=production bundle exec rake db:migrate)
- Precompile assets (RAILS_ENV=production bundle exec rake assets:precompile)
- Change config/unicorn.rb to match your environment
- Fire up unicorn (bundle exec unicorn_rails -c config/unicorn.rb -D -E production)
- Add nginx listening stuff
