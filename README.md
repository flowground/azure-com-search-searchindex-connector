# ![LOGO](logo.png) SearchIndexClient **flow**ground Connector

## Description

A generated **flow**ground connector for the SearchIndexClient API (version 2017-11-11-Preview).

Generated from: https://api.apis.guru/v2/specs/azure.com/search-searchindex/2017-11-11-Preview/swagger.json<br/>
Generated at: 2019-05-07T17:38:48+03:00

## API Description

Client that can be used to query an Azure Search index and upload, merge, or delete documents.

## Authorization

This API does not require authorization.

## Actions

### Searches for documents in the Azure Search index.

*Tags:* `Documents`

#### Input Parameters
* `search` - _optional_ - A full-text search query expression; Use "*" or omit this parameter to match all documents.
* `$count` - _optional_ - A value that specifies whether to fetch the total count of results. Default is false. Setting this value to true may have a performance impact. Note that the count returned is an approximation.
* `facet` - _optional_ - The list of facet expressions to apply to the search query. Each facet expression contains a field name, optionally followed by a comma-separated list of name:value pairs.
* `$filter` - _optional_ - The OData $filter expression to apply to the search query.
* `highlight` - _optional_ - The list of field names to use for hit highlights. Only searchable fields can be used for hit highlighting.
* `highlightPostTag` - _optional_ - A string tag that is appended to hit highlights. Must be set with highlightPreTag. Default is &lt;/em&gt;.
* `highlightPreTag` - _optional_ - A string tag that is prepended to hit highlights. Must be set with highlightPostTag. Default is &lt;em&gt;.
* `minimumCoverage` - _optional_ - A number between 0 and 100 indicating the percentage of the index that must be covered by a search query in order for the query to be reported as a success. This parameter can be useful for ensuring search availability even for services with only one replica. The default is 100.
* `$orderby` - _optional_ - The list of OData $orderby expressions by which to sort the results. Each expression can be either a field name or a call to either the geo.distance() or the search.score() functions. Each expression can be followed by asc to indicate ascending, and desc to indicate descending. The default is ascending order. Ties will be broken by the match scores of documents. If no OrderBy is specified, the default sort order is descending by document match score. There can be at most 32 $orderby clauses.
* `queryType` - _optional_ - A value that specifies the syntax of the search query. The default is 'simple'. Use 'full' if your query uses the Lucene query syntax.
    Possible values: simple, full.
* `scoringParameter` - _optional_ - The list of parameter values to be used in scoring functions (for example, referencePointParameter) using the format name-values. For example, if the scoring profile defines a function with a parameter called 'mylocation' the parameter string would be "mylocation--122.2,44.8" (without the quotes).
* `scoringProfile` - _optional_ - The name of a scoring profile to evaluate match scores for matching documents in order to sort the results.
* `searchFields` - _optional_ - The list of field names to include in the full-text search.
* `searchMode` - _optional_ - A value that specifies whether any or all of the search terms must be matched in order to count the document as a match.
    Possible values: any, all.
* `$select` - _optional_ - The list of fields to retrieve. If unspecified, all fields marked as retrievable in the schema are included.
* `$skip` - _optional_ - The number of search results to skip. This value cannot be greater than 100,000. If you need to scan documents in sequence, but cannot use $skip due to this limitation, consider using $orderby on a totally-ordered key and $filter with a range query instead.
* `$top` - _optional_ - The number of search results to retrieve. This can be used in conjunction with $skip to implement client-side paging of search results. If results are truncated due to server-side paging, the response will include a continuation token that can be used to issue another Search request for the next page of results.
* `api-version` - _required_ - Client Api Version.
* `client-request-id` - _optional_ - The tracking ID sent with the request to help with debugging.

### Retrieves a document from the Azure Search index.

*Tags:* `Documents`

#### Input Parameters
* `key` - _required_ - The key of the document to retrieve.
* `$select` - _optional_ - List of field names to retrieve for the document; Any field not retrieved will be missing from the returned document.
* `api-version` - _required_ - Client Api Version.
* `client-request-id` - _optional_ - The tracking ID sent with the request to help with debugging.

### Queries the number of documents in the Azure Search index.

*Tags:* `Documents`

#### Input Parameters
* `client-request-id` - _optional_ - The tracking ID sent with the request to help with debugging.
* `api-version` - _required_ - Client Api Version.

### Autocompletes incomplete query terms based on input text and matching terms in the Azure Search index.

*Tags:* `Documents`

#### Input Parameters
* `client-request-id` - _optional_ - The tracking ID sent with the request to help with debugging.
* `api-version` - _required_ - Client Api Version.
* `search` - _required_ - The incomplete term which should be auto-completed.
* `suggesterName` - _required_ - The name of the suggester as specified in the suggesters collection that's part of the index definition.
* `autocompleteMode` - _optional_ - Specifies the mode for Autocomplete. The default is 'oneTerm'. Use 'twoTerms' to get shingles and 'oneTermWithContext' to use the current context while producing auto-completed terms.
    Possible values: oneTerm, twoTerms, oneTermWithContext.
* `fuzzy` - _optional_ - A value indicating whether to use fuzzy matching for the autocomplete query. Default is false. When set to true, the query will find terms even if there's a substituted or missing character in the search text. While this provides a better experience in some scenarios, it comes at a performance cost as fuzzy autocomplete queries are slower and consume more resources.
* `highlightPostTag` - _optional_ - A string tag that is appended to hit highlights. Must be set with highlightPreTag. If omitted, hit highlighting is disabled.
* `highlightPreTag` - _optional_ - A string tag that is prepended to hit highlights. Must be set with highlightPostTag. If omitted, hit highlighting is disabled.
* `minimumCoverage` - _optional_ - A number between 0 and 100 indicating the percentage of the index that must be covered by an autocomplete query in order for the query to be reported as a success. This parameter can be useful for ensuring search availability even for services with only one replica. The default is 80.
* `searchFields` - _optional_ - The list of field names to consider when querying for auto-completed terms. Target fields must be included in the specified suggester.
* `$top` - _optional_ - The number of auto-completed terms to retrieve. This must be a value between 1 and 100. The default is 5.

### Sends a batch of document write actions to the Azure Search index.

*Tags:* `Documents`

#### Input Parameters
* `api-version` - _required_ - Client Api Version.
* `client-request-id` - _optional_ - The tracking ID sent with the request to help with debugging.

### Autocompletes incomplete query terms based on input text and matching terms in the Azure Search index.

*Tags:* `Documents`

#### Input Parameters
* `client-request-id` - _optional_ - The tracking ID sent with the request to help with debugging.
* `api-version` - _required_ - Client Api Version.

### Searches for documents in the Azure Search index.

*Tags:* `Documents`

#### Input Parameters
* `api-version` - _required_ - Client Api Version.
* `client-request-id` - _optional_ - The tracking ID sent with the request to help with debugging.

### Suggests documents in the Azure Search index that match the given partial query text.

*Tags:* `Documents`

#### Input Parameters
* `api-version` - _required_ - Client Api Version.
* `client-request-id` - _optional_ - The tracking ID sent with the request to help with debugging.

### Suggests documents in the Azure Search index that match the given partial query text.

*Tags:* `Documents`

#### Input Parameters
* `search` - _required_ - The search text to use to suggest documents. Must be at least 1 character, and no more than 100 characters.
* `suggesterName` - _required_ - The name of the suggester as specified in the suggesters collection that's part of the index definition.
* `$filter` - _optional_ - An OData expression that filters the documents considered for suggestions.
* `fuzzy` - _optional_ - A value indicating whether to use fuzzy matching for the suggestions query. Default is false. When set to true, the query will find terms even if there's a substituted or missing character in the search text. While this provides a better experience in some scenarios, it comes at a performance cost as fuzzy suggestions queries are slower and consume more resources.
* `highlightPostTag` - _optional_ - A string tag that is appended to hit highlights. Must be set with highlightPreTag. If omitted, hit highlighting of suggestions is disabled.
* `highlightPreTag` - _optional_ - A string tag that is prepended to hit highlights. Must be set with highlightPostTag. If omitted, hit highlighting of suggestions is disabled.
* `minimumCoverage` - _optional_ - A number between 0 and 100 indicating the percentage of the index that must be covered by a suggestions query in order for the query to be reported as a success. This parameter can be useful for ensuring search availability even for services with only one replica. The default is 80.
* `$orderby` - _optional_ - The list of OData $orderby expressions by which to sort the results. Each expression can be either a field name or a call to either the geo.distance() or the search.score() functions. Each expression can be followed by asc to indicate ascending, or desc to indicate descending. The default is ascending order. Ties will be broken by the match scores of documents. If no $orderby is specified, the default sort order is descending by document match score. There can be at most 32 $orderby clauses.
* `searchFields` - _optional_ - The list of field names to search for the specified search text. Target fields must be included in the specified suggester.
* `$select` - _optional_ - The list of fields to retrieve. If unspecified, only the key field will be included in the results.
* `$top` - _optional_ - The number of suggestions to retrieve. The value must be a number between 1 and 100. The default is 5.
* `api-version` - _required_ - Client Api Version.
* `client-request-id` - _optional_ - The tracking ID sent with the request to help with debugging.

## License

**flow**ground :- Telekom iPaaS / azure-com-search-searchindex-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
