# Mars Mission Analysis
The goal of this project was to develop a webpage to present scraped data from several NASA Mars Mission websites. Python with Splinter, BeautifulSoup, and Pandas, and MongoDB were used to scrape and store the required data, and Python with Flask was used to automate those processes. HTML with Bootstrap CSS was used to generate and format the completed webpage presenting the scraped data.

![mission_to_mars](Images/mission_to_mars.png)

---
## Data Sources
* [NASA Mars News Site](https://mars.nasa.gov/news/) 
* JPL Featured Space Image [here](https://www.jpl.nasa.gov/spaceimages/?search=&category=Mars)
* Mars Facts webpage was visited [here](https://space-facts.com/mars/)
* The USGS Astrogeology site [here](https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars) 

---
## Tools Used
* Jupyter Notebook
* Python - Pandas, Browser from splinter, BeautifulSoup from bs4, Flask, PyMongo, Datetime
* PyCharm - Python IDE
* MongoDB
* HTML, CSS

---
## Tasks
### Step 1 - Scraping
1.  

Initial scraping was completed by using Jupyter Notebook, BeautifulSoup, Pandas, and Requests/Splinter.  The Jupyter Notebook file was called `mission_to_mars.ipynb`.

### NASA Mars News

* The latest news title and paragraph text were scraped from the [NASA Mars News Site](https://mars.nasa.gov/news/) 

### JPL Mars Space Images - Featured Image

* JPL Featured Space Image [here](https://www.jpl.nasa.gov/spaceimages/?search=&category=Mars).

* Splinter was used to navigate the site and find the image url for the current Featured Mars Image. The url string was saved to a variable called `featured_image_url`.

### Mars Facts

* The Mars Facts webpage was visited [here](https://space-facts.com/mars/).  Pandas was used to scrape the table containing facts about the planet including diameter, mass, etc.

* Pandas was used to convert the data to an HTML table string.

### Mars Hemispheres

* The USGS Astrogeology site [here](https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars) was visited to obtain high resolution images for each of Mar's hemispheres.

## Step 2 - MongoDB and Flask Application

MongoDB with Flask templating was used to create a new HTML page that displays all of the information that was scraped from the URLs above.

* The Jupyter notebook was converted into a Python script called `scrape_mars.py` with a function called `scrape` that executed all of the scraping code from above and returned one Python dictionary containing all of the scraped data.

* A route was created called `/scrape` that imported `scrape_mars.py` script and called the `scrape` function.

* Return value stored in Mongo as a Python dictionary.

* A root route `/` was created that queried the Mongo database and passed the mars data into an HTML template to display the data.

* A template HTML file called `index.html` was creted that took the mars data dictionary and displayed all of the data in the appropriate HTML elements. 

* Bootstrap was used to structure the HTML template.

![final_app_part1.png](Images/final_app_part1.png)
![final_app_part2.png](Images/final_app_part2.png)



