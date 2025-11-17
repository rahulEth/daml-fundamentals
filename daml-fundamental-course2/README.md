
# contractId
   assigned autometically when contract is created
   unstable references when modeling mutable contract state types

# Contract key
   stable reference
   specified in the template
   must have atleast one signatory in the key and as a maintainer of the key

# Fetch Functions
   fetch @templatename contractId: fetchs the contract payload
   fetchByKey @templatename key: fetch the contract id and the payload


# Transaction Tree
    transaction tree is a way to visualize the actions committed to the ledger . There are 4 type of actions in a transaction tree
      1. create a contract
      2. exercise a choice
      3. fetch a contract
      4. key assertion : an assertion that the given contract key is not asigned to any active  contract on the ledger. Made using the function lookUpKey which looks upto the contractId associated the the contract key 
         lookUpKey: k -> Update (Optional (ContractId t))   
NOTE: eact action is a node of tree that may or may not have child nodes, depending on weather the action has any consequences. Only exerice have consequences and whould have child nodes      

# Query
   query the set of active contracts of the template that are visible to the given party
   there are 4 diffenret way to query the ledger 
   1. query @T p : query all active contract of a template T visible to party p.
   2. queryContractId p cId : query for an active contract with contract id cid and visible to party p
   3. queryContractKey p @T k : Query for an active contract if a template T with a key k visible to partry p.
   4. queryFilter @T p c : Query for all active contracts of template T visible to party p that meet the predicate c. 

# Functor, Applicative and Action

# functor type class
fmap notation <$>

fmap (+2) [1,2,3] <----->  (+2)<$>[1,2,3]

# Applicative Type Class
 
The Applicative type class applies one or more functions sequencelly to a function

Its function is denoted as <*>

        (<*>) : f(a->b) -> fa -> fb

<*> takes two inputs :  a functor with one or two functions in it and anothor functor. extracts the function from the first functor and then maps it over to second functor.

# Action Type Class

an applicative type that sequentilly composes actions, passing any value produced by the first action as an arguemnt to the next. it has bind operator
       
       class Applicative m => Action m where
          (>>=) : m a -> (a -> m b) -> m b

# Actions and Loops



