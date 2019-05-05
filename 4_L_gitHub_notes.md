### Git Hub notes


'git' commands
          git  init
            starts a new repository
          git add "x"
            adds files for git to track
          git commit -m
            saves changes to the repository
            -m notates that you are adding a comment to document something about the save/commit
          *remote repository
            an off current computer repository like GitHub or another computer with a connected git repositroy
          git push
            pushes the saved files you have to some specified remote repository
          git pull
            pulls down changes that others have made to the same repository and files you are working on from the remote repository
          
  'git config' commands
        git config --global push.default simple
            prevents anoying message from being sent when you push
        git config --global credential.helper 'cache --timeout=14400'
            this sets it so you only have your user and pass asked for once every 4 hours
        
        
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
  
  
  
  