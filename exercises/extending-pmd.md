# Extending PMD

Use XPath to define a new rule for PMD to prevent complex code. The rule should detect the use of three or more nested `if` statements in Java programs so it can detect patterns like the following:

```Java
if (...) {
    ...
    if (...) {
        ...
        if (...) {
            ....
        }
    }

}
```
Notice that the nested `if`s may not be direct children of the outer `if`s. They may be written, for example, inside a `for` loop or any other statement.
Write below the XML definition of your rule.

You can find more information on extending PMD in the following link: https://pmd.github.io/latest/pmd_userdocs_extending_writing_rules_intro.html, as well as help for using `pmd-designer` [here](https://github.com/selabs-ur1/VV-ESIR-TP2/blob/master/exercises/designer-help.md).

Use your rule with different projects and describe you findings below. See the [instructions](../sujet.md) for suggestions on the projects to use.

## Answer
### Answer of exercice 3
PMD is Open-source. He have is own rule, but anyone can add his rule for be more specific about his project. PMD is based on AST of a programm. In this exercice and with the help of JAVAFX, we created a rule to detect if we have 3 if in a row. Like the exemple below :
```
if (...) {
    ...
    if (...) {
        ...
        if (...) {
            ....
        }
    }
}
```
So to detect this rule, we wrote in JAVAFX this, this line can detect if we have 3 if in a row : 
```
IfStatement[ancestor::IfStatement[ancestor::IfStatement]]
```
After that, JAVAFX generated a .xml with the rule :
```
<?xml version="1.0"?>

<ruleset name="Custom Rules"
    xmlns="http://pmd.sourceforge.net/ruleset/2.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://pmd.sourceforge.net/ruleset/2.0.0 https://pmd.sourceforge.io/ruleset_2_0_0.xsd">

    <description>
        My custom rules
    </description>


    <rule name="rule3if"
      language="java"
      message=""
      class="net.sourceforge.pmd.lang.rule.XPathRule">
   <description>

   </description>
   <priority>3</priority>
   <properties>
      <property name="version" value="2.0"/>
      <property name="xpath">
         <value>
	 <![CDATA[
	 //IfStatement[ancestor::IfStatement[ancestor::IfStatement]]
	 ]]>
         </value>
      </property>
   </properties>
</rule>

</ruleset>
```
We have to place the .xml in PMD and we can use our rule in any project we want.

