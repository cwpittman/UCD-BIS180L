# Template for BLAST, orthologs, and paralogs (Week 2-3, 18 pts possible)

__Name:__ Chad Pittman

__Student ID:__ 914960676

*_Please answer the following questions which are each worth 2 points. Be clear and concise with any written answers. Late assignments will be penalized with a 2pt deduction per day without prior communication of extenuating circumstances._*

__Q1__.  __Write a for loop to pluralize peach, tomato, potato (remember that these end in "es" when plural).  Provide the code below.  (See "for loop" lab)__

        set Item peach tomato potato
        
        for Item in $Item
          echo {$Item}es
        end  

__Q2__.  __In your own words provide a "translation" of the loop below (from "for loop" lab)__

      for file in $myfiles
          cat $file
      end
      
Translation:

Designate a variable called 'file' that acts as a function for each action called from 'myfiles'.  
The function of 'file' is as follows: 
  Concatonate text to terminal of each file of myfiles in order of the set,  
  such that it prints; "cat: 'name of set #:' 'concatination of set #'"  
Repeat this function of 'file' until all files of the set in myfiles have been concatenated.
exit for loop to terminal 
  
  
__Q3__. __Create a table that indicates blastp runtime as a function of
threshold value.  Is there a linear relationship?  Why does does
changing the threshold change the search time?  Include the `for` loop command that you used.__

      for T in 10 11 12 13 14 15
          echo "Starteing blastp with threshold $T"
          time blastp -db plantpep -query p450 -threshold $T >default$T.blastp  
      end

| Threshold Value | Runtime (seconds) | 
|:----------------|:------------------|
| 10 | .88|
| 11 | .64|
| 12 | .50|
| 13 | .41| 
| 14 | .36|
| 15 | .33|

* There is no linear relationship, but instead something more relatable to an expenential decay towards a plaeu. This is observed as the difference between runtimes with an increase of Threshold is as the follwing: .24,.14,.09,.05,.03 .  
* Changing the threshold changes the amount of workload on the function. If you increase the Threshold Value, there is less work for the function to do. Decreasing inturn adds work, thus adding time to complete such work. 
* Overall, Increasing the threshold decreases the number of alignments that the BLAST function is going to produce. Since an there is less work for the function to do, it is done faster.

__Q5__.  __What search parameters (matrix and threshold) would you use to
search two proteomes? Justify your answer.__  
  
  * Searching two different proteomes will mean that there will be a high percentage of differences. The smaller the Threshold Value, the longer it will take to run. So I would generally choose a higher Threshold to cut down on the runtime and prevent the production of alignments that didnt actually report what I was looking for anyway. I ran a few functions with various thresholds and I found that 100 was a good place I will likely start from next time. It took 17 minutes, but as I coninued down the threshold value, I got to a point where it didnt ever stop and I just quit the experiement after an hour or so. Though I am sure running multiple runs at the same time didnt help.
  * Again, since the question is in how to search two different proteiomes, I would want to run a matrix that accounts for this. Thus I would go with the BLOSUM instead of PAM. PAM is more for global alignments, but I am essentially needing something that accounts for local and different alighments that BLOSUM can do. I expereimented with some of the various BLOSUM programs and I belive that starting with BLOSUM90 would be a decent place to start. It would give me results pretty quick as it would only show me highly related sequences first (90%). If I so desired, I could start to bump it down until I got the results I felt were relevent to the actual project in this comparison. 

__Q6__.  __How long will it take to search two proteomes (given the above)?__  
* Well as I said, it took me 17 minutes at 100 for the Threshold Value while using BLOSUM90. I will note though, I was running multiple funcions at the same time. And I am going to assume you understand why I dont wish to get a more accurate number by running them indivudually again.

__Q7__.  __Using E-value to determine the best match, find a worm gene with a single plant ortholog and record their names and the reciprocal E-Values.  Is there more than one plant "hit" for your worm gene?  If so how do you decide if there is a single orthlog?__  

B0334.3a AT5G17380.1: 3.51e-114
AT5G17380.1 B0334.3a: 5.91e-109

* There were two hits for B0334.3a and T26C12.1. 
* Though the E-value was over 100 for B0334.3a where T26C12.1 was to the 36. So im assuming B0334.3a is the orthalog since it is so much lower in contrast. T26C12.1 is more likely to have been hit by random chance. 

__Q8__.  __Discuss what makes orthology difficult to determine by the reciprocal BLAST method.__
  
  * Orthology by recoprocal BLAST is difficult in part because of the nature of determining the threshold value that leads to hits of orthalogs.
  * If you hypothesise two protiens as orthalogs, a reciprocal BLAST can give you other hits. These could be paralogs or lead in other directions.
  
__Q9__.  __How many paralogs did you find for T21B10.2a and for B0213.10?  What criteria did you use?__

  * No paralogs were found since the E-value was greater than 0 for all of the hits for T21B10.2a.
  * There are 8 paralogs that have an E-value of 0 for B0213.10. 

__Q10__.  __Is alignment score sufficient for determining orthology or paralogy? What other sources of information from the BLAST output might be useful?  What other types of analyses would be helpful?__
 
 * No, alightment score is not sufficent for determining ortholog or paralogy. 
 * The E-score is what gives the score any credibility to justify whether it is simply ranodomly hit or actually a ortolog or paralog.
 * WATER could be used to or if needed a phylogony could be used to determin if past historic relitives also had or did not carry the gene amung other ways of evauation by this method.  
 
Add and commit changes for both this document and your lab notebook to the repository.  Push to GitHub and set an issue to indicate that you are ready for this to be graded.
