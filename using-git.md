## Using Git During Your Projects

### Rules
1. Master branch should be protected -- do not merge or push anything to master unless it comes from a pull request
2. Pull requests should be reviewed and approved by at least one team member who was not involved in the development of the feature


### General Feature Work Flow
1. Pull master so you have the most recent changes
2. Create a new feature branch
```git
git checkout -b my-feature-branch
```
3. Commit work to your feature branch
4. Whenever master moves on, merge master into your feature branch to resolve conflicts as quickly as possibly
```git
git checkout master
git pull 
git checkout my-feature-branch
git merge master
```
5. When your feature feels done (i.e. you have completed all the acceptance criteria), push to github and open a pull request to merge the changes into master

### Resolving Merge Conflicts
Merge conflicts will arise -- its part of working on a team -- you can't avoid working on the same files occasionally. This is why its important to pull master and merge it into your feature branch often. 

```git
Auto-merging [filename1]
CONFLICT (content): Merge conflict in [filename1]
Automatic merge failed; fix conflicts and then commit the result.
```
When you see this, git has identified two changes on the same line and doesn't know how to merge the files. The resulting conflict will look like this on the file that is referenced
```javascript
<<<<<<< HEAD
console.log("i am an edited line on the feature branch")
=======
console.log("i am an edited line on the master branch")
>>>>>>> master
```
If one line is meant to replace the other, then you can just remove the lines and the corresponding merge tags. If you need both changes, you should keep both lines. 

Many times merge conflicts aren't this simple and require you to work with the person whose code you have a conflict with to determine how to merge your changes while maintaining functionality. When in doubt, call in your project advisor. 

Also note that VSCode has some functionality built in that will help you resolve conflicts but be aware that more complex conflicts will still likely need to resolved manually. 



