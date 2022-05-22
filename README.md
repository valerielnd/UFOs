# UFO Analysis

## Project Overview

This project aims to build a table to organize and neatly display UFO data stored 
as a JavaScript array. In addition, this table will have the ability to filter data based on specific criteria. 
For example, users can refine their search on more than one level, such as countries or cities. 
The table will be inserted into and visually displayed by an HTML page built and styled using basic HTLM, 
Bootstrap and CSS.

The list of deliverables for this project is:
- Filter UFO sightings on multiple criteria
- A written report on the UFO analysis (README.md)


## Resources

The data that will be displayed in the table is stored as a JavaScript array in the file [data.js]()

We will use JavaScript as the primary coding language to create the table. The code to build the table will be
contain the file [app.js]().

We will use basic HTLM, Bootstrap, and CSS to build and style the HTML page where the table will be visually displayed: 
[index.html]()

[style.css]()

## Analysis results

### Storyboarding 

Before building the website, we decided to plan it out. Using a storyboard and mapping the elements out beforehand 
made it easier to assemble them later.

As the goal is to create an interactive webpage that allows readers to parse the data around UFO sightings, 
it should let users view the article title and paragraph and then the data in a dynamic table with a filter section.

Hence, the web page has the following layout:

![storyboard]()

### Build the dynamic table

Once the template for the web page had been created, we started coding the JavaScript portion to build the table.

To proceed, we created the function buildTable() that will receive as a parameter a variable that references the data 
imported from the file data.js, iterate through the array of objects, and append them to a table row.

The function will be used to do the following:

* Looped through each object in the array using a forEach function. 
* Appended a row to the HTML table.
* Added each value from the object into a cell.

![build_table]()

### Filter the table

The table we created displayed every object in the data.js file making every sighting information available.
However, since there are a lot of objects, the table is enormous and is entirely too much for one person to 
reasonably look through and study.

Therefore, we created two other functions updateFilters() and filterTable(), to add the ability to filter the 
data for multiple criteria simultaneously, such as date, city, state, country, and shape.

In the function updateFilters(), we use D3.js to select the element, value, and id of the filter changed by the 
user. So, if a search criterion is entered, the "id" and the value that was entered are stored in a global variable 
"filters" used to keep track of all the elements changed. Then, the function filterTable() is called inside 
updateFilters() to filter the table data by the value entered for the "id" that has changed.

![update_filters]()

![filter_Table]()

To complete the script's code in app.js, we added the following line of code to create an event listener that 
detects a "change" on each input element and calls the updateFilters() function:

![event_listener]()

Before building the HTML web page, the final step is to make sure the table loads as soon as the page does so 
that users will see the original table to begin using the filter we've set up. To achieve this, at the very 
end of the code, we called the buildable function using the original data we've imported:

![original_table]()

### Build the HTML page to showcase the table

Using the different ids created in app.js and the storyboard, we build the web page in the index.html file.

We set the document's title to "UFO Finder" and added links to Bootstrap's content delivery network (CDN) 
and the stylesheet in the web page head section.

In the body, we established a navigation bar using a nav tag with a "navbar navbar-expand-lg" class. 
Then as seen in the storyboard, to display the article title and paragraph, we created a div with 
a class of "container-fluid," and then nested a row within it with two columns, one for the title 
and the second for the paragraph.

To create the filter portion of the web page, we added a new fluid container and nested a row inside it. 
In this row, there are two columns, one for the filter displayed as an unordered list and another one for 
the table data.

Finally, to add the data, at the bottom of the page, under the last <div /> tag, we added the scripts in the
following order:

* A link to a D3.js CDN
* The file path to data.js
* The file path to app.js

[index.html]()

### Using the seach criteria

Once the page is loaded, as explained previously, the user can see the navigation bar followed by the article title
and paragraph.

![first_section]()

In the last part of the web page, the user has access to the table of UFO data and the filter section.

When the web page is first loaded, all fields are empty with the information entered as placeholders in the background.

![filter]

Filtering the table by multiple criteria needs to be done gradually. For example, if the users need to filter by state and city, 
they need to enter first the state and click outside the input area or press enter to display the results for that specific state:  

Then, they need to enter the city and again click outside the input area or press enter to display the results for that specific 
state and city:

If the users want to get back to the original table, they can refresh the web page or manually remove all search criteria entered.







