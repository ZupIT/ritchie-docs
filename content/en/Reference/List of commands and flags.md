---
title: List of commands and flags
weight: 93
description: In this section, you will find the list of Ritchie's main commands 
---

---

## **Commands**

### **Configuration commands**

| Commands      | Operation                                  |
| :------------ | :----------------------------------------- |
| rit init      | initialize Ritchie before use              |
| rit upgrade   | upgrade to the last Ritchie stable version |
| rit tutorial  | enable or disable the tutorial             |
| rit -v        | return Ritchie currently installed version |

### **Repo commands**

| Command               | Operation                                                                               |
| :-------------------- | :-------------------------------------------------------------------------------------- |
| rit add repo          | add a new repository (to access repository formulas with Ritchie)                       |
| rit list repo         | show a list with all your available repositories                                        |
| rit update repo       | update all repositories (to access new formulas from those repositories with Ritchie)   |
| rit set repo-priority | set a repository priority                                                               |
| rit delete repo       | delete a repository (to remove access to the repository formulas with Ritchie)          |

### **Formula commands**

| Command                     | Operation                                                                               |
| :-------------------------- | :-------------------------------------------------------------------------------------- |
| rit create formula          | create a new formula from scratch (as well as a new local repository if necessary)      |
| rit build formula           | build a formula locally for test                                                        |
| rit build formula --watch   | build a formula monitoring the code to update real time changes                         |
| rit rename formula          | rename a local formula                                                                  |
| rit list formula            | list all available formulas from specific/all repositories                              |


{{% alert color="danger" %}}

The rit build formula command was deprecated from Ritchie's version 2.5.0.

{{% /alert %}}

### **Autocomplete commands**

| Commands                  | Operation                       |
| :------------------------ | :------------------------------ |
| rit completion zsh        | add autocomplete via zsh        |
| rit completion bash       | add autocomplete via bash       |
| rit completion fish       | add autocomplete via fish       |
| rit completion powershell | add autocomplete via powershell |

### **Env commands**

| Commands       | Operation                         |
| :------------- | :-------------------------------- |
| rit set env    | set a new environment             |
| rit show env   | show the current environment used |
| rit delete env | delete a environment              |

### **Credential commands**

| Commands            | Operation                            |
| :------------------ | :----------------------------------- |
| rit set credential  | set new credentials for the context  |
| rit list credential | list all credential names and fields |

### **Workspace commands**

| Commands             | Operation                                                                                       |
| :------------------- | :---------------------------------------------------------------------------------------------- |
| rit list workspace   | list all formula's workspaces                                                                   |
| rit add workspace    | add a new workspace                                                                             |
| rit delete workspace | delete a specific formula's workspace                                                           |
| rit update workspace | update a specific formula's workspace (to access new formulas from this workspace with Ritchie) |

## **Flags**

### **Main flags**

| Flags     | Operation                                                              |
| :-------- | :--------------------------------------------------------------------- |
| -\-default | attribute the **default** values configured on the formula.            |
| -\-docker  | run a formula using **Docker**                                         |
| -\-help    | returns a list of executable available commands and flags for the user |
| -\-local   | run a formula **locally**                                              |
| -\-verbose | run a formula without log details                                      |
