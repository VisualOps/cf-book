# Design the rule

1. First log in to the [IDE](https://ide.cloudfielder.com/)

2. Create a new rule by clicking 'Create' on rule tab, then we will create an untitled rule for you.
![](https://raw.githubusercontent.com/VisualOps/cf-book/master/images/create_rule.png)

3. Name and description can be written what ever you want.
![](https://raw.githubusercontent.com/VisualOps/cf-book/master/images/rule_name_desc.png)

4. Parameter can be reference within condition 'if'. Parameter value can be string, dict and list.
![](https://raw.githubusercontent.com/VisualOps/cf-book/master/images/rule_param.png)

5. In 'if' section, user can write the expression to represent how to filter there resource. Now we support 19 resources and a set of operator. Please check the [reference](http://docs.cloudfielder.com)
![](https://raw.githubusercontent.com/VisualOps/cf-book/master/images/rule_if.png)

6. Finally, if we found any violation, we will notify user using method in 'do' section. Now we only support email().