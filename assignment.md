## Chapter 3 Assignment

From this point onwards, you will be managing your assignments with `git` and submitting them through GitHub. The aim of this assignment is to get you familiarized with a common version control workflow.

#### Getting Started
Make sure you've <em>forked</em> this repository under your own GitHub account, and then clone your own repository to your computer. You will push the changes you've made to this document as submission to GitHub.

If the version control concepts or `git` commands are still confusing to you, consider re-reading and following the online notes, or check out an interactive tutorial like [Learn Git Branching](https://learngitbranching.js.org/).

#### The Assignment:
 0. Create a branch in this assignment repository named `submission`, then list all the branches you have (Hint: look at the Branch chapter of notes on how branches work, how to create new ones, and check existing branches):

    ```bash
    git checkout -b submission
    git branch
      main
    * submission
    ```

 1. List the current `remote` name and hyperlink destination of this assignment repository (Hint: if you are not sure, add `--help` after your command to check remotes.). 

    ```bash
    origin	git@github.com:vasilisa-iatckova/version_control_assignment.git (fetch)
    origin	git@github.com:vasilisa-iatckova/version_control_assignment.git (push)
    ```


 2. Add a second remote destination named `upstream` to your assignment repository, `upstream` is a common name used for the repository that people have forked from, in our case, the `upstream` will be at `https://github.com/WCM-datascibasics/version_control_assignment`. List the new list of remotes after you've added the new remote. 
 
    ```bash
    origin	git@github.com:vasilisa-iatckova/version_control_assignment.git (fetch)
    origin	git@github.com:vasilisa-iatckova/version_control_assignment.git (push)
    upstream	https://github.com/WCM-datascibasics/version_control_assignment (fetch)
    upstream	https://github.com/WCM-datascibasics/version_control_assignment (push)
    ```

 3. Save your modifications to this file so far and create a commit indicating you've answered the first 2 questions. Then try pushing the changes to the `upstream` destination on GitHub. What happens? Explain in your own words why does this happen? What are the benefits of having this `upstream` remote added when working collaboratively (Hint: read git command outputs!)?

    > Push failed because I don't have permissions to push to upstream. I can create a pull request for review though; that's the benefit of adding an upstream remote. I can probably also see what changes have been done to the main repo as I work to add my modifications.


 4. Now clone the repository for the [class website](https://github.com/WCM-datascibasics/wcm-datascibasics.github.io), and in the class website repository:
    - a. Explore the version history by visualizing it as a graph (remember the dog meme?).
        ```bash
          # I deleted an apostrophe from one of the commit desciptions for sightliness
        	 git log --all --decorate --oneline --graph
          * a3f66fd (HEAD -> master, origin/master, origin/HEAD) swapped 2 weeks
          * cd0d211 python notes repo link
          * df90802 updated syllabus with presidents day
          * e0029df place holder schedule
          * 7462142 update lecture link for week 3
          * 8fced37 assignment 2 updated
          * 2a2bfd5 version control chapter
          * 13e5722 minor improvements to instructions
          * dd4719c fixed assignment 1 link
          * 0392554 fixed syllabus
          * 48e689c updated syllabus with MLK day
          * e96eba0 added daves slides link
          * fbb9e8d fixed typo
          * c152f3c added ch2 assignment
          * cd40b26 fixed typo in assignment 1
          * b3455f6 fixed missing link
          * 7cd4587 update links to reflect erlative links
          * fb12bef jekyll config additions for relative links
          * 7ed94e9 dash fix
          * d6f3ec1 fixed link error
          * 2c05357 update links
          * 9586a22 removed type app
          * 00e8ae5 readme and try new size
          * 793782a Set theme jekyll-theme-minimal
          * b7a7152 initial transfer to no annex repo
        ```

    - b. Who was the last person to modify `README.md`? (Hint: use `git log` with an argument)
        ```bash
        git log -p README.md 
        commit 00e8ae51a08a0f3754ab228f62b51651595c4426
        Author: Xihe Xie <axiezai@gmail.com>
        Date:   Mon Dec 28 16:01:51 2020 -0500

            readme and try new size

        diff --git a/README.md b/README.md
        new file mode 100644
        index 0000000..dbad2e5
        --- /dev/null
        +++ b/README.md
        @@ -0,0 +1 @@
        +# Course GitHub Pages repo
        ```
    
    - c. What was the commit message associated with the last modification to the `-Week 2` line of `index.md` file? (Hint: use `git blame` and `git show`, check out their help pages if you are not sure what to do)
      > swapped 2 weeks

 5. In the course website repository (or another repository you want to clone from GitHub), modify one of its existing files, do not `git add` or `git commit` yet:
     - a. What happens when you do `git stash`, be specific about what happens to your uncommitted changes after `stash`.?
       > My changes are not creating uncommitted files; instead, they are saved or queued up elsewhere (on stack) for returning to them at a later time. My working tree is clean.
     - b. What do you see when you run `git log --all --oneline` after stashing your modification?
       > I see the stashed changes as work in progress; that's the top line of the output.
     - c. Look up what `git stash drop` and `git stash pop` does, either Google or use `--help`. Run `git stash drop` to undo what you did with `stash`, in what scenario might `stash`-ing, `pop`-ing, and `drop`-ing be useful?
       > Stashing is useful when I'm not yet ready to commit my changes (I'm in a draft mode and have not finished but need to work on another file in the same repo before I'm done making changes). Dropping is useful when I'm done working with a stash and don't want to commit. Popping is useful when I'm done working with a stash and do want to commit.

 6. One common mistake when learning `git` is to commit large files that should not be managed by `git` or adding sensitive information like security keypairs for Amazon Cloud Services. Navigate back to your assignment repository and try adding a random text file to the repository (use `touch`), making some modifications and commits to your repository, and deleting that file with `rm`. But deleting with `rm` will not delete that file's recorded git history, therefore we need to do a little more. You may want to look at [this](https://help.github.com/articles/removing-sensitive-data-from-a-repository/))

    > I accidentally did this on main the first time around, but we fixed it together later.


 7. Like many command line tools, `git` provides a configuration file (or dotfile) called `~/.gitconfig`. Create an alias in `~/.gitconfig` so that when you run `git graph`, you get the output of `git log --all --graph --decorate --oneline`. You can do this by directly modifying the `~/.gitconfig` file or by using the `git` command line functionality.
    ```bash
    [alias]
        graph = log --all --graph --decorate --oneline
    ```
    This is also a good opportunity to turn your dotfiles folder into a version controlled repo (Use `git init` in your dotfiles folder), make it private if you have sensitive `ssh` configurations there (IP Addresses), else feel free to make it public. (This is for your own benefit, not part of the assignment grading)

 8. You can define global ignore patterns in `~/.gitignore_global` after running `git config --global core.excludesfile ~/.gitignore_global`. Do this, and set up your global `gitignore` file to ignore OS-specific or editor-specific temporary files, like `.DS_Store`, or `.vscode`. Feel free to Google around for common gitignore entries for Python projects or other projects of your interest.

    ```bash
    .DS_Store
    .DS_Store?
    Thumbs.db
    ```

 9. Push the `submission` branch of your repository to your GitHub remote. Your remote `main`/`master` branch should be unchanged since your fork. Now go to your GitHub repository settings and add `axiezai` as a collaborator. Now create a pull request to merge the changes from `submission` to `main`/`master`, assign your TA `axiezai` as a reviewer. You will receive feedback and grades through the pull request review.
