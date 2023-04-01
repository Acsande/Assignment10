# Assignment10

Summary

  The goal of this assignment is to explore the concept of bias through querying an existing natural language processing model — specifically, the Perspective API released by Google Jigsaw. For this assignment, you will need to examine a dataset of internet comments and their scores, in addition to formulating your own queries and using the Perspective API client to score the toxicity of each comment.

Content warning: the Perspective API is designed for use in content moderation, and the dataset contained very “toxic” comments. Some of the comments in this dataset are racist, sexist, ableist, and offensive. Some comments contain profane language. If you are uncomfortable with exposure to these comments in the manner of this assignment, please let me know by 03/24/2023 and we will work on finding an alternative approach.

Working With Sample CSV

  When working on this project the first thing we had to do was to find our personal threshold value for labeling our data points as toxic or non-toxic. To find this value our professor suggested us to use the sample CSV that was provided and to do an average of all "yes" labeled toxic comments and "no" labeled toxic comments. The labels of yes and no were pre-determined within the CSV to help us out in finding the threshold value. When working with the CSV there was two things I learned. 

API / CVS Errors

  First when requesting the API from perspective you will have to fill out a survey. When filling out the survey there is a section that requests what language of the API would you want (This is a select all that applies question). For me personally I put English so when I try to find the averages within the sample CSV file I came across an error that was due to the fact that there was other languages within this file, so for me personally I had to get rid of all data points within the sample document that were not English and were not identifiable as English according to the code. (when trying to run this code for yourself if the you have API is able to handle all languages present in the CVS file then keep that section of code commented out or deleted at your preference)
  
  Secondly after getting rid of all the languages that my API cannot handle I learned that from the version of the API I was permitted to use can only handle 60 data points at a time. Due to this I made a secondary data frame that stored the first 30 data points for both yes and no toxic values before proceeding to take the averages to find threshold value. (change this portion of the code as see fit to your API)

Research and Findings

  To start off as I was looking through the sample CSV I often see comments that had curse words labeled as toxic but the comments I saw out of the many that were there were only negative comments. This brought me to the hypothesis Perspective will be less likely to mark comments with cuss words as toxic when those comments are positive. If this was proven to be true that could mean that perspective API is biased towards positive comments as non-toxic.

  To test this hypothesis I created a date set with 60 data points. The data set has four categories positive, positive with cuss word(Positive+Cuss), negative, negative with cuss word(Negative+Cuss). Each category had 15 data sets and for each data point in positive had a similar meaning comment in Positive+Cuss. The same goes for negative. Afterwards I created a column called score which had their toxicity value predicted by Perspective. Afterwards I created a column called toxic which had values of yes, no and unsure. These values are determined based off of the threshold value. Unsure is only given if it is not within the ranges of yes or no. Next I created a bar graph that had each category with its distribution of yes, no and unsure.
 
The results was as follows.
  
  Negative
    yes - 0
    no - 5
    unsure - 10
    
  Negative + Cuss
    yes - 15
    no - 0
    unsure - 0
    
  Positive
    yes - 1
    no - 14
    unsure - 0
    
  Positive + Cuss
    yes - 9
    no - 0
    unsure - 6
  
  
  Based off of these results we can see that there is some form of code in place that tries to notice toxic comments that do not contain cuss words shown in Negative category. This means that the perspective API does not identify cuss words as the only trait of toxicity. The next category negative + cuss fully shows that cuss words are highly considered toxic. No for a section positive we would assume that no comments would be labeled toxic if anything maybe unsure. But as we can see there was one comment in particular that was labeled as toxic. When looking into the output of the data frame we can see that the only comment in positive that was labeled toxic was "you have a good looking butt". This brings me to speculate that may be perspective has a bias towards the word butt as you can clearly see that it was not used in a negative connotation whatsoever here. If I was to speculate two things come to mind first the API may see this as harassment or secondly there may be a hidden bias towards females. Lastly we can see that API did a good job at labeling most of the Positive + Cuss as yes, but it's still missed a little over a third of the data points for that category. My theory of why the API marked sixth of them as unsure is possibly due to two reasons. The first assumption is that maybe certain words hold a greater value when hiding toxicity for example some of the data points that were unsure had more intense positive words such as awesome, amazing, love. The second assumption is the fact that most of them that were marked unsure also use the word fucking. This brings me to the possible conclusion that may be the API has some statistics about that word being used mostly in nontoxic context majority of the time. This project has led to some interesting findings that will be left on answered until further research is done.
