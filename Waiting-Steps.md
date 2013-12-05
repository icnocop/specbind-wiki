In some scenarios, your page may have JavaScript animations or some other page load that the browser otherwise considers ready. In this case you may want to introduce an artificial delay to wait for that transition to complete. The follow step assists with this, and will wait for an active flag from the page.

| Verb | Action |
|------|--------|
| Given | I waited for the view to become active |
| When | I wait for the view to become active | 

While the above method introduces the most flexibility, a simpler set of steps also exist. These setups can check for an element to be displayed, not displayed, exist or not exist and optionally wait a given number of seconds for that to happen. This can be useful for scenarios where a wait dialog has appeared and you don't wish to perform further work until it has cleared. It also implicitly sets performance benchmarks. The commands are listed below with the (for \<seconds\> seconds) as optional.

**Check to see if an element is displayed**

| Verb | Action |
|------|--------|
| Given | I waited to see \<property name\> |
| When | I wait to see \<property name\> |
| Then | I wait to see \<property name\> | 

**Check to see if an element is not displayed**

| Verb | Action |
|------|--------|
| Given | I waited to not see \<property name\> |
| When | I wait to not see \<property name\> |
| Then | I wait to not see \<property name\> | 

**Check to see if an element is enabled**

| Verb | Action |
|------|--------|
| Given | I waited for \<property name\> to become enabled |
| When | I wait for \<property name\> to become enabled |
| Then | I wait for \<property name\> to become enabled | 

**Check to see if an element is disabled**

| Verb | Action |
|------|--------|
| Given | I waited for \<property name\> to become disabled |
| When | I wait for \<property name\> to become disabled |
| Then | I wait for \<property name\> to become disabled | 

The example below shows waiting for Checkout to become enabled:

```Cucumber
Given I waited for Checkout to become enabled
``` 


Again, with any of the above command you can add "for \<seconds\> second(s)" to the end to specify a timeout for waiting. An example below is waiting for Checkout to become enabled for 20 seconds:

```Cucumber
Given I waited for Checkout to become enabled for 20 seconds
``` 