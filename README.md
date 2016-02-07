# CourseRepoScripts
These scripts help manage users and teams of organizations used for education

These three bash scripts can help manage repositories, teams and users of organizations used in education.

createrepos - a script that will take a file with a markdown style table (without the header and --- rows) containing a real name (ie student name) and another with github id.  This script will create a team and repository based on the realname, add the user with the github id to the team and and assign the team to the repository.  Used this script to generate a single repository for each person in the table.  This script will produce a log file that can be used by the deleteallrepos script

deleteallrepos - a script will take the log file (or any file of the correct format) and delete the teams and repos from the organization

cloneall - a script that will clone every repository within an organization, no input file is needed, just clones every repo.
