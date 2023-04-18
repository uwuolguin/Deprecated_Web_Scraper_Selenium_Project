Problem Summary:

For its marketing strategies, a company needs to know the price of the models with which it competes in order to establish campaigns and price policies, the problem is that they are so many models, that they have to  buy the database with the prices from an external company that does not always deliver the prices correctly, so they still have to do manual work, which translates into a loss of time and resources.

Challenge:

Find a way to get the correct prices with the least amount of time and money possible.

Solution:

1) The company has the professionals with the knowledge to build webscrapers to get the prices.
2) The company has the possibility to hire interns to do expecific jobs.
3) The company has the URLs with the prices of the models that they are interested in.
4) With points 1,2 and 3, a good solution could be to have a professional developer build the main webscrapers that the company needs (with the help of an intern) and once the scripts are written, hire an intern monthly to maintain or create the web scrapers.


Script Explanation: 

	-This script its only to get prices of Suzuki's motorcycles (BMW, BAJAJ, Royal Einfield, etc. are also companies that could be of interest).

	-Lines 1, 68 and 69 let us export the script to another one if we would have the need to.

 	-Between lines 1 and 10 we import the libraries that we are going to use, which are:

    		-pandas:the URLs come in an excel file which also contains the brand and model of each motorcycle of interest, to retrieve and transform this  			 data into a data frame we use pandas.
   		-selenium: is a web testing library that we can use to access html/css elements that need to be loaded before being displayed to the user.
		-time: We will use this library to make the algorithm stop at each iteration for 2 seconds before starting.
    		-datetime: We will use this library to create a column with the date when the data was obtained.
	
	-In line 12 we use pandas to load the excel file with the URLs.
	-In line 13 we specifically load the sheet "SUZUKI" into a dataframe.
	-Between lines 15 and 21 we  create a dictionary that its going to contain the brand, model, URL, price and  date data for each model of interest.
	-In line 23 we start the iteration for every record that is in the dataframe.
	-Between lines 25 and 30 we try to load the url of the current iteration.
	-Between lines 32 and 36 we find and save the price of the model that we were searching.
	-Between lines 40 and 44 we add all the information that we have to the dictionary created in between lines 15 and 21.
	-Between lines 48 and 52, If we did not find the price, we add all the information that we have to the dictionary created in between lines 15 and 21,		 but the price is going to be a string value.
	-Between lines 57 and 61, If we could not load the page, we add all the information that we have to the dictionary created in between lines 15 and 21, 	 but the price is going to be a string value.
	-In line 63 we transform the dictionary into a dataframe.
	-In line 64 we load a .csv with the historical records of prices into a dataframe.
	-In line 65 we merge the dataframes in line 63 and 64.
	-In line 66 we overwrite the historical .csv with the merged data frame from line 65.
