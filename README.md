# KataTracker

Increments matter.

KataTracker commits each step you perform in a kata. Each time you run the tests the status, output and code are saved. This way, when you want to discuss your kata experience you can share the decisions and trade-offs made in each step.

## Setup

### Dependencies

- `git`: version control system. https://git-scm.com
  - Ubuntu: `sudo apt install git`
  - MacOS: `brew install git`

### Install katatracker

```
sudo curl -sL https://raw.githubusercontent.com/sapagat/katatracker/master/katatracker -o /usr/local/bin/katatracker
sudo chmod +x /usr/local/bin/katatracker
```

## Usage

### Initialize git

KataTracker makes use of Git in order to track the steps you take during the Kata. You will need to have an initialized git project on your working directory.

You can initialize it as follows:

```
cd <kata-directory>
git init
```

### Test & Commit

This command runs the tests and automatically commits each time you execute it. The commits  include both the code changes and the test output so that you can share it later.

```
katatracker tc <your test command>
```

For example:

```
katatracker tc rspec
```

### Watch

This does the same as `tc` but it will run it for you when a file has changed.

```
katatracker watch <test-command>
```

## Development

When developing new features for katatracker, you can check if it is working as expected making use of the `checks`.

- `green_test`: simulates a green test with exit code 0.
- `red_test`: simulates a red test with exit code 1.

Example:

```
./katatracker tc checks/green_test
./katatracker tc checks/red_test
```
