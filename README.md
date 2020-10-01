# atosone-cli
A CLI tool for atosone.com, deploy your full-stack apps to the cloud

## Installation

Install with 
`npm install -g atosone-cli`

## Commands

atosone-cli v1.3.0

Usage  : atosone-cli command <args>

### Options list :
 
   **-a [APPID]**
   
   Input your appId directly in the command line instead of using `init`.

   **-t [TOKEN]**
   
   Input your token directly in the command line instead of using `login`.

   **-i [SUFFIX]**
   
   (fs pull specific) Only pulls files with the specified suffix.

   **-e [SUFFIX]**
   
   (fs pull specific) Exclude files with the specified suffix from bein pulled.')

   
Available commands :


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
   
