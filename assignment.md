    git checkout -b submission
    git branch
      main
    * submission
    origin	git@github.com:vasilisa-iatckova/version_control_assignment.git (fetch)
    origin	git@github.com:vasilisa-iatckova/version_control_assignment.git (push)
    origin	git@github.com:vasilisa-iatckova/version_control_assignment.git (fetch)
    origin	git@github.com:vasilisa-iatckova/version_control_assignment.git (push)
    upstream	https://github.com/WCM-datascibasics/version_control_assignment (fetch)
    upstream	https://github.com/WCM-datascibasics/version_control_assignment (push)
    > Push failed because I don't have permissions to push to upstream. I can create a pull request for review though; that's the benefit of adding an upstream remote.
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
      > swapped 2 weeks
       > My changes are not creating uncommitted files; instead, they are saved or queued up elsewhere (on stack) for returning to them at a later time. My working tree is clean.
       > I see the stashed changes as work in progress; that's the top line of the output.
       > Stashing is useful when I'm not yet ready to commit my changes (I'm in a draft mode and have not finished but need to work on another file in the same repo before I'm done making changes). Dropping is useful when I'm done working with a stash and don't want to commit. Popping is useful when I'm done working with a stash and do want to commit.
    > I accidentally did this on main + I don't think I removed it completely. I could have redone the whole thing but I will not.
    [alias]
        graph = git log --all --graph --decorate --oneline
    .DS_Store
    .DS_Store?
    Thumbs.db