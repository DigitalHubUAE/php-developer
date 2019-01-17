# Backend Developer Challenge

As a Backend developer, we need more than making code to create functionality. So this test is going to be split into several sections with a different kind of challenge. As a framework for simplification, we are going to use Laravel 5.7, MySql as a Database. 

If you have any issue understanding some concepts you can find more information here [PHP The Right Way](https://phptherightway.com/)

## First Challenge

We are going to use Docker for use Nginx/Apache, PHP 7.1.13, MySql, so the first step is to create a new project with Laravel and serve new project using Docker together with MySQL, the PHP version need to be 7.1.3 or higher. After you finish with the configuration is expected to have a port on your machine running a web server through Docker. We should be able to run php artisan command related with the database in the command line without a problem. 

#### Considerations
- Create a database
- Use docker compose for handling docker configuration
- You can use the existent configuration on the internet to achieve this step
- MySql, Apache or Nginx need to run in a docker container 
- One line of code is required to spin up the project, preferable ```docker-compose up -d```


## Second Challenge

Starting with our API we need to create an endpoint, [GET]```/products```, to return all the products available paginated using the https://jsonapi.org/ standards. Our endpoint should be able to receive the max amount of product required and the offset. You should include a minimal version of the product. 

The second endpoint will be [GET]```/products/{id}```, this endpoint will bring all the information related to a product. 

The Product object should be similar to the one as follow. 

```
Product {
  id, 
  title, 
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

- We are not going to use auto-numeric id for our IDS we are going to use Universal Unique ID, you should adjust your models base on this, you can use whatever library you fancy more for this. There is plenty for PHP 
- Remember to create the migrations using Laravel and the command line
- Use Laravel Seeders to generate at least 100 different products
- Use [Faker](https://github.com/fzaninotto/Faker) to create dummy data
- It's a plus if you use [Fractal](https://fractal.thephpleague.com/transformers/) for the format of the API 
- You Should throw proper HTTP Errors when the list doesn't have content or when the product that you want to get doesn't exist. The error should be in JSON API standard too


## Third Challenge

We should be able to create new valid product through the endpoint [POST]```/products```

#### Considerations 
- Validate the data going in
- Use Event and Listener to encapsulate the product creation logic. 
- No need to update Product, just create new ones. 


## Forth Challenge

Test all the things. We are going to focus on functional tests, no need for unit test but will be a plus if is properly implemented and separated from the functional Test.

The scenarios to tests are simple, the possible response for [GET/POST]```/products``` and [GET]```/products/{id}```

#### Consideration
- The tests are going to check only the HTTP responses, so the script needs to run outside of the Docker Containers, without using the database.
- The endpoint can return different results, you need to check if we have some content or not, the content is going to be regenerated so you need to apply certain rules to know if the response is the one expected.
- Remember to Test the different status code, 404 and 422 also need to be cover in the tests. 



## Lately 

Document the project, how to spin up the project, how to run the tests and how to generate the database and the dummy content. 

After you have the documentation, create a repository in GitLab/Github/Bitbucket and send us the link of the repository to pablo.morales@mailmac.net


We are going to give you feedback as fast as possible. 

