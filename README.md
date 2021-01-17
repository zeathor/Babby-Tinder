# Babby-Tinder
Python Jupyter-based code to help you figure out what a good babby name is, based on you and your partner's input. 
ENSURES 'MYSTERY' as it is random if the name you are looking at is one your partner liked or just a random name.
Installation instructions (for Windows):
 - Checkout repository
 - Install some sort of Jupyter distribution (I used Anaconda) and Python3 distribution
 - Fire up a Jupyter instance, and open up the notebook in the repository
 - Ensure you read the first cell and change the relevant settings before execution, particularly the location of the input name lists
 - pip3 install the various packages that you are missing. The main one is pandas, solely to do the data analysis at the end
 
Flow chart of process:
1. Choose a centralised location for csvs, set the corresponding variable (csvDir) to that folder
2. Set your bias threshold for user names. The higher the value, the more often names that have either been user-supplied or that have been rated highly by your partner will appear. Too high a value will mean that they will be overwhelmingly picked, removing much of the mystery. Keep a small value.
3. Download whatever seeding set of names to that folder. Ensure the files are comma delimited, not tab or | delimited. I leave it up to the user to change the delimiter type
4. You can add more seeding sets at any time, just follow subsequent instructions.
5. OPTIONAL - You can also use your own set of names, as well as your partner set. 
5a. Name the csv file <your_name.csv>: order is <name>,<score> where <score> is 0-10. 
5b. Considering you are entering a manual set of names that your partner will view, I would ensure the score for a given name is at least > 0. Otherwise the name will not be shown to your partner
6. Run the first cell, enter in your name at the prompt. This name must be consistent with subsequent executions and any manually entered name lists. It also must be different from your partner name(s)
7. Run the second cell, the metadata tracking cell. This checks the consistency of previous executions and sees if there have been new files added to the seeding list. It asks for the format of the files (the location of the name column) and whether it is a user-defined list, meaning the names will be seen more often.
8. Run the third cell, the actual Tinder-like aspect of the code. Names will be shown to the user ad nauseam, give them a numeric rating out of 10 (or out of the pre-agreed range). 0 is a special case, any name with a rating of 0 will not be shown to your partner (consider it a veto). Type c to exit the loop
9. Repeat steps 6-8 with your partner and rotate as many times as you like. 
10. When ready to analyse the data, change the variables in cell 4 to you and your partner's name and execute. The top set of matching names will be printed, sorted by combined meanAverageError
