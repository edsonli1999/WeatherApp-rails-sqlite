# Tech Stack
- Ruby on Rails, Tailwind CSS, both Postgresql and Sqlite3, deployed on Heroku and Fly.io
- Due to ease of deployment, Fly.io would most likely be the most updated out of the 3.
- Fly.io link (Sqlite3): https://edsons-weather-app.fly.dev
- AWS EB link (Sqlite3): http://edsons-weather.ap-southeast-2.elasticbeanstalk.com
- Heroku link (Postgresql): https://frozen-peak-54821-90696d8859b1.herokuapp.com

# Some important CLI commands

## To start server in CLI
### (windows 11 cmd) 
  - Navigate to the app home directory
  - run using the command: `ruby bin/rails s`
### (on wsl)
  - Navigate to app home directory
  - run using the command: `bin/dev`
  - alternatively: bin/rails server

## To generate a new page (tested in the home page)
  - Command: `bin/rails generate controller NAME [action action] [options]`
  - Example: `bin/rails generate controller Greetings hello`
  - Full documentation: https://guides.rubyonrails.org/command_line.html

## Changing DB from sqlite to postgresql using cli
  - `bundle exec rails db:system:change --to=postgresql`
  - https://www.youtube.com/watch?v=AA6GZBPeveU

# Deployment notes
  - This app exists on both Heroku and Fly.io
  - links at the top of this readme

### To deploy to AWS Elastic Beanstalk:
  - (Tested) DB is Sqlite3
  - run `bundle lock --add-platform ruby` to add platform ruby to Gemfile.lock
  - run `bundle` to install missing gems
  - run `zip ../rails-default.zip -r * .[^.]*`, modifying the .zip name is possible but not necessary
  - Go to `https://ap-southeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-southeast-2#/environments` and create new environment and upload source code there (tested) OR upload source code on an existing environment (untested)

### To deploy to Heroku: 
  - change DB to postgresql 
  - run `bundle` to install missing gems
  - commit to git, then run `git push heroku`

### To deploy to Fly.io 
  - change DB to sqlite3
  - `bundle` to install missing gems
  - then run `fly deploy`

# Ruby version
ruby 3.2.2 (2023-03-30 revision e51014f9c0) [x86_64-linux]

# Resources:
Main tutorial (https://www.youtube.com/watch?v=PjVzoW-rB9U)
