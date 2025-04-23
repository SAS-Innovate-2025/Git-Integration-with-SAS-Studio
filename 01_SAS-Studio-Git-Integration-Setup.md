![Global Enablement & Learning](https://gelgitlab.race.sas.com/GEL/utilities/writing-content-in-markdown/-/raw/master/img/gel_banner_logo_tech-partners.jpg)

# SAS Studio - Git Integration Setup
- [SAS Studio - Git Integration Setup](#sas-studio---git-integration-setup)
  - [Exercise Description](#exercise-description)
  - [Create Personal Access Token for GitHub](#create-personal-access-token-for-github)
  - [Confirm your Email Settings for GitHub](#confirm-your-email-settings-for-github)
  - [Create a Fork of a GitHub Repository](#create-a-fork-of-a-github-repository)
  - [Create a Git Profile in SAS Studio](#create-a-git-profile-in-sas-studio)
  - [Create a Folder for the Local Copy of the Repository](#create-a-folder-for-the-local-copy-of-the-repository)
  - [Add Repository in SAS Studio](#add-repository-in-sas-studio)
  - [Review Git Repository](#review-git-repository)
  - [Exercise Navigation](#exercise-navigation)

<br>

## Exercise Description
In this exercise, you will setup the integration between a GitHub repository and SAS Studio.  The cloning of the repository in this exercise is done using HTTPS.  For an example using SSH, review <a href="https://communities.sas.com/t5/SAS-Communities-Library/How-to-Clone-a-GitHub-Repository-in-SAS-Studio-Using-SSH/ta-p/872728" target="_blank">this post</a>.

<br>
<br>

## Create Personal Access Token for GitHub
1. In *Google Chrome*, navigate to <a href="https://github.com" target="_blank">https://github.com</a>.
1. Click **Sign in** to sign in with your *GitHub* credentials.

     > &#9755; If you do not already have *GitHub* credentials, then click **Sign Up** and follow the instructions to create them.  Please do the sign-up portion on a browser on your actual PC rather than the course image.  You can return to the course image if you want after the sign-up process or continue to work in GitHub on your PC.

1. Select your account picture **&#10132; Settings**.

    ![GitHubSignIn](images/GitHub_SignIn.png)

1. Scroll down and select **<> Developer settings**.
1. Select **Personal access tokens &#10132; Tokens(classic)**.

    ![](images/PersonalAccessTokens.png)

1. Select **Generate new token &#10132; Generate new token (classic)**.

    ![](images/GenerateNewToken.png)

1. Enter the following information:
   - *Note*:  **My Token for SAS Studio VLE class**
   - *Expiration*: **30 days**
   - *Select scopes*: ![](images/SelectedCheckbox.png) **repo**  and  ![](images/SelectedCheckbox.png) **user**

    ![](images/GenerateToken.png)
    > &#9998; **user** section is not displayed in this screenshot.

1. Scroll down and click **Generate token**.

    ![](images/GenerateToken2.png)

1. Select ![](images/Copy.png) to copy the token.
   > &#9888; Make sure to copy your personal access token now. You won’t be able to see it again!

    ![](images/CopyToken.png)

1. Paste the token in *Notepad++* and save it.

      > &#9998; There is an icon on the taskbar for the application.

    ![](images/SavedToken.png)

1. Select ![](images/GitHubImage.png) to return to your *GitHub dashboard*.

<br>
<br>

## Confirm your Email Settings for GitHub
1. Select your account picture **&#10132; Settings**.
1. Select **Emails**.
1. Make note of your **primary email address**.

     > &#9998; You will need this for your Git Profile in SAS Studio.

1.  Ensure that the option to **Block command line pushes that expose my email** is unchecked.

    ![](images/GitEmailSettings.png)

1. Select ![](images/GitHubImage.png) to return to your *GitHub dashboard*.

<br>
<br>

## Create a Fork of a GitHub Repository

1. Enter **SAS-Innovate-2025/Zephyr-System** in the *Search* area.

    ![](images/GitHub_Search.png)

1. Press **Enter** key to perform the search.
1. Select the hyperlink for the **SASInnovate2025/Zephyr-System** repository.
1. Select **Fork &#10132; Create a new fork**.

     ![](images/CreateNewFork.png)

     > &#9998; If you have previously created a fork of this repository, then click the hyperlink for the existing fork.  Select ![GitHub Settings](images/GitHubSettings.png), scroll down and click **Delete this repository**.  Complete the deletion process for the existing fork, then create a new fork.

1. Keep the default settings and click **Create fork**.

     > &#9998; This process can take a few minutes depending upon the size of the repository.

1. Once the creation of the fork is complete, then select **Code**.

     ![](images/CodeButton.png)

1. On the *Local* tab, make sure **HTTPS** is selected, and then select ![](images/Copy.png) to copy the path to *clone* this fork of the repository.

     ![](images/CloneRepository.png)

1. Paste the URL in the *Notepad++* file you saved in the token in.

<br>
<br>

## Create a Git Profile in SAS Studio
1. Open the **Google Chrome** browser on your Windows RACE Image.
1. Select the **SAS Viya** bookmark.
1. Enter the following:
   - User ID: **Alex**
   - Password: **lnxsas**


1. Click **Sign In**.
1. Select ![Viya Menu Selector](images/HamburgerMenu.png) **&#10132; Develop Code and Flows** to open *SAS Studio*.

    ![](images/SASStudio.png)

1. Select **Options &#10132; Manage Git Connections**.
1. On the *Manage Git Connections* window, select the **Profiles** tab.
1. Select ![](images/AddIcon.png) to add a profile.

    ![](images/AddGITProfile.png)

1. Select **HTTPS** tab and enter the following information:
   - Profile name: **MyGitHubProfile**
   - User name: ***&lt;your GitHub user name&gt;***
    - Email: ***&lt;your GitHub primary email address&gt;***
    - Password: ***&lt;paste saved Personal Access Token for GitHub&gt;***

        > &#9998; You created and saved it earlier in this exercise.

    ![](images/HTTPSGITProfile.png)

1. Click **OK** to create the profile.

    ![](images/SavedGITProfile.png)

1.  Click **Close**.


<br>
<br>

## Create a Folder for the Local Copy of the Repository
1. Select ![](images/ExplorerIcon.png) to view the **Explorer** tab in *SAS Studio*.

    ![](images/ExplorerTab.png)

1. Navigate to **SAS Server &#10132; Home &#10132; gelcontent** and select ![](images/NewFolderIcon.png) **&#10132; Folder**.

    > &#9998; The folder for a Git Repository must exist on the SAS Server and be an empty folder.

    ![](images/CreateNewFolder.png)

1. Enter the Name **MyGitClone**.

    ![](images/NewFolder.png)

1. Select **OK** to create the folder.
<br>
<br>

## Add Repository in SAS Studio
1. Select **Options &#10132; Manage Git Connections**.
1. On the *Manage Git Connections* window, select the **Repositories** tab.
1. Select ![](images/AddIcon.png) **&#10132; Clone a repository** to add a cloned repository.

    ![](images/AddRepository.png)

1. Enter the following information:
    - Repository: ***&lt;paste saved URL for cloned (forked) Git repository&gt;***

        > &#9998; You created and saved it earlier in this exercise.

    - Server location: **/gelcontent/MyGitClone**

        > &#9755; Select ![](images/FileIcon.png) to navigate to **SAS Server &#10132; Home &#10132; gelcontent &#10132; MyGitClone** or **Folder Shortcuts &#10132; Shortcut to MyGitClone**.

         > &#9998; This must be an empty folder location.

    - Profile: **MyGitHubProfile**.

    ![](images/CreateCloneRepository.png)

1. Click **Clone** to clone the repository in the location specified.
1. Click **Close**.

<br>
<br>

## Review Git Repository
1. Select ![](images/ExplorerIcon.png) to view the **Explorer** tab in *SAS Studio*.
1. Expand **Folder Shortcuts &#10132; Shortcut to MyGITClone** to view the contents of the cloned repository.

     ![](images/RepositoryContents.png)

1. Select ![](images/GITIcon.png) to view the **GIT Repositories** tab in *SAS Studio*.
1. Double-click **MyGitClone** to open it in a tab.

    ![](images/MyGITCloneTab.png)

      > &#9998; This is where you can view the staged/unstaged changes in your local repository and pull/push changes to the external Git repository.

1. Close the *MyGitClone* tab.


<br>
<br>

## Exercise Navigation
<!-- startnav -->
* [01 SAS Studio-Git-Integration-Setup](/01_SAS-Studio-Git-Integration-Setup.md)**<-- you are here**
* [02 SAS Studio SAS Program](/02_SAS_Studio_SAS_Program.md)
* [03 SAS Studio GIT Branches 1](/03_SAS_Studio_GIT_Branches_1.md)
* [04 SAS Studio GIT Branches 2](/04_SAS_Studio_GIT_Branches_2.md)
<!-- endnav -->


