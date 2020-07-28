# plentyDevTool User Guide

plentyDevTool helps you streamline your plugin development workflow. Synchronise your local files with the ones on your plentymarkets system.

## Setup

1. Log in with the PID and valid user credentials of your plentymarkets system.
2. After logging in for the first time, the **Settings** menu will open automatically.
3. Select a local folder. plentyDevTool will use this folder for synchronisation.

The **Settings** menu will also open if plentyDevTool does not recognize a local path for synchronisation.

### Folder structure

When downloading new plugins from remote, plentyDevTool will automatically create new folders in the folder you selected for synchronisation. Folders will be created in the following pattern:

```shell
LokalerSyncOrdner/
    ├── System_PID/
    │   ├── Set_ID/
    │   │   │
    │   │   ├── Plugin_Name/
    │   │   │
    │   │   ├── Plugin_Name/
    │   │   │
    │   │   └── . . .
    │   └── . . .
    └── . . .
```

**Do not change this structure or the folder names.** If you do, plentyDevTool will no longer recognize those systems, plugin sets and plugins locally.

**Do not add, delete or modify files manually anywhere outside the plugin subfolders.**

## Synchronisation

Before you can start coding, you need to decide which plugins you want to work on. On the left-hand side, open the plugin set which contains the plugin you want to synchronise, then toggle the plugin. You can select as many plugins as you want this way.

Open the **Dashboard** and **Pull** the plugins. Depending on how many plugins you download or update this way, the process may take a few seconds to complete. If you download a file that has also been modified locally, your local file will be renamed and labeled as backup before the download, allowing you to reconcile the remote and local versions of the file. The renamed file will show up as an addition on the **Dashboard**.

After you have modified a plugin locally, you can **Push** the changes back to your plentymarkets system. Check the changes you have made on the **Dashboard**. Note that only changes of plugins toggled active will be pushed to the system. When working on a set that is not linked to a client, you can also trigger a faster, abbreviated version of the plugin build on **Push**. To do this, activate the **plentyDrive: build automatically** toggle in the respective plugin set in the back end. This setting is set dependent, so you can choose to automatically build some sets, but not others.

### Warning

The auto build is an abbreviated build. It only checks the files changed, but does not validate how they interact with other files. Consequently, the auto build may not show errors that would become apparent in the manual build.

## Add local plugins

You can not only work on plugins that already exist on your system, but also add new ones locally. Once you have created a plugin folder in one of your set folders and filled it with all relevant files, click **Detect new local plugins** to detect all new plugins. Plugins are not detected if the root namespace of the folder and the name and namespace in the plugin JSON differ.

Click **Install** to add a plugin for synchronisation.

## Best Practices

1. plentyDevTool is not a version control system. Use it in combination with [Git](https://git-scm.com/), so you can recover previous versions of your work in case anything goes wrong.

2. Note that even though plentyDevTool creates backup versions of local files during **Pull**, it does not create backups of remote files during **Push**. This means that once you upload your local files to your plentymarkets system, the respective remote files will be overwritten. It is recommended that you always **Pull** before you **Push**.