- Length of presentation?
    - 30 minutes upper limit
- Zoom backgrounds
    - consistent image, blurry background feature
- Teams
    - 3-4 members
- Git Workflow:
- My Way of working with teams on Github
1. One person shares screen and sets up project, packages, folders, structure, etc. Push to main. Make a development branch off of main.
2. Each developer picks a feature to work on. Clone the project and create a branch from development based on that feature. (login, register, etc.)
3. Each developer works on their feature until completed. Continually push your changes to the feature branch. 
4. Once feature is completed, ensure all changes are persisted to the feature branch. 
5. Submit a pull request on Github. 
6. Have team lead, or other team member share screen and resolve merge conflicts. 
7. Merge Pull Request into development. 
8. Delete the feature branch from remote repo.
9. On local computer, checkout development and branch again. (You don't want to branch from the now-deleted feature branch). 
10. When you have a stable project, you can merge to main and then work work in increments and merge to main whenever you reach another milestone.