If I have a package (honestly just a folder of code) that I want to version
control, these are instructions to add it to github for the first time. 

We'll start with some code, In my case, I have a very messy folder where I've
been working through some of the ORKID data reduction. It includes code I've
written, scripts from other people I've been using, some data files, and some
plots. It looks like this: 

[ls-from-orkid](images/ls-from-orkid.png)

Since I know my intention is to make this into a respositry on GitHub I will
start by making it an empty repository on the GitHub side. Navigate to the
repositories tab and click new. (You can do this from
your own user or from the LAO account.) 

[making-a-repo](images/making-a-repo.png)

Choose private or public and make sure you *don't* initialize it with a README. 

[repo-options](images/repo-options.png)

You'll notice that now this repository has instructions on how to connect your
local code. What follows is a slightly more detailed version of those
instructions. 

Back on my end where the code is, it's time to turn this folder into a repository. 
I'll start by intializing it: 

>> git init 

Once I've done that, typing ``git status`` will tell me that I now have a git
repository with many untracked files, some I do want, most I don't... It's
generally not advised to version control things like plots other than for
important demos or documentation, things like ``__pycache__``, ``.swp`` files,
and other misc files your computer might make you, and *especially* not large
data files. Large data files will often clog up your repository and are a pain
to remove from your commit history. 

[status-after-init](images/status-after-init.png)

The simple solution is to make a
`.gitignore`, a little set of instructions of what not to commit. I've included
the `.gitignore` in this folder as an example. In this ``.gitignore`` I've included 3 scripts that I'm
using that I did not write, so I don't feel it's appropriate to version control
them as if I did. 

>> git add .gitignore 

Finally, I add the files of note (you can do this by naming each file or with
wildcards) 

>> git add *.py* 

In my case, because I included some ``.py`` files in my ``.gitnore`` git is
kindly making sure I'm okay ignoring these. 

[status-after-add](images/status-after-add.png)

Now I'm just following the instructions that are up on my blank repository (note
that you don't need the echo/add step, that's just creating blank content) to
make an initial commit, rename the main branch, connect it to GitHub by adding
an origin, and finally pushing the code to GitHub. 

```python
git commit -m "Some informative message about your first commit."
git branch -M main 
git remote add origin git@github.com:user/name-of-repo.git 
git push -u origin main
```

Now when I go to that same blank repository I can see these python files, as
well as the ``.gitignore``. 

[new-repo-who-dis](images/new-content-in-repo.png)
