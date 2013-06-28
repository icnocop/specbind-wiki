### Overview

In SpecBind, the glue that links page steps with the underlying CodedUI framework is a page model that is represented in code. As discussed in other sections, pages are instantiated with [[navigation steps|Navigation Steps]] that are either an explicit navigation action or the result of a link click or page submission. 

The life cycle of this is as follows:

1. User calls the Navigate step with a page name specified (i.e. home)
2. The framework looks for a class that inherits from the proper driver base class and matches the name. (i.e. home -> HomePage)
3. The page is instantiated and validated against the URL defined by the PageNavigation attribute.
4. The page is ready for use as the context for further actions.

### Page Construction

Most pages follow some simple construction rules that must be observered:

* Pages must be non-abstract classes and inherit from the appropriate base class
   * For CodedUI this is *Microsoft.VisualStudio.TestTools.UITesting.HtmlControls.HtmlControl*
   * For Watin this is *WatiN.Core.Page*
* Page class names must end in Page. So the "home" page class would be named *HomePage*
* For CodedUI pages must have a single constructor that has a single parameter of type *Microsoft.VisualStudio.TestTools.UITesting.UITestControl*. This parameter should be passed to the base class constructor.
* Pages should contain a *PageNavigation* attribute that defines the URL match for the page. More on this in the [[Linking Navigation|#Linking Navigation]] section.

A sample page using CodedUI as a driver would look like:

```C#
using System;
using Microsoft.VisualStudio.TestTools.UITesting.HtmlControls;
using Microsoft.VisualStudio.TestTools.UITesting;

namespace My.Application
{
	[PageNavigation("/products")]
	public class ProductsPage:HtmlDocument
	{
		public ProductsPage(UITestControl parent) : base(parent)
		{
		}
	}
}
```

### Aliasing Pages

In some cases you may have a page where the class name does not match the name in the steps, or multiple names may refer to the same model. In this case you can use the *PageAlias* attribute to specify a different name the page should map to. The following example shows how the "Products" page maps to an alias of "Product List" page.

```C#
using System;
using Microsoft.VisualStudio.TestTools.UITesting.HtmlControls;
using Microsoft.VisualStudio.TestTools.UITesting;

namespace My.Application
{
	[PageNavigation("/products")]
	[PageAlias("Product List")]
	public class ProductsPage:HtmlDocument
	{
		public ProductsPage(UITestControl parent) : base(parent)
		{
		}
	}
}
```

### Linking Navigation

Most navigation and matching is performed through the *PageNavigation* attribute. 