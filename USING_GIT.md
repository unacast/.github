↖️ 🍔 for Table of Contents

# Using Git

The following is a set of tips for using git. These are mostly tips, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request. 

Be sure to check out the [Git Tutorial on W3 School](https://www.w3schools.com/git/). There is almost bound to be something to learn there, even if you feel 1337 to git.

## 1. Write good commit messages

Read up on https://cbea.ms/git-commit/, tldr;

1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line
4. Do not end the subject line with a period
5. **Use the imperative mood in the subject line**
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how

## 2. Avoid long lived branches

From [Thoughtworks radar on Gitflow](https://www.thoughtworks.com/radar/techniques/long-lived-branches-with-gitflow)

> Essentially, long-lived branches are the opposite of continuously integrating all changes to the source code, and in our experience continuous integration is the better approach for most kinds of software development.

How old is a long lived branch? According to [trunkbaseddevelopment.com](https://trunkbaseddevelopment.com/short-lived-feature-branches/):

> One key rule is the length of life of the branch before it gets merged and deleted. Simply put, the branch should only last a couple of days. Any longer than two days, and there is a risk of the branch becoming a long-lived feature branch (the antithesis of trunk-based development).


Although, if you like merge conflicts and [cherry-pick](https://git-scm.com/docs/git-cherry-pick), disregard the above.

Recommended way to mitigate this is to use [Github Flow](https://www.w3schools.com/git/git_github_flow.asp) or [Trunk based development](https://trunkbaseddevelopment.com/). Trunk based development really fixes this, but can be hard to implement for some teams. Good patterns to help keep your branches short lived:

- Focus on pair programming. Knowledge is shared, and you don't have to asynchronously wait for your PR to be accepted (and context switch).
- [Feature toggle](https://en.wikipedia.org/wiki/Feature_toggle). A great way to share your code with others, but not disrupt the production running code.
- [Expand and contract(parallel change)](https://martinfowler.com/bliki/ParallelChange.html) is another great way of keeping the status quo of production and at the same time adding new features


## 3. Commit early and often

Git only takes full responsibility for your data when you commit. If you fail to commit and then do something poorly thought out, you can run into trouble. Additionally, having periodic checkpoints means that you can understand how you broke something.

## 4. Use git pull --rebase

This will keep your history more linear, and you will reduce those pesty "merge remote tracking ...".

On Github, you can keep your branch up to date with master with the Update Branch button. If you are good at keeping your branch short lived, you could also Update with rebase.

## 5. Give your git config some ❤️

Your personal `~/.gitconfig` file can certainly help your daily `git` commands a lot. You can draw inspiration from various smart people out there in [Github :heart dotfiles](https://dotfiles.github.io/), or maybe someone you know closely has some niceties laying around on their public Github account. All the same, here are some config that you might find useful

```gitconfig
[user]
        # This one is essential and you should always set this!
        name = My Fancy Name
        email = my-fancy@email.com
[credential]
        # In case you are using a Mac
        helper = osxkeychain
[alias]
        # Saves keyboard for some extra typings
        co = checkout
        br = branch
        glog = log --graph --pretty=format:'%Cred%h%Creset %an: %s - %Creset %C(yellow)%d%Creset %Cgreen(%cr)%Creset' --abbrev-commit --date=relative
```

## Inspirations/references used in this document

- [github git cheat sheet](https://training.github.com/downloads/github-git-cheat-sheet/)
- [Seth Robertson Git Best Practices](https://deepsource.io/blog/git-best-practices/)
- [Google Cloud DevOps tech: Trunk-based development](https://cloud.google.com/architecture/devops/devops-tech-trunk-based-development)
