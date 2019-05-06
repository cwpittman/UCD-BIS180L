### Lab 5 Sequence Alignment


# Part 1

helpful actions


        gunzip
          to unzip a .gz file  
          was quicker to just use the GUI to unzip by rightclicking and calling the actions
        unzip 
          this was used for normal zip files
        git reset --hard HEAD^
          used to revert to last commit status
        ln -sF "file/x" "./new name"
          used to create aliases of other large files
        ls -lR "file/x"
          used to print a list of file creations etc as asked
          
          
# Part 2

File Info


        1. size of the file  
            ls -s "file-x"
              prints size of file in blocks
        2. number of the choimosomes  
            grep '>' <file>
              you can serach for whatever you want instead of the '>'
        3. size of the genome
            grep -v '>' c_elegans.PRJNA13758.WS269.genomic.fa | wc -m     
        4. number of the protein0coding genes
            grep -c '>' Araport11_genes.201606.pep.fasta    
        5. average protein length
            grep '^[ARNDBCEQZGHILKMFPSTWYV].*' Araport11_genes.201606.pep.fasta  | awk '{sum+=length($0)}END{print sum/NR}'                               
        
        
# Part 3

Local Alignment


      water  
        water <file1> <file2> -gapopen # -gapextend 5 -outfile <newfilename>
          used to compare two files of sequences against one another to see how closely related the sequences are.  
          
# Part 4
      shufflseq
        suffleseq <file1> -outseq <newFileName.suffle.fa> -shuffle <#>
          used to recognize the amount of each amino acid in a protein and randomize the order into a new file  
      Compseq 
        compseq <file1> -word 1 -outfile <file1.comp>
          used to derive the average amount of each amino acid per line 
      diff 
        diff <file1> <file2>
          used to compare two files against eachother
          if nothing is printed afterwards, they are identical
      Cut 
        cut OPT FILE 
          allows you to remove certain things from a file 
      Histogram
        grep Score 1k.water | cut -d " " -f 3 | sort -n | uniq -c  
      Median
         grep Score 1k.water | cut -d " " -f 3 | sort -n | head -501 | tail -2  
      Mean  
        grep Score 1k.water | awk '{sum+=$3} END {print sum/NR}'  
      
      
      general notes as I progressed
        1. made header files of all the protiens to capture the first protien only
        2. water 
        3. shuffle 
        4. compseq 
        5. diff 
        6. shufflseq 1000 into one file 
        7. grep Score 1k.water to populate scores w/ values
        8. grep Score 1k.water | cut -d " " -f 3 | sort -n | uniq -c
          
          
          
          
          
# part 5