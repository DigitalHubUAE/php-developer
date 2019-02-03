# Backend Developer Challenge

As a Backend developer, we need more than making code to create functionality. So this test is going to be split into several sections with a different kind of challenge. As a framework for simplification, we are going to use Laravel 5.7 or Django depending if you choose PHP/Python/NodeJS, MySql/MongoDB as a Database. 

If you have any issue understanding some concepts you can find more information here [PHP The Right Way](https://phptherightway.com/)

## First Challenge

We are going to use Docker for use Nginx/Apache, PHP/Python/NodeJS, MySql, so the first step is to create a new project using Docker together with MySQL. After you finish with the configuration is expected to have a port on your machine running a web server through Docker. We should be able to see a landing page in the browser

#### Considerations
- Create a database
- Use docker compose for handling docker configuration
- You can use the existent configuration on the internet to achieve this step
- MYSql, Apache or Nginx need to run in a docker container 
- One line of code is required to spin up the project, preferable ```docker-compose up -d```


> We are using as example the creation of a Restful API but create a GRAPHQL API with MongoDB is a plus. 


## Second Challenge

Starting with our API we need to create an endpoint, [GET]```/products```, to return all the products available paginated using the https://jsonapi.org/ standards. Our endpoint should be able to receive the max amount of product required and the offset. You should include a minimal version of the product. 

The second endpoint will be [GET]```/products/{id}```, this endpoint will bring all the information related to a product. 

The Product object should be similar to the one as follow. 

```
Product {
  id, 
  sku,
  title, 
  url,
  abstract,
  description,
  price,
  image_url, 
  stock,
  created_at,
  updated_at,
}
```

#### Considerations

- We are not going to use auto-numeric id for our IDS instead we are going to use Universal Unique ID, UUID, you should adjust your models base on this, you can use whatever library you fancy more for this. There is plenty ready to use in Google
 
- Remember to create the migrations using the command line
- Use Seeders to generate at least 100 different products
- You Should throw proper HTTP Errors when the list doesn't have content or when the product that you want to get doesn't exist. The error should be in JSON API standard too


## Third Challenge

We should be able to create new valid product through the endpoint [POST]```/products```, the differenciation about this endpoint and the previous one is that only valid user can create products, use Token Authentication for this endpoint. 

What solution you use for this is up to you. 


#### Considerations 
- Validate the data going in
- Use Event and Listener to encapsulate the product creation logic. 
- No need to update Product, just create new ones. 
- Avoid Product duplication, SKU is a unique value


## Forth Challenge

Test all the things. We are going to focus on functional tests, no need for unit test but will be a plus if is properly implemented and separated from the functional Test.

The scenarios to tests are simple, the possible response for [GET/POST]```/products``` and [GET]```/products/{id}```

#### Consideration
- The tests are going to check only the HTTP responses, so the script needs to run outside of the Docker Containers, without using the database.
- The endpoint can return different results, you need to check if we have some content or not, the content is going to be regenerated so you need to apply certain rules to know if the response is the one expected.
- Remember to Test the different status code, 404 and 422 also need to be cover in the tests. 


## Lately 

Document the project, how to spin up the project, **how to run the tests** and how to generate the database and the dummy content. 

The README file should have all the step to set up the project locally. Remember as less command for set up the project much better. 

After you have the documentation, create a repository in GitLab/Github/Bitbucket and send us the link of the repository to pablo.morales@mailmac.net

The time estimated for the project is between 1 and 5 hours, if you feel that will take more you can cut corners, but that will affect the result of the test. 

We are going to give you feedback as fast as possible. 

