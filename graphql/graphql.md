__| Graphql 
Graphql is query language used by API to access data from the database.
As an alternative to REST, GraphQL lets developers construct requests that pull data from multiple data sources in a single API call.

2 Operations:
1. Query: Only used for reading data
2. mutation: used to modigy data


Syntax:
              query Users{
                    user{
                         name
                         email
                         userid
                         }
                        }


1. Introspection query:
   Whenever we want information like supported query by graphql we use introspection system to do that.
   Introspection gives details about quries, fields, are supported by graphql.

__ (two underscore) indicate the introspection. two underscore are the prefix on introspection queries 
1. __schema:
            Enable use to fetch whole schema. schema gives information about what queries it supports
2. __types:
            
3. __queryType: This tells us what are the available query operation in the schema


Attack:

Tips:
Its always helpfull to navigate /graphql in the web browser some times it gives UI to perform operations.

__| 
Check Introspection is enabled or not.

      query Introspection{
                  __Schema{
                      types{
                        name
                        }
                       }
                      }
                      
__|
IDOR

intercept the api request and change id name

__|
sql injection

We can also try sql injection in graphql


Bonus:

To check availabe query:

       query availableQueries{
             __schema{
             queryType{
                  fields{
                  name
                  }
                 }
                }
               }
               
               
 ####to check available query
 
 
{"query":"\n    query IntrospectionQuery {\r\n      __schema {\r\n        queryType { name }\r\n        mutationType { name }\r\n        subscriptionType { name }\r\n        types {\r\n          ...FullType\r\n        }\r\n        directives {\r\n          name\r\n          description\r\n          locations\r\n          args {\r\n            ...InputValue\r\n          }\r\n        }\r\n      }\r\n    }\r\n\r\n    fragment FullType on __Type {\r\n      kind\r\n      name\r\n      description\r\n      fields(includeDeprecated: true) {\r\n        name\r\n        description\r\n        args {\r\n          ...InputValue\r\n        }\r\n        type {\r\n          ...TypeRef\r\n        }\r\n        isDeprecated\r\n        deprecationReason\r\n      }\r\n      inputFields {\r\n        ...InputValue\r\n      }\r\n      interfaces {\r\n        ...TypeRef\r\n      }\r\n      enumValues(includeDeprecated: true) {\r\n        name\r\n        description\r\n        isDeprecated\r\n        deprecationReason\r\n      }\r\n      possibleTypes {\r\n        ...TypeRef\r\n      }\r\n    }\r\n\r\n    fragment InputValue on __InputValue {\r\n      name\r\n      description\r\n      type { ...TypeRef }\r\n      defaultValue\r\n    }\r\n\r\n    fragment TypeRef on __Type {\r\n      kind\r\n      name\r\n      ofType {\r\n        kind\r\n        name\r\n        ofType {\r\n          kind\r\n          name\r\n          ofType {\r\n            kind\r\n            name\r\n            ofType {\r\n              kind\r\n              name\r\n              ofType {\r\n                kind\r\n                name\r\n                ofType {\r\n                  kind\r\n                  name\r\n                  ofType {\r\n                    kind\r\n                    name\r\n                  }\r\n                }\r\n              }\r\n            }\r\n          }\r\n        }\r\n      }\r\n    }\r\n  ","variables":null}
