## Git

### Git Branching
- Use branches to segment features/work from others
- Keeping different "versions" of the project based on features/developers
- Feature-based branching or Developer-based branching
    - Feature:
        - Login
            - Harry
            - Ron
        - Register
        - Cart
        - Comment
    - Developer:
        - Harry
        - Ron
        - Hermione

### Git Merging
- Take changes from one branch and put those changes into another
- Two Ways:
    - Make a Pull Request on Github and resolve any conflicts through the Github GUI
    - Command Line: ex: "git merge development"
        - git checkout development
        - git merge hermione
        - This would merge hermione's changes into development
            - Any merge conflicts that arise would be denoted by the special syntax (=========, main, head)

### Git Flow
1. One person will create the project
    - Set up directory structure
    - Create the repo
    - Set up main/development branches
2. All developers would clone the repo
3. All developers would create a branch off of development for themselves or for the feature they're working on
4. Developers continue to work on their branches
5. Once done with changes, submit a pull request to development branch 
    - Have someone else look it over and help solve any merge conflicts
    - If branch is feature-based, delete the branch
6. At some point, get team leads to verify that the development branch can be merged into main
    - Submit a pull request to merge development into main

### General Tips
1. Branch early/often
2. Merge as often as you can, don't wait until the very end of the project to merge
3. Merge parties - getting all teams together to merge the work, maybe at the end of the sprint

### Practice
- https://learngitbranching.js.org/

