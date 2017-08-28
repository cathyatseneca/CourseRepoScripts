# CourseRepoScripts
These scripts help create, clone and delete multiple repos for an organization.  It was designed to generate a large number of private repos and assign the appropriate access to each of these repos.  Once created, other scripts are available that will allow you to clone the repos generated, clone every repo in the organization and delete every repos.

These four bash scripts can help manage repositories, teams and users of organizations used in education.

createrepos - a script that will take a csv file and create repos based on it.  The csv file assumes the full name is in column 2, the github id is in column 4.  The file has a header row (which is ignored by the script) and no empty line at bottom of the file.  It will create a log file as part of the process.  this log file can be used by the deleteallrepos and clonelog scripts.  

deleteallrepos - a script will take the log file (or any file of the correct format) and delete the teams and repos from the organization

clonelog - a script that will take the log file and clone every repo listed in the log file.

cloneall - a script that will clone every repository within an organization, no input file is needed, just clones every repo.


### Suggested Usage:

These scripts were originally designed to help set up private repos for students under an organization.  The following instructions will help you use the spreadsheet as is without modification.  

1. Create a google form that will ask for the following information:
    * Full name
    * student id  (note this is not used by the script, its just to help you identify your students)
    * githubid
2. Have the form save the information to a google spreadsheet and give the form link to your students
   * Note that if you did it in the order above, the google spreadsheet will have 4 fields per row in the following order:
     * Date/Time Stamp
     * Full Name
     * Student ID
     * githubid
   * if the ordering is not as above or you have more/less fields, you will need to adjust the script.
3. Once the students have filled in their info, do a quick check for duplicate entries and other mistakes...like brackets in the name fields.
4. Once the spreadsheet is good, you can download it as a csv file, place into the same directory as the createrepos script
5. Edit the createrepo script by filling in your github id, access token, organization, name of the csv file, and logfile name.
6. run the script.  This will:
     * generate a private repo for each entry named according the the student's full name (spaces will be automatically removed)
     * create a team based on the full name
     * add the githubid to the team
     * associate the repo with the team, providing read/write access
     * generate an entry in a log file
 
 You can verify it worked by checking the organization for the repos.
 
#### to add additional students
 
 To add additional students:
 * download the csv file
 * erase the lines for the students that already have repos created
 * rerun the script
 
 The additional entries will be logged into the same log file as long as you don't change the log file name in the script.
 
 
#### log file
 
The assumption made is that repos that were created (and thus logged into the same log file) have a related relevancy.  That is, you will likely want to see all repos related to the log file together.  When it comes to cleaning up the repos (deleting them) you are likely to want to delete them at the same time.  The deleteallrepos script is designed to only delete the repos associated with a particular log file while leaving other repos alone.


#### to clone based on log file

* Use the clonelog script
* Edit appropraite variables in script with your github id, organization name, access token and log file
* Run the script

#### to delete repos based on log file

* Use the deleteallrepos script
* Edit appropraite variables in script with your github id, organization name, access token and log file name
* run the script

#### To clone every repo
* use the cloneall script
* Edit appropraite variables in script with your github id, organization name, access token
* run script
