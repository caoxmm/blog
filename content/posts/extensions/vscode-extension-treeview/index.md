---
author: "Simon"
title: "VScode Extension Treeview"
date: 2023-07-05T11:03:24+08:00
description: "vscode extension treeview Guide"
tags: ["Opensumi", "vscode", "Extension", "work"]
ShowToc: false
ShowBreadCrumbs: false
---

The Tree View API allows extensions to show content in the sidebar in Visual Studio Code. This content is structured as a tree and conforms to the style of the built-in views of VS Code.

For example, the built-in References Search View extension shows reference search results as a separate view.
vscode extension docs [TreeView](https://code.visualstudio.com/api/extension-guides/tree-view)

<!--more-->

## using the contributes.views Contribution Point in package.json.

```json
{
  "contributes": {
    "views": {
      "explorer": [
        {
          "id": "nodeDependencies",
          "name": "Node Dependencies"
        }
      ]
    }
  }
}
```

## The second step is to provide data to the view you registered so that VS Code can display the data in the view.

```typescript
export class DepNodeProvider implements vscode.TreeDataProvider<Dependency> {
  // implemants
}
```

## The third step is to register the above data provider to your view.

```typescript
const rootPath =
  vscode.workspace.workspaceFolders &&
  vscode.workspace.workspaceFolders.length > 0
    ? vscode.workspace.workspaceFolders[0].uri.fsPath
    : undefined;
vscode.window.registerTreeDataProvider(
  "nodeDependencies",
  new NodeDependenciesProvider(rootPath)
);
// or

vscode.window.createTreeView("nodeDependencies", {
  treeDataProvider: new NodeDependenciesProvider(rootPath),
});
```
