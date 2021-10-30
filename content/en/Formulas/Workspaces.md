---
title: Workspaces
weight: 44
description: >-
  In this section, you will find how to use workspaces.
---

---

## **What is the difference between workspace and repository?**

Repositories and workspaces are used to interact with formulas on Ritchie, but the way they work is different, check out:

1. **`workspace`** You can use workspace commands to develop, edit and test formulas `locally`.

2. **`repository`** You can use repository commands to import formulas from `Git repositories` and execute them.

- See an example to add a repository on the [**Hello World Formula**]({{< ref path="Formulas/Hello world formula" >}}) page.

Commands for repos and workspaces are similar, they allow the CLI to "see" available formulas on your local machine. Workspaces have **higher priority** than Repos, for example, if you use both commands for the same formulas' repositories, the workspaces' formulas will be executed.

For more information about workspace and repositories commands, check out [**the list of commands and flags**]({{< ref path="Reference/List of commands and flags" >}}).

## **How to add?**

Follow the next steps:

**Step 1:** Run this command:

```text
rit add workspace
```

**Step 2:** Enter the requested input:

- 1: Inform the workspace name (don't use *spaces* or *special characters*).
- 2: Inform the workspace path on the local machine.

![](/shared/rit-add-workspace.gif)

## **How to list?**

To list avalaible workspaces, you just have to run this command:

```text
rit list workspace
```

![](/shared/rit-list-workspace.gif)

## **How to update?**

If you're not the only person updating the workspace (e.g: if it's a cloned repository from Git) you may need to update the workspace to allow the CLI to "see" the newly available formulas or updates on your local machine after *pulling* the code.

To update a workspace, run this command:

```text
rit update workspace
```

After that, select the workspace name and wait for the CLI output message:

![](/shared/rit-update-workspace.gif)

## **How to delete?**

To delete a workspace, run the command below:

```text
rit delete workspace
```

After that, follow the next steps:

**Step 1:** Select the workspace name;

**Step 2:** Confirm you want to delete the workspace.

![](/shared/rit-delete-workspace.gif)

## **Learn More**
- Check out all the available formulas on Ritchie in the [**list of commands and flags**]({{< ref path="Reference/List of commands and flags" >}}).
