
# Payment_App_futures

this is a basic Payment app consists of basic futures

1) one can add amount int thiwe wallets by hitting the dummy webhook after it redirects to hdfc/axis Payment gateway

2) users can send money to each other

3) user can see the transaction status.

# Technologies used

1) used NEXT.js for frontend and backend
2) created a dummy bank webhook using EXPRESS.js
3) used PRISMA as ORM and POSTGRESS database
4) NEXT_AUTH for authentication (Signin/signup).
5) created a CI pipeline using github to ensure faster pullrequest and efficient collbaration
6) used turborepo to manage toplevel dependiencies mainly ZOD validation.
7) created a DOCKER IMAGE and posted in DOCKERHUB

# why questions??
1) why next.js?
ans:   currently its the popular framework so want to explore it
and it solves some drawbacks of REACT framework like
    1) SEO optimazation so that browser crawlers can recognise what our website does it happens because its server side rendering feauture.
    2) waterfalling problem

2) why dummy bank webhook??
ans: I created sepearte webhook because if our server may goes down
and if the bank sends you a request there may be chance that our request get fails so to avoid this we need a separate webhook and we have to hit it through postman because we dont have access to bank URls 

3) why dockerimage??

ans: i created it beacuse i want to perform CD opeartion by having an EC2 instance currently i dont have an EC2 instance .
our EC2 instance will get the images of our app from the DockeR hub

# START THE PROJECT

1) git clone https://github.com/gunasekharsai/PAYMENT_APP_NEXT_TURBOREPO.git

2) go to packages/db/prisma there is .env replace dataabase URl of yours (you can get it from aiven/neondb for free)

3) cd apps/user-app  run command npm run dev

4) open the website enter a number and password and go transfer add some amount and select some bank click on the enter button 
then you will go to the respective bank page then come back you can onramptransaction proccessing after that got to postman place this URL http://localhost:3003/hdfcWebhook and place these as body   "token": "611.681682591642",
                "user_identifier": "6",
                "amount":"666600"
make sure no headers then you can see the balance gets updated
5) you can also do p2p transfer and can send money from one user to other
 