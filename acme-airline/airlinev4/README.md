# Airline Model Version 3

## Hyperledger Modelling Notes

### High level Components

- Basic Aircraft
  - As an airline we have to have some planes right?
  - Defines a basic structure for an aircraft model respresenting a plane.

- Participants
  - As the parent case study suggests our system will need to handle various actors or `particitant` definitions. e.g. A Network Admin, a B2BPartner, A personal participant.
  - An abstract `participant` role is defined with infomation that every participant needs and then this is extended to specific role types with any custom details that each participant type may have.
  - Further encapsulation is demonstarted by the `Contact` concept to keep track of users. This isn't an explicit `Resource` but can be used in a resource.

- Routing
  - Let'S say a particular route for ACME flys from [EWR(New York) to HOU], [HOU to SEA] and then from [SEA to EWR].
  - Each route is assigned a flight number and if it is flow more than once that day it is assigned.
  - Since ACME has multiple planes with possibly diffent capacity we want the flexiblity to have either the entire route or even portions of a route to be assigned to one of more planes depending on availabilty and demand.
    - e.g. If a first leg needed a jumbo jet but subscequent flight only needed half the seats a smaller plane can be used for the rest of the route.
  - Suppose we also have smaller airlines that share flight with ACME Air. Suppose ACME Air(AE101) hosts seats on a flight for Budget air(BU450). In this case BU450 would be an alias for AE101.

---

### Composer modelling language

- .cto is the standard extension.
- Defines - Participants, Assets, Transactions, Events
- Has a Namespace
- Can import other resources in other model files.
- Each namespace can be used only once.
- Name space standard: Namespace.cto

### Resources

- Resemble Java class 
- Has different types e.g. String, Double, Integer, Long , Datetime, Boolean
- Identified by key word must be used for below
- Optional items - Items that are not always required - optional
- Default values can be set - default
- `asset` and `participant` represent structures that need to be `identified by` soem kind of ID.

```javascript
asset Aircraft identified by aircraftId {
    o String aircraftId
}
```

### Enumerations

These can be used to define custom types.

- enum key word
- List of constants allowable

### Abstraction

- Abstract resources can be created that follow standard OO principals.
- The extended class must be of the same type as its ancestor. e.g. a custom `participant` should have a child that is also type `participant`.
- You do not always have to extend an abstract class.
- You cannot inherit from multiple  classes.

### Concepts

- Concept = Generic class
- Can be thought of a way to create generic classes. These do NOT represent Resource.
- How to use?
  - Group together related field. These can be reused within your resources.
  - An example would be an address with fields that are used over and over. An Address concept can be defines which can be used by many kinds of resources.
- Concepts can be extended much like resources can.

---

## Organizing Models

### Arrays

- Defined as []

### Registries

- Manages instances of resources.
- Each instance has a unique ID.
- Separate registry for each resource type.

### Relations

- Depicted in resources using `-->`
- Can be though of as a Pointer to a specific type

### Importing from other namespaces

- The key work `import` 
- A single item can be imported from the namespace OR all resources in the namespace (`*`) can be imported.
- Value Assignment
  - Requires fully qualified resource name and identity
  - e.g. On a given flight `AE101` there could be a an aircraft ```"aircraft": "org.acme.airline.aircraft.Aircraft#CRAFT0001"```
- Deletion of a resource
  - The filed returns a null value on the linked resource.
    - If the aircraft were deleted then null bould be returned
  - Deletion is uni-deirectional
    - Suppose in the example above the flight itself is deleted then there would be no change to `CRAFT001`
