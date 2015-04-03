---
layout: post
title:  "Ruby Splat Operator"
date:   2015-04-02 22:13:27
categories: ruby
---
Splat operator can be used in following cases:

### Variable number of arguments

Splat operator can be used to send variable number of arguments during method calls.
The arguments are available as an array inside the method.

{% highlight ruby %}
def print_hi(*names)
  names.each { |name| puts "Hi, #{name}" }
end
print_hi "jack", "alice"
# Will print
# Hi, jack
# Hi, alice
{% endhighlight %}

### Converting an array to arguments

In this case splat can be used for converting array members into method argument. 
For example:

{% highlight ruby %}
def full_name(first_name, last_name)
  "Name : #{first_name} #{last_name}"
 end
array = ["will", "smith"]
full_name *array
# will print
# Name : will smith
{% endhighlight %}

### Array extraction

As you know you can assign array elements to variables:

`x,y = [1, 2]`

Splat operator can be used to extract a sub-array into an array variable. For example:

{% highlight ruby %}
[79] pry(main)> x, y, *array = [1, 2, 3, 4]
=> [1, 2, 3, 4]
[80] pry(main)> array
=> [3, 4]
[81] pry(main)> 
{% endhighlight %}

