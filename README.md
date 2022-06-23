bumpme is a short utility that will help developer maintain clear versioning for their packages and projects.
The package is fairly lightweight. It works by parsing the git commit message and extracting the command and size of the commit.

# Getting started

Install bumpme with npm by running: `npm install @food7go/bumpme`.
That's it! You are ready to use bumpme in your project.

# How to use it

Triggering bumpme works by running `bumpme` in your terminal.
The `bumpme` command takes several arguments that you can check by running `bumpme -h`.
`bumpme` will by default, if no arguments are passed, try to read your latest git commit message versioning insructions. The script looks for something formatted like this: `[[instruction:increment]]`. A few use case would be:

- `[[patch:1]]`: would turn 1.0.0 into 1.0.1
- `[[patch:2]]`: would turn 1.0.1 into 1.0.3
- `[[minor:1]]`: would turn 1.4.9 into 1.5.0
- `[[major:1]]`: would turn 1.2.5 into 2.0.0

If you do not wish to run bumpme with automated git message instructions, you could pass some arguments as well.
For most use cases, one argument is sufficient: `-s` (severity).
Severity takes three values:

- 'patch'
- 'minor'
- 'major'

Each of those will increment the relevant number by 1 if no value is specified.
The value position are described as follows: `major.minor.patch (ex: 1.0.2)`.

If you wish to increment the severity value by more than the default 1, you could pass `-i` (increment) followed by the value you wish to increment. Realistic examples would be:

- `bumpme -s patch -i 1`: would turn 1.0.0 into 1.0.1
- `bumpme -s patch -i 2`: would turn 1.0.1 into 1.0.3
- `bumpme -s minor -i 1`: would turn 1.4.9 into 1.5.0
- `bumpme -s major`: would turn 1.2.5 into 2.0.0
- `bumpme -s major -i 2`: would turn 1.2.5 into 3.0.0

**Enjoy your version management! 😁**
