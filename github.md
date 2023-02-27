# Github Standards

## Workflow
``` bash

# New feature
git checkout develop
git pull
git checkout -b feature/{feature-description}
git add .
# Use conventional commits
# TODO: Make a link here for the conventional commits
git commit "feat: Fixes/Adds/etc (issue #)"

# Rebase daily
git checkout develop
git pull
git checkout feature/{feature-description}
git rebase develop

# Feature is done
# TODO: Make pull request

git checkout develop
git merge feature/{feature-description}

# Create a release with feature(s)
git checkout develop
git checkout -b release/v1.1.1 - {version description}
./prepare-release.sh  # project dependent
git add -A
git commit -m "release: {version} - {version description}"
git tag '{version}'

# Merge release into master
git checkout master
git merge release/{version} - {version description}

# Merge master into develop
git checkout develop
git merge master

```
Create a release on github using the tag and pull request to auto-populate.


__Daily:__
git checkout feature/feature-description


TODO: Organize and incorporate the following:
https://github.com/dbt-labs/corp/blob/main/git-guide.md


## Commits
https://cbea.ms/git-commit/
https://blog.mocoso.co.uk/talks/2015/01/12/telling-stories-through-your-commits/

## Pull Requests
https://www.pullrequest.com/blog/why-your-team-isnt-reviewing-pull-requests/

https://mtlynch.io/human-code-reviews-1/

- Try to review and complete a pull request before there is a merge to `develop`

!!! quote
    PRs should be reviewed within one business day and if they can not you should inform your coworkers to possibly ask someone else (if you are in fact that busy).
    If you notice the PR and can not get to it right away, you should also inform your coworkers so that they can adjust their expectations.
    PRs should be treated as a high priority and reviewed as soon as possible. Think of them as blocking work. Without the review, the person can not continue with their work and might be blocked. This helps to set a culture of fast turnaround on PRs. The last point also helps to reinforce smaller PRs. If the review window is quick and PRs are smaller, than iteration will be much quicker and efficiency will go up.
    

## Merging
- Merging to shared branches should always be completed with a notification
- Rebase with each new merge
- This means merges should be as clean and as small as necessary to encompass the feature

