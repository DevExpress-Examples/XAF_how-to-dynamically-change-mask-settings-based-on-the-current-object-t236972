# How to dynamically change mask settings based on the current object


<p><strong>Scenario:<br></strong>It is necessary to change mask settings of a certain editor dynamically, e.g. based on properties of the current object.<br><br><br><strong>Steps to implement:</strong><br>There are two ways to implement this functionality:<br>1. Implement a ViewController that handles the current View's events and changes settings of the required editors, as shown in the <a href="https://documentation.devexpress.com/#Xaf/CustomDocument2729">Access Editor Settings</a>.<br>2. Implement a custom Property Editor (e.g. a descendant of the corresponding built-in property editor) and change settings of its control. Refer to the <a href="https://documentation.devexpress.com/#Xaf/CustomDocument3097">Implement Custom Property Editors</a> topics for additional information.<br><br>In this example, the first approach is demonstrated. To implement it, the following classes are added:<br><strong>    </strong><em>DemoObject </em>- a persistent class with the TestString and Mask properties. Mask settings of the TestString property are changed based on the Mask property value;<br><strong>    </strong><em>ChangeMaskControllerBase </em>- a platform-independent controller that handles events required for updating mask settings at an appropriate moment;<br><strong>    </strong><em>WinChangeMaskController </em>- a WinForms-specific controller that customizes settings of a WinForms control;<br><strong>    </strong><em>WebChangeMaskController </em>- an ASP.NET-specific controller that customizes settings of an ASP.NET control.<br><br>Note that these approaches can be used only for detail views. To implement the same functionality in a ListView, create a ViewController for it and customize its List Editor according to specifics of the List Editor's control (see <a href="https://documentation.devexpress.com/#Xaf/CustomDocument3165">Access Grid Control Properties</a>). For example, in WinForms you can use the GridView.CustomColumnDisplayText event to pass the required text directly to the grid cell. You can also use the GridView.CustomRowCellEdit event to provide editors with different settings for different rows. Refer to the <a href="https://www.devexpress.com/Support/Center/p/Q310943">Q310943</a>, <a href="https://www.devexpress.com/Support/Center/p/Q500155">Q500155</a> and <a href="https://www.devexpress.com/Support/Center/p/T297444">T297444</a> tickets for more examples.<br><br><strong>See also:</strong><br><a href="https://documentation.devexpress.com/#WindowsForms/CustomDocument583">Mask Editors Overview (WinForms)</a><br><a href="https://documentation.devexpress.com/#AspNet/CustomDocument8171">Mask Editing (ASP.NET)</a></p>

<br/>

