# Assignment10

When working on this project the first thing we had to do was to find our personal threshold value for labeling our data points as toxic or non-toxic. To find this value our professor suggested us to use the sample CSV that was provided and to do an average of all "yes" labeled toxic comments and "no" labeled toxic comments. The labels of yes and no were pre-determined within the CSV to help us out in finding the threshold value. When working with the CSV there was two things I learned. 

API / CVS Errors

  First when requesting the API from perspective you will have to fill out a survey. When filling out the survey there is a section that requests what language of the API would you want (This is a select all that applies question). For me personally I put English so when I try to find the averages within the sample CSV file I came across an error that was due to the fact that there was other languages within this file, so for me personally I had to get rid of all data points within the sample document that were not English and were not identifiable as English according to the code. (when trying to run this code for yourself if the you have API is able to handle all languages present in the CVS file then keep that section of code commented out or deleted at your preference)
  
  Secondly after getting rid of all the languages that my API cannot handle I learned that from the version of the API I was permitted to use can only handle 60 data points at a time. Due to this I made a secondary data frame that stored the first 30 data points for both yes and no toxic values before proceeding to take the averages to find threshold value.
