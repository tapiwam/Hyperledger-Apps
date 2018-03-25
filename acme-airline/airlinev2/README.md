# Airline Model Version 2

## Purpose

LOOK AT PARENT README

---

## Hyperledger Modelling Notes

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

## Concepts

- Concept = Generic class
- Can be thought of a way to create generic classes. These do NOT represent Resource.
- How to use?
  - Group together related field. These can be reused within your resources.
  - An example would be an address with fields that are used over and over. An Address concept can be defines which can be used by many kinds of resources.
- Concepts can be extended much like resources can.