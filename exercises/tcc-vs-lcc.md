# TCC *vs* LCC

Explain under which circumstances *Tight Class Cohesion* (TCC) and *Loose Class Cohesion* (LCC) metrics produce the same value for a given Java class. Build an example of such as class and include the code below or find one example in an open-source project from Github and include the link to the class below. Could LCC be lower than TCC for any given class? Explain.

## Answer
### Answer of exercice 1
**TCC** : Number of direct connections/number of possible connections

**LCC** : Number of direct connections+number of indirect connections /number of possible connections

If TCC and LCC have the same value it means that there is no indirect connection between methods and attributes.

The LCC cannot be lower than the value of the TCC due to their formula :

TCC = number of direct connections/number of possible connections
LCC= number of direct connections+number of indirect connections /number of possible connections

