### Overview

At times we need to work with dialog that show up on the screen. For web application these fall into 2 categories: Dialogs that are HTML and cover the existing page, like a Light Box model (we'll call these inline dialogs), and JavaScript pop-up dialog boxes that ask the user to confirm an action.

### Inline Dialogs

Inline dialogs are easy to construct. The look like [[page classes|Page Navigation Binding]], but instead of a *PageNavigation* attribute they contain an *ElementLocator* attribute that helps the system locate the root dialog element on the page. The dialog class should also inherit from the element type that it is made of and end in the name Dialog. A sample of a simple dialog page that has a yes and no button looks like the following:

```C#
	[ElementLocator(Id = "modal-no-btn")]
	public class DeleteConfirmDialog : HtmlDiv
	{
		public DeleteConfirmElement(UITestControl parent)
			: base(parent)
		{
		}

		[ElementLocator(Id = "modal-no-btn")]
		public HtmlButton No { get; set; }

		[ElementLocator(Id = "modal-yes-btn")]
		public HtmlButton Yes { get; set; }
	}
``` 

## JavaScript Dialogs

Currently JavaScript dialogs are not supported, they are being considered as an addition to a future release.