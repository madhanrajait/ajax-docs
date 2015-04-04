---
title: Client-side Selection
page_title: Client-side Selection | UI for ASP.NET AJAX Documentation
description: Client-side Selection
slug: treelist/functionality/selecting/client-side-selection
tags: client-side,selection
published: True
position: 0
---

# Client-side Selection



## 

Telerik __RadTreeList__ has built-in mechanism for items selection. You canselect items either on the client or on the server as per your requirements.

To enable the RadTreeList client-side selection you need to set the__ClientSettings.Selecting.AllowItemSelection__ to true. This will allow you toselect an item on mouse click. As a result the __OnItemClick__,__OnItemSelecting__ and __OnItemSelected__ client-side eventsof the RadTreeList will be fired so you can perform further actions and handle the item selection in a custom manner.

You can also use the below settings to enable additional modes of the client-side selection:

* __ClientSettings.Selecting.AllowToggleSelection__ - When set to__true__ (the default value is false) enables you to deselect an item byclicking on one that is already selected.

* __ClientSettings.Selecting.UseSelectColumnOnly__ - When set to__true__ (the default value is false) prevents users from selecting items onmouse click and forces them to use the __TreeListSelectColumn__ for that purpose.

With RadTreeList you might want to provide the ability for multi-item selection. This is done bysetting its __AllowMultiItemSelection__ property to true (its default value is false).And to select a few items at a time, one can use the __[Ctrl]__ and__[Shift]__ keys as in Windows Explorer. Or, in case the AllowToggleSelection propertyis true, just click on the desired items to select them.

The below sample illustrates a simple usage of the above properties:

````ASPNET
	    <telerik:RadTreeList ID="RadTreeList1" runat="server" AllowPaging="True" DataKeyNames="EmployeeID"
	        DataSourceID="SqlDataSource1" ParentDataKeyNames="ReportsTo" AllowMultiItemSelection="True"
	        AutoGenerateColumns="false">
	        <Columns>
	            <telerik:TreeListSelectColumn UniqueName="SelectColumn">
	            </telerik:TreeListSelectColumn>
	            <telerik:TreeListBoundColumn DataField="LastName" HeaderText="LastName" UniqueName="LastName">
	            </telerik:TreeListBoundColumn>
	            <telerik:TreeListBoundColumn DataField="FirstName" HeaderText="FirstName" UniqueName="FirstName">
	            </telerik:TreeListBoundColumn>
	            <telerik:TreeListBoundColumn DataField="Title" HeaderText="Title" UniqueName="Title">
	            </telerik:TreeListBoundColumn>
	            <telerik:TreeListBoundColumn DataField="TitleOfCourtesy" HeaderText="TitleOfCourtesy"
	                UniqueName="TitleOfCourtesy">
	            </telerik:TreeListBoundColumn>
	            <telerik:TreeListBoundColumn DataField="City" HeaderText="City" UniqueName="City">
	            </telerik:TreeListBoundColumn>
	        </Columns>
	        <ClientSettings>
	            <Selecting AllowItemSelection="true" AllowToggleSelection="true" />
	        </ClientSettings>
	    </telerik:RadTreeList>
	    <asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:NorthwindConnectionString %>"
	        SelectCommand="SELECT [EmployeeID], [LastName], [FirstName], [Title], [TitleOfCourtesy], [City], [ReportsTo] FROM [Employees]">
	    </asp:SqlDataSource>
````



>note Note that when client-side selection is enabled through the AllowItemSelection property, theTreeListSelectColumn selects the items on the client. If the AllowItemSelection property is false,server-side selection is performed.
>


For a live demo illustrating the client-side items selection functionality, follow[this link](http://demos.telerik.com/aspnet-ajax/treelist/examples/selecting/clientsideselection/defaultcs.aspx).