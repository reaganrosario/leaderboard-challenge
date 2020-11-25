# Real-time Leaderboard

## Description
A leaderboard is the most commonly used game feature across multiplayer games. Though leaderboard can be of various types and some times customized as per requirement but basic tenant remains same i.e. to rank the players. Providing leaderboard as a service will help any new/old game add this functionality to the game very quickly

Build a leaderboard system where users can compare their performance against other players. Users will want to compare their total score against other players as well as view the leaderboard for specific levels in the game. Finally, a user may want to see all of the scores they’ve received in a particular level.


## Solution hints
<details>
<summary>Click to expand!</summary>
1. Setup an IDE and an AWS account
2. Provision a database (use Aurora Serverless). 
    1. Use the Data API for Aurora serverless to query your database via HTTP. Use AWS SDK for javascript (https://aws.amazon.com/sdk-for-node-js/) with the Data API.
    2. Use Secrets Manager to to save database credentials required for Data API usage.
3. Plan Data Model
    1. Create a data model (you can represent it in form of an ER diagram)
    2. Create your database tables, you can use code to create your database tables. 
    3. Populate the database tables.
    4. Test your data access using the Data API
4. Launch a Elasticache cluster
    1. Launch an Elasticache cluster using the Redis Engine in a private subnet
    2. Configure access to the cluster using security groups for lambda functions.
    3. Test Access to your cluster using code.
5. Design Data Model:
    1. Access Patterns:
        1. Fetch the highest scores for all time;
        2. Fetch the highest scores in the last month;
        3. Fetch the highest scores for a given day.
    2. Use Sorted Sets as data structure
    3. Load Sample data in the Redis cluster.
6. Add Authentication
    1. Add Authentication using Amazon Cognito user pools.
    2. You allow users to register via your application. After they’ve registered, they can login via a client to receive an ID token.
7. Deploy the application
    1. Deploy application to AWS LAmbda
    2. Use Amazon API Gateway yo configure an HTTP endpoint
    3. You can use AWS SAM to manage your serverless application.
8. Detailed setup information: https://aws.amazon.com/getting-started/hands-on/real-time-leaderboard-amazon-aurora-serverless-elasticache/
</details>

## Tags
#leaderboard #aurora #elasticache #cloud9 #cognito #lambda

## Rubric

* All project code is stored in a github repo
* The project uses an in-memory cache such as Amazon Elasticache to perform high volume, low latency leaderboard checks
* Project stores historical data in a relational database such as Amazon Aurora
* Project adds authentication to the application. You allow users to register via your application and then login via a client.
* Application is reliable and highly available.
* Project uses infrastructure as code.
* Project uses SAM to manage serverless application


## Suggested trainings/labs:
* https://awsauroralabsmy.com/index.html
* https://github.com/aws-samples/amazon-S3-cache-with-amazon-elasticache-redis
* https://github.com/aws-samples/reinvent2019-svs217 (SAM Cli)
* https://serverless-idm.awssecworkshops.com/

## Source Code
https://aws.amazon.com/getting-started/hands-on/real-time-leaderboard-amazon-aurora-serverless-elasticache/2/
