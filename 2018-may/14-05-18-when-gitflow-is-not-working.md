## When GitFlow isn't working and you want to make a release

1. `git checkout develop`
1. `git checkout -b release/version-number`
1. `git push` - this will come up with a message saying:

    `git push --set-upstream origin release/version-number`

    copy and paste that
1. Check what tags are available with `git tag`
1. Tag your current release branch with `git tag version-number`
1. Check current tags again `git tag`
1. `git push --tags` to push your new tag to remote

Once the release branch has been deployed, remember to merge this back into master/dev via PR. If there are merge conflicts, you will need to resolve this locally. Then do git add, commit and push

When merge conflict happened to me, I had to `git merge master` into release branch and resolve which version I would accept at the conflict. I then pushed the changes to remote before I could do a PR from release into master.
