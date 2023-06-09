# Guidelines for commit message

## Contents:
* [Common Commit Message](#common-commit-message)
* [Keywords](#commit-message-keywords)
* [Emoji](#commit-message-emoji)
* [Rules & Guidelines](#commit-message-rules)
* [Commands](#commit-commands)
* [Full Commit Msg Example](#example-full-commit-message)
* [Git Issue Type](#git-issue-type)
* [Semantic Versioning](#semantic-versioning)
* [Reference](#reference)

## Common Commit Message
- :tada: Initial commit
- :books: Document commit initial message guidelines
- :zap: Start documentation project
- :sparkles: Add feature for searching content


## Commit Message Keywords

First Word | Meaning | Example
--- | -- | --
Add | Create a capability e.g. feature, test, dependency. | Add feature for a user to like a post
Bump | Increase the version of something e.g. dependency. | Bump dependency library to current version
Cut | Remove a capability e.g. feature, test, dependency. | Drop feature for a user to like a post
Document | Refactor of documentation, e.g. help files.    | Document community guidelines for post content
Fix | Fix an issue e.g. bug, typo, accident, misstatement.| Fix association between a user and a post
Make | Change the build process, or tooling, or infra.    | Make build process use caches for speed
Optimize | Refactor of performance, e.g. speed up code.   | Optimize search speed for a user to see posts
Remove | Remove deprecated codes | Remove deprecated methods
Release | Release a version | Release version 1.0.0
Refactor | A code change that MUST be just a refactoring. | Refactor user model to new language syntax 
Reformat | Refactor of formatting, e.g. omit whitespace.  | Reformate home page text to use more whitespace
Revise | A change that MUST be just a revising patch e.g. a change, an alteration, a correction, etc. | Revise link to update it to the new URL
Reword | A change that MUST be just a wording patch, e.g. change a comment, label, doc, etc. | Reword home page text to be more welcoming
Redraw | A change that MUST be just a drawing patch, e.g. change a graphic, image, icon, etc. | Redraw diagram of how our web app works
Rearrange | A change that MUST be just an arranging patch, e.g. change layout. | Rearrange buttons so OK is on the lower right
Start | Begin doing something; e.g. create a feature flag.| Start feature flag for a user to like a post
Stop | End doing something; e.g. remove a feature flag.   | End feature flag for a user to like a post
Update | Update some ongoing code | Update getting started documentation

## Commit Message Emoji

|   Commit type              | Emoji                                         |
|:---------------------------|:----------------------------------------------|
| Initial commit             | :tada: `:tada:`                               |
| Version tag                | :bookmark: `:bookmark:`                       |
| New feature                | :sparkles: `:sparkles:`                       |
| Bugfix                     | :bug: `:bug:`                                 |
| Metadata                   | :card_index: `:card_index:`                   |
| Documentation              | :books: `:books:`                             |
| Documenting source code    | :bulb: `:bulb:`                               |
| Performance                | :racehorse: `:racehorse:`                     |
| Cosmetic                   | :lipstick: `:lipstick:`                       |
| Tests                      | :rotating_light: `:rotating_light:`           |
| Adding a test              | :white_check_mark: `:white_check_mark:`       |
| Make a test pass           | :heavy_check_mark: `:heavy_check_mark:`       |
| General update             | :zap: `:zap:`                                 |
| Improve format/structure   | :art: `:art:`                                 |
| Refactor code              | :hammer: `:hammer:`                           |
| Removing code/files        | :fire: `:fire:`                               |
| Continuous Integration     | :green_heart: `:green_heart:`                 |
| Security                   | :lock: `:lock:`                               |
| Upgrading dependencies     | :arrow_up: `:arrow_up:`                       |
| Downgrading dependencies   | :arrow_down: `:arrow_down:`                   |
| Lint                       | :shirt: `:shirt:`                             |
| Translation                | :alien: `:alien:`                             |
| Text                       | :pencil: `:pencil:`                           |
| Critical hotfix            | :ambulance: `:ambulance:`                     |
| Deploying stuff            | :rocket: `:rocket:`                           |
| Fixing on MacOS            | :apple: `:apple:`                             |
| Fixing on Linux            | :penguin: `:penguin:`                         |
| Fixing on Windows          | :checkered_flag: `:checkered_flag:`           |
| Work in progress           | :construction:  `:construction:`              |
| Adding CI build system     | :construction_worker: `:construction_worker:` |
| Analytics or tracking code | :chart_with_upwards_trend: `:chart_with_upwards_trend:` |
| Removing a dependency      | :heavy_minus_sign: `:heavy_minus_sign:`       |
| Adding a dependency        | :heavy_plus_sign: `:heavy_plus_sign:`         |
| Docker                     | :whale: `:whale:`                             |
| Configuration files        | :wrench: `:wrench:`                           |
| Package.json in JS         | :package: `:package:`                         |
| Merging branches           | :twisted_rightwards_arrows: `:twisted_rightwards_arrows:` |
| Bad code / need improv.    | :hankey: `:hankey:`                           |
| Reverting changes          | :rewind: `:rewind:`                           |
| Breaking changes           | :boom: `:boom:`                               |
| Code review changes        | :ok_hand: `:ok_hand:`                         |
| Accessibility              | :wheelchair: `:wheelchair:`                   |
| Move/rename repository     | :truck: `:truck:`                             |
| Other                      | [Be creative](http://www.emoji-cheat-sheet.com/)  |

## Commit Message Rules

- Commit messages must have a subject line
- Commit messages may also have body copy which must be separated by a blank line.
- The subject line must not exceed 50 characters
- The subject line should be Capitalized and must not end in a period (!,?,...)
- The subject line must be written in *imperative* mood (*Fix*, not *Fixed* / *Fixes* etc.)
- The body copy must be wrapped at 72 columns
- The body copy must only contain explanations as to *what* and *why*, never *how*. The latter belongs in documentation and implementation.

## Commit Commands

- To perform a *simple* commit, a single command if sufficient:

```sh
$ git commit -m "Fix my subject line style"
```

- If you need to write body copy, issue `git commit`. 
- Git will now open your default text editor. 
- To set a custom editor, use `git config --global core.editor nano` (in this example, nano is the editor).
- Here's an example of a subject and body commit message:

```txt
Derezz the master control program

MCP turned out to be evil and had become intent on world domination.
This commit throws Tron's disc into MCP (causing its deresolution)
and turns it back into a chess game.
```

- This makes browsing the `git log` easier:

```txt
$ git log
commit 42e769bdf4894310333942ffc5a15151222a87be
Author: Kevin Flynn <kevin@flynnsarcade.com>
Date:   Fri Jan 01 00:00:00 1982 -0200

 Derezz the master control program

 MCP turned out to be evil and had become intent on world domination.
 This commit throws Tron's disc into MCP (causing its deresolution)
 and turns it back into a chess game.
```

- You can view a shorter log, by restricting the output to the subject lines:

```txt
$ git log --oneline
42e769 Derezz the master control program
```

- This provied an easy way to get a quick overview by means of reading the shortlog:

```txt
$ git shortlog
Kevin Flynn (1):
      Derezz the master control program

Alan Bradley (1):
      Introduce security program "Tron"

Ed Dillinger (3):
      Rename chess program to "MCP"
      Modify chess program
      Upgrade chess program

Walter Gibbs (1):
      Introduce protoype chess program
```

## Example Full Commit Message

This is an example of a complete commit message that adheres to this standard. Parts of this are optional, so read on.

```txt
Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequences of this
change? Here's the place to explain them.

Further paragraphs come after blank lines.

 - Bullet points are okay, too

 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here

If you use an issue tracker, put references to them at the bottom,
like this:

Resolves: #123
See also: #456, #789
```

## Use the Body to Explain the Background and Reasoning, not the Implementation

*Especially* if the diff is rather large or extremely clustered, you can save all fellow developers some time by explaining *why* you did *what*.

Here's a perfect example:

```txt
commit eb0b56b19017ab5c16c745e6da39c53126924ed6
Author: Pieter Wuille <pieter.wuille@gmail.com>
Date:   Fri Aug 1 22:57:55 2014 +0200

   Simplify serialize.h's exception handling

   Remove the 'state' and 'exceptmask' from serialize.h's stream
   implementations, as well as related methods.

   As exceptmask always included 'failbit', and setstate was always
   called with bits = failbit, all it did was immediately raise an
   exception. Get rid of those variables, and replace the setstate
   with direct exception throwing (which also removes some dead
   code).

   As a result, good() is never reached after a failure (there are
   only 2 calls, one of which is in tests), and can just be replaced
   by !eof().

   fail(), clear(n) and exceptions() are just never called. Delete
   them.
```

This is *way* easier to parse than the [corresponding diff](https://github.com/bitcoin/bitcoin/commit/eb0b56b19017ab5c16c745e6da39c53126924ed6.patch).

## Git Issue Type
- feat: A new feature or functionality has been added to the software.
- fix: A bug or issue has been fixed.
- docs: Documentation has been updated or improved.
- refactor: Code has been refactored or reorganized without changing its behavior.
- test: Tests have been added or updated.
- style: Code style or formatting has been updated or improved.
- chore: Miscellaneous changes or updates that do not fit into other categories.
- perf: Performance improvements have been made to the software.
- build: Changes related to the build or deployment process.
- revert: A previous commit has been reverted.

## Semantic Versioning

<img width="300px" style="float: right;" src="https://onlinecommunityhub.nl/images/blog/2020/semver.png">

We use semantic versioning for many of our projects:

  * **Add**, **Start**: Increment SemVer MINOR version when there is a new capability.

  * **Drop**, **Stop**: Increment SemVer MAJOR version when there is an incompatibility.

  * **Fix**, **Bump**, **Make**, **Optimize**, **Document**: Increment SemVer PATCH version.

  * **Refactor**, **Reformat**, **Rearrange**, **Redraw**, **Reword**: Increment SemVer PATCH version.

## Reference
> - More about commit message body https://github.com/joelparkerhenderson/git_commit_message
> - More about commit message emoji https://github.com/dannyfritz/commit-message-emoji
> - https://chris.beams.io/posts/git-commit/
> - https://gist.github.com/tonibardina
