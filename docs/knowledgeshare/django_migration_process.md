Steps to Follow by Developers for Adding new Django Migrations/Schema changes  
\==============================================================================  
  
1\. Any schema change will require developers to generate the migration files and commit these files.  
2\. In case any schema change, create a feature branch (even if it is a one liner schema change).  
3\. During development while working on feature branch, developers will generate migration files with default names. (e.g. 009\_cameraalert.py   
etc) These 'in development' migration files WILL NOT BE COMMITTED.  
4\. During merge (from feature branch to develop or from feature branch to bugfix), developer has to generate final migration file. This   
migration MUST have a name. Use 'makemigrations  --name " command to give a name to migration.  Select a name which gives a fair   
idea of change. Follow the steps below for merge  
  
   1. These steps are for feature branch to develop branch merges. Please make appropriate adjustments for feature branch to bugfix merge  
   2. Delete all new migration files generated during development  
   3. switch to 'develop' branch.  
   4. Generate a new sqlite database. This database will represent status of schema before you apply new changes.   
   Please note you have to do this BEFORE MERGE.  
   5. Merge the feature branch into 'develop' branch.  
   6. Run 'makemigrations --name" command. This will generate a new raw migration file comparing the old database status and new model   
   files code.  
   7. Commit this new file.  
   8. Review the migration file. Sometimes the migrations are complex (e.g. renaming a field or you need to compute values for some  
    fields). In such cases you have to 'hand edit' the migrations. If you are not sure, ask for review (me or Shreeda will review these).   
    Make necessary changes.  
   9. Commit the updated migration files.  
  
Testing of Schema changes/Migrations  
\=====================================  
  
Test migrations on following different variations of test database  
  
1\. Test the migrations on freshly prepared empty database   
2\. Test the migration on previous versions empty database tables. (where  tables   previous versions schema exist but those do not contain any data)  
3\. Test the migrations on previous versions database with some test data.