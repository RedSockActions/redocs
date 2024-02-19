# Configuration
In order to work properly ReDocs needs configuration file

Create a redocs.json file in root of redocs branch

## Example of redocs.json file

```json
{
  "tittle": "ReDocs action",
  "link": "https://raw.githubusercontent.com/RedSockActions/redocs/redocs/",
  "basicPage": "Introduction",
  "sections": [
    {
      "name": "Introduction",
      "link": "/README.md"
    }
  ]
}

```

## tittle
A web page tittle that will be displayed ones redocs is launched

## sections
List of sections with sub folders and files 
that will be accessed (via lazy loading)  
and displayed on a page

## link
A link to place where all the folders and md files are stored

For example (free one) you can use GitHub raw 
as a hoster for all the files. 

In that case, when Introduction document will be opened
ReDocs will try to find it at https://raw.githubusercontent.com/RedSockActions/redocs/redocs/README.md

## basic page
A page that will be displayed by default when root of ReDocs is opened 

