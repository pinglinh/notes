## Team City CI and Octopus Deploy

Using GitFlow branching model, every branch (i.e. feature, develop, release etc.) triggers a build process via Team City and creates a release package ready to be deployed by Octopus.

You can check how your feature is currently working on a dev environment (this will be alongside other features that others are working on). The built feature package needs to first be saved and deployed to correct dev environment in Octopus before the changes can be seen. After this has been done, everytime you push your changes, you'll be able to view them on the dev environment (note that other people will also be able to use this environment so you may be able to see their changes as well but obviously you will only be interested in the feature you're working on and making sure it doesn't break anything else).

Once you've finished and have tested your feature, you need to create a pull request to merge into develop. You will need to merge the latest changes from develop into your branch before making a PR. Once a PR is reviewed and accepted, this will start a build process for the development branch. Once all the steps pass and a release package is created, this can be deployed to the test environment. This is where QAs do their acceptance testing (I think).
