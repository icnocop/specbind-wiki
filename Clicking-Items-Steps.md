Selecting items on a page are one of the most common actions on a page is one of the most common actions performed. To click on an item use the following step:

| Verb  | Action                     |
|-------|----------------------------|
| Given | I chose \<property name\>  |
| When  | I choose \<property name\> |

The \<property name\> argument is used to map to the [[property|Page Model Properties]] on the page to select. Most elements in the frameworks are clickable so this should be supported with most element types. 

As with other property locators, SpecBind normalizes the name so that you can make the step more readable. For instance if your property name is "FirstName" you can enter the value "First Name" in the step and it will locate the correct property.
 
**If this results in navigation to a new page or display of a inline dialog, you must use the [[Ensure Step|Navigation Steps]] step next to set the correct context.**

#### Example ####

```Cucumber
When I choose Checkout
``` 