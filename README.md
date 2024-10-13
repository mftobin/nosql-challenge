# nosql-challenge

To complete the setup_starter, I referenced the following class activities:
- 12.1.05 Ins_ImportData
- 12.2.04 Stu_PyMongo_with_Imported_JSON_data
- 12.2.03 Ins_PyMongo_with_Imported_CSV_data
- 12.2.10 Stu_SortAndLimitPets
- 12.3.6-8 Mongo_Mini_Projects

Error handling:

In the setup_starter, part 2 question 2, at first I wasn't getting any results because I was using BusinessTypeID for my query instead of BusinessType. I figured it was a typo, but I ran this through XPert Learning Assist to find my error.

For part 2, question 1, at first I created a dictionary with only the information I had. I did not have all of the information for this new restaurant, so I filled out the dictionary with the sections I knew based on the restaurant name and location. I hoped this would leaves the additional sections blank when I add this new restaurant to the collection, however when I went to update the BusinessTypeID, it wouldn't add it because it wasn't a field in the document. I went back and deleted the Penang Flavors document and reran my code with the additional blank sections.

I also had to troubleshoot some issues where it seemed like the new restaurant was not being updated. This is because I was not spelling Penang Flavours consistently with the British spelling "Flavours" instead of "Flavors".

Part 2, question 5 problem solving sections:

# Checking coordinates and rating values are now numbers
# import pandas as pd
# dtypes_df = pd.DataFrame(list(establishments.find()))
# dtypes_df.dtypes

I tried this above method first, but since longitude and latitude are subcategories of geocode, they did not pull through as specific columns once establishments was turned into a dataframe.

When I pulled a sample of documents from establishments and used a for loop to check their types, I confirmed that longitude/latitude was showing as floats and RatingValue was showing as an integer. I used Xpert Learning Assist to help with formatting this code.

## Analysis Notes

Question 2:
When searching by "LocalAuthorityName":"London", I got zero results because the LocalAuthority name is longer than just "London" so I used $regex to match it to results that included London.

Question 3:
The documentation did not have a latitude and longitude for Greenwich, however, I looked it up online to confirm my values. It's a fun Easter Egg to use Greenwich because Greenwich is the site of the Royal Observatory where time and place are measured from around the world.
*** I made this more complicated than it needed to be because the latitude and longitude were listed on Canvas, however, that location is actually Plumstead and not Greenwich itself which is about 4 miles away. Not far, but it makes a big difference for a densely populated urban area like London!

Question 4:
I referenced the mongo_mini_project and the class notes for completing this question.