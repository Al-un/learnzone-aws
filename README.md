| branch  | status                                                                                                                                         |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| master  | [![master](https://circleci.com/gh/Al-un/learnzone-aws/tree/master.svg?style=svg)](https://circleci.com/gh/Al-un/learnzone-aws/tree/master)    |
| develop | [![develop](https://circleci.com/gh/Al-un/learnzone-aws/tree/develop.svg?style=svg)](https://circleci.com/gh/Al-un/learnzone-aws/tree/develop) |

# Rails-on-AWS

Testing AWS stuff:

- How to deploy a Rails app on AWS with a Postgresql DB
  - manual deploy
  - involved components
  - database migration and stuff
- Integration with CircleCI
- Integration with Travis CI

Sources:

- https://www.awsrails.com/#create-a-rails-app-to-deploy

## Steps

- Adding `dotenv-rails` gem
- Generate employee:
  ```shell
  rails generate scaffold Employee first_name:string last_name:string
  ```
- Configuring databases url for development and test
- Setup DB:
  ```shell
  rails db:setup
  ```
- Once DB are setup, create the table:
  ```shell
  rails db:migrate
  ```
- Update `config/routes.rb`:
  ```ruby
  root to: "employees#index"
  ```
- run server
  ```shell
  rails server
  ```
