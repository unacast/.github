↖️ 🍔 for Table of Contents

# Using Git

The following is a set of tips for using git. These are mostly tips, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request. 

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

Recommended way to mitigate this is to use [Github Flow](https://www.w3schools.com/git/git_github_flow.asp) or [Trunk based development](https://trunkbaseddevelopment.com/). Trunk based development really fixes this, but can be hard to implement for some teams. 
Focus on pair programming, [feature toggle](https://en.wikipedia.org/wiki/Feature_toggle) and [expand and contract(parallel change)](https://martinfowler.com/bliki/ParallelChange.html) together with good commit messages can help you merge into trunk(main) often, regardless of using trunk based or Github flow.


## 3. Commit early and often

Git only takes full responsibility for your data when you commit. If you fail to commit and then do something poorly thought out, you can run into trouble. Additionally, having periodic checkpoints means that you can understand how you broke something.

## 4. Use git pull --rebase

This will keep your history more linear, and you will reduce those pesty "merge remote tracking ..."


## Inspirations used in this document

[Seth Robertson Git Best Practices]([https://deepsource.io/blog/git-best-practices/](https://sethrobertson.github.io/GitBestPractices/))
[Google Cloud DevOps tech: Trunk-based development](https://cloud.google.com/architecture/devops/devops-tech-trunk-based-development)
