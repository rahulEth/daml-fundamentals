



daml Lists can hold many elements of one data type
Tuples are similar to Lists but it can hold eleemts of diffrent data types
Sets can hold only unique value of that data type 
Map contains key-value pairs

## Typeclasses and Records

data records : it allow to create data types, it contain one or more fields of differnet data type. it is similra to tuple but it fields heaving name
we can make data types that can implements the behivours of typeclasses by implementing its functions. 
When data type impletemts a function defined by typeclass, we call it instance of typeclass

```
data Data_Type = Data_Type with
    field_1 : data_type
    field_2 : data_type
```

Typeclasses and : it is an interface for a function, implemented by data types.
like - show, Eq, Ord. 
to create typeclass first need to create record.
Typeclasses represent a category of types. it specify function that need to be implemented by type to be become instance of typeclass

we can create our own typeclasses.

```
   class Encryptable i o where 
       encrypt: i -> o
```


## ControlFlow

if-then-else - use boolen value
Guards - if multiple if condition required
use guard where we use "|" to seperare differnet condiation.
Case statements -  use pattern matching
Either : type with 2 possible data types



