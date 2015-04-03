---
title: OnClientContextMenuItemClicked
page_title: OnClientContextMenuItemClicked | UI for ASP.NET AJAX Documentation
description: OnClientContextMenuItemClicked
slug: treeview/client-side-programming/events/onclientcontextmenuitemclicked
tags: onclientcontextmenuitemclicked
published: True
position: 28
---

# OnClientContextMenuItemClicked



## 

The __OnClientContextMenuItemClicked__client-side event occurs when the user clicks the context menu item for a node.

The event handler receives parameters:

1. The treeview instance that fired the event.

1. Event arguments with functions:

* __get_menuItem()__ retrieves a reference to the selected context menu item. You can also call get_menu() from the menu item reference and use the menu to retrieve the other items on the menu.

* __get_node()__ retrieves a reference to the clicked on node.

* __get_domEvent()__ retrieves the DOM event object of the item click.

The example below displays the text for the selected context menu item, the text for the node and the ID for the menu.

````ASPNET
	
	    <script type="text/javascript" language="javascript">
	    
	        function ClientContextMenuItemClicked(sender, eventArgs) {
	            var node = eventArgs.get_node();
	            var item = eventArgs.get_menuItem();
	            var menu = item.get_menu();
	
	            alert("Menu item " + item.get_text() +
	             " selected for node " + node.get_text() +
	             ",\nMenu " + menu.get_id());
	        }
	    </script>
	
	    <telerik:RadTreeView ID="RadTreeView1" runat="server" MultipleSelect="True" CheckBoxes="True"
	        EnableDragAndDrop="True" AllowNodeEditing="True" OnClientContextMenuItemClicked="ClientContextMenuItemClicked">
	        <Nodes>
	            <telerik:RadTreeNode runat="server" ExpandMode="ClientSide" Text="Search" ImageUrl="~/images/search.ico"
	                Expanded="True" Value="1">
	            </telerik:RadTreeNode>
	        </Nodes>
	        <ContextMenus>
	            <telerik:RadTreeViewContextMenu ID="SearchMenu" runat="server" Flow="Horizontal">
	                <DefaultGroupSettings ExpandDirection="Auto" Flow="Vertical" />
	                <Items>
	                    <telerik:RadMenuItem runat="server" ExpandMode="ClientSide" Text="Local Search">
	                        <GroupSettings ExpandDirection="Auto" Flow="Vertical" />
	                    </telerik:RadMenuItem>
	                    <telerik:RadMenuItem runat="server" ExpandMode="ClientSide" Text="Search Network">
	                        <GroupSettings ExpandDirection="Auto" Flow="Vertical" />
	                    </telerik:RadMenuItem>
	                </Items>
	            </telerik:RadTreeViewContextMenu>
	        </ContextMenus>
	    </telerik:RadTreeView>
````



# See Also

 * [OnClientContextMenuItemClicking]({%slug treeview/client-side-programming/events/onclientcontextmenuitemclicking%})

 * [OnClientContextMenuShowing]({%slug treeview/client-side-programming/events/onclientcontextmenushowing%})

 * [OnClientContextMenuShown]({%slug treeview/client-side-programming/events/onclientcontextmenushown%})

 * [RadTreeNode]({%slug treeview/client-side-programming/objects/radtreenode%})