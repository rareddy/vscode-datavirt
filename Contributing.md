# Help to participate in the development of the project

## How to start development

### Inside VS Code

* Click menu *Terminal* -> *New Terminal* to open a terminal view

### Inside the Terminal View

* Enter *npm install* to install all the needed dependencies. You will need to call it again only if dependencies are modified in package.json.
* Enter *npm run watch* to monitor the project for changes and to rebuild automatically
  * You can also click menu *Terminal* -> *Run Task* and then select *npm:watch* from the list
  * Both ways this will make any manual compiling obsolete which is a great help
* Go to *Debug perspective* (*Ctrl+Shift+D*)
* Select *Run DataVirt extension*
* Click on the green arrow OR press *F5* to launch the extension

## How to provide a new version on VS Code Marketplace

* Check that the version in package.json has not been published yet
  * If already published:
    * Upgrade the version in package.json
    * Run 'npm install' so that the package-lock.json is updated
    * Push changes in a PR
    * Wait for PR to be merged
* Check that someone listed as _submitter_ in Jenkinsfile is available
* Create a tag
* Push the tag to vscode-datavirt repository, it will trigger a build after few minutes
* Check build is working fine on [Travis CI](https://travis-ci.org/jboss-fuse/vscode-datavirt)
* Start build on [Jenkins CI](https://dev-platform-jenkins.rhev-ci-vms.eng.rdu2.redhat.com/view/VS%20Code/job/vscode-datavirt-release) with _publishToMarketPlace_ parameter checked
* Wait the build is waiting on step _Publish to Marketplace_
* Ensure you are logged in
* Go to the console log of the build and click "Proceed"
* Wait few minutes and check that it has been published on VS Code Marketplace
* Keep build forever for later reference and edit build information to indicate the version
* Prepare next iteration:
  * Upgrade the version in package.json
  * Run 'npm install' so that the package-lock.json is updated
  * Push changes in a PR
  * Follow PR until it is approved/merged
  