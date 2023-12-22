This is an automatic translation, may be incorrect in some places. See sources and examples!

## How to add your project
- Register for GitHub, create a project repository (see Google)
- draw up a project - description, scheme, instructions, etc.
- Create and fill out the file of information about the project, it should be along the path `/project.json`

Sample information file:
`` `json
{
  "Version": "X.X",
  "Notes": "Comments on the version of the update",
  "ABOUT": "Short description of the project"
}
`` `
> The name of the project will be taken from the name of the repository

### Add to the base
You just need to make the FORK of this (Gyverhub-Projects) repository, add a link to the repository of your project to the Projects.txt file and create PULL REQUEST:
- Go to the [editing page] (https://github.com/gyverlibs/gyverhub-projects/edit/main/projects.txt) Projects.txt file
    - If this is the first addition - click ** Fork this repository **
- Add a link to the repository of your project to the project list
- click ** comit changes ... ** in the upper right corner of the screen
- click ** propose changes ** in the window that appears
- click ** Create Pull Request ** in the upper right corner of the screen
- click ** Create Pull Request ** on the page opened
- wait for manual moderation

> Note: this is a public base of projects, so only well -designed projects will be added

## Automatic update
How to configure an update with GitHub from the application [read wiki] (https://github.com/gyverlibs/gyverhub/wiki/5.-%D0%94%D0%BE%D0%BF%D0%BE%D0%BB%BB%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE)