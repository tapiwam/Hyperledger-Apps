# Airline MOdel Version 1

## Purpose
Define a basic layer of the aircraft model to demonstrate basic structure of a model file and resource.

Composer modelling language
	- .cto
	- Defines - Participants, Assets, Transactions, Events
	- Has a Namespace
	- Can import other resources in other model files. 
	- Each namespace must be must used only once
Name space standard: Namespace.cto

### Resources
	- Resemble Java class 
	- Has different types e.g. String, Double, Integer, Long , Datetime, Boolean
	- Identified by key word must be used for below
		○ asset 
			```
            asset Aircraft identified by aircraftId {  
				o String aircraftId
			}
            ```
		○ participant 
	- Optional items - Items that are not always required - optional
	- Default values can be set - default

### Enumerations
	- enum key word
	- List of constants allowable



