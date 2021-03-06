# API to power a software similar to LinkedIn

[![Build Status](https://travis-ci.org/ghoshnirmalya/linkedin-rails.svg?branch=master)](https://travis-ci.org/ghoshnirmalya/linkedin-rails)
[![Maintainability](https://api.codeclimate.com/v1/badges/44ac5eaed20a31c9b97c/maintainability)](https://codeclimate.com/github/ghoshnirmalya/linkedin-rails/maintainability)

A clone of LinkedIn software with basic functionalities.

<p align="center">
  <img src="https://user-images.githubusercontent.com/6391763/47952048-5689f800-df8f-11e8-9491-472b3cb9ce00.png" alt="Logo">
</p>

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### API documentation

The API documentation is available [here](https://documenter.getpostman.com/view/325212/RWMFtU4c#rate-limit).

### Prerequisites

What things you need to install the software and how to install them:

- [Docker](https://docs.docker.com/)

### Installing

#### 1. Clone the repository

```
git clone git@github.com:ghoshnirmalya/linkedin-rails.git && cd linked-rails
```

#### 2. Build the project

```
docker-compose build
```

#### 3. Create the database

```
docker-compose run linkedin.rails.web rake db:create
```

#### 4. Copy the env files

```
cp .env.development.example .env.development && cp .env.test.example .env.test
```

#### 5. Run the migrations

```
docker-compose run linkedin.rails.web rake db:migrate
```

Please have a look at [Quickstart: Compose and Rails](https://docs.docker.com/compose/rails/) if you run into any trouble while installing.

## Running the tests

You can run all the specs using the following command:

```
docker exec -it linkedin-rails_linkedin.rails.web_1 rspec .
```

If you want to run a single spec, use the following pattern:

```
docker exec -it linkedin-rails_linkedin.rails.web_1 rspec spec/controllers/v1/users_controller_spec.rb
```

You'll have to update the `.env` files to make all the specs pass.

## Checking the logs

You can check the development logs using the following command:

```
docker exec -it linkedin-rails_linkedin.rails.web_1 tail -f log/development.log
```

If you want to check the test logs, you'll need to use the following command:

```
docker exec -it linkedin-rails_linkedin.rails.web_1 tail -f log/test.log
```

## Built With

- [Ruby on Rails](https://rubyonrails.org/) - The web framework used to build the app
- [Docker](https://www.docker.com/) - Used to containerize the app
- [Postgresql](https://www.postgresql.org/) - The database used to store the data

## Contributing

If you find any bugs, please feel free to create an issue for that.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

- [How to Test Rails Models with RSpec](https://semaphoreci.com/community/tutorials/how-to-test-rails-models-with-rspec)
- [Writing One-Liner RSpec Tests in Rails with Shoulda-Matchers](https://semaphoreci.com/community/tutorials/writing-one-liner-rspec-tests-in-rails-with-shoulda-matchers)
- [An Introduction to Using JWT Authentication in Rails](https://www.sitepoint.com/introduction-to-using-jwt-in-rails/)
- [Token-based authentication with Ruby on Rails 5 API](https://www.pluralsight.com/guides/token-based-authentication-with-ruby-on-rails-5-api)
- [Simple approach to Rails 5 API authentication with Json Web Token](https://www.codementor.io/omedale/simple-approach-to-rails-5-api-authentication-with-json-web-token-cpqbgrdo6)
- [Tutorial: Create a simple messaging system on Rails](https://medium.com/@danamulder/tutorial-create-a-simple-messaging-system-on-rails-d9b94b0fbca1)
- [How to test Rails mailers using RSpec](https://www.lucascaton.com.br/2010/10/25/how-to-test-mailers-in-rails-with-rspec/)
- [Sending emails with ActionMailer and Sidekiq](https://gist.github.com/maxivak/690e6c353f65a86a4af9)
- [RSpec Cheatsheet](https://gist.github.com/eliotsykes/5b71277b0813fbc0df56)
- [Factory Bot cheatsheet](https://devhints.io/factory_bot)

## Todo

- [x] Authentication
- [x] Make APIs follow JSON-API specification
- [x] Users Listing API
  - [x] Search (for Users)
- [x] Companies Listing API
  - [x] Search (for Companies)
- [x] Jobs Listing API
  - [x] Search (for Jobs)
- [x] Conversations Listing API
  - [x] Messages belonging to a conversation Listing API
- [x] Send an email after a new user signs up
- [x] Send an email after an existing user requests for a new password
