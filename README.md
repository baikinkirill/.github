# RTUITLab Github Actions templates
## How to use
### General rules
All variables in `UPPERCASE` you should replace with your variables
### update-submodules.yml
1. Your repo MUST have:
    1. Submodules

1. Description of this action:
    1. Triggers:
        1. `default` branch 
            > Default branch of your repo
        1. Schedule `8:30` and `15:30` every day
    1. Check for repository changes in the Actions workspace. This includes:
        > [Full description of this job](https://github.com/peter-evans/create-pull-request)
        1. untracked (new) files
        1. tracked (modified) files
        1. commits made during the workflow that have not been pushed
            > Commit all changes to a new branch, or update an existing pull request branch.  
            Create a pull request to merge the new branch into the base—the branch checked out in the workflow.


### build-image-and-update-service.yml
1. Your repo MUST have:
    1. Dockerfile named `Dockerfile` in root folder of your repo.
        > This Dockerfile creates a docker image of your app
    1. [RTUITLab's](https://github.com/RTUITLab) secrets:
        1. RTUITLAB_MANAGER_VM_USERNAME
        1. RTUITLAB_MANAGER_VM_SSH_KEY
        1. RTUITLAB_MANAGER_VM_HOST

1. Description of this action:
    1. Triggers:
        1. `default` branch 
            > Default branch of your repo
    1. Creates [github package](https://github.com/features/packages) with docker image of your project
        > After this job, you can find your packages on main page of your repo.  
        [Check this](https://docs.github.com/en/packages/learn-github-packages/viewing-packages) to turn on packages viewing on repo main page
    1. Goes to RTUITLab manager virtual machine and updates service with new github package
