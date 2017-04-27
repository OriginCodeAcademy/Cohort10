# Website Scraper

"Web Scraping" is a popular computer software technique of extracting information from the HTML of a website when there is no API available.

For this code test, you will be writing a web scraper that extracts information from a website and converts it into a well formed JSON file.

## Requirements
- Your scraper must download the most recent HTML from the website.
- Your scraper must extract values from the downloaded HTML and convert them into well formed JSON. (See `Expected JSON Output` for the desired format)
- Your scraper must be able to save the JSON to a file named `books.json`.

## Constraints
- You may not pair with a partner for this code test
- You may use Google.
- You may only use NodeJS for this code challenge.
- You must commit whatever solution you have by 12pm Thursday Morning to GitHub.

## URL to Scrape
```
https://originbooks.herokuapp.com/
```
[Click here to visit the webpage](https://originbooks.herokuapp.com)

## Helpful NPM Packages
* `axios` - A package that makes HTTP requests very simple in NodeJS.
* `cheerio` - A jQuery like package that will allow you to fetch values from the HTML string as if you were accessing the DOM in a browser.

## Helpful resources
https://www.codementor.io/johnnyb/how-to-write-a-web-scraper-in-nodejs-du108266t

## Expected JSON Output
```
[
    {
        "name": "Programming Pearls",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/41KHvfm4-fL._AC_UY270_.jpg",
        "author": "Jon Bentley",
        "price": "$28.79"
    },
    {
        "name": "Algorithms to Live By",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51FhJXhhK6L._AC_UY270_.jpg",
        "author": "Brian Christian",
        "price": "$14.99"
    },
    {
        "name": "The Pragmatic Programmer",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/41uPjEenkFL._AC_UY270_.jpg",
        "author": "Andrew Hunt",
        "price": "$31.65"
    },
    {
        "name": "Code: The Hidden Language",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/31Fb8fGBU-L._AC_UY270_.jpg",
        "author": "Charles Petzold",
        "price": "$12.83"
    },
    {
        "name": "Programming Interviews Exposed",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51csf0YWimL._AC_UY270_.jpg",
        "author": "John Mongan",
        "price": "$14.51"
    },
    {
        "name": "Exercises for Programmers",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/513azvyRViL._AC_UY270_.jpg",
        "author": "Brian P. Hogan",
        "price": "$15.83"
    },
    {
        "name": "Algorithm Design Manual",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51uABdrgnrL._AC_UY270_.jpg",
        "author": "Steven S Skiena",
        "price": "$69.99"
    },
    {
        "name": "The Passionate Programmer",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51m3yzmDFCL._AC_UY270_.jpg",
        "author": "Chad Fowler",
        "price": "$20.00"
    },
    {
        "name": "Introduction to Algorithms",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51fgDX37U7L._AC_UY270_.jpg",
        "author": "Thomas H. Cormen",
        "price": "$63.00"
    },
    {
        "name": "Coders at Work",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/41rQjRyMmwL._AC_UY270_.jpg",
        "author": "Peter Seibel",
        "price": "$20.99"
    },
    {
        "name": "Code Complete",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51MEZDyKvZL._AC_UY270_.jpg",
        "author": "Steve McConnell",
        "price": "$23.49"
    },
    {
        "name": "Write Great Code",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/41Rnqj%2BkGDL._AC_UY270_.jpg",
        "author": "Randall Hyde",
        "price": "$17.25"
    },
    {
        "name": "How Software Works",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51qJQPs4tzL._AC_UY270_.jpg",
        "author": "V. Anton Spraul",
        "price": "$14.37"
    },
    {
        "name": "Algorithms",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/41SRhYah3AL._AC_UY270_.jpg",
        "author": "Robert Sedgewick",
        "price": "$57.59"
    },
    {
        "name": "How to Stop Sucking + Be Awesome Instead",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51DAEjoFNtL._AC_UY270_.jpg",
        "author": "Jeff Atwood",
        "price": "$3.99"
    },
    {
        "name": "Clean Code",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51d1qVhmAmL._AC_UY270_.jpg",
        "author": "Robert C. Martin",
        "price": "$30.63"
    },
    {
        "name": "Site Reliability Engineering",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51XswOmuLqL._AC_UY270_.jpg",
        "author": "Betsy Beyer",
        "price": "$24.49"
    },
    {
        "name": "The DevOps 2.0 Toolkit",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/41TWSblk7HL._AC_UY270_.jpg",
        "author": "Viktor Farcic",
        "price": "$29.00"
    },
    {
        "name": "The Go Programming Language",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/510Qib-dSCL._AC_UY270_.jpg",
        "author": "Alan A. A. Donovan",
        "price": "$15.99"
    },
    {
        "name": "How Linux Works",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51Xx8GvPL%2BL._AC_UY270_.jpg",
        "author": "Brian Ward",
        "price": "$19.99"
    },
    {
        "name": "Nine Algorithms That Changed the Future",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/517mmn6wLnL._AC_UY270_.jpg",
        "author": "John MacCormick",
        "price": "$9.99"
    },
    {
        "name": "JavaScript: The Good Parts",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/511j6cza5bL._AC_UY270_.jpg",
        "author": "Douglas Crockford",
        "price": "$13.49"
    },
    {
        "name": "Web Development with Node and Express",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/51L%2Biq%2Bh6EL._AC_UY270_.jpg",
        "author": "Ethan Brown",
        "price": "$16.49"
    },
    {
        "name": "Coding Interview Ninja",
        "imageUrl": "https://images-na.ssl-images-amazon.com/images/I/41NF0fQRIFL._AC_UY270_.jpg",
        "author": "Ekim Ouye",
        "price": "$2.99"
    }
]
```

## Turn in instructions
- Submit your test to GitHub in a repository called `CT-WebScraper`
- [Click here to submit an issue](https://www.github.com/OriginCodeAcademy/2016-CW-SpringCohort/issues/new?title=CT-WebScraping&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20Which%20programming%20language%20did%20you%20use%3F%0A%0A3.%20What%20was%20the%20most%20difficult%20part%20of%20this%20code%20test%3F%0A%0A4.%20What%20feedback%20do%20you%20have%20about%20this%20code%20test%3F))