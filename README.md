<image src="https://ci.appveyor.com/api/projects/status/github/delegateas/Delegate.Office365.Common.WorkflowActions?branch=master&svg=true" />
# Introduction
`Delegate.Office365.Common.WorkflowActions` provides a series of Custom Workflow Actions to supplement the existing actions on SharePoint Online and SharePoint 2013, deployable to any SP.Web as a WSP package.

# Documentation

## Web Services

### Call OData Web Service

Convenience action that automatically appends

```
accept: "application/json;odata=verbose",
content-type: "application/json;odata=verbose"
```

to the header of the HTTP Request, if not present.

>HTTP **%2** to **%1** OData web service with **%3** and **%4** (Output response header: **%5**, response content: **%6**, status: **%7**

* %1 : The fully qualified URI to contact (with protocol specified)
* %2 : The HTTP Verb to use (GET, POST, PUT, DELETE, and so on)
* %3 : Dictionary representing the Request Headers to send
* %4 : Dictionary representing the Request Body to send
* %5 : Resulting dictionary containing the HTTP Response headers
* %6 : Resulting dictionary containing the HTTP Response body
* %7 : Resulting string containing the HTTP Status Code

## Workflows

### Start 2013 List Workflow

>Start SharePoint 2013 List Workflow with Name **%1** (Optionally on list with name **%2**, on item id **%3**)

* %1: Display name of the List Workflow 
* %2: (Optional) Display name of the List. If not specified, action assumes the current list
* %3: (Optional) Integer id of the item in the List. If not specified, action assumes the current item's id.

##### Additional arguments
For debugging purposes, the following additional output parameters may be specified by selecting "Properties..." 

* OutStatusCode
* OutResponseHeaders
* OutResponseBody

These parameters return the HTTP Response to the REST call made to `SP.WorkflowServices`

## String Transformation

### Parse JSON String to Dictionary

>Build Dictionary from Json String **%1** (Output to **%2**)

* %1 : string of valid json data
* %2 : resulting dictionary

### Format DateTime object to string

>Format DateTime object **%1** with formatting string **%2** (Output to **%3**)

* %1 : DateTime object
* %2 : Formatting string (ex: "yyyyMMdd")
* %3 : resulting string

### Check if string contains substring

>Check if **%1** contains substring **%2** and output result to **%3** (Is case sensitive? %4)

* %1 : Source string to search
* %2 : Substring to search source string for
* %3 : Boolean result
* %4 : Boolean controlling case sensitivity of the search

### Check if string starts with substring

>Check if **%1** starts with substring **%2** and output result to **%3** (Is case sensitive? %4)

* %1 : Source string to search
* %2 : Substring to search source string for
* %3 : Boolean result
* %4 : Boolean controlling case sensitivity of the search

### Check if string ends with substring

>Check if **%1** starts with substring **%2** and output result to **%3** (Is case sensitive? %4)

* %1 : Source string to search
* %2 : Substring to search source string for
* %3 : Boolean result
* %4 : Boolean controlling case sensitivity of the search

### Get length of string

> Get the length of string **%1** (Output to **%2**)

* %1 : String to find the length of
* %2 : resulting Integer

### Convert string to upper case

> Convert string **%1** to upper case (Output to **%2**)

* %1 : String to convert
* %2 : String result

### Convert string to lower case

> Convert string **%1** to lower case (Output to **%2**)

* %1 : String to convert
* %2 : String result
