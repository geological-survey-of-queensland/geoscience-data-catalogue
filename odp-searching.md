

# Open Data Portal - SOLR Search Guide

## Simple search guide

Search for a single term such as  **relinquishment**  or  **Northwest**.

Search for a phrase using a group of words surrounded by double quotes such as  **"well completion report"**.

Multiple terms can be combined together with Boolean operators to form a more complex query (see below).

## Advanced search

### Field search

You can search any field by typing the field name followed by a colon ":" and then the term you are looking for. As an example, if you want to search the title and the description field, you can enter:

`title:Cloncurry AND text:"radiometric survey"`

or

`title:"Super Isa Basin" AND "well completion report"`

Note: Since text is the default field, the field indicator is not required.

### Wildcard Searches

To perform a single character wildcard search use the "?" symbol.

To perform a multiple character wildcard search use the "*" symbol.

The single character wildcard search looks for terms that match that with the single character replaced. For example, to search for "text" or "test" you can use the search: te?t

Multiple character wildcard searches looks for 0 or more characters. For example, to search for test, tests or tester, you can use the search:

`test*`

You can also use the wildcard searches in the middle of a term.

`te*t`

Note: You cannot use a * or ? symbol as the first character of a search.

### Fuzzy Searches

To do a fuzzy search use the tilde, "~", symbol at the end of a Single word Term. For example to search for a term similar in spelling to "roam" use the fuzzy search:

`roam~`

This search will find terms like foam and roams.

### Proximity Searches

SOLR supports finding words are a within a specific distance away. To do a proximity search use the tilde, "~", symbol at the end of a Phrase. For example to search for a "apache" and "jakarta" within 10 words of each other in a document use the search:

`"jakarta apache"~10`

### Range Searches

Range Queries allow one to match documents whose field(s) values are between the lower and upper bound specified by the Range Query. Range Queries can be inclusive or exclusive of the upper and lower bounds. Sorting is done lexicographically.

`mod_date:[20020101 TO 20030101]`

This will find documents whose mod_date fields have values between 20020101 and 20030101, inclusive. Note that Range Queries are not reserved for date fields. You could also use range queries with non-date fields:

`title:{Adavale TO Camooweal}`

This will find all documents whose titles are between Aida and Carmen, but not including Aida and Carmen.

Inclusive range queries are denoted by square brackets. Exclusive range queries are denoted by curly brackets.

### Boosting a Term

SOLR provides the relevance level of matching documents based on the terms found. To boost a term use the caret, "^", symbol with a boost factor (a number) at the end of the term you are searching. The higher the boost factor, the more relevant the term will be.

Boosting allows you to control the relevance of a document by boosting its term. For example, if you are searching for

`jakarta apache`

and you want the term "jakarta" to be more relevant boost it using the ^ symbol along with the boost factor next to the term. You would type:

`jakarta^4 apache`

This will make documents with the term jakarta appear more relevant. You can also boost Phrase Terms as in the example:

`"jakarta apache"^4 "Apache SOLR"`

By default, the boost factor is 1. Although the boost factor must be positive, it can be less than 1 (e.g. 0.2)

### Boolean Operators

Boolean operators allow terms to be combined through logic operators. SOLR supports AND, "+", OR, NOT and "-" as Boolean operators(Note: Boolean operators must be ALL CAPS).

The OR operator is the default conjunction operator. This means that if there is no Boolean operator between two terms, the OR operator is used. The OR operator links two terms and finds a matching document if either of the terms exist in a document. This is equivalent to a union using sets. The symbol || can be used in place of the word OR.

To search for documents that contain either "jakarta apache" or just "jakarta" use the query:

`"jakarta apache" jakarta`

or

`"jakarta apache" OR jakarta`

AND

The AND operator matches documents where both terms exist anywhere in the text of a single document. This is equivalent to an intersection using sets. The symbol && can be used in place of the word AND.

To search for documents that contain "jakarta apache" and "Apache SOLR" use the query:

`"jakarta apache" AND "Apache SOLR"`

+

The "+" or required operator requires that the term after the "+" symbol exist somewhere in a the field of a single document.

To search for documents that must contain "jakarta" and may contain "SOLR" use the query:

`+jakarta SOLR`

NOT

The NOT operator excludes documents that contain the term after NOT. This is equivalent to a difference using sets. The symbol ! can be used in place of the word NOT.

To search for documents that contain "jakarta apache" but not "Apache SOLR" use the query:

`"jakarta apache" NOT "Apache SOLR"`

Note: The NOT operator cannot be used with just one term. For example, the following search will return no results:

`NOT "jakarta apache"`

-

The "-" or prohibit operator excludes documents that contain the term after the "-" symbol.

To search for documents that contain "jakarta apache" but not "Apache SOLR" use the query:

`"jakarta apache" -"Apache SOLR"`

Grouping

SOLR supports using parentheses to group clauses to form sub queries. This can be very useful if you want to control the boolean logic for a query.

To search for either "jakarta" or "apache" and "website" use the query:

`(jakarta OR apache) AND website`

This eliminates any confusion and makes sure you that website must exist and either term jakarta or apache may exist.

Field Grouping

SOLR supports using parentheses to group multiple clauses to a single field.

To search for a title that contains both the word "return" and the phrase "pink panther" use the query:

`title:(+return +"pink panther")`

Escaping Special Characters

SOLR supports escaping special characters that are part of the query syntax. The current list special characters are

`+ - && || ! ( ) { } [ ] ^ " ~ * ? : \`

To escape these character use the \ before the character. For example to search for (1+1):2 use the query:

`\(1\+1\)\:2`

## Accessing data through the API (application programming interface)

The open data portal provides an API for developers who want to write code that interacts with the open data portal.

CKAN’s Action API is a powerful, RPC-style API that exposes all of CKAN’s core features to API clients. All of a CKAN website’s core functionality (everything you can do with the web interface and more) can be used by external code that calls the CKAN API.

The Open Data API Guide provides API instruction and examples:  [https://github.com/geological-survey-of-queensland/open-data-api](https://github.com/geological-survey-of-queensland/open-data-api)  .

The full CKAN API user guide is at:  [https://docs.ckan.org/en/2.8/api/](https://docs.ckan.org/en/2.8/api/)

Access to the API does not require authentication.
