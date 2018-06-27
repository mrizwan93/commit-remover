# commit-remover

This tools helps in removing last commit.

While submiting patch to [FreeIPA](https://github.com/freeipa/freeipa/), first we need
to run it on pr-ci. If pr-ci passes then the patch can be pushed.

For running the patch in pr-ci we need to follow steps:
1. Edit the [.freeipa-pr-ci.yaml](https://github.com/freeipa/freeipa/blob/master/.freeipa-pr-ci.yaml) and make relevant changes.
2. git add .freeipa-pr-ci.yaml
3. git commit -s -m "temp commit for pr-ci"
4. Push the changes to branch (i.e git push origin <branch-name>)

But When reviewer suggests changes then we need to remove temp commit for pr-ci in order to make changes in actual PR.

For that we follow process:
1. git reset HEAD~1
2. cp .freeipa-pr-ci.yaml /root/
3. git checkout .freeipa-pr-ci.yaml

And then we can make changes to actual PR.

This tool will automate this process.
