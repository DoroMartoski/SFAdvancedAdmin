# Environment Management and Deployment
#### Estimated Number of questions out of 60: 4.2 (4) questions

ALM defines the process of managing an app’s development, from design to final release.

ALM process:
* Plan the release
  * Gather and analyze the requirements
  * create the design specifications
  * determine the the development and testing environments necessary

* Develop
  * complete the development in a development environment that does not have production data but has production metadata.

* Test:
  * execute your tests in your development environment seperate from integrated testing environment.
  * focus on testing your code and not on how your changes may affect other peoples code or their changes in the release. 

* Build release
  * aggregate all your change components into a bundle. focus on the entire release from this point
  * before the build step, you migrate all of the changes from every project to the same environment for integration
  * in the test release step that follows build, you test all the changes together

* Test Release: done in a production copy environment  
  * conduct UAT
  * conduct regression
  * final performance test

* Release
  * deploy your changes to production after your release has met your testing and your quality benchmarks
  * train your users on the impact of the changes - if a release has significant user impact, create a separate environment with realistic data for training users.

3 models of Application lifecycle management (ALM) based on change complexities:

* change set development: the team’s release artifact is a set of metadata changes, like a diff or delta, relative to what’s in the production org 
 * What gets released is only metadata that has been added or changed—if it doesn’t change, it’s not in the release.
 * change set development you manage a set of changes from multiple projects as though they’re going into one container
 * In change set development, the source of truth is a combination of the metadata already in the environment and the last build of the change set


* org development
 * change set development model has its limitations such as fields cannot be deleted through change sets.
 * can use the Salesforce CLI to extract metadata from a development environment to integrate with a version control system (VCS).
 * can also use the Salesforce CLI to script routine tasks and boost the productivity of everyone contributing to the release

* package development: In package development, you manage different customizations as separate packages, not as one big release of changes to the org
 
 * When releases become so complex that it makes sense to manage the org as multiple containers, it’s time to move to the package development model
 * Instead of a set of changes relative to production, your team creates a package that contains all the relevant metadata. The metadata in the package includes both changed and unchanged components.
 * A package version is a fixed snapshot of the package contents and related metadata. The package version lets you manage what’s different each time you release or deploy a specific set of changes added to a package
 * your source of truth is the metadata in your package project. This makes it easy to integrate to a VCS that can help your team manage the project changes they make.
 * use scratch orgs: Scratch orgs are empty orgs (no metadata or data) that are easy to create and dispose of as needed
 * You use packages to segment the ownership of org metadata, so each project has its own package plus any dependent packages
 * you can re-use and share the scratch org definition file with other team members, because it’s part of the project integrated into the VCS.
 * You can manage the upgrade of individual segments independently through each subsequent package version, allowing you to maintain separate release schedules.


Package dependency: A metadata component can be in only one package at a time. If more than one package needs the same component, you can devise a modular package strategy for that component. A package containing one or more metadata components shared by multiple packages is a package dependency.




#### Release Management process
Releases could fall into 3 categories
* Patches/bug fixes/small changes

* Minor changes with limited impact

* Major release with significant impact

Release on a consistent schedule.


