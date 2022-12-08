# Using PMD

Pick a Java project from Github (see the [instructions](../sujet.md) for suggestions). Run PMD on its source code using any ruleset. Describe below an issue found by PMD that you think should be solved (true positive) and include below the changes you would add to the source code. Describe below an issue found by PMD that is not worth solving (false positive). Explain why you would not solve this issue.

## Answer
#### False positive
```
~/V&V/Tp2/commons-collections-master/src/main/java/org/apache/commons/collections4/map/AbstractHashedMap.java:316:	MethodNamingConventions:	The instance method name '_putAll' doesn't match '[a-z][a-zA-Z0-9]*'
```

The error above can be a **false positive** because the name of the method is not necessarily to be changed, it may be suitable for a company convention for example.

#### True positive
```
~/V&V/Tp2/commons-collections-master/src/main/java/org/apache/commons/collections4/comparators/NullComparator.java:133:CompareObjectsWithEquals:     	Use equals() to compare object references
```

This is above a true positive, because using '==' instead of .equals can lead to some errors, depending on the object being compared
