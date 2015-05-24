---
layout: post
title:  "Rails Routing"
date:   2015-05-07 22:13:27
categories: ruby rails
---
#Namespace and Scope

Namespace can be used to map routes to controllers which are under a module. For example, lets say we have

`app/controllers/projects_controller.rb`

Then following route definition allows mapping /admin/projects to admin/projects#index

{% highlight ruby %}
namespace :admin do
  resources :projects
end
{% endhighlight %}


##Scope
Scope can be used for 2 things:

* Mapping a special path to controller

   For example, let's say we have a controller 
   
   `app/controllers/posts_controller.rb`
   
   `resources :posts, path: '/admin/posts'`
   
   This allows mapping /admin/posts to posts#index

* Mapping a path to namespaced controller.
   For example let's say we have a controller
   
   `app/controllers/admin/users_controller.rb`
   
   We would like to map /users to admin/users#index
   
   `resources :users, module: :admin`
   
   
