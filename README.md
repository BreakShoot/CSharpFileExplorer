# CSharpFileExplorer
An implementable file explorer with remarkable capability

# How to Setup
## 1) Add a reference to the tool through the toolbox. It will show up named as "FileExplorer"
![Step 1](https://i.imgur.com/e6ag1bn.png)

## 2) Drag the tool onto your form
![Step 2](https://i.imgur.com/YuYqHmZ.png)

## 3) On your Form_Load event, set up a few functions such as
![Step 3](https://i.imgur.com/KWsk4Ly.png)

### File Filtering
```cs
this.fileExplorer1.FilteringExtensions = true;
this.fileExplorer1.Extensions.AddRange( new List<string>() { ".txt", ".lua"} );
```

### Saving
```cs
ToolStripItem tool = new ToolStripButton("Save");
this.fileExplorer1.NodeContextMenuStrip.Items.Insert(1, tool);

tool.Click += (q, p) =>
{
  File.WriteAllText(this.fileExplorer1.SelectedNode.Name, this.fastColoredTextBox1.Text);
};
```

### File Selection Action
```cs
this.fileExplorer1.SelectionAction += (q, p) =>
{
    this.fastColoredTextBox1.Text = this.fileExplorer1.ReadSelectedNode();
};
```
---

# Options
* Utilize the BookMarkColor property to set the color for bookmarks
* If you wish to only witness files of a certain extension, add to the Extensions list, and set FilteringExtensions to true
* If you wish to remove/show the file information on file hover, set ShowFileInfoOnHover

![Example Properties](https://i.imgur.com/vh3lMRa.png)

---

# Pictures
![Pic1](https://i.imgur.com/1gDIVRK.png)
![Pic2](https://i.imgur.com/PJqdW1M.png)
![Pic3](https://i.imgur.com/kSCUgBS.png)
