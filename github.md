% Introduction to git & GitHub
% Presentation: [arbr.dk/github.html](http://www.arbr.dk/github.html)
% Demo repo: [TBroedsgaard/github-demo](https://github.com/TBroedsgaard/github-demo)

## Agenda:
    
- About git
    - Basic workflow
    - git demo, how it works
- About GitHub
    - [GitHub Flow](http://scottchacon.com/2011/08/31/github-flow.html)
    - [Project Management](http://net.tutsplus.com/articles/general/team-collaboration-with-github/) (briefly)
- Hands-on demo
    - GitHub for Windows
    - Creating and merging branches
    - Merge conflicts
- Questions 
    - extras / beer
    
## You need:

- [GitHub for Windows](http://windows.github.com/)
- [GitHub account](https://github.com/)

## git:
    
- "fast, scalable, distributed revision control system"
    - Repository (archive) with full history (versioning)
    - Local copy (fast, good for offline usage)
    - Powerful and cheap branching and merging
    - Flexible: a workflow for any project
    - not an improved version of SVN - very different
    
> - "the stupid content tracker"
    - You can break your repo
    - git cannot fix it for you
    - But it wants to help you    
    
## Basic git workflow:
    
- Develop features in iterations
    - Write minimum code to make it work
    - Stage and commit changes
    - Iterate, adding try-catch
    - Stage and commit changes
    - Iterate, clean up code (add comments etc)
    - Stage and commit changes
    - Move on...

- Develop features in isolation
    - Need a new feature? Get a new branch!
    - You can experiment in the branch without breaking your main program
    - When it works, you merge the new and main branches
    - If it never works, you throw it away
    - Several branches for several features

## git basics demo:
    
- Directory with two files:
    
~~~
git init // create local repo
git status // get status
~~~

![](images/git1.png)

## git basics demo:

- Do first commit

~~~
git add . // add all untracked files to staging
git commit -m "message" // commit with message
~~~

![](images/git2.png)

## git basics demo:
    
- More work, second commit

~~~
git status // check status
git diff // line-by-line comparison
git commit -am "message" // add all tracked files to staging and commit with message 
git log // show commit log
~~~

![](images/git3.png)

## git basics demo:
    
- Introducing HEAD

![](images/git4.png)

## git basics demo:
    
- Point HEAD at commit
    
~~~
git checkout <commit> // point HEAD at commit
git status
~~~

![](images/git5.png)

## git basics demo:

- Introducing branches

~~~
git branch // list branches
git checkout master // point HEAD at master
~~~

![](images/git6.png)

## git basics demo:
    
- Branching

~~~
git branch answer-hello // create branch answer-hello
git checkout answer-hello // point HEAD at answer-hello
~~~

- Do some work, commit

~~~
git status // check status
git commit -am "message" // add all tracked files to staging and commit with message 
~~~

![](images/git7.png)

## git basics demo:
    
- To illustrate merging, do some stuff on master:
    
~~~
git checkout master
// do work
git commit -am "message"
~~~

![](images/git8.png)

## git basics demo:
    
- Merge branches:
    
~~~
git merge answer-hello // merge answer-hello into your current branch
git log --graph --oneline --decorate // pretty!
~~~

![](images/git9.png)

## git basics demo:
    
- Working with remotes:    
    
~~~
git remote add origin <repo url> // add remote with repo url and call it origin
~~~
    
![](images/git10.png)    

## git basics demo:
    
~~~
git push origin master // push master to remote repo called origin
~~~

![](images/git11.png)

## git basics demo:

~~~
git clone <repo url> // make local clone of remote repo
~~~

![](images/git12.png)

## git basics demo:
    
~~~
// do work
git commit -am "message"
~~~

![](images/git13.png)

## git basics demo:
    
~~~
git push origin master
~~~

![](images/git14.png)

## git basics demo:
    
~~~
git pull origin master
~~~
    
![](images/git15.png)

## git basic commands:

~~~ 
git init // create local repo
git status // get status
git add . // add all untracked files to staging
git commit -m "message" // commit with message
git diff // line-by-line comparison
git commit -am "message" // add all tracked files to staging and commit with message 
git log // show commit log
git checkout <commit> // point HEAD at commit
git branch // list branches
git checkout master // point HEAD at master
git branch answer-hello // create branch answer-hello
git checkout answer-hello // point HEAD at answer-hello
git merge answer-hello master // merge answer-hello into master
git clone <repo url> // get everything from repo url
git push origin master // push new commits to origin/master
git pull origin master // pull new commits from origin/master
~~~

## git basic branching and merging:    

- The master branch is sacred (contains working code)
- New features developed in seperate branches
- To bring a feature into master you merge the branch containing the feature
- To maintain virginity of master: 
    - merge master into the feature branch
    - make sure the code compiles (and works)
    - only now push to master
    - to achieve nirvana: **never** push to master - use pull request

## git-flow:

![](http://nvie.com/img/2009/12/Screen-shot-2009-12-24-at-11.32.03.png)    

## GitHub:

- "Social coding"
- Central repo hosting
- Issue management (and wiki and other awesome features)
- Pretty stable
- De facto standard for open source (forking, pull request)
- Team and organization repo
- Expensive for private repo

## GitHub-flow:
    
![](http://theodi.github.io/presentations/open-data-flow/github_flow.png)    

- master is always in a deployable state
- Bugfixes and features developed in seperate branches
- Keeps it simple 
- Easy to learn, difficult to screw up real bad
- Works both with team repo and forked repos

## GitHub-flow step by step:

- Create a repo on GitHub, invite team members
- Clone the repo to an empty folder using GH4W
- Either copy your existing solution-folder into the new folder or create a new solution
- Create a new branch locally with GH4W, select it and publish it - always do your own work in your own branch
- Now do your work and commits
- when the feature is done, do a pull request on GitHub
- Remember to sync master once a day, and merge it into your working branch

## Project management:
    
- Issues & Milestones
- [Huboard](http://www.huboard.com) - Beta version rocks
- Pull request as discussion
- Code review
- No timetracking & burndown :( (do it yourself)
    
## Break:

- Post your username to [issue #1](https://github.com/TBroedsgaard/github-demo)

## Hands-on:
    
- Create branch    

![](images/branch.png)    

- Do work, then commit

![](images/commit.png)    

- Publish

![](images/publish.png)    

- Pull request

![](images/pullrequest.png)

## Merge conflicts:
    
- Merge in GH4W:

![](images/managemerge.png)

![](images/preparingmerge.png)
    
- Boom!

![](images/unabletomerge.png)

## git status to the rescue!

~~~
git status // read and comprehend
~~~

![](images/gitstatus-conflict.png)

## Fix conflict in src/atest/atest/Program.cs:
    
- Before:
    
![](images/file-conflict.png)
    
- After:

![](images/file-fixed.png)

## Commit to complete merge (commandline):
    
- stage
    
~~~
git status
git add <filename>
git status
~~~

![](images/gitstatus-fixed.png)

- and commit (can also be done in GH4W)

~~~
git commit - m "message"
git status
~~~

![](images/conflict-fix.png)  
    
## Merge conflict summary:
    
- Try to merge, conflict breaks your repo
- Find conflicted files with git status
- Fix conflict in Visual Studio
- Stage and commit

## Resources:

- [git reference](http://gitref.org/)
- [Pro Git](http://git-scm.com/book)
- [Code School](https://www.codeschool.com/)
    - Try Git 
    - Git Real 1 & 2
    
## Questions / extras / beer    

- GH4W and commandline sucks? Try SourceTree
- GitHub sucks? Try Bitbucket (or GitLab)
- rebase, squash to rewrite history
- add only parts of file to staging