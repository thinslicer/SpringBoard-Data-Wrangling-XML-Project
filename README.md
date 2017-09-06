# SpringBoard-Data-Wrangling-XML-Project
Data Wrangling Project: Using XML Data Files

This assignment involves answering the 4 Data Wrangling questions below based on an xml file

The data file is labled (mondial_database.xml)
The original examples and exercise prompts are in the file (sliderule_dsi_xml_exercise.ipynb)
My answers are located in the file (gia_nguyen_xml_exercise.ipynb) please open using Jupyter Notebook

Q1 To find 10 countries with the lowest infant mortality rates
-I first import lxml package and parse the XML file and print the document in string form to get an idea of the data structure and briefly see the elements of the XML tree
-Then I create a for loop to find the infant mortality rate, child of the element country 
-Then I create a dictionary of countries and corresponding infant mortality rates
-Then I sort the rates to find the lowest 10 

Q2 To find 10 cities with the largest population
-Similar to Q1, I scan the data structure then proceed to find the element 'city' and its subelement 'population' to find the answer
-I created a for loop and then dictionary to convert to a dataframe that is then sorted to show the 10 cities with the biggest populations
-Scanning the data structure shows that there are multiple population years so it's important to get the latest one using 
    temp_pop = int(child.findall('population')[-1].text)
    
Q3 To find 10 ethnic groups with the largest overall populations 
-Similar to Q1 and Q2, I find the 'ethnic group' element in the data file and create a function that add the LATEST population for each ethnic group for all countries 

Q4 To find the Longest River, Largest Lake, and Highest Airport
-After scanning and searching in the data structure (line 34) for the tags river, lake, and airport, I see that each has an abbreviation code for the country it's located in
-I first create a dictionary for a code reference for countries and their codes in the data ex. Albania = 'AL' 
-For the longest river, the tag length is used to find the longest one in the document and then match that with the river name and corresponding country
-For the largest lake, a function is created to calculate the max volumes using area and depth and then loop to find the highest volume then match with corresponding lake name and country
-For the airport with highest elevation, a similar approach with a loop function to find the highest airport is used 
