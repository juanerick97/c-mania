# INST377-FA2020

This is the lab support repository for the Fall 2020 version of INST377. 

The following steps are to do the following:
* Give you a LOCAL copy of the lab code that you can mess with - if you know how, you can also use the "fork" button on this repository, clone your fork, and have your own copy that way.
* give you a remote, public link to your labs as you complete them that can be graded.

At the end of these instructions, your github pages repository should look like a copy of this repository. You can then work on your labs locally, push to your own remote, and pull changes I make here into your repos without wrecking your work.

It'll be great! But it is tricky to get there.

### Installation
* Clone this repository into Github Desktop using the large green Code button.
* Open it using the "open this repository in VSCode" button within Github Desktop.
* In VSCode, open a new terminal window by going to the Terminal option and selecting New Terminal.
* Type `npm install` in that window.
* Your labs should now be set up well enough for week one.

### Keeping Up To Date With The Course Repository
* You cannot publish your changes to the course repository.
* Instead, you will need to add a remote to your code base, and publish your work there.

#### Github Pages
So: First, get set up with Github Pages by following the instructions present here: https://pages.github.com/
- "User or Organization site"
- You are using Github Desktop.

#### Back to VSCode ---> This portion is experimental.
In your terminal window, in your copy of this repository (folder) - it should be called "INST377-FA2020":
* type `git remote -v` - this will list all the remote places you can save your code.
    * It should list one: this repo, called "origin" - `origin https://github.com/aleitch1/INST377-FA2020`
* type `git remote rename origin classfiles`
* type `git remote -v` and confirm you now have one remote, called "classfiles"
* in Github, find the link to your **Github Pages** repository.
    * It should be something like `https://github.com/YOUR-GITHUB-USERNAME/YOUR-GITHUB-USERNAME.github.io.git`
    * the `.git` at the end specifies it is a repository and not a webpage
* type `git remote add origin [THE LINK YOU JUST FOUND]` and hit enter.
* type `git remote -v` and check that you have two possible remote repositories: the course repo, and your Github Pages repo.
* type `git pull origin master` - it won't WORK because you have two different histories, but it will clear related problems.
* Type `git push origin master --force-with-lease`
    * `--force-with-lease` is like saying "Do it now but don't overwrite any serious local changes."
    * If it doesn't work, you can use `git push origin master --force`, but it will blow away all changes on your remote. Use with caution.
* You have now **overwritten your Github Pages repository**
    * Check by navigating to `https://github.com/your-username/your-username.github.io` - a bunch of lab files should be there.
* You should be able to check that your labs are visible online by visiting `https://YOUR-GITHUB-USERNAME.github.io/public/lab_1/index.html`
* Changes to your repository should be visible in Github Desktop

#### A Slight Problem: Github Desktop Does Not Like This Situation
It will not let you keep tabs on both remotes at once, there's a four-year-long conversation on the topic available below if you care.
Link For Reference: [Github Desktop supports only one remote](https://github.com/desktop/desktop/issues/1442)

**To set your repository remote (where you publish code to) in GH Desktop**
* [Setting Your Remote On Github Desktop](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/changing-a-remotes-url-from-github-desktop)

### How It Should Look When You're Done
* `git remote -v` should output this:
```
classfiles https://github.com/aleitch1/INST377-FA2020.git (fetch)
classfiles https://github.com/aleitch1/INST377-FA2020.git (push)
origin https://github.com/your-username/your-username.github.io.git (fetch)
origin https://github.com/your-username/your-username.github.io.git (push)
```
* going to https://github.com/your-username/your-username.github.io should show a copy of the lab files
* in twenty minutes or so, going to https://your-username.github.io/public/lab_1 should show whatever is in your `/public/lab_1/index.html` file.
* your local directory on your laptop - in finder or explorer - will be named INST377-FA2020
* in Github Desktop it'll turn up as your-username.github.io
   * you may have a duplicate repository now
   * delete the one with no lab files in it

#### Last Steps: Making Sure You Can Push From GH Desktop
Back in the VSCode terminal in your repository, type `git pull origin master --allow-unrelated-histories`
* Ideally, this should integrate your remote repository's history with your local repo, allowing you to use Github Desktop in future.
* If this does _not_ work, good news: you have a remote copy of the lab in the right place.
* You can delete all local copies of everything and re-clone your remote from your Github Pages Repo
* If you have to delete everything and re-clone, please `git remote add classfiles https://github.com/aleitch1/INST377-FA2020.git` so you can pull updates from the class repository.

##### How To Update Your Own Remote From The Main Lab Files
You will need to pull from the class repository periodically as we go through the semester, though hopefully not for the first few weeks.
To do this, in VSCode:
* Open a terminal window.
* Type `git pull classfiles master`, and you should have the updated files.
* You should do this pretty much every time you get working with the labs.
* If it messes with you, which it may do, please join us for office hours and we'll work it out.
