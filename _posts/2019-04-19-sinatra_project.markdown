---
layout: post
title:      "Sinatra Project"
date:       2019-04-19 19:53:36 +0000
permalink:  sinatra_project
---


Creating a web application from scratch is intimidating, but I learned throughout my Learn lessons that as long as I had a plan of what I wanted to create, it would make the process much easier. I didn't need to know all the code I would use or how I would use it. Instead I needed to focus on what I wanted my project to look like, what kind of models and how many I would have, how many views, what kind of relationships through associations would my models have and any other basic components that are used in an MVC(models-views-controller) application. So after planning this out on paper it was time for me to generate my sinatra app. Fortunately, I found this really handy gem called Corneal that allows you to generate a Sinatra template with all the required environments, gems, and configurations.

At this point I had everything ready to begin, but had no idea what I wanted to create. So, I spoke with my wife and asked her what was an application that she could use or thought would be helpful to others. She loves interior design and decorating, so she wanted a way to keep track of the paint colors she had used in the rooms around the house. She recalled there being a time where she needed to retouch the paint on a wall, but could not remember the color or brand she had used. Having a simple application like this where she could log in and add rooms and colors would've saved her from multiple trips to the store to get that perfect match of paint. 

I began my application with 3 models; a User, Room, and Paint model. However, as I started to lay out the structure for my app I realized that I didn't need a seperate model for Paint. Instead, I opted to give a Room attributes of a paint color, brand, and sheen. I deleted the Paint model. And because the Room model belongs to user I had to assign it a foreign key. A foreign key is a field in one database that uniquely identifies a row in another table, so in this case it adds a user_id column to the rooms table .  So when a user creates a new room while logged in, that room will belong to that user in our database and to that user only until it is deleted. 

```
class User < ActiveRecord::Base
  has_many :rooms
  has_secure_password

  validates :username, :password, presence: true
  validates_uniqueness_of :username, :message=>"That username has already been taken, please use another."
end
```

```
class Room < ActiveRecord::Base
  belongs_to :user
end
```

```
ActiveRecord::Schema.define(version: 20190413012459) do

  create_table "rooms", force: :cascade do |t|
    t.string  "name"
    t.integer "user_id"
    t.string  "color"
    t.string  "brand"
    t.string  "sheen"
  end

  create_table "users", force: :cascade do |t|
    t.string "username"
    t.string "password_digest"
  end

end

```

After building out my models, I also created a users controller and a rooms controller. Each controller creates the appropriate routes and relays data from the browser to the application, and from the application to the browser.

I also created .erb files for Users and Rooms under Views to hold the web forms to create and login users, and create, display, edit and delete rooms.

I found this project to be frustrating at times, but enjoyable overall. I found myself using Pry often to debug my application and figure out why views and controller routes weren't working as expected. It was very satisfying when I got all of my code to work and I still see new features that I can eventually add, in addition to adding some styling. As of now it is a very raw application, but it does its job and I'm happy to have been able to apply all the knowledge I've learned into one project. 

Thanks for reading and happy coding!
