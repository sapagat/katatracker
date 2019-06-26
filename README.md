# KataTracker

Increments matter.

KataTracker commits each step you perform in a kata. Each time you run the tests the status, output and code are saved. This way, when you want to discuss your kata experience you can share the decisions and trade-offs made in each step.

## Setup

### Dependencies

- `git`: https://git-scm.com/downloads
- `tig`: Very light terminal interface for git. https://jonas.github.io/tig/INSTALL.html

### Install katatracker

```
sudo curl -sL https://raw.githubusercontent.com/sapagat/katatracker/master/katatracker -o /usr/local/bin/katatracker
sudo chmod +x /usr/local/bin/katatracker
```

## Usage

### Test & Commit (tc)

This command commits automatically each time you run the test and also includes the test output so that you can share it later.

```
katatracker tc <your test command>
```

For example:

```
katatracker tc rspec
```

Notice that you should run this command inside a git project. This means that at some point you should have done `git init`.

### Present (present)

This command makes usage of Tig, a terminal interface that makes it easy to navigate through `git`.

```
katatracker present
```

Once opened, these are the most useful keys:

- `up` & `down` arrows to navigate through commits
- `enter` to select a commit
- `ctrl + u` & `ctrl + d` to scroll up and down in the code (you will need to select a commit first)
- `q` will close view(s)


## Development

When developing new features for katatracker, you can check if it is working as expected making use of the `checks`.

- `green_test`: simulates a green test with exit code 0.
- `red_test`: simulates a red test with exit code 1.

Example:

```
./katatracker tc checks/green_test
./katatracker tc checks/red_test
```
