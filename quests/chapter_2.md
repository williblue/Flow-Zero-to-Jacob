# Chapter 2 Quests

## Day 1

#### 1. Deploy a contract to account 0x03 called "JacobTucker". Inside that contract, declare a constant variable named is, and make it have type String. Initialize it to "the best" when your contract gets deployed.

<img width="1440" alt="0x03 " src="https://user-images.githubusercontent.com/90781813/155904238-4a1a3e34-e2de-44a2-b432-fd1016b987a8.png">


#### 2. Check that your variable is actually equals "the best" by executing a script to read that variable. Include a screenshot of the output.

<img width="1440" alt="script" src="https://user-images.githubusercontent.com/90781813/155904246-f954d6dd-c017-4c49-874f-983b36bc3840.png">

## Day 2

#### 1. Explain why we wouldn't call changeGreeting in a script.
The function changeGreeting does not return anything it only modifies data on the Blockchain. 

#### 2. What does the AuthAccount mean in the prepare phase of the transaction?
AuthAccount is a type of account that allows a transaction to access its data such as storage, public key, and code.. only if the account approves it. 

#### 3. What is the difference between the prepare phase and the execute phase in the transaction?
**The prepare phase** is used when the transaction needs an account to sign the transaction so it can execute whatever is written in the execute phase. 

**The execute phase** is where the logic for modifying data on the Blockchain is written. 

#### 4. This is the hardest quest so far, so if it takes you some time, do not worry! I can help you in the Discord if you have questions.

* Add two new things inside your contract:

  * A variable named myNumber that has type Int (set it to 0 when the contract is deployed)
  * A function named updateMyNumber that takes in a new number named newNumber as a parameter that has type Int and updates myNumber to be newNumber
  * <img width="1440" alt="myNumber variable + updateMyNumber function" src="https://user-images.githubusercontent.com/90781813/155907788-425175a1-a048-4bb8-88d2-034433cf1fec.png">

* Add a script that reads myNumber from the contract
* <img width="1440" alt="myNumber script" src="https://user-images.githubusercontent.com/90781813/155907815-0858bbd8-d59c-44bc-b8af-e6e420c2be49.png">

* Add a transaction that takes in a parameter named myNewNumber and passes it into the updateMyNumber function. Verify that your number changed by running the script again.
* <img width="1440" alt="updateMyNumber transaction" src="https://user-images.githubusercontent.com/90781813/155907860-51cff0ff-e66f-4986-90d6-0c8eaa72ffd2.png">
* <img width="1440" alt="read myNumber script again" src="https://user-images.githubusercontent.com/90781813/155907888-3f47342d-4e68-45a1-8efb-5fdd87a70e90.png">

## Day 3


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
