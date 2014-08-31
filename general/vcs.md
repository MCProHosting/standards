# Version Control

### General rules and policies regarding version control.

 * Open source is a good thing. If you are not developing something that's specific to MCProHosting or its services, ask if it may be open source.
 * You must **not** add configuration files with specific or sensitive information to version control. You may instead include a `config.example.json` with instructions to copy the file to `config.json` and fill in appropriate details (`config.json` being gitignored, of course), for instance.

### Regarding Git's own files:

 * The `.gitignore` in the root directory must define ignored files or folders throughout the application, *except* in the case where a folder is wished to be kept without its contents. In that instance, creating a `.gitignore` file in that folder with the following contents is preferred:

```
*
!.gitignore
```

 * The `.gitignore` file must contain rules such that the application can be run or compiled without causing any files tracked in git to be changed, and without causing any additional files to be created that git wants to track.
 * In the somewhat rare event where an empty folder must be present in repository, but you do not want to ignore its contents, simply creating the folder and a blank `.gitkeep` file within the folder is sufficient.

### Gitflow

We follow [Atlassian's Gitflow](https://www.atlassian.com/git/workflows#!workflow-gitflow). Read it for details on how the code flows!

![Gitflow](https://www.atlassian.com/git/workflows/pageSections/00/contentFullWidth/0/tabs/02/pageSections/010/contentFullWidth/0/content_files/file0/document/git-workflow-release-cycle-4maintenance.png)