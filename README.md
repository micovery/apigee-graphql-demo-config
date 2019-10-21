## Apigee GraphQL Demo Config


### Description

This repo contains configuration assets meant to be used with the [Apigee GraphQL Demo](https://github.com/micovery/apigee-graphql-demo).
The repo makes use of the [Apigee maven config plugin](https://github.com/apigee/apigee-config-maven-plugin) to create the necessary config assets.


### Prerequisites

 * Deploy the demo [graphql-proxy](https://github.com/micovery/apigee-graphql-demo-proxy) API proxy
 * Deploy the demo [graphql-oauth](https://github.com/micovery/apigee-graphql-demo-proxy) API proxy   

    
### How to deploy it 

To deploy the config assets run the following command:

```bash
mvn install -Ptest \
    -Dusername=$APIGEE_USERNAME \
    -Dpassword=$APIGEE_PASSWORD \
    -Dorg=$APIGEE_ORG
```
This will deploy the configuration assets to the specified $APIGEE_ORG organization under the `test` environment.



### Assets
The following assets will be created in your Apigee organization:
  
* **Product(s)**
    * **graphql-bronze**
    
        This is an API product that provides access to the `graphql-oauth`, and `graphql-proxy`
        endpoints. This product provides rate-limited access to the Ski resorts schema.
    
    * **graphql-platinum**
    
        This is an API product that provides access to the `graphql-oauth`, and `graphql-proxy`
        endpoints. This product provides un-limited read/write access to the ski resorts schema.
        
    * **graphql-admin**
    
        This is an API product that provides access to the `graphql-oauth`, and `graphql-proxy`
        endpoints. This product provides un-limited read/write access to the ski resorts schema 
        including scopes for administrative tasks.
    
    * **graphql-playground**
    
        This is an API product that provides access to the `graphql-oauth`, and `graphql-proxy`
        endpoints. This product provides limited read-only access to the ski resorts schema.


* **Developer App(s)**
    * graphql-peter-app
    * graphql-playground-app
    * graphql-admin-app
    
* **Developer(s)**
    * GraphQL Service (owner of the `graphql-playground-app`)
    * Peter Parker (owner of the `graphql-peter-app`)
    * Miles Morales 


## Not Google Product Clause

This is not an officially supported Google product.
