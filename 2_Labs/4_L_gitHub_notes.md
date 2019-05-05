### Git Hub notes


'git' commands

          git  init
            initiates git tracking of the file you are in as a repsoitory
          git add "x"
            adds files for git to track
            git add .   this is a easy way to add all the current files into the queen to be monitored
          git commit -m "text"
            saves changes to the repository of those you are tracking by git add
            -m notates that you are adding a comment to document something about the save/commit
          git push <remotename> <BranchName>
            pushes the saved files you have to some specified remote repository
            git push <RemoteName> --delete <BranchName>
              deletes a branch from GitHub itself.
          git pull <remotename> <BranchName>
            pulls down changes that others have made to the same repository and files you are working on from the remote repository
          git fetch --dry-run  
            preview the changes of a branch before actually pulling
          git merge <BranchName>
            this saves the changes of the branchname you call into the repository you are currently in
          git diff
            populates the differences between the files you have on you local repository and that of the associated repository on GitHub  
          git status
            populates what is currently being monitored by Git in this Repository
            populates what is different from the last commit
            populates what has yet to be and has yet to change since the last commit
          git branch <BranchName>
            makes a new branch of the repository you are currently in
            git branch -m <BranchName>
              can rename the branch  
            git branch
              prints branches
            git branch -d <BranchName>
              deletes specified branch  
          git checkout <BranchName>
            you can go into the Branch to work on it there  and not the more main branch "branchstalk?" it came from   

Forking

        This can be done on GitHub.
        go to the website hosting the file you wish to copy onto your account and press the for option in the upper right corner
        a repsitory should now be in you github with this contents in it

Adding Collabroators

        This can be done on GitHub.com  
          
'git remote' commands

        git remote add <remotename> <HttpsFromGitHub>
          this will add in a place for you to push and pull from 
          <remotename> 
            this can be origin if it is refering to your cloned in files
            Can name upstream if you are pulling and pushing to the original files
          git remote -v
            check the linked repositories connected to this file. 
          git remote set-url <remotename> <HttpsFromGitHub>
            Change the adress of the specified name  
            Windows GitHub: the origin is already made when you git init. so you need to simply use this command to set a GitHub adress


            
  'git config' commands  
  
        git config --global push.default simple
            prevents anoying message from being sent when you push
        git config --global credential.helper 'cache --timeout=14400'
            this sets it so you only have your user and pass asked for once every 4 hours
        git config --global user.name <ActualName>
        
        git config --global user.username <UsernameOnGit>
        
        git config --global user.email   <EmailAssociateWithGit>
        
        
        
'github.com' website
          to make a repository from the website....
              1. From your github.com home page click on the green “+ New Repository” button (right hand side of screen)  
              2. On the resulting page give it a name, check the “Initialize this repository with a README” box and press the “Create Repository” button.  
              3. Click on the clipboard icon to copy the URL  
              4. Open the terminal on your computer, cd to the parent directory of wherever you want the repository to reside and then git clone URL where URL is the URL that you copied from Github.  
              5. You can now cd to your repository and begin working on it.  
              
              OR

              1) Create the repository on your computer first.
              2) cd to the parent directory of where you want the repository to reside.
              3) mkdir NAME where NAME is the name you want for your repository.
              4) Very Important cd NAME to move into the repository
              5) git init to initialize a repository in the current directory
              6) Add a file to the repository. For example:
                  touch README.md
                  git add README.md
                  git commit -m "Added README.md"

              7Go to Github.com
              8From your github.com home page click on the green “+ New Repository” button (right hand side of screen)
              9On the resulting page give it a name and press the “Create Repository” button. DO NOT check the “Initialize this repository with a README” box.
              Click on the clipboard icon to copy the URL next to the heading “…or push an existing repository from the command line”
              Paste that into the terminal while in the directory of your repository. i.e.

              git remote add origin git@github.com:jnmaloof/test2.git
              git push -u origin master


        
  
  tutorial to teach how to use github is as follows
  just past all of the follwing into a linux terminal and get goin
              cd
            ls
            mkdir Apps
            cd Apps

            #OK to cut and paste the next line...
            wget https://github.com/jlord/git-it-electron/releases/download/4.4.0/Git-it-Linux-x64.zip

            ls
            unzip Git-it-Linux-x64.zip 
            ls
            cd Git-it-Linux-x64/
            ./Git-it &
  
  
  
  