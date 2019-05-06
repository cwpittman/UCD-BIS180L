### L6 Fish And Bash For Loops


# For Loops


      contains three parts
        1. a for statement for what items we want to loop over
        2. the commands repeating
        3. the end statement to finish the Loops
      
    example
    1. this sets a variable called 'list' that is designated the numbers as the list
        ===============
        set list 1 2 3 4 5 6
        ===============
    2. printing the values of the variable
        ===============
        echo "$list"
        _______
        1 2 3 4 5 6
        ===============
          the '$' calls the list
          w/o the '$' it just prints fruits
    3. Printing line by line each value in the 'list' by taking one value at a time
        ===============
        for l in $list
        echo "$l"
        end
        ______
        1
        2
        3
        4
        5
        6
        ===============
    4. If you wanted to add text after each value...
        ===============
        for l in $list
          echo {$l}text
        end 
        ______
        1text
        2text
        3text
        4text
        5text
        6text
        ===============
    5. Other ways to create a list of files 
        ===============
        echo "this" > file1.txt  #making files  
        echo "is" > file2.txt
        echo "silly" > file3.txt
        set myfiles (ls)          #setting the files in current directory for_example
        echo $myfiles             #proving the correct list
        _______
        file1.txt file2.txt file3.txt   #printout of myfiles values
        ===============
    6. How to make a for loop to print the contents of each file in a list
        ===============
        for i in $myfiles
        cat $i
        end
        _______
        this
        is
        silly
        ===============
    7. Aditional options  
        ===============
        for file in $myfiles
          echo (echo file {$file}contains)
          cat $file
        end
        _______
        file file1.txtcontains
        this
        file file2.txtcontains
        is
        file file3.txtcontains
        silly
        ===============
    8. ways to auto create files  
        ===============
        set newFiles one two three four
        
        for f in $newFiles
            touch {$f}.txt
        end

        ls
        ________  
        four.txt  one.txt  three.txt  two.txt
        ===============
        
    9. optional exercise 4 didnt do

# Nested for Loops

            set fruits banana apple orange grape plum pear durian pineapple

            for fruit in $fruits 
                for number in 1 2 3 4 5 6 7 8 9 10
                    echo $fruit $number
                end #ending the inside loop
            end #ending the outside loop

  
        
        