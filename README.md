# CourseRepoScripts
These scripts help create, clone and delete multiple repos for an organization.  It was designed to generate a large number of private repos and assign the appropriate access to each of these repos.  Once created, other scripts are available that will allow you to clone the repos generated, clone every repo in the organization and delete every repos.

These four bash scripts can help manage repositories, teams and users of organizations used in education.

createrepos - a script that will take a csv file and create repos based on it.  The csv file assumes the full name is in column 2, the github id is in column 4.  The file has a header row (which is ignored by the script) and no empty line at bottom of the file.  It will create a log file as part of the process.  this log file can be used by the deleteallrepos and clonelog scripts.  

deleteallrepos - a script will take the log file (or any file of the correct format) and delete the teams and repos from the organization

clonelog - a script that will take the log file and clone every repo listed in the log file.

cloneall - a script that will clone every repository within an organization, no input file is needed, just clones every repo.
