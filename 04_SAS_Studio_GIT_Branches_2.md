![Global Enablement & Learning](https://gelgitlab.race.sas.com/GEL/utilities/writing-content-in-markdown/-/raw/master/img/gel_banner_logo_tech-partners.jpg)

# SAS Studio - Working with Git Branches

<br>

## Exercise Description

In this exercise, you will work with Git branches in SAS Studio.

<br>

- [SAS Studio - Working with Git Branches](#sas-studio---working-with-git-branches)
  - [Exercise Description](#exercise-description)
  - [Exercise Preparation](#exercise-preparation)
  - [4. Reset a Branch](#4-reset-a-branch)
    - [Branch *your-branch*](#branch-your-branch)
    - [Branch  *his-branch*](#branch--his-branch)
  - [5. Rebase a Branch with Another](#5-rebase-a-branch-with-another)
    - [Branch  *his-branch*](#branch--his-branch-1)
    - [Branch  *your-branch*](#branch--your-branch)
    - [Rebase](#rebase)
  - [6. Stash your Work in Progress](#6-stash-your-work-in-progress)
  - [End](#end)
  - [Navigation](#navigation)

## Exercise Preparation

1. Open the **Google Chrome** browser on your Windows RACE Image.
1. Select the **SAS Viya** bookmark.
1. Enter the following:
   - User ID: **Alex**
   - Password: **lnxsas**

1. Click **Sign In**.

1. Select ![Viya Menu Selector](images/HamburgerMenu.png) **&#10132; Develop Code and Flows** to open *SAS Studio*.
2. Complete the steps in the previous exercise.  This exercise builds on that one.


## 4. Reset a Branch

### Branch *your-branch*

1. Be sure to do the previous steps so that your repository is in a modified state, and have a known state (commit), you can reset to.

1. Open the Git ![](images/GITIcon.png) and select the **History** tab.
1. Check out **your-branch** by selecting it from the **Current branch** drop down menu.
1. *Right click* the **feature/T-545-report-change main** `Report change` commit and select **Reset**.
   - > This action takes **your-branch** back to its state at that particular commit.

   ![](images/resetCommand.png)

1. You'll see dialog box asking which reset type you would like to perform:
   - >**Soft** = Only reset the repository.  Leave the changes in the staging area and the working directory.
   - >**Mixed** = Reset the repository and the staging area.  Leave the changes in the working directory.
   - >**Hard** = Reset the repository, the staging area, and the working directory.  Completely erase the changes.

1. Select a **Hard** reset and push **OK**.

   ![](images/resetChoices.png)

1. After the reset, you'll see **your-branch** has been returned to the commit you selected.

   ![](images/afterReset.png)

   - > Note that **his-branch** has not been affected by the reset.

1. With **your-branch** checked out, confirm that the changes to your working directory files have been erased by the reset. In `TopNCategories.sas` you should see `%let n=5;`.

### Branch  *his-branch*

9. Check out **his-branch** and reset it to the same commit as well.

<br>

## 5. Rebase a Branch with Another

### Branch  *his-branch*

1. Check out **his-branch** and add the following code to **TopNCategories.sas** after the **footnote** statement:

```sas
/* his-branch: add merror option */
options merror;
```

   ![](images/hisBranchSaveRebase.png)

2. Save and close the **TopNCategories.sas** file.
3. Return to the Git ![](images/GITIcon.png) page, stage and commit the change with the message, **merror**.

### Branch  *your-branch*

4. Check out **your-branch** and add the following code to **TopNCategories.sas** in the **%let** statement block:

```sas
/* your-branch: Added q macro variable */
%let q=16;
```

   ![](images/qMacro.png)

5. Save the file, stage and commit the change with the comment: **q macro**.

### Rebase

6. Select the **History** tab.
7. Right click the latest commit, **his-branch merror** and select **Rebase your-branch on > Selected Commit**

   ![](images/rebaseBranch.png)
8. You will see the following text box:

   ![](images/rebaseAlert.png)

9.  Select **OK**.
10. On the **History** tab, note that:

   - >**your-branch** now includes the **his-branch merror** commit.
   - >The commit illustration shows no merge.  It's as if **your-branch** was created from **his-branch**.
   ![](images/rebaseAfterFile.png)

11. Open the **TopNCategories.sas** file and see that it includes the modification from **his-branch**.
    ![](images/rebaseAfterFileChanges.png)

<br>

## 6. Stash your Work in Progress

1. Use **Git Stash** to save your work temporarily while you quickly complete a hotfix for a different project.

2. Make the following changes to **your-branch**:
   1. Copy the **TopNCategories.sas** program by right clicking it and selecting **Copy to** and selecting the **myGitClone** folder.
   2. This will create a file named **TopNCategories_Copy1.sas**.
   3. Right click that file and rename it **NewCategoriesReport.sas**.
   4. Rename **TopNCategories.sas** to **OldCategoriesReport.sas**.
   5. Rename **PythonSample.py** to **PythonProgram.py**.
   6. Add a note to the **Class_Export.flw** flow by opening it, right clicking the canvas and selecting **Add a Note**: `This flow writes the CLASS table to a text file`.

      ![](images/flowNote.png)

1. Save and close the flow.
1. Return to the Git screen and **stage** your changes.  **Do not commit them.**
   ![](images/stageStash.png)

1. Stash your changes by pushing the stash icon ![](images/gitStashIcon.png) and selecting **Stash**.
1. After the stash, note that the staged changes have disappeared.  The changes are now stored in the stash.
1. Return to the Explorer ![](images/ExplorerIcon.png) and look at the contents of your Git working directory.  It has reverted back to its state prior to your stashed changes.

   ![](images/stashDirectory.png)

1. Complete the work for your hotfix by editing the **PythonSample.py** and adding the code **import swat** as shown below.
   ![](images/importSwat.png)
1. Save and close the file.
1. On the git screen ![](images/GITIcon.png), **stage** and **commit** the change with the comment **hotfix #1**.
1. Open the history tab and note that **your-branch** is now one commit ahead of the stash.

   ![](images/commitStash.png)

1. Push the stash icon ![](images/StageIcon.png) and select **Pop stash**.
   - > **Pop stash** applies the stashed changes and deletes the stash.
   - > **Apply stash** applies the stashed changes but keeps the stash.

   ![](images/popStash.png)

1. After **Pop stash**, note that the stashed changes are re-introduced, and that the hotfix change is also maintained and applied to the renamed file.

   ![](images/postStashPy.png)

<br>


## End

## Navigation

<!-- startnav -->

<!-- endnav -->
