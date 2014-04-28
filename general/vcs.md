# Version Control

General rules and policies regarding version control.

 * If you're planning on writing something that will take more than a day to do, you should use version control.
 * Open source is a good thing. If you are not developing something that's specific to MCProHosting or its services, ask if it may be open source. 
 * **All code pushed into the master branch must be tested and fully functional.**. Do not push code into master that is not ready for production the moment it's pushed.
 * You must **not** add configuration files with specific or sensitive information to version control. You may instead include a `config.example.json` with instructions to copy the file to `config.json` and fill in appropriate details (`config.json` being gitignored, of course), for instance.

Regarding contributions to repositories:

 * For notable new features and updates that may take more than one or two commits to develop, you should cut another branch, develop, and put in a pull request when the feature is ready to go into production.
 * If you open a pull request, you must not merge it. Ask for another equally or better-skilled developer to review your code prior to merging the feature.
 * On unit-tested projects, you should use Travis CI. Pull requests must have a passing build status before being merged. If, at any time, the build status is not passing in a repository, fixing the project (either via fixing the code or adjusting unit tests, where appropriate) should be a high priority task.

Regarding Git's own files:

 * The `.gitignore` in the root directory must define ignored files or folders throughout the application, *except* in the case where a folder is wished to be kept without its contents. In that instance, creating a `.gitignore` file in that folder with the following contents is preferred:

```
*
!.gitignore
```

 * The `.gitignore` file must contain rules such that the application can be run or compiled without causing any files tracked in git to be changed, and without causing any additional files to be created that git wants to track.
 * In the somewhat rare event where an empty folder must be present in repository, but you do not want to ignore its contents, simply creating the folder and a blank `.gitkeep` file within the folder is sufficient.