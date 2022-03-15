## Chapter 2 - Day 3 - Quests


#### 1. In a script, initialize an array (that has length == 3) of your favourite people, represented as Strings, and log it.

<img width="1440" alt="Favpeeps" src="https://user-images.githubusercontent.com/90781813/156044004-9ff8cad5-7087-4551-835e-36e0aab92c08.png">

#### 2. In a script, initialize a dictionary that maps the Strings Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a UInt64 that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!

<img width="1440" alt="platformRatings" src="https://user-images.githubusercontent.com/90781813/156045022-5619f977-6101-4be2-8250-75b158cb649f.png">

#### 3. Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type).

##### Puppy name mission
We need to find a name for our new cutie puppy.. <img src="https://user-images.githubusercontent.com/90781813/158469482-974a122b-5c33-4893-bf29-af02c9ce8851.jpeg" width="100" height="100">.. it's hard to find a good one..

So, we know that we need a puppy name suggestion. 
We can therefore use the optional type `?` as we know that the variable `puppyNameSuggestion`'s value needs to be set in the near future. 

```
var puppyNameSuggestion: String? = nil  // assign to nil because the value hasn’t been set yet
```

Now let say that we want another variable `finalPuppyName`, to store the perfect puppy name. 

```
var finalPuppyName: String = puppyNameSuggestion // this will give an error
```

 ##### **Error message:**

<img width="406" alt="Screenshot 2022-03-15 at 21 58 52" src="https://user-images.githubusercontent.com/90781813/158471520-f0a13bdd-1260-41f2-ba4f-186e2ee18228.png">


It means that Cadence does not know if `puppyNameSuggestion` is a `String` or `nil`. Here you need to unwrap the `puppyNameSuggestion` with force-unwrap operator `!` to let Cadence know what to do:

whether to

* assign `puppyNameSuggestion`'s value to `finalPuppyName` variable 

or 

* PANIC, if `puppyNameSuggestion`'s value is `nil` as you can not give a puppy an empty name. (`finalPuppyName` has `String` as a type so it expects `String`)



##### **Use force-unwrap operator `!`**
```
var finalPuppyName: String = puppyNameSuggestion! // PANIC - unwrap a nil is a no no 
```


##### **Assign a puppy name**
```
puppyNameSuggestion = "Iris"
var finalPuppyName: String = puppyNameSuggestion! // this works and our puppy is named Iris!
```


#### 4. Using this picture below, explain...

* What the error message means
  * That we try to return an `optional type` but Cadence expects a `String`. 
* Why we're getting this error
  * When accessing a key in a dictionary the value will be returned as an optional. Cadence does not know if it will return a `String` or a `nil`. 
* How to fix it
  * Use force-unwrap operator `!` to return the actual type.

<img width="1361" alt="wrongcode" src="https://user-images.githubusercontent.com/90781813/156041835-f03ae49b-4ebb-4e26-b9be-5df819cb09fa.png">
