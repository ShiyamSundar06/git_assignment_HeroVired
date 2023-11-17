# git_assignment_HeroVired

# Q.1: You are part of a development team working on a Python application called "CalculatorPlus." The application provides basic arithmetic operations, such as addition, subtraction, multiplication, and division. Your task is to implement a new feature that adds support for calculating the square root of a number.

# a. Create a repository name: git_assignment_HeroVired
Clone a repository from github in your local.

# b. Create a ‘dev’ branch and add this code.
--Add following lines of code.
git branch dev
git switch dev

--Add the following lines of code

import math

class Calculator:

  def add(self, a, b):

    return a + b

  def subtract(self, a, b):

    return a - b

  def multiply(self, a, b):

    return a * b

  def divide(self, a, b):

    return a / b

  if __name__ == "__main__":

    calculator = Calculator()

    num1 = 16

    num2 = 4

  print(f"{num1} + {num2} = {calculator.add(num1, num2)}")

  print(f"{num1} - {num2} = {calculator.subtract(num1, num2)}") print(f"{num1} * {num2} = {calculator.multiply(num1, num2)}")

  print(f"{num1} / {num2} = {calculator.divide(num1, num2)}")



# c. Merge this branch with the main branch and make a release of version 1 of the ‘calculator plus app’.
git switch main
git merge dev

# d. Add any of your classmates as collaborators.
Added Prajjwal as collaborator

# e. Implement a feature by creating a new branch called ‘feature/sqrt’. f. Add the ‘sqrt’ code to it.
git branch feature/sqrt
git switch feature/sqrt

-- Add the following lines to python script
def square_root(self, x):
  return math.sqrt(x)

-- After Main, add the following:
num3 = 25
print(f"The square root of {num3} = {calculator.square_root(num3)}")

git status
git add .
git commit -m "Added sqrt code to feature/sqrt branch"

# g. While you are working on this feature, imagine that one critical bug is reported in the main branch, and you need to switch back to the ‘dev’ branch, create fixes, and apply them while keeping your ‘feature/sqrt’ branch up-to-date. For this, you need to create

git switch dev

-- Add the following code
def divide(self, a, b):
  if b == 0:

    raise ValueError("Cannot divide by zero.")

  return a / b

git status
git add .
git commit -m "Fixed the bug in main branch on divide function"

# h. After completing the feature implementation and ensuring that the application works correctly, create a pull request targeting the main branch.
Advise the colloborator to create a pull request on github targeting the main branch.

# i. Request a code review from a team member and make any necessary improvements based on the review feedback.
Covered above

# j. Once the code reviewer approves your pull request, merge the "feature/sqrt" branch into the ‘dev’ branch.
Post approval from reviewer, merge the "feature/sqrt" branch into "dev" branch either using github or git followed by push.

# k. Finally, do the testing in the ‘dev’ branch itself and merge it into the ‘main’ branch and create a ‘version 2’ release.
Post successful testing of python file in dev branch, merge it into main using following code.
git switch main
git merge dev

and finally go to respective branches and push them to github using following code:
git switch "branch_name"
git push origin "branch_name"


## Q.2: For a project that deals with large binary files, integrate Git LFS (Large File Storage) to handle these files efficiently. Demonstrate how to add, commit, and push binary files to the repository, ensuring they are tracked by Git LFS correctly. Clone the repository on another machine to verify that the binary files are downloaded correctly.

# In the repository ‘git_assignment_HeroVired’, create a branch ‘lfs’. Upload any large file whose size is over ‘200mb’ and try to push this file into the repository.

Step1: Download a dummy lfs file with size 200mb from internet and save it in the same local folder used for first question.
Step2: Run the following commands.
git branch lfs
git switch lfs
git lfs install
git lfs track "*.bin"
git add .gitattributes
git add file.bin
git commit -m "Add LFS binary file"
git push origin lfs


# Q.3: In this same GitHub repository, create a new branch ‘geometry-calculator’, we'll work on a simple Python program that calculates the area of a circle and the area of a rectangle. We'll use Git stash to switch between working on multiple features (calculating circle area and calculating rectangle area) without committing incomplete changes.

# a. Create a New Branch:
  - Create a new branch named "feature/circle-area" to work on the circle area feature

-- Run the following commands:
git branch feature/circle-area
git switch feature/circle-area

-- Add the following lines of code in a python file with .


import math

class GeometryCalculator:

  def calculate_circle_area(self, radius):

    return math.pi * radius ** 2

  def calculate_rectangle_area(self, length, width):

    return length * width

  if __name__ == "__main__":

    calculator = GeometryCalculator()


# a. Create a New Branch:
- Create a new branch named "feature/circle-area" to work on the circle area feature

-- Add the folowing lines of code:
git branch feature/circle-area

--Add following after __main__ in python file:
radius = 5
print(f"The area of the circle with radius {radius} = {calculator.calculate_circle_area(radius)}")


# b. Stash Changes for Circle Area Feature:

- Before committing the changes, stash them using git stash to save the incomplete feature implementation.
--Add following lines of code:
  git add .
  git stash
  
- Verify that the working directory is clean
Visually, the changes made will be removed and stored in stash.


# c. Create a New Branch for Rectangle Area Feature:

- Create a new branch named "feature/rectangle-area" to work on the rectangle area.
--Add the following lines of code:
  git branch feature/rectange-area
  git switch feature/rectange-area

--Add the following lines of code in python file after __main__ function:

length = 10
width = 6

print(f"The area of the rectangle with length {length} and width {width} = {calculator.calculate_rectangle_area(length, width)}")


# d. Stash Changes for Rectangle Area Feature:

- Before committing the changes, stash them using git stash to save the incomplete feature implementation.
--Add following lines of code:
  git add .
  git stash
  
- Verify that the working directory is clean.
Visually, the changes made will be removed and stored in stash.

# e. Switch Back to Circle Area Branch:

- Switch back to the "feature/circle-area" branch to continue working on the circle area feature.
git switch feature/circle-area

- Retrieve the stashed changes
--Add following lines of code
  git stash apply 'stash@{0}'
  git add .
  git commit -m "Stashed Circle Area change included"
  git push origin feature/circle-area

# g. Switch Back to Rectangle Area Branch:

- Switch back to the "feature/rectangle-area" branch to continue working on the rectangle area feature.
  git switch feature/rectangle-area

  - Retrieve the stashed changes
  --Add following lines of code
    git stash apply 'stash@{1}'
    
  - Complete the rectangle area feature implementation and save the changes. h. Commit and Push Rectangle Area Feature
  --Add following lines of code
    git add .
    git commit -m "Stashed rectangle area change included"
    git push origin feature/rectangle-area

# i. Create Pull Requests:
  Advise the collaborator to create a pull request.

# j. Review and Merge

- Have another team member or reviewer review your pull requests. - After receiving approval, merge both pull requests into the main branch.
  Post approval from team member, merge the appropriate branches into main.
