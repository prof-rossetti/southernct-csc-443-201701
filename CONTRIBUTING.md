## Contributing

This document describes instructions and best practices for contributing to this repository.

### Workflow

Clone the repository and optionally rename it:

```` sh
git clone git@github.com:SCSU-CSC-Department/201701-csc-443-01.git
mv 201701-csc-433-01/ csc-433-01/
cd csc-433-01/
````

Check-out a new branch before making any changes (recommended):

```` sh
git checkout -b NAME_OF_BRANCH
````

Add or revise files using a text editor, then review them:

```` sh
atom . # atom is the default text editor for this course
git diff
````

Commit the changes when you are satisfied:

```` sh
git add .
git commit -m "Your description of the changes"
````

Push the changes to GitHub:

```` sh
git pull origin NAME_OF_BRANCH # always pull before pushing (best practice) in case another contributor has since pushed changes to the branch
git push origin NAME_OF_BRANCH
````

When your branch is ready to be merged, [find your branch](https://github.com/SCSU-CSC-Department/201701-csc-443-01/branches) on GitHub, then click the button to create a **Pull Request (PR)**. In the PR message, describe what changes you made and why.

An admin will review your PR within a timely manner. If an admin accepts your changes, he/she will merge them into the master branch.

Congratulations and Thank You!


### Guidelines

*TODO*
