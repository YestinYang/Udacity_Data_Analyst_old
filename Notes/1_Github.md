# Udacity Data Analyst Nano Degree

## Part 1: GitHub

### Importance from Recruiter Perspective 

- Clear personal and repo information
- Nice activity heat map -->  passion on coding
- Informative README.md file of repo
  - Important for you / coworkers / end users / recruiter
  - Bad documentation will stop others using your code
  - **Principle of README**: communicate essential information for end user without assumption about what they already knows
    - what steps need to be taken?
    - what should the user already have installed or configured?
    - what might they have a hard time understanding right away?
- Formatted commit message

  - easier to maintain your code
  - well communication while contributing to  open source project
  - [Udacity Git Commit Style](https://udacity.github.io/git-styleguide/)
- Contributing to open source project -->  you are a collaborator
  - comment on pull request --> how interact with other engineer
  - answer issues especially to the new guys of the community
  - How to start?
    - start from update documentation like README with pull request
    - following the steps of README and try to clarify based on the problems you have

### Github: Commands

- Create repo
  - `git init` initial a folder as a new repo, tracking all modification under it
    - `.git/config` configure only for this repo
  - `git clone <path> [<new dir name>]`
    - cannot create nested repo, so do check your `pwd`
  - `git status`
- Check commit
  - `git log` for commit history
    - `git log --oneline` show only 7 characters of SHA and commit
    - `git log --stat` show files changed for each commit
    - `git log --patch` or `git log -p` show the detailed changes of each commit
    - `git log -w` ignore the change of blank when showing patch info
    - `git log <7 character of SHA>` start from particular commit
  - `git show` show commit with knowing SHA
    - share all arguments of `git log`
- Create commit
  - `git add` 
    - `git add .` to stage all folders and files
    - `git rm --cached <file>` to unstage
  - `git commit` open default editor
    - `git commit -m "commit message"` for short commit with only message
    - Rules of writing commits
      - Message: explain the role of submission
        - Good: "Update the footer to copyright information"
        - no why / no how / no and
      - Description: skip a line after message then start
  - `git diff` show changes of unstaged / uncommited files
  - `.gitignore` file under repo to ignore specified files

## Part 1 Project: Stroop Effect

### T-score vs Z-score

![t or Z](http://www.statisticshowto.com/wp-content/uploads/2013/08/t-score-vs.-z-score.png)

- Z-distribution is exact normal distribution
- t-distribution is close to normal while $n\ge30$  [Animation](http://rpsychologist.com/d3/tdist/)
- Assumption of t-test [Reference](http://www.csic.cornell.edu/Elrod/t-test/t-test-assumptions.html)
  - Bivariate independent variable
  - Each observation of the dependent variable is independent of the other observations
    - Exception: for the paired t-test, we only require that the pair-differences (Ai - Bi) be independent from each other (across i)
  - **Dependent variable has a normal distribution**

### Understanding of p-value

![](https://udacity-reviews-uploads.s3.amazonaws.com/_attachments/60529/1492190110/Screen_Shot_2017-04-15_at_1.14.44_AM.png)