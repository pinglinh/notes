## Team City CI and Octopus Deploy

Using GitFlow branching model, every branch (i.e. feature, develop, release etc.) triggers a build process via Team City and creates a release package ready to be deployed by Octopus.

You can check how your feature is currently working on a dev environment (this will be alongside other features that others are working on). The built feature package needs to first be saved and deployed to correct dev environment in Octopus before the changes can be seen. 
