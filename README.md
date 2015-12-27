# Introduction to Nested Hashes
## Overview

We'll introduce nested, or multidimensional, hashes and explain how they're useful in programming. 

## Objectives

1. Describe how nested hashes can store complex associations of data.
2. Give examples of real-world situations that can require nested hashes. 
3. Describe the structure of a nested hash.
4. Retrieve data from a nested hash.

## Introduction: Why Use Nested Hashes

So far, we've seen hashes that store values in associated keys. In the hashes we've built up until now, each key points to a single value. Hashes are so useful, however, because they can be multi-dimensional, or nested. A key in a hash can point to a value that is a *collection of objects*, i.e. an array or even another hash. 

As programmers, we strive to write code that models the real-world. The programs we write serve a purpose––whether you're creating a simple command line game or an app to help hospitals manage patient data, our code is designed to do a real job, like run a game or communicate critical information. 

### Where Will You Find Nested Hashes?

Nested hashes are a very common way to store and operate on complex associated data in a program. You are likely to encounter them any time you find yourself working with a large collection of information. In particular, you will encounter these data structures when working with data you will pull from APIs. 

API stands for "Application Programming Interface" and here refers to the way in which organizations, companies and governments will expose their data to the public for use. 

New York City, for example, has a robust API called NYC Open Data. Developers can connect to this API to find information about city programs, public housing, parks, schools, construction, health information––[like this collection of NYC doctors who participate in project REACH](https://data.cityofnewyork.us/resource/7btz-mnc8.json)––you name it.

**Top-Tip:** To view the nested hash data from the NYC Open Data API, linked to above, in an organized and legible way in your browser, use the [Chrome JSON Viewer extension](https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh?hl=en-US). 

When you send a request for data to such an API, the data you get back from them will be in the form of a nested hash that can contain information about thousands of records. 

We'll learn a lot more about APIs later on in this course. For now, just understand that nested hashes are a very common occurrence in programming. They are used to store complex collections of data and you will encounter them when working with APIs, among other places.

### Nested Hashes Model Real-World Data

We can imagine so many real-world situations and environments in which we are dealing with complicated collections of data. 

Let's take, for example, a list of instructors at the Flatiron School. They can be stored in an array like this:

```ruby
instructors = ["Avi", "Jeff", "Rose"]
```

What happens when we expand our data collection to include the members of the development team here at the Flatiron School? We could create yet another array:

```ruby
dev_team = ["Jonas", "Logan", "Amanda", "Seiji", "Kate", "Spencer"]
```

With this set-up, though, there is no way to associate our two arrays and tell them that they both belong to the Flatiron School.

This is where nested hashes come in. 

## Our First Nested Hash

With a nested hash, we can store complex collections of data. In other words, we can store data that is associated to other data via categories and subcategories. 

Both the `dev_team` array and the `instructors` array should be associated to the Flatiron School. So, we can create a hash, `flatiron_school`, that contains keys to denote the `instructors` and `dev_team` categories. We can point these keys to the arrays that contain our instructors and dev team members respectively. 

Let's take a look:

```ruby
flatiron_school = {
  instructors: ["Avi", "Jeff", "Rose"], 
  dev_team: ["Jonas", "Logan", "Amanda", "Seiji", "Kate", "Spencer"]
}
```
In this example, each key in our hash points to a value that is an array. 

Nested hashes allow us to further group, or associate, the data we are working with. They help us to deal with situations in which a category or piece of data is associated not just to one discrete value, but to a collection of values. In such a situation, we can create a hash key that points to a value of another hash or an array. 

### A Note On Mixing our Collection Types

You may have noticed in the above example that we have a hash in which the value of a key is an array. 

Understand that arrays and hashes can store *any type of data*. In other words, the individual index items of an array can be strings, integers, or even other arrays and hashes. The same is true of hashes. The values that hash keys point to may be strings, integers, even arrays and hashes. 

In fact, one of the most common nested data structures you'll see when working with APIs, as discussed above, is an array of hashes. 

## Nested Hash Example

We'll be building up our own nested hash and operating on such data structures in a number of ways over the course of the next few lessons. For now, just read through the next example and get comfortable looking at a nested hash. 

In this example, we have a hash, `flatiron_school`, which stores some data about us. This data is broken down into the categories of `:instructors`, `:dev_team` and `:students`, thanks to our nested hash. 

```ruby
flatiron_school = {
  instructors: ["Avi", "Jeff", "Rose"], 
  dev_team: ["Jonas", "Logan", "Amanda", "Seiji", "Kate", "Spencer"],
  students: ["Sarah", "you", "John", "David"]
}
```

In the above example, each key points to an array of names. We may not know how to work with nested hashes just yet, but we *do* know how to work with one-dimensional hashes and arrays. 

The `flatiron_school` hash has a key of `:instructors`. The value of that key is an array of instructors. In order to access that array, we can use the `[]` method we've been using all along to grab the values of a particular hash key.

```ruby
instructors = flatiron_school[:instructors]
 # => ["Avi", "Jeff", "Rose"]
``` 
Here, we set a variable, `instructors`, equal to the return value of calling `flatiron_school[:instructors]`, which is simply the array of instructors. 

Now, to operate on that collection of instructors, we can simply operate on our `instructors` array. 

What if I wanted to grab *just the first name* in the instructor's array? We use the same methods for accessing array index items that we've been using all along: 

```ruby
instructors[0]
#  => "Avi"
```

Nested hashes can get pretty complicated. Read through the example in this lesson again before moving on. It's okay if you don't understand everything; just try to get comfortable reading through the above nested hash. 

<a href='https://learn.co/lessons/nested-hashes-intro' data-visibility='hidden'>View this lesson on Learn.co</a>
