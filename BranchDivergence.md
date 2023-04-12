# Branch Divergence Error :white_check_mark:
:sparkles: :sparkles: :sparkles: Give me a star to motivate me :sparkles: :sparkles: :sparkles:

## Content
* [Problem Statement](#problem-statement)
* [The three solution](#the-three-solution)
* [What is fast-forward?](#what-is-fast-forward)
* [What's next after rebase](#whats-next-after-rebase)
* [Suggestions](#suggestions)

## Problem Statement

- When we do the `git push`, we often face the following error:

```sh
>>> git push
To github.com:lalalam123/Git-Best-Practices
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'github.com:lalalam123/Git-Best-Practices'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g. 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
- Then, we run the `git pull`, to fetch and merge(fast-forward) the branch, but ...

```sh
>>> git pull
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint: 
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint: 
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
fatal: Need to specify how to reconcile divergent branches.
```

## The three solution

The above error message indicates that the branch you are trying to pull from has diverged from your local branch, and Git doesn't know how to reconcile the differences automatically.

To fix this issue, you need to specify how Git should handle the merge of the divergent branches. The error message suggests three possible options:

- Merge: This option will merge the changes from the remote branch into your local branch, creating a merge commit to reconcile the differences.

    You can use this option by running the following command:

    ```sh
    git config pull.rebase false
    ```

- Rebase: This option will reapply your local changes on top of the remote branch, creating **a linear history** without merge commits.

    You can use this option by running the following command:

    ```sh
    git config pull.rebase true
    ```

- Fast-forward only: This option will only perform the pull operation if it can be done as a fast-forward, which means that your local branch has no new commits that are not in the remote branch.

    You can use this option by running the following command:

    ```sh
    git config pull.ff only
    ````

Choose the option that is appropriate for your situation and run the corresponding command before running git pull again. If you want to set the option as the default behavior for all repositories, add the --global flag to the git config command.

## What is fast-forward?

- Git Pull & Git Fetch & Git Merge

    First, we know that `git pull` is equal to 'git fetch' + `git merge`, in which `git pull` do a fast-forward merge.

    A fast-forward merge is just moving the pointer forward to the latest commit to form a linear merge.

    The following is a good example, let's say we are at commit '1-...' in the main branch. When we fast-forward, the main branch pointer just move to the latest one '3-...' to complete the merge.
    
    ```mermaid
    gitGraph
    commit
    commit
    branch develop
    checkout develop
    commit
    commit
    checkout main
    ```

- However, there're some limitations, for example like the following, the main branch has a totally different commit '4-...' that does not occur in develop branch. Fast-forward will then look a bit weird, since we have no idea which branch should we go, hence we will choose the alternatives to handle such case.

    ```mermaid
    gitGraph
    commit
    commit
    branch develop
    checkout develop
    commit
    commit
    checkout main
    commit
    ```

## What's next after rebase
- Since the default value of pull.rebase is neither True or False, so the first time you do the git merge, git will ask for your preference.

- You can also view your current settings by

    ```
    git config --get pull.rebase
    ```
- Or, also reset to default, to determine what to do next time depends on the situation

    ```
    git config --unset pull.rebase
    ```

## Suggestions

Personally, I would prefer Rebase for personal projects and Merge for co-operating projects.

* [Back to Top](#branch-divergence-error)

