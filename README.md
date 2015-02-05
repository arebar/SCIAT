# SCIAT
#R script for scoring SCIAT data

Scores a folder full of Single-Category Implicit Association Tests

SCIAT.score automates the scoring of a folder full of individual Single-Category Association Test scores. It outputs the D score with split scores for reliability (Greenwald, McGhee, & Schwartz, 1998) and the Information Processing Score (Rebar, Ram, & Conroy, 2014).

#usage
SCIAT.score(folder)

#arguments
  {folder}
  
#details
All you need to run this package is the path file of a folder which only includes .csv files as ouputted from DirectRT (or formatted in the same manner). The name of the files will be used as the id number in the output, so make sure they each have individual names.

You will also need to install the R packages: 'plyr', 'VIM', and 'gdata'.

Use the function file.choose() if you need to find the path file for the folder with the data (just select a .csv file within the folder for the function and then copy and paste the file path excluding the file name)

Data format: Variables needed: 'RT' = response time (in ms), 'Block' = which block it is with 2 & 4 being the compatible and incompatible test trials, respectively), 'Correct' = whether the respondent selected the correct button for each trial (True/TRUE and False/FALSE), 'Trial' = Number of trial; is only used for randomization of the split reliability scores, so it should NOT be the order of the trial because trials should be ordered randomly (so basically it's a random value for each trial between 1-72 for each test block)

If there is missing data in the output for an individual, check the original file to make sure it has full data in it (most important is that it has 72 trials for Block 2 and Block 4).

#value
You will be provided with ouput containing id = identification number (the name of each file), d = Greenwald's d score, reld1 = the first split-half d score to calculate reliability with, reld2 = the second split-half d score to calculate reliability with, tooTiny = how many trials people responded faster than 100 ms, tooLittle = how many trials people responded faster than 1.5 times their first (25 percent) interquartile range, tooBig = how many trials people responded slower than 1.5 times their last (75 percent) interquartile range, IP = Rebar et al.'s information processing score

#references
Greenwald, A. G., McGhee, D. E., & Schwartz, J. L. (1998). Measuring individual differences in implicit cognition: the implicit association test. Journal of Personality and Social Psychology, 74(6), 1464-1480.

Rebar, A. L., Ram, N., & Conroy, D. E. (2015). Using the EZ-diffusion model to score a Single-Category Implicit Association Test of physical activity. Psychology of Sport and Exercise, 16, 96-105.

#author
Amanda L. Rebar

#examples

SCIAT.score("/Users/me/Desktop/sciat data/")
