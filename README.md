# README

1. `rails new friends`
2. Generate the `/home` view and associated controller: `rails g controller home index`
3. Point the `/root/index` route to the `/` route: modify the `config/routes.rb` file to
```
Rails.application.routes.draw do
  root 'home#index'
end
```

- Create a new RoR project: `rails new friends`
- Create a model named `friends` and a DB named `Friends` with the following columns: `last_name`, `first_name`, `birthdate`.
```
 rails g scaffold friends first_name:string last_name:string birthdate:date
 rails db:migrate
```

- Manipulate the `friend` object:
  ```
  rails console
  ```
  - create: `Friend.new(first_name:"Roger", last_name:"Rabit")`
  - get:
    - one result: `Friend.find_by(first_name:"Roger")`
    - multiple results: `Friend.where(firt_name:"John")`
  - update:
  ```
  roger = Friend.find_by(id:2)
  roger.update(:birthdate => Date.new(1995,03,10))
  ```
  - finds with condition: `Friend.where("LENGTH(first_name) > 2")`
  - delete:
  ```
  roger = Friend.find_by(id:2)
  roger.delete
  ```
- Create HTTP routes to:
  - GET one friend: `/friends/[:id]`
  - GET all friends: `/friends`
  - POST: `/friends/new` 
  - PUT/PATCH a friend via an id: `/friends/[:id]/edit`
  - DELETE 1 user: `/friends/[:id]`


* Ruby version
  ruby 3.2.0 (2022-12-25 revision a528908271) [x86_64-linux]

* Database initialization
```
rails db:migrate
```

* Instructions
- Start the server: `rails s`
- Go on `https://localhost:3000`

