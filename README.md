9th of December 2015

#Webpage Optimization

This is a project done by Unnar Thor Bachmann in the Udacity's front-developing course.
This project involves optimizing the web page in the folder.
Two main optimizations were done:

1. Optimize the PageSpeed Insights score for index.html.
2. Optimize frames per second in pizza.html by optimizing main.js (primarly).

The main optimization that were made:

* Minimized the images.
* asynchronized or inlined all render blocking files.
* Deleted all spaces in index.html.

Recieves a PageSpeed Insights score of 94/100 for mobile phones.


##Optimizations made in views/main.js and style.css:


1. Inside determineDx:
   Made the function return 25, 33 or 5 if the value of size was
   1, 2 or 3 respectively.

2. Insice changePizzSizes:
   The for loop was shortened. The dom elements of class
   randomPizzaContainer was calculated once using jQuery function getElementsByClassName. 
   The parameters dx and newwidth were calculated
   only from the first element as percentage.

3. Inside updatePositions and 'DOMContentLoaded' event listener:
   ..* Used 25 dom elements for the small pizzas moving 
      horizontally instead of 200.
   ..* Updated the updatePosition function so that it took an array diffArray 
      which was precalculated in order to skip the % calculations.
   ..* The dom  elements of class mover calculated
      with function getElementsByClassName instead of 
      document.querySelectorAll.

4. CCS speedups:
   Added to the mover class in style.css:
   ```
   translate:transformZ(0);
   will-change:transform;
   ```
##How to run on computer: 

1. Open the index.html file in the project folder in a web browser to run the website.

##How to run the computer on a simple server with ngrok:


1. Install  ngrok (https://ngrok.com/)
2. Install python.
3. Open a shell (on linux and mac) or command line on windows.
4. Open the project folder in the shell and write the command:
```
python -m SimpleHTTPServer 8080`
```
5. Open the project folder in another shell and write the command:
```
ngrok http 8080
```
6. The screen that opens contains the URL.

##How to load on PageSpeed insights:

1. Open the PageSpeed insights page (https://developers.google.com/speed/pagespeed/insights/)
2. Paste the URL given by ngrok into the box.
3. Press the analyze button

