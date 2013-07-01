The directories here are maintained using [git
annex](http://git-annex.branchable.com/). Feel free to either use the directory
index powered by [h5ai](http://larsjung.de/h5ai/) or clone it via

    git clone http://downloads.the-huck.com/<top-level-dir>/.git/

Run `git annex get <filename>` to retrieve a specific file or `git annex get .`
for all files in the directory.

List of h5ai features
---------------------

* switch icon or list view in upper right corner (top bar)
* hover to left screen border for a tree view for better navigation
* breadcrumbs in top bar a clickable
* search filter in top bar
  - searches ignorecase
  - whitespace-separated words are OR'ed
  - search terms prefix'ed with re: are interpreted as regex.
* images previewed on click. shortcuts: up, down, F(ullscreen), ESC
* select files by click and drag over icons/filenames.
  - button to download a zip archive will appear in top bar
* use ctrl key to unselect/extend selection
* text files previewed, too
  - includes syntax highlighting and markdown rendering.
* QR codes shown for convenience

Setup
-----
see NOTES.md

Author
------
Patrick Huck, 06-30-2013
