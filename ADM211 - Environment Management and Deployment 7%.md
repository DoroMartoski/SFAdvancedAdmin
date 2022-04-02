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

* Test Release: done in a production copy environment  
  * conduct UAT
  * conduct regression
  * final performance test

* Release
  * deploy your changes to production after your release has met your testing and your quality benchmarks
  * train your users on the impact of the changes - if a release has significant user impact, create a separate environment with realistic data for training users.

3 models of Application lifecycle management (ALM):
* change set development
* org development
* package development
