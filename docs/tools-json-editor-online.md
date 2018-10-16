A big part of contributing to Terasology comprises of asset creation and modification. Assets in Terasology are just JSON hierarchy files, often bundled with images. Thus arises a need for a good, reliable and powerful tool to edit JSON files.

"JSON Editor Online" is one such powerful editor. The editor window consists of two panes: a source code pane, and a tree view. The tree view displays the JSON code as a hierarchical view. The file itself can be edited from both editor panes, and changes made to either pane can be transferred easily to the other. The editor is available as a web widget which you can access online [here](http://www.jsoneditoronline.org/). You can also embed the widget in your own web-page. An added bonus is that the editor is free and open source (the source can be found [here](https://github.com/josdejong/jsoneditor/)), and is under constant development.

![](https://github.com/mjuvekar7/TerasologyWikis/blob/master/JSON_Screenshot.png)

# Usage
JSON Editor Online is a fairly simplistic, easy to use editor.
* To use the editor, visit [this site](http://www.jsoneditoronline.org/).
* To open a file, select `Open` -> `From disk` (or `From URL` if it's online). If you want to create a new file altogether, select `New`.
* You can write JSON code in the editor window as you would in any text editor. To use the tree view, see the sub-section below. To transfer changes made from one editor pane to the other, click the appropriate arrow button.
* You can then save the file either offline (on disk) or online by using the `Save` dropdown. Files saved online can be shared by sharing a generated link.

## The Tree View
The tree view is a convenient way to edit JSON files since it provides a simple, easy-to-understand graphical representation of the JSON hierarchy created. It also allows you to focus on the actual content without worrying about syntax errors. Some basic operations and how they can be performed with the tree editor are given below. For a more complete specification, visit [this page](http://www.jsoneditoronline.org/doc/index.html#tree_editor).
* Adding a new field: Click on the box button next to he drag area of an existing field to open the `options` dropdown (See the image below). Select `Insert` to add a new blank field. If you want to add a certain type of field, click the arrow to the right of `Insert` and select the type of field you want to add. If you are adding fields to an empty object, there will be no `Insert` option; instead, there will be an `Append` option. Note that inserted fields will be created on a new line placed *above* the line whose options menu is being used to create the field.
* Duplicate a field: Open the options menu of the field you want to duplicate, and click `Duplicate`. The field will be duplicated onto a new line placed below the field that has been duplicated.
* Remove a field: Open the options menu and click *Remove*.

![](http://www.jsoneditoronline.org/doc/img/actions_menu.png)

A complete beginner's guide can be found [here](http://www.jsoneditoronline.org/doc/index.html).