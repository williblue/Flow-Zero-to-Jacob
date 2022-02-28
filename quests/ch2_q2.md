## Chapter 2 - Day 2
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
