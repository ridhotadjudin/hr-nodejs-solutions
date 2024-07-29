# Express: Pagination Middleware

You have been given the task to write an Express middleware that has to standardize the query, search, and projection parameters for all the endpoints.

The middleware should parse the query parameter from the URL and create an object containing the following properties:

- `page:` The page of the resource to fetch. Defaults to 1. [NUMBER]
- `limit:` The number of items to return in a response. Defaults to 3. [NUMBER]
- `skip:` The actual number of items that have to skip while fetching the data. Its value is ((page - 1) * limit). [NUMBER]
- `searchTerm:` The search term to be used in the data-store query. The term is extracted from the q query parameter. [STRING]
- `search:` A Regex expression that can be evaluated to match the names of the items in the recipes. The search should be global and case insensitive ("gi"). [RegexP]
 

The generated object should then be added to the context property in the Express request object, and the control should be forwarded using the next function.
     

# Express Recipes Filter

The request to the route `/recipes/shopping-list?ids` returns a list of all the aggregated ingredients contained in the matching IDs.