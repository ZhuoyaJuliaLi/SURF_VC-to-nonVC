# Julia Li

# Overview:
My project aims to characterize the features of the companies VC focus on when filtering out which companies to invest in. I will perform comparison between VC-backed firms and NonVC-backed firms. 

# Goals of the code:
This ipynb file contains the data collection process since we have limited knowledge on some of the firms. The code is to grab information about each company from the Diffbot API. Besides, another part is using the API to collect patents data from the website named Patentsview. 

# Original input file:
My original input file for the Diffbot API is 500 companies(a testing sample) that went IPO eventually, but there is a variable in the file named VC_dummy where it marked whether each company is supported by the VC or not before going public. With this column, I can compare the two types of companies. There are many variables in the original input file, but the two I used for pulling information from the API are just company names and their founding states. For the Patentsview part, the original input file is the same as the one used for the Diffbot API. I also used the companies' names to find the information about the patents they own. I also regulated the patents information to be inside the time frame from its founding year and the year it went IPO (contained in the original input file), since I only care about its patent performance prior to being public.

# Code content and output result:
With the two characteristics (name and founding state), the API will find the most matching result and return all the information it has on this company. The output is originally in a json output format which was barely human-readable. I transformed to a csv file that can be further used as the dataset for comparing between the VC and nonVC firms. The output csv file contains 500 rows, which represents 500 companies though some of them are empty for being not found in the Diffbot API; and, the file has 68 columns, where each column stands for one piece of information on this company, including indsturies, competitors, yearly revenues, decriptions, etc. Similarly, the patent data returns three columns, the first column is called patents with all the information about the patents a company has; the other two columns are the number of patents in the restricted time frame and the number of patents the company has in total, which is just an integer type of column. This will be useful for simple comparison analysis of the number of patents VC and nonVC firms own.
