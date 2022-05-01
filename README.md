# atosone-cli
A CLI tool for atosone.com, deploy your full-stack apps to the cloud

## Installation

Install with 
`npm install -g atosone-cli`

## Commands

Usage  : atosone-cli command <args>

### Options list :
 
   **-a [APPID]**
   
   Input your appId directly in the command line instead of using `init`.

   **-t [TOKEN]**
   
   Input your token directly in the command line instead of using `login`.

   **-i [SUFFIX]**
   
   (fs pull specific) Only pulls files with the specified suffix.

   **-e [SUFFIX]**
   
   (fs pull specific) Exclude files with the specified suffix from bein pulled.

   **--skip-existing-files**

   (fs pull specific) Skip files already existing in your filesystem.

 
### Available commands :


### Setup

   `login` 					                     Login to our service
   
   `init 	    <app-id>` 			            Link folder with your app-id
   

### Filesystem
  
   `fs pull  	<source-folder>` 		         Pull folder from SERVER to LOCAL
   
   `fs push  	<folder-to-push> <opt: dest>`	Push folder from LOCAL to SERVER
   

### Database - CloudBackend

   `db pull` 					                     Retrieves .sql file of your database from SERVER to LOCAL
   
   `db push  	<sql-file>` 			            Restore the database on SERVER from the LOCAL .sql backup provided
   

### Api - CloudBackend

   `api pull  	<opt: function_id>`		        Pull all (or one) function(s) of your CloudBackend to LOCAL
   
   `api push  	<opt: function_id>`		        Push all (or one) function(s) from LOCAL to your CloudBackend
   
   
### Export

   `export  	<path>`		                    Export your project to the specified folder

### Help

   `help` 					                    Displays this help text
   
## Usage examples

After logging-in through our ``login`` command or using the ``-t`` flag, and setting up your appId with -a or with ``init``. You will be able to use the CLI.
Here are some examples to help you through the process.

**Pulling only files ending by ".js" in the root folder of your appdrag app.**

``atosone-cli fs pull -i .js``.

**Pulling specific functions using a Function Id**

``atosone-cli api pull FUNCTION_ID``

To be able to find your function ID you simply need to visit the specific function in your cloudbackend and look at the URL. 
It will look like this : www.atosone.com/cloudbackend.html?appId=YOUR_APP_ID#FUNCTION_ID Simply copy the function ID after the '#', and paste it into your command.


**Pushing specific folder from your local files into your project**

``atosone-cli fs push YOUR_FOLDER``

Our CLI will create a zip of our folder and push it to the root of your appdrag project.

**Pushing specific folder from your local files into a specific folder in your project**

``atosone-cli fs push YOUR_FOLDER DESTINATION_FOLDER``


### Setting up continuous delivery from development project A to production project B


Import API Functions from project A:

`atosone-cli -a dev-project-a -t USER_API_TOKEN api pull`


Push API Functions to production project B:

`atosone-cli -a prod-project-b -t USER_API_TOKEN api push`

Up to date functions on the production project won't be updated if their last update date are greater or equal to the ones on the dev project on AppDrag.
If you do changes locally, don't forget to push it on the dev project before pushing to the production, if not, updates will be skipped.