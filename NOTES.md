notes on how I set this up. ([.] indicate footnotes)

setup
-----
- remotely:
  * `mkdir <top-level-dir>; cd <top-level-dir>`
  * `git init; git annex init "<name>"`
  * set numcopies to 2 [1]:  
    `echo "* annex.numcopies=2" >> .gitattributes`  
    `git add .gitattributes; git commit -m "add .gitattributes"`
  * to let people download over http (`git update-server-info`) [2]:  
    `mv .git/hooks/post-update.sample .git/hooks/post-update`
  * to automatically sync the directory structure and get all symlinks,  
    copy `annex-content` from this repo to `.git/hooks/` and make it executable [3]
- locally:
  * clone repo: `git clone linode:<path-to-top-level-dir>/.git` [4]
  * fill cloned (empty) dir with files to be annex'ed
  * add and commit files: `git annex add .; git commit -m "initial annex add"`
  * sync repos: `git annex sync`
  * `git annex copy --auto --to origin` to start copying all files acc. to numcopies

daily work on local machine
---------------------------
- `git annex add <filename(s)>; git commit -m "<message"`
- adding and committing files makes them read-only, use:  
  `git annex unlock <filename>` to modify/update/replace file
- `git commit` to keep changes, `git annex lock` to discard changes after unlock.
- `git annex sync` [5]  
- copy files: `git annex copy --auto --to origin`

footnotes
---------
1. [numcopies](http://git-annex.branchable.com/walkthrough/backups/)
2. [web site](http://git-annex.branchable.com/tips/setup_a_public_repository_on_a_web_site/)
3. [annex-content](http://git-annex.branchable.com/git-annex-shell/)
4. remark: `linode` is set up as an entry in `.ssh/config` with appropriate
   Hostname, User, and IdentityFile  
   (see [here](http://cgit.the-huck.com/cgit.cgi/?p=about))
5. [sync](http://git-annex.branchable.com/sync/)

author
------
Patrick Huck, 06-30-2013, [github](https://github.com/tschaume?tab=repositories)
