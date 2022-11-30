# Web Scraping

This topic matters as it relates to learning what is web scraping and how to implement it with python.

---

## What is Web Scraping?

Web scraping aka  web harvesting, or web data extraction, is a technique to automatically access and extract large amounts of information from a website. Web scraping software may directly access the World Wide Web using the Hypertext Transfer Protocol or a web browser. The term typically refers to automated processes implemented using a bot or web crawler. It is a form of copying in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet, for later retrieval or analysis.

## Web Scrape with Python in 4 minutes

> Important notes

* Read through the website’s Terms and Conditions to understand how WE can legally use the data. Most sites prohibit you from using the data for commercial purposes.
* Make sure we are not downloading data at too rapid a rate because this may break the website. You may potentially be blocked from the site as well.

### Inspecting the Website

We need to figure out where we can locate the links to the files we want to download inside the multiple levels of HTML tags. Find the relevant pieces of code that contains our data. We use `inspect` in our browser to locate `.txt` files, usually located inside of `<a>` tags.

### Python Code

#### Import libraries:

```python
import requests
import urllib.request
import time
from bs4 import BeautifulSoup
```

#### Set the url to the website and access the site with our requests library:

```python
url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)
```

#### Parse html with BeautifulSoup:

```python
soup = BeautifulSoup(response.text, "html.parser")
```

#### Use the method .findAll to locate all of our `<a>` tags:

```python
soup.findAll('a')
```

#### Extract the link that we want:

```python
one_a_tag = soup.findAll('a')[38]
link = one_a_tag['href']
```

#### Pause code to avoid spamming the website with requests:

```python
time.sleep(1)
```

- [*source_1*](https://en.wikipedia.org/wiki/Web_scraping)
- [*source_2*](https://towardsdatascience.com/how-to-web-scrape-with-python-in-4-minutes-bc49186a8460)

---

## How to scrape websites without getting blocked

Web scraping is a task that has to be performed responsibly so that it does not have a detrimental effect on the sites being scraped. Web Crawlers can retrieve data much quicker, in greater depth than humans, so bad scraping practices can have some impact on the performance of the site. While most websites may not have anti-scraping mechanisms, some sites use measures that can lead to web scraping getting blocked, because they do not believe in open data access.

#### Best practices to avoid getting blocked:

* Respect Robots.txt
* Make the crawling slower, do not slam the server, treat websites nicely
* Do not follow the same crawling pattern
* Make requests through Proxies and rotate them as needed
* Rotate User Agents and corresponding HTTP Request Headers between requests
* Use a headless browser like Puppeteer, Selenium or Playwright
* Beware of Honey Pot Traps
* Check if Website is Changing Layouts
* Avoid scraping data behind a login
* Use Captcha Solving Services

[*source*](https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)

---

### Things I want to know more about

* I would like to know more about web crawlers and how to web scrape efficiently without getting blocked. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)
