# mcomp_project
Repo for my mcomp project

For instruction on the web applicatino please navigate to the Web Application folder and see the Read Me file.

Within this structure you will find the python scripts in this project inside of the Python Scripts Folder, the files and folders found in here are:

Classifiers - this folder contains both the bespoke created classifier "Project Classifier" and the TextBlob classifier "Text Blob Classifier". 
To be able to run the project classifier one of the training data CSV files will be needed (can be found under CSV Files in the root document) and 
also one of the companies CSV files that has not already been classified (these can be found under Companies Precomputed CSV Files). These files
need to be present in the root of the script that is running and the script has to be modified to run with the csv files chosen. For the
Project Classifier the function that runs takes two arguments, the first is the name of the Companys CSV that has not already been classified
(e.g. google_tweets.csv) the second argument is the name of what the output file will be called. On line 32 of the code it can be seen that
the name of the training data is present when calling another function, if a different training data set is used this value must be changed accrodingly.

The Text Blob Classifier script is much like the pne before but instead does not require training data. The function still takes two areguments,
the name of the file that is to be classified and the name of what the ouptput file will be called.

Data Collection Scripts -  Within this folder is the script that was used to collect positive and negative tweets from Twitter. it can be seen on code line
6, 7, 9 and 10 that the keys are present, these are to a dummy twitter account that was created just for this project. You can see within this file there
is two seperate functions, get_n_tweets and get_p_tweets. Each one is resposible for either obtaining positve tweets or negative tweets. As
can be seen there is a section of using regular expression to remove some of the noice within the tweets, this is the first step of pre processing
in the cycle. At the bottom of the script there is a while loop that loops 100 times before stopping, this calls each function to gather positive and
negative tweets. 

Also within this folder is an obtain_company_tweets script, this was used to obtain tweets that mentioned the company in, to change which
company was being collected the variable company value was change to the releveant one. 

Preprocessing Scripts - The first file in the folder is the merge script. This script was used to merge together the positve and negative csv files
outputted by the obtain_tweets script. Merging the two files together created a the training data that would be preprocessed further, when each
line was being added to the singular csv file their label was added to them.

The next file is no-repats, this script was used to take the data from the training_data csv file and make sure there is no repeating tweets within
it. this was done by a function which takes two arguments, the folder that is being checked and the name of the output file.

The final script, special_char_extraction was used to extract all the weird charaters from the tweets. This was done with an array that was looped
through and if the character is present then it is taken out. The function takes two strings, the first is the file to be preprocessed
and the second is the name of the output file.





  
