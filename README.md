## My implementation for *Project HTML/CSS* at the Odin Project - Cloning the layout of Google's Search Results Page

##### Details:  http://www.theodinproject.com/courses/web-development-101/lessons/html-css

This is an implementation of the second, 'difficult' version, mentioned at Odin: Cloning the look (positional layout) of the Google Search Results Page.  

There was a couple of interesting decisions to be made.  I decided to go for what it looks like when nobody is logged in, and I also wanted to recreate as much of the hover effects as possible.

"Why not also implement the actual search??", I thought!  It's probably just a simple API call.

Some research showed Google has a [deprecated Web Search API](https://developers.google.com/web-search/) that they still support.  Initially it seemed like a good choice because of its simple interface and no need for API key.  It turns out though that it embeds it's own UI widgets, so that made it useless.

The [Google Custom Search API](https://developers.google.com/custom-search/docs/tutorial/introduction) is what you're suppposed to use these days anyway.  It allows indexing and searching on your own site, but also you can make calls to search the whole web.  So I implemented basic search functionality for kicks, but the downside is the **requirement of an API key** in *line 16 of my googleSearch.html*.  I will not be checking in my API key to this public repo; you can image why!

So... *no live demo* of this puppy, but if you want to make it work, all it takes is to get your own [API key here](https://developers.google.com/custom-search/docs/tutorial/creatingcse), and pop it in as mentioned above.      



#### Here is a snapshot of the Google results page : 
![Google's Search](http://res.cloudinary.com/techblogpics/image/upload/v1393145445/screenshot-googleSearch_xnn5bt.jpg)

#### Here is my version with same search string : 
![My Search](http://res.cloudinary.com/techblogpics/image/upload/v1393145445/screenshot-my-googleSearch_gfpb5p.jpg)

There are a bunch of interesting little differences.  The most glaring is that Google's search page builds a footer after you run the search, and also puts images and/or ads in a right column... *I'm not trying to go there!*


#### Bugs / Inconsistencies with Google's page:
* Hover over #search-controls input doesnt work, 
	because hover on search button was triggering it when I had the :hover on #search-controls
	so i chose to put the hover on the search button in the css.

* When browsers size is between 856px and 1010px, the Apps-Grid button & Sign-in buttons
	are too far to the right.  C'est la vie.

* Web links red underline is too short.

* Category links show up even if no search has been done!

* More link's triangle should register the mouse-over, not the 'More' text itself!!

* Search Button doesn't do anything.  Have to hit return to kick-off a search.

* Real Search results adds a footer, I dont.

* Redirection to search results page reload results in empty Search input field!

* Hovering over cog button doesn't change opacity of cog image; it should.

* .gsc-control-cse is not responding to my settings, causing too low spacing on search results

* Google's results are certainly a combo of more things than a straight call to the API like I'm making.  Therefore their real results definitely differ - sometimes dramatically, sometimes not.


