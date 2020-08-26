# Repository for [differentialprivacy.org](https://differentialprivacy.org/)

This github repository is the "back end" for [differentialprivacy.org](https://differentialprivacy.org/), which is hosted via [github pages](https://pages.github.com/). Please see [the website's About page](https://differentialprivacy.org/about/) for more details.

## Contribute to [differentialprivacy.org](https://differentialprivacy.org/)

This website is meant to represent the differential privacy research community. 
Thus we welcome contributions from the community. 
We aim to host a variety of content, from simple announcements to detailed blog posts.

**The first step to contributing is to get in contact with the site administrators.** 
You can email [admin@differentialprivacy.org](mailto:admin@differentialprivacy.org) and let us know what you would like to add to the website.
The site administrators will help you figure out how to create content.

Below are technical instructions for creating and adding content to the website.

## How to put content on the website

Posts must be written in [markdown](https://www.markdownguide.org/basic-syntax/). (Although some HTML can be included if necessary.)

Math is rendered using [MathJax](https://www.mathjax.org/). Inline math should use be written as `\\\(e^{i\pi}+1=0\\\)` (in LaTeX this would simply be `\(e^{i\pi}+1=0\)` or `$e^{i\pi}+1=0$`) and displayed equations should be written as `\\\[\sum_{n=0}^\infty \frac{x^n}{n!} = e^x\\\]` (in LaTeX this would be `\[...\]` or `$$...$$`). The reason for the excessive backslashes is to escape special characters; markdown renders `\\` as `\` and `\(` as `(` etc. You can convert LaTeX to markdown by simply doing find and replace. Note that you must use "plain" LaTeX; your macros can't be used.

Look at the [Welcome Post](https://github.com/differentialprivacy/differentialprivacy/blob/master/_posts/2020-07-16-welcome.md) or any other post as an example for the format. Note that the administrators will also add your details to the [contributors list](https://github.com/differentialprivacy/differentialprivacy/blob/master/_data/contributors.yml)

### The easy way: email the editors!

- Email your markdown file to
  [admin@differentialprivacy.org](mailto:admin@differentialprivacy.org).


### The GitHub way: create a pull request
- First *Fork* our repository. On [the repo's github page](https://github.com/differentialprivacy/differentialprivacy), click the Fork button on the
  top-right corner. This creates a new copy of the repo under your
  GitHub user account under the url
  ```
  https://github.com/<YourUserName>/differentialprivacy
  ```
  You can skip this step if you have already done so previously.

- Next, clone the repo by running the command:
  ```
  # Clone with ssh. You can also clone with https.
  git clone git@github.com:<YourUserName>/differentialprivacy.git
  cd differentialprivacy/
  # Add the remote (original repo that you forked) and call it “upstream”
  git remote add upstream https://github.com/differentialprivacy/differentialprivacy.git 
  ```

- If you have already forked the repo before, you should skip this. But you may want to update the forked repo with `git rebase`:
  ```
  # Fetch all branches of remote upstream
  git fetch upstream
  # Rewrite your master with upstream’s master using git rebase.
  git rebase upstream/master
  git pull upstream master
  # Push your updates to your own master. You may need to force the push with “--force”.
  git push origin master --force
  ```

- Now you can add your post or otherwise edit the content on your system.
  ```
  cd _posts/ # go to the post directory
  cp 2020-07-16-welcome.md YYYY-MM-DD-My-Post-Name.md #make a copy of the Welcome post
  open YYYY-MM-DD-My-Post-Name.md #open it in your favourite editor and make changes
  ```
  
- Next you must add your post to your github repository.
  ```
  git add YYYY-MM-DD-My-Post-Name.md
  git commit -m "Adding my post"
  git push -u origin master
  ```

- Go back to `https://github.com/<YourUserName>/differentialprivacy/` on github and click `Pull request`. You can leave some comments and then click `Create pull request`.
  
- The site administrators will then review your edits and merge them into the live version of the website. 

## Preview your content

Before making your content live on the website, please test it out on your computer.

- You will need to install [Jekyll](https://jekyllrb.com/). If you have the relevant [requirements](https://jekyllrb.com/docs/installation/#requirements), you can simply install with the command:
```
 gem install bundler jekyll
```

- To preview the website locally, simply navigate to the copy of the repository on your computer, run `jekyll serve`, and open `http://localhost:4000` in your browser:
```
#first make a copy of the website repository https://github.com/differentialprivacy/differentialprivacy
cd differentialprivacy/ #go to the repo directory
jekyll serve #start the local server
open http://localhost:4000 #view the website in your web browser
```
