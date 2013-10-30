                CALIFORNIA STATE UNIVERSITY, FRESNO
                                        ASSIGNMENT 4

In this python program you will write a web crawler in Python. Web crawlers are the foundation of all search engines, like Google, Bing, or Yahoo, and start with a URL that you provide and download the HTML page at that URL. The crawler then looks through all of the links in that page and identifies all the HTML pages. These are downloaded, and all their links examined. Real web crawlers, like Google's, will run as robots, continually downloading and parsing pages, and storing new data or updating existing data. 
To avoid downloading lots of pages from the same URL we will randomize the order of the links that we download. We will also introduce a small random delay between each download to ensure that host computers recover and don't immediately block our attempts as a denial of service attack.

Our approach to tackle this problem will therefore follow this outline:

Open a text file that contains one URL per line and one or more lines:
Read the file and store the contents as an array while we have not downloaded 100 web pages and there are still URLs in that array:
Take the first entry from the array
Connect to the web page at that URL
If it is a text/html file: increment the value of our counter. Download the web page at that URL into a file called counter.html (e.g. 1.html, 2.html, 3.html, etc.)And all these are stored in a separate directory.
Store the name of the file that we wrote and the URL that we downloaded it from in a separate file 
If we downloaded a page successfully: open the file parse through the page and extract all the URLs from that page. If we got 1 or more URLs from that page add them to the array of URLs randomize the order of the URLs sleep for 1-5 seconds.

Algorithm:

Step 1: Read in the name of the file into a variable
x=raw input ("Enter URL: ")
print x
Step 2: Create an Array and read the contains of the file into the array
myList = []
file_object=open(x, 'rU')
for line in file_object:
myList.append(line)
Step 3: Loop through each element in the array
while(myList):
myItem = myArray.pop(0)
Print value
Step 4: In your loop read the contains of the URL into a variable
Step 5: Write the data into an local file
Step 6: If more than 100 files have been copied break out of the while loop
Step 7: find URL references in the data from the file
Step 8: add the new URLs to the list
Step 9: randomize the list
Step 10: wait between 1 and 5 seconds.

To run the python program:

I have implemented a web crawler which takes the source url input from a urls.txt file. It then downloads the URL page and traverses the page to find URLs within the page. The script creates two sub directories. One holds all the HTML pages and the other hold a text file which contains information linking the HTML page to the source URL.
Steps to run the script
a) Create a directory for the project. 
b) Inside the project directory create urls.txt file with a URL link in it (Ex - https://news.google.com/)
c) Copy the script to the project directory.
d) Execute the script.

Algorithm:

First, create a PERL file that connects to database. My database file is called websites. DB:
use DBI
$dbh = DBI->connect ("dbi:SQLite:websites.db", "", "", {RaiseError => 1, AutoCommit=>1});
In that database we are going to create a table with three columns: id, url, contents. The first column (id) has the number 1, 2, 3, etc. The second (url) is just the URL, and the third will contain the entire contents of the html file that you downloaded.
First create the database:
$dbh->do("CREATE VIRTUAL TABLE webpages USING FTS3 ( 'id', 'url','contents)
then create a statement that will allow you to store all the data.
$dbh->prepare("INSERT INTO webpages (id, url, contents) VALUES (?, ?, ?);");

As the last step to the first part, you need to write the code that iterates through and loads all the files. You need to read your URL id file using split /\t/ to separate the file into the numbers and the URLs. You need to read the entire contents of the file, which you can do like this:
$contents = join("", (<IN>));

For the second part we are going to write a standalone program that takes a single argument, a word, and returns all the URLs that match that word.

You will need to connect to the database:
$dbh = DBI->connect("DBI:SQLite:websites.db", "", "", {RaiseError=>1, AutoCommit=>1});
prepare a query:
prep = $dbh->prepare("select url from webpages where contents match ?"); then write code to retrieve the matches and iterate through and print out the URLs.


Perl program explanation:

Part 1 of the program will load the data into a SQLite database using PERL,
From the first (python) program we got a output file that contains the URL of a website and the name of a file that corresponded to the web site. 
The first part of the assignment will CREATES the database using the output of the first assignment .urlifo.txt. 
Second part is to make a PERL program that queries the database which allows command line argument to be used as a search term.



