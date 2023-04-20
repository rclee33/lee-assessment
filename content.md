## Overview

As part of your interview, you'll complete a technical writing and editing project. You can expect this project to take 1-2 hours.

Before getting started, please review HashiCorp's [writing style guide](../styling-guide-snippet.md).

## Instructions

For this assignment, imagine you are editing a colleague's work. Using the following content snippet ([Content](#content)), edit the text for clarity. You are welcome to make any changes to improve the text, such as clarifying meaning, improving the explanations of concepts, or providing best practices. You may also include any questions about the content's meaning. The result should be a document that you, as a technical writer, are comfortable sharing with end users.

You'll share your edits using GitHub. Create a new GitHub repository with the ([Content](#content)) snippet as the first commit. Make a branch and open a Pull Request (PR) for your edits. Once you're finished with your edits, send the PR link to the HashiCorp recruiter.

**Note:** Please do not fork the original assignment repository. Instead, make a copy of all files, create your own repository, and submit a Pull Request for your own project. Do not merge the Pull Request.

## Guidelines

As you work on your assignment, please keep the following in mind:

- Construct your PR to teach the author how to make atomic commits.
- Write your commit messages to show your rationale for edits.
- Craft your commits, commit messages, and PR description as if you were collaborating with a team on an actual PR.
- Edit the files on your local machine and push with the `git` command or a desktop Git application rather than editing directly on the GitHub website.

Edit the text so that it is easy to read:
- Correct errors.
- Use the active voice and present tense.
- Address the reader as "you", not "we".
- Phrase statements positively rather than negatively.
- Use simple, plain language. 
- Avoid euphemisms.
- Structure the text so it has a logical flow. 

---

## Content

### What is the difference between `git push`, `git pull`, and `git fetch`?

- `git push` - sent changes from a local branch to a remote repo
- `git fetch` - get changes from a remote repo into your tracking branch
- `git pull` - will get changes from a remote branch into your tracking branch and merge them into a local branch

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since under the hood `git pull` does two things. `git push` takes our current branch, and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, our changes are taken from our branch and pushed to the remote branch. This is how code is shared with a remote repository, you can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with git pull or git fetch and git merge.`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.
