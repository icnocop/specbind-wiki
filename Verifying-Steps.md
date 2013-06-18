## Validating Fields ##

The final key part of the process is verifying that what you expect to see on the screen matches what is there. To assist with this the following step exists.

| Verb | Action |
|------|--------|
| Given | I saw \<validation table\> |
| When | I see \<validation table\> |

The *validation table* is a SpecFlow table that consists of three columns; *Field*, *Rule* and *Value*. Similar to data entry steps the *Field* column defines the field name to locate as a [[property|Page Model Properties]] and the *Value* column is the value to check. It is converted to the correct value by the framework, and will throw an error if the value cannot be converted. The *Rule* column determines the type of validation to perform on the field.

| Rule | Description |
|------|-------------|
| Equals | The expected value and actual value are an exact match. |
| Does Not Equal | The expected value and actual value do not match. |
| Not Equals | Same as *Does Not Equal* |
| Not Equal  | Same as *Does Not Equal* |
| Contains | The actual value contains the expected value within it. |
| Does Not Contains | The actual value does not contain the expected value within it. |
| Starts With | The actual value starts with the expected value. |
| Ends With | The actual value ends with the expected value. |
| Exists | The specified field exists. |
| Does Not Exist | The specified field does not exist. |
| Enabled | The specified field is enabled for editing. |
| Is Enabled | Same as *Enabled* |
| Not Enabled | The field is not enabled for editing. |
| Disabled | Same as *Not Enabled* |
| Is Not Enabled | Same as *Not Enabled* |

Data types are converted to match the field type as well as the system attempting to force a rule match on a field if possible. If the rule is incompatible with the field type a validation exception will be thrown for the step. The fields are checked in the order defined by in the table.

### Validating Lists ###

Similar to validating fields, lists or grids of items need to be validated for correct data. A similar step exists to validate a list.

 
| Verb | Action |
|------|--------|
| Given | I saw \<field name\> list \<rule\> \<validation table\> |
| When | I see \<field name\> list \<rule\> \<validation table\> |

In this case *field name* indicates the [[property|Page Model Properties]] that represents the table and *rule* is the evaluation applied on the list. Not that while the validation table is the same as in validating fields, The field names map to the column or field values in the list. In order for the list rule to be valid, all field evaluations must succeed.

| List Rule | Description |
|-----------|-------------|
| Contains | At least one row in the list matches all the validations. |
| Exists | At least one row in the list matches all the validations. |
| Does Not Contain | No rows in the list match the validations. |
| Not Exists | No rows in the list match the validations. |
| Starts With | The first row in the list matches the validations. |
| Ends With | The last row in the list matches the validations. |

Support for defining custom validation rules will be coming in a future release.