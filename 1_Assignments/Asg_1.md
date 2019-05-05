
# Assignment1: Unix, git, and Sequence Alignment Assignments (20 pts possible)
__Full Name:__ Chad Pittman  
__Student ID:__ 914960676
## Markdown  

  #### Fellow Studnet
  Name: Samvardhini (Sam) Sridharan  
  Major: **Genetics and Genomics**  
  Year: _3rd year (junior)_  

  | Location | Start Year | End Year |
  |:---------|:---------|:---------|
  | Chennal, India | 1998 | 2000 |
  | Fremont | 2000 | 2004 |
  | San Jose | 2004 | 2019 |

  Likes:
  * books
  * podcasts
  * documentaries

  [Click here to see one of her favorite podcast site][1]

  [1]:https://www.nosuchthingasafish.com/

## __Unix__

        date "+%Y-%m-%d %H:%M:%S" 
        2019-04-19 12:44:24

        date "+%A" 
        Friday

## ____Git____
Paste the URL for the shared github repository that you created with your lab partners here.  Use proper markdown formatting: [RRKPK Repository](https://github.com/rabednorz/RRKPK.git) 
Paste the saved output of the `git log` command here (format as a code block)
```



[Click this link for ther GitHub account with shared file](https://github.com/cwpittman/sharedFiles)

    commit 2e0938ba53976156acf9a423a7779dc27f0a4692 (HEAD -> master, origin/master)
    Author: fakeuserfor180L <chadwpittman.bills@gmail.com>
    Date:   Mon Apr 15 17:26:19 2019 -0700

        adding more info yada yada

    commit 5fedddd546143cd67b55c8f8688dc5e602413e97
    Author: Chad Pittman <cwpittman@ucdavis.edu>
    Date:   Mon Apr 15 16:42:08 2019 -0700

        notes from personon one

## ____Sequence Alignment____  

*_Please answer the following questions Be clear and concise with any written answers._*

 Unless otherwise noted we are not requiring you to include your code here.  However, I advise that you record it in a separate Markdown file for your reference.  That way if you need it again (e.g. for the midterm) you have a record of what you did  

__1.__  ____Paste in the result of the `ls -lR Data` command performed at the beginning of the Sequence_Alignment exercise that shows the aliases (symbolic links).  Format this as a code block.____ 
      
        Data:
        total 8
        drwxr-xr-x 4 ubuntu ubuntu 4096 Apr  11 21:23 Sequences/
        drwxr-xr-x 5 ubuntu ubuntu 4096 Apr  11 21:23 Species/

        Data/Sequences:
        total 8
        drwxr-xr-x 2 ubuntu ubuntu 4096 Apr  11 21:25 Genome/
        drwxr-xr-x 2 ubuntu ubuntu 4096 Apr  11 21:25 Proteome/

        Data/Sequences/Genome:
        total 354180
        -r-xr-xr-x 1 ubuntu ubuntu 121183082 Apr  11 21:29 A.thaliana.fa*
        -r-xr-xr-x 1 ubuntu ubuntu 101957874 Apr  11 21:30 C.elegans.fa*
        -r-xr-xr-x 1 ubuntu ubuntu 139534256 Apr  11 21:30 D.melanogaster.fa*

        Data/Sequences/Proteome:
        total 57232
        -r-xr-xr-x 1 ubuntu ubuntu 13992864 Apr  11 21:32 A.thaliana.fa*
        -r-xr-xr-x 1 ubuntu ubuntu 10643447 Apr  11 21:33 C.elegans.fa*
        -r-xr-xr-x 1 ubuntu ubuntu 33963228 Apr  11 21:33 D.melanogaster.fa*

        Data/Species:
        total 12
        drwxr-xr-x 2 ubuntu ubuntu 4096 Apr  11 22:01 A.thaliana/
        drwxr-xr-x 2 ubuntu ubuntu 4096 Apr  11 22:01 C.elegans/
        drwxr-xr-x 2 ubuntu ubuntu 4096 Apr  11 22:01 D.melanogaster/

        Data/Species/A.thaliana:
        total 8
        lrwxrwxrwx 1 ubuntu ubuntu 61 Apr  11 22:03 genome.fa -> /home/ubuntu/Assignment_1/Data/Sequences/Genome/A.thaliana.fa*
        lrwxrwxrwx 1 ubuntu ubuntu 63 Apr  11 22:03 proteome.fa -> /home/ubuntu/Assignment_1/Data/Sequences/Proteome/A.thaliana.fa*

        Data/Species/C.elegans:
        total 8
        lrwxrwxrwx 1 ubuntu ubuntu 60 Apr  11 22:04 genome.fa -> /home/ubuntu/Assignment_1/Data/Sequences/Genome/C.elegans.fa*
        lrwxrwxrwx 1 ubuntu ubuntu 62 Apr  11 22:05 proteome.fa -> /home/ubuntu/Assignment_1/Data/Sequences/Proteome/C.elegans.fa*

        Data/Species/D.melanogaster:
        total 8
        lrwxrwxrwx 1 ubuntu ubuntu 65 Apr  11 22:09 genome.fa -> /home/ubuntu/Assignment_1/Data/Sequences/Genome/D.melanogaster.fa*
        lrwxrwxrwx 1 ubuntu ubuntu 67 Apr  11 22:12 proteome.fa -> /home/ubuntu/Assignment_1/Data/Sequences/Proteome/D.melanogaster.fa*


__2.__ ____Paste in the markdown table from the lab manual that includes for each genome:____

| Organism | Size of File in bytes * | Chromosome # ** | Genome bp # | # protein coding genes | Average Protein Length |
|:------|:------|:------|:------|:------|:------|
| D.melanogaster  | 98M | 8 | 137567484 | 30553 | 660  |
| A.thalinana     | 116M | 7 | 119667750 | 27655 |  400 |
| C.elegans       | 134M | 7 | 100286401 | 20191 |  403 | 

_* The file size is of raw size with headers and not limited to just sequenc as others had disucssed this might be asking for._  
_** Includes mitochondrial Chromosomes_**  

          grep '^[GATC].*' C.elegans-Proteome.fa | awk '{sum+=length($0)}END{print sum/NR}'

__3.__ ____How do you know that when you use `shuffleseq` that the sequences have the same exact composition?____

You can verify it by using the **_diff_** command against the two sequences. That is, against the original sequence and the randomized one. If there is any difference between them, the command will reply with a report. It will not reply anything if there is no differnence, just like when you enter in your password in correctly you get no responce acknowledging it. Compseq was utilized in this following command as well.
ex--    

      _diff seq.comp seq.shuffle.comp_

__4.__ ____Create a text based "histogram" as described in the lab manual that shows the distribution of scores when aligning shuffled sequences.____


                    1 19.0
                    8 20.0
                   27 21.0
                   48 22.0
                   97 23.0
                  106 24.0
                  126 25.0
                  138 26.0
                  102 27.0
                   75 28.0
                   79 29.0
                   69 30.0
                   73 31.0
                   85 32.0
                  107 33.0
                   96 34.0
                  113 35.0
                  106 36.0
                   91 37.0
                   78 38.0
                   67 39.0
                   71 40.0
                   41 41.0
                   48 42.0
                   38 43.0
                   28 44.0
                   18 45.0
                   14 46.0
                   10 47.0
                    9 48.0
                   14 49.0
                    4 50.0
                    5 51.0
                    2 52.0
                    2 56.0
                    2 60.0
                    1 62.0
                    1 70.0
                    

__5.__ ____Is the shape of the curve normal? Do you expect it to be normal?____  

No. It is a skewed curve that trends towards the lower scores around 20 to 30. This is expected as the measurements are scores of simmilarity. And since they are randlomly scattered, they should generally be low in similarity. So low scores in this range are expected to be common as some will randomly match, but not most of the time. If I was expecting a high similarity (ie. close evolutionary relation between two species) then I would expect a higher percentage nuber in comparison between the two organisms. Not the case for the 1 thousand random generations.
  
__6.__ ____Perform the experiment 3 more times with a different 1000 shuffled sequences. Create a table using markdown with the mean, mode and median for each run (include your first run for a total of 4 runs).____  

| Run | Mean | Mode | Median |
|:-----|:-----|:-----|:-----|
| 1 | 37.755 | 37   |36 |
| 2 | 37.652 | 37   |35 |
| 3 | 37.895 | 37   |36 |
| 4 | 37.695 | 37   |37 |



__7.__ ____What would be the effect of doing more than 1000 shuffled sequences?____

  The averages calculated would become more and more simmlar upon a true avarage by the law of large numbers. Currently they are pretty close, but done to 10 thousand times, they modes and medians would likely be the same and the mean would be the same into or past the thousands place as well.
  
  
__8.__ ____Search the ce1 sequence against a shuffled version of the same sequence (ce1) and report the average score.____

ce1 compared against the shuffled version of ce1 was 40.5

__9.__ ____Does amino acid composition affect the scores?  To find out, create a fake protein sequence where the last half of ce1 is replaced with Qs. Now make a shuffled version of this to distribute the Qs around. Align this sequence to the ce1 and at1 sequences and report the alignment score. ____
  
ce1 gave 33  
at1 gave 46

__10.__ ____Create 1000 shuffles of the Q-enriched sequence above and report the average score.____

The Q-enriched average socre was 39.753

__11.__ ____Briefly discuss parts 8-10 with respect to how sequence composition affects score. (*2pts*)____

When composition of two sequences are the same, the odds of their maching against one another is higher as their are an equal amount of amino acids in each comparison. The only variable is the alignment of them. this was noted in question 8. For a change in composition (as displayed when you swap out half the amino acids for all Q's), the change of the scores also changs according to the amount of Qs in each of the compared alignments. Though the protien that I changed in the start was from ce1, it turns out that at1 had a higher concentration of Q amino acids and thus had a hgiher probability of matchnig. this explains the higher than expected score between the modified protien and at1. Generally, the relationship between two sequences with the same amount of amino acids being compared vary in score accourding to how simmilar the overall compositions between the two are. This will fluctuate around the score generated when comparing the true sequence and the randomized sequence.  

__14.__ ____Starting with the C. elegans B0213.10 protein, find the best match in the A. thaliana and D. melanogaster proteomes with `water`. Record their alignment scores, percent identities, and protein names here.  (Use a markdown table!)____

| Species | Score | % Identity | Protein |  
|:-------:|:-------:|:-------:|:-------:|
| A. tha | 337.0 | 28.2 | AT2G23190.1 |
| D. mel | 333.0 | 26.3 | FBpp0074380 |


__15.__ ____What is the expected (average) score of each pairwise alignment
at random? (Perform some shuffled alignments to get an idea of what the
random expectation is).____  

| Species | Average |
|:-------:|:-------:|
| A. tha | 35.511 |
| D. mel |35.152 |

__16.__ ____How many [Z-scores](https://www.statisticshowto.datasciencecentral.com/probability-and-statistics/z-score/) away from the mean is the best alignment?  If you know how to use R to do this, great.  If not you will learn in the next couple of weeks.  In the meantime, you can use "LibreOffice Calc" on your instance (Applicatoins > Office > LibreOffice Calc), or an online calculator to calculate the mean and sd of your alignments.  [mean](https://goodcalculators.com/statistics-calculator-graph-generator/) [sd](https://goodcalculators.com/standard-deviation-calculator/) [Z](https://goodcalculators.com/z-score-calculator/)____

| Species | Mean | Standard Deviation | Z-score |  
|:-------:|:-------:|:-------:|:-------:|
| A. tha | 33.548 | 5.12 | 62.4899 |
| D. mel | 33.753 | 5.095 | 61.5581 |

__17.__ ____Briefly discuss the statistical and biological significance of your results.____

I found the method of determining statistically significant similarity of a protien in its relation another protien in another species most impressive, though I am sure it is more common place than I am used to. The average (mean) of the suffled versions of the protiens represent a comparable set of unrelated protiens and what a score of such a protien would be. In my case, it was around 33. So to compare another protien that you want to know if it is similar, you would need to see how far away it was from this average. And to grasp the magnitude of distance or lack of from random chance (or in our case dissimilarity) you would want the protien you are compareing to be many standard deviations away from the determined average. That would be determined by the z-score. And since both socres were in the 60's in distance. it implies a great distance away from random chance. It could be inturpreted that they are both considered simmilar to the protien sequence and statisticly significant. This translates into the idea that these protiens are more or less the same accorss the speecies. Though there might be some post translational modifications and thus we cannot say they the purpose of these protiens are used the same way, we can say that the protiens seem to be highley conserved and thus have stayed preserved across much evololution. 
