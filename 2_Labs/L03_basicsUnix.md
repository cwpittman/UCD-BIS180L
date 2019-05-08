### L3.Basics of Unix

      date
        prints date
      man "x"
        opens manual about "x"
      --help
        same as man but with other options
          ex x --help | less
      history
        populates a history of what has been entered into the terminal
      printenv "x"
        prints the contents of a variable "x"
      nano
        in terminal text editor
      atom
        out of terminal text editor
      df
        populates the data used in your hardrive or whtaerver
        -h makes it easier for 'humans' to read
      du
        shows how much data each file is utilizing
      touch "x"
        makes a file "x"
      cat > "x"
        creates a file "x" and you start to immidialty type into it w/o tet editor
        usefull for general notes
        to exit, ctrl + D
      head "x"
        print the first 10 lines of "x"
      tail "x"
        print last ten lines of "x"
      more "x"
        this is a pager command
        it presents text one 'page' at a time
        press 'spacebar' to advance page
        press 'q' to quit
      less "x"
        same as more, but more options
      pwd
        prints current location in directories
      ls
        lists contents of current directory
      ls . 
        prints name of curent directory
      . 
        reffers to current directory
      .. 
        reffers to previeous directory
      ls -F
        prints names of files with type of files at the end of the names
      /
        reffers to home directory
      cd "x"
        change direcoty to "x"
      mkdir "x"
        makes a new directory "x"
      mv "x" "/y"
        move file "x" to location "/y"
        can rename a file if the "/y" doesnt exist causing it to take the new name in place of
        can move more than one file at a time into whatever the last name on the list is called as the destination files
      cp "/direcotyA/directoryB/x"
        coppies file "x" by being in the destination directory and placing it there
        can change the name of the new copy by placing a name after the input of the file to be coppied in the command
      '*'
        this is used to put infront of a few letters of what you think it is called to act on ALL files in the system that start with what you put in front of it in common
      ln -sF "file/x" "./new name"
        this creates an alias of file "x"
        it is not a copy, but a 'shortcut' to whatever file "x" in its origional location
        will have a '*' after it once made to signifiy it is an alias
        -F shows the '@' after to notate what are alias files
      rm "x"
        this removes or deletes file "x"
      gunzip
        this is able to unzip .gz files
        use ctrl + c to stop the constant print loading of the files
        if that doesnt work, you can sleep the file by ctrl + z
      gzip "x"
        reduces the file down about 50 to 75%
      |
        the pipe command takes the results of the left and 'pipes' it into the right arguments
      grep "x"
        if you want to look for patterns, this function is great to look for whatever  "x"
      ">"
        like pipe, it puts the left into the right
      tar 
        to send many multiple of files, you cand send them as a 'tar ball'
        ex
          tar -c -f project0.tar Project0
            -c tells tar to creates
            -f tells tar to gather the files within the specified
            -z automatically compresses the file as with gunzip
              it is often good practice to compress the tarballs with gunzip
            -x this used instead of -c will inflate a compressed file 
      ls -l  
        this displays the data size and the permissions of each user
      chmod  
        this adds and deletes the permissions for each designated user
        There are three kinda
          shortcut  name      octalname
          r         read     4
          w         wright   2
          x         exicute  1
          ex
            chmod u-x chromosomes.txt
              this removes exicutable feature from the user
            chmod u+x chromosomes.txt
              this adds the exicutable feature to the user
        there are 0-7 different numbers to enter into the chmod function
          each number can be entered into three slots that respectivley act on user, group, and public
            ex
              so 000 makes no one able to rwx
              and 777 gives everyone the ablity to rwx
              thngs inbetween that are customized according to oct  
        top  
          this is basicly control alt delete in windows
          it pulls up the page to view the health of the current condition of the computer
        htop
          this is a variant of top  
          it has color coordination and hightlighted areas
        perl -e 'while(1){print $i++, chr(10)}'
          idk if this is usefull in the future, but it counts forever
        ctr + z
          puts a program into sleep
        ctr + c 
          stops a program
        fg
          resumes a program from sleep
        ps -u 'username'
          populates the current processes
        kill PID#
          you can kill certain processes by lookingup the PID number in the ps function list.
        bg
          put this at the end of the command line to put it into the background
        &
          acts the same way as 'bg'
        ~
          home directory
        ctr + d
          send end of file 
        rmdir "x"
          removes directory "x"
        wc "x"
          counts words of file  "x"


### general info

    File types
      there are two different file types
      text and binary
        text
          more for human readibility
          comes in three different flavors commonly
            linux, mac, and windows
            this is why you cannot easily transfer between systems as they differ slightly
        binary
          meant for human consumption and is generally unreadable
      displaying the permissions with 'ls -l'
      