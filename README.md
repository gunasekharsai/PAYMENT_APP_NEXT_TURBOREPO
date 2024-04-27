
# Payment_App_futures

this is a basic Payment app consisting of basic futures

1) one can add an amount int the wallets by hitting the dummy webhook after it redirects to hdfc/axis Payment gateway

2) users can send money to each other

3) The user can see the transaction status.

# Technologies used

1) used NEXT.js for frontend and backend
2) created a dummy bank webhook using EXPRESS.js
3) used PRISMA as ORM and POSTGRESS database
4) NEXT_AUTH for authentication (Signin/signup).
5) created a CI pipeline using GitHub to ensure faster pull requests and efficient collaboration
6) used turborepo to manage top-level dependencies mainly ZOD validation.
7) created a DOCKER IMAGE and posted it in DOCKERHUB

# why questions??
1) why next.js?
ans:   currently it's the popular framework so want to explore it
it solves some drawbacks of the REACT framework like
    1) SEO optimization so that browser crawlers can recognize what our website does it happens because of its server-side rendering feature.
    2) waterfalling problem

2) why dummy bank webhook??
ans: I created a separate webhook because if our server goes down
and the bank sends you a request there may be a chance that our request fails so to avoid this we need a separate webhook and we have to hit it through postman because we dont have access to bank URls 

3) why docker image??

ans: I created it because I want to perform CD operations by having an EC2 instance currently I don't have an EC2 instance.
our EC2 instance will get the images of our app from the Docker hub

# START THE PROJECT

1) git clone https://github.com/gunasekharsai/PAYMENT_APP_NEXT_TURBOREPO.git

3) go to packages/db change .env.example to .env to replace your database URL of yours (you can get it from aiven/neondb for free)
4) run npx prisma migarte dev an dnpx prisma genrate in packages/db
5) cd apps/user-app  run command npm run dev

6) open the website enter a number and password and go transfer add some amount and select some bank click on the enter button 
then you will go to the respective bank page then come back you can see onramptransaction processing after that go to Postman place this URL http://localhost:3003/hdfcWebhook and place these as body
                "token": "611.681682591642",
                "user_identifier": "6",
                "amount":"666600"
make sure no headers then you can see the balance gets updated
8) you can also do p2p transfer and can send money from one user to another

# How it looks
![Screenshot (37)](https://github.com/gunasekharsai/PAYMENT_APP_NEXT_TURBOREPO/assets/113043690/8495823b-aa8d-4e46-92a3-8f30b3c92bc4)
![Screenshot (38)](https://github.com/gunasekharsai/PAYMENT_APP_NEXT_TURBOREPO/assets/113043690/446c30b0-9e5d-48b7-8f7b-12d9efeb07ef)

 
