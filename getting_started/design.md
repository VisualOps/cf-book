# Design the rule

1. First login to the [IDE](https://ide.cloudfielder.com/)

2. Create a new rule by clicking "Create" on the "rule" tab. An untitled rule will be created for you.<br /><br />
![](https://raw.githubusercontent.com/VisualOps/cf-book/master/images/create_rule.png)

3. "Name" and "description" can be written anywhere you want.<br /><br />
![](https://raw.githubusercontent.com/VisualOps/cf-book/master/images/rule_name_desc.png)

4. "Parameter" can be referenced within "if" condition. "Parameter" value can be a string, dictionnary, or list.<br /><br />
![](https://raw.githubusercontent.com/VisualOps/cf-book/master/images/rule_param.png)

5. In "if" section, you can write an expression to represent how to filter the resource. At the moment, CloudFielder supports 19 resources and a set of operators. Please check the [reference](../reference/resource_type.md) documentation for more details.<br /><br />
![](https://raw.githubusercontent.com/VisualOps/cf-book/master/images/rule_if.png)

6. Finally, if any violation has been found, CloudFielder will notify you using the method defined in "do" section. At this time, only the action "email()" is available. More actions are being implemented.
