# Archi Plugin Tutorial - coArchi1

- [Archi Plugin Tutorial - coArchi1](#archi-plugin-tutorial---coarchi1)
  - [Contents](#contents)
  - [0. Introduction](#0-introduction)
    - [0.1 Opening and Introduction](#01-opening-and-introduction)
    - [0.2 Setup Archi Test Environments](#02-setup-archi-test-environments)
  - [1. coArchi1 Setup and Configuration](#1-coarchi1-setup-and-configuration)
    - [1.1 coArchi1 Setup](#11-coarchi1-setup)
    - [1.2 coArchi1 Configuration](#12-coarchi1-configuration)
  - [2. coArchi1 Basics](#2-coarchi1-basics)
  - [3. Manage Workspace](#3-manage-workspace)
  - [4. Manage Changes](#4-manage-changes)
    - [4.2 Refresh and Publish](#42-refresh-and-publish)
      - [4.2.1 Refresh a Model](#421-refresh-a-model)
        - [4.2.1.1 Refresh `not authorized` Error](#4211-refresh-not-authorized-error)
      - [4.2.2 Publish a Model](#422-publish-a-model)
  - [5. Manage Branches](#5-manage-branches)
    - [5.3 Handling Branches in the Team](#53-handling-branches-in-the-team)
  - [6. Connection, Authentication \& Security](#6-connection-authentication--security)
  - [7. Do's \& Don't and Other Known Issues](#7-dos--dont-and-other-known-issues)

## Contents

<img src="img/Archi_Plugins_coArchi1.png" alt="coArchi1 TOC" width="600"></img>

## 0. Introduction

### 0.1 Opening and Introduction

Why this tutorial?

- Since Archi itself is one standalone client tool for ArchiMate modeling, if you're working in the architect team on the common Archi model, the coArchi is the must adopted collaboration plug-in.
- I (and our architect team) have used coArchi since 2021, keep evolving the way of working to handling our Archi repository (12K+ Elements, 14K+ Properties and 35K+ Relationships)
- Share our practices to the community to help making Archi better

Why coArchi1 tutorial still?

- coArchi1 (v0.9.5 as of 2026/02/28) is provided from the Archi development team and keep evolving, you may find coArchi2 is on the way which bring more feature and better performance.
- however, since coArchi2 have the big changes and not compatible with coArchi1, you may still keep in coArchi1 for certain reason, thus, know how coArchi1 in detail still valuable as the foundation

How's the tutorial structured and where are the resources?

- This repo stores the hands-on README as the central information
- Practice Archi models are kept in dedicate "[Enterprise Architecture Playground](https://github.com/EA-PlayGround)" in Github for remote model demo
- Mindmap file (using FreePlane tool) shows the table of contents
- Check [wiki page](https://github.com/archimatetool/archi-modelrepository-plugin/wiki) to learn the words from Archi project. Below are based on the wiki structure with adding more practical reference.
- Tutorial videos will be packaged to [Udemy](https://www.udemy.com/user/xiaoqi-zhao/) and also shared in [YouTube](http://www.youtube.com/@yasenzhao) (stay tunes)

### 0.2 Setup Archi Test Environments

To simulate and demo collaboration within one team, using Archi zip package to install two parallel instances, configure the `Archi.ini` to point to its specific path so that their programs are not conflicted and you may open them at the same time.

Archi version: 5.7.0

Default `Archi.ini` content:

```conf
-startup
plugins/org.eclipse.equinox.launcher_1.6.800.v20240513-1750.jar
--launcher.library
plugins/org.eclipse.equinox.launcher.win32.win32.x86_64_1.2.1000.v20240507-1834
-cleanConfig
--launcher.defaultAction
openFile
-eclipse.keyring
@user.home/AppData/Roaming/Archi/secure_storage
-vmargs
-Dosgi.requiredJavaVersion=21
-Dfile.encoding=UTF-8
-Declipse.p2.data.area=@config.dir/p2
-Ddata.location=@user.home/Documents/Archi
-Dslf4j.internal.verbosity=ERROR
--add-modules=ALL-SYSTEM
-Dosgi.instance.area=@user.home/AppData/Roaming/Archi
-Dosgi.configuration.area=@user.home/AppData/Roaming/Archi/config
-Dorg.eclipse.equinox.p2.reconciler.dropins.directory=%user.home%/AppData/Roaming/Archi/dropins
```

## 1. coArchi1 Setup and Configuration

### 1.1 coArchi1 Setup

Download and Installation Steps:
1. Download the coArchi1 (in .archiplugin extension) from Archi plug-in page https://www.archimatetool.com/plugins/
2. In Archi, select "Manage Plug-in..." from the main Help menu. From the Plug-ins Manager window, select "Install New..." and select the plug-in file and then, when prompted, allow Archi to restart
   
- ![install-coArchi1](img/screenshots/001_install-coArchi1.png)
  
3. The "Collaboration" menu should now be visible
   
- ![coArchi-plugin-window](img/screenshots/002_manage-plugin-coarchi1.png)

### 1.2 coArchi1 Configuration

From Archi menu [Edit]>[Preferences], click "Collaboration" tab as below:

![Collaboration Configuration](img/screenshots/003_preference-collaboration.png)

| Setting Item Group | Explanation |
| --- | --- |
| Global User Details | - Stored in `.gitconfig` file<br>- Every commit is signed with these identity, comprising by `Name` and `Email`<br>- NOTE: you cannot change the signature of a commit after committing! |
| Workspace | - The `Collaboration Workspace folder` is by default located in Archi's home folder. This folder contains local copies of all the models that you have in your workspace. In some aspects, it **is** your workspace.<br>- You can change this location if required.<br>- If you want the models to update their status in the background, check the setting here. `Background fetch` allos Archi to automatically get remote updates to update a model's status base on the `Refresh interval` setting. Note: this does NOT actually refresh the model but only the status. |
| Authentication | - For all actions a `Primary Password` is required. You can set or change this password here.<br>- The `primary password` secures an encryption key that is used to encrypt all other passwords (passwords for each repository), the password that secures the SSH identity (if used) and the password that secures the Proxy settings (if used).<br>- `SSH`: if using SSH repositories set the path to the identity file and password here. If using more than one SSH key select the option to scan the `~/.ssh` folder for SSH keys, this allows more than one SSH key for different remote hosts. NOTT that the identity password must be the same for all key files. Reference: [SSH Authentication section](https://github.com/archimatetool/archi-modelrepository-plugin/wiki/SSH-Authentication)<br>- `HTTP`: If not enabled you will be prompted for your credentials each time you have to connect to a server (i.e. when refreshing or publishing a model). You can enable (by default) this option if you want a seamless experience. |
| Proxy | - If the models you work with are stored on a server which is behind a web proxy, you can configure that here.<br>NOTE: if proxy support is enable - by default not- it will be used to connect to all of your models. |

## 2. coArchi1 Basics

## 3. Manage Workspace

## 4. Manage Changes

### 4.2 Refresh and Publish

#### 4.2.1 Refresh a Model

![Refresh Model](img/screenshots/Refresh_Model.png)

This action updates the local copy of a model by importing and merging all changes that have been published to the remote model by other users.

If you have uncommitted changes in your local model (even if they are not in conflict with other changes to the repository), coArchi will require you to commit them as you do a refresh.

##### 4.2.1.1 Refresh `not authorized` Error

When using HTTPS via GitHub with 2-factor authentication (2FA), if you areabel to import and refresh your model but see the following message on publish:

`There was an error: <repo URL>: not authorized`

[Create a Personal Access Token (PAT)](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) and use it in place of your normal GitHub password.

#### 4.2.2 Publish a Model

![Publish Changes](img/screenshots/Publish_Changes.png)

This action allows you to share your changes with your colleagues by saving them to the (remote) model repository.

If needed, a resolution of conflicts will be triggered.

Technically, the publication corresponds to a `git pull` followed by a `git push`.

## 5. Manage Branches

### 5.3 Handling Branches in the Team

Below steps are the reference "bible" for our modeler team to collaborate using coArchi1 on the common model:

<img src="img/handle_branch_v11_20250429.png" alt="handling branches steps" width="800">

## 6. Connection, Authentication & Security

## 7. Do's & Don't and Other Known Issues

---

Last updated at 2026-03-01