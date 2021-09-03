# pangea-react-challenge


React coding challenge is a coding challenge for React developers applying for a job at Pangea Technology.

Notice: You should solve this challenge in an RTL setup.
The api returns arabic text.
Don't spend a lot of time in design , as it is not important for this challenge.

The api documentation can be found bellow 

In this challenge you will build a search using the api search.turath.io

The user will type the search query in a filed and then click a button to start searching. 
Show the reuslts under the search field.

You can pass the search query to the api like this https://search.turath.io?q=بسم الله&page=1
use the `q` param for the query and the `page` param for pagination

In the results you should only show the snipet returend as `snip` from the api.
When clicking on a result it should open a new page showing the text of current page in the book with the page before and the page after.

You can fetch the pages from the api files.turath.io 
like this https://files.turath.io/get.php?action=page&src=30362&pg=14341
the `src` param is the book id returend as `book_id` by the search api. The `pg` param is the page number returend as `page` by the search api.
You should only display page text and ignore the other fields.

In addition you should save the search queries of the user in local stoarge and add an auto suggest feature for his old searches like this

![image](https://user-images.githubusercontent.com/9167620/131968613-7be85807-eff0-48c9-b42b-31ee8e547674.png)



The desgin of the page is not important.



# Mission

- [ ] Generate a react app
- [ ] Copy this README.md to your app
- [ ] add a search text field
- [ ] integreate the search.turath.io api 
- [ ] show the serach results under the search field (only display the snippets)
- [ ] integrate the files.turath.io api
- [ ] On click on a result: show the text of the previous, current and next page
- [ ] Save the history of queries in local stoarge 
- [ ] add autocomplete feature to the search: the source should be the history from local stoarge



# API Documentation

## Search API

search.turath.io

params: 
`q` search query  
`page` for pagination 

example: 

https://search.turath.io/?q=بسم الله&page=2

will return second page of the results for the query `بسم الله` 


The API returns a json object
```json
{
  "data": [...],
  "count": 148757
 } 
```

The search results can be found in the data array 
a page is an object which has many fields
The only ones relevant for this challenge are: 
`page`, `book_id` and `snip`
`page`: page number in the book
`book_id`: The book id (will be later used to fetch the pages)
`snip`: a snippet of the page which should be showed int the search result


## Book pages API

With this api you can fetch pages of a certain book 

files.turath.io

the params of the api are 
`action` and this should always be equal to `page`
`src`: the is the book id
`pg`: is the page number for this specific book

example:
https://files.turath.io/get.php?action=page&src=30362&pg=14341

this will return page number 14341 of the book with the id 30362

The api returns a json object

```json
{
  "text": "the page text",
  "page": "14341",
  "vol":"vol1"
}
```



