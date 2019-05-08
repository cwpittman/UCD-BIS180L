# Blast For Paralogs & Orthologs

## Part 1

1. Orthologs
  In terms of Bioinformatics, an ortholog is typically found by comparing the proteome of an organism against that of another. 
  If the best match of these two are found when this process is done in reverse, ie second serched against the first, then they are otrhologs.  
  
2. Takeaways
  * there are always best matches between any two proteomes statistically.
    They may just not be related in reality  
  * The distribution of random scores is not normal.
    they hover around 37 I belive
  * The randomness depends on 
    * lengths, composition and scoring parameters of the sequences
  
3. Finding all orthalogs between two proteomes

        water would take a long time
        
        Blastp
            
        formatdb
          To turn a FASTA file into a BLAST database
          
      Making a BLAST database
        ln -s ~/Assignment_1/Data/Species/A.thaliana/protein.fa ./plantpep   #making an alias
        formatdb -i plantpep -p T     #actual making of database 
            Makes thre diferent files
        this was also done with the worm file to make another database
      checking what files and info in the cd
        ls -lrt  
      making a file of one protien 
        cp mainBLASTFile > 2
        grep -A 8 -e '>B0213.10' 2 > B0213.10.txt 
      Blastp 
        ============================================
        time blastp -db plantpep -query P450 > default.blast
        ________________________________________
        0.60user 0.01system 0:00.68elapsed 90%CPU (0avgtext+0avgdata 45420maxresident)k
        11744inputs+944outputs (54major+2379minor)pagefaults 0swaps  
        =============================================
        
      Timing the Blastp
        =============================================
        for T in 10 11 12 13 14 15
        do
          echo "Starting blastp with threshold $T"
          time blastp -db plantpep -query P450 > file$T.txt 
          done 
        ________________________________________
        
                for T in 10 11 12 13 14 15
                                               echo "Starting blastp with threshold $T"
                                               time blastp -db plantpep -query P450 > file$T.blast
                                           end
        Starting blastp with threshold 10
        0.61user 0.00system 0:00.61elapsed 99%CPU (0avgtext+0avgdata 46168maxresident)k
        0inputs+944outputs (0major+2372minor)pagefaults 0swaps
        Starting blastp with threshold 11
        0.61user 0.01system 0:00.62elapsed 100%CPU (0avgtext+0avgdata 45616maxresident)k
        0inputs+944outputs (0major+2366minor)pagefaults 0swaps
        Starting blastp with threshold 12
        0.60user 0.01system 0:00.61elapsed 100%CPU (0avgtext+0avgdata 46284maxresident)k
        0inputs+944outputs (0major+2378minor)pagefaults 0swaps
        Starting blastp with threshold 13
        0.61user 0.01system 0:00.62elapsed 99%CPU (0avgtext+0avgdata 46228maxresident)k
        0inputs+944outputs (0major+2380minor)pagefaults 0swaps
        Starting blastp with threshold 14
        0.60user 0.00system 0:00.61elapsed 99%CPU (0avgtext+0avgdata 46440maxresident)k
        0inputs+944outputs (0major+2383minor)pagefaults 0swaps
        Starting blastp with threshold 15
        0.59user 0.02system 0:00.62elapsed 99%CPU (0avgtext+0avgdata 46436maxresident)k
        0inputs+944outputs (0major+2381minor)pagefaults 0swaps

it made the corrisponding files and saved them to the cd.

        