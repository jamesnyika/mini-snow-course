# Managing Updates and Sources
As you make all these changes you will need to secure them back in some kind of repository.
Here -we learn to set up your link to the repo.

## Git Repository Configuration
Studio provides a mechanism for you to link to a source control repository. Currently git is the only repository supported.
To access it, go to the 'Source Control' menu and select Link to Source control.
![ModuleEdit](https://github.com/jamesnyika/motivf-snow/blob/master/chap8/images/git1.png)


Add your credentials to that they look as follows
![ModuleEdit](https://github.com/jamesnyika/motivf-snow/blob/master/chap8/images/git2.png)

You can now commit changes by clicking on Commit changes

![ModuleEdit](https://github.com/jamesnyika/motivf-snow/blob/master/chap8/images/git3.png)

### Things to note:
ServiceNow allows you to tag your commits or even to create and work on branches. However, it does not permit merges of branches (which would)
be quite diffcult to do. In addition, the flow is a little cumbersome when working with other developer requiring them to each manage the commits
carefully to prevent corruption. A big limitation is that once a repository has been configured, you *cannot* change and point to a different repository.



### Tasks
1. Configure your project to link to your git repo
2. Commit your changes to your git repo
3. Try and stash changes and then re-apply them over an update you made later.

---

[Chapter 9 - Creating Reports](../chap9/README.md)
