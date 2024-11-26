# Event Manager Company: Software QA Analyst/Developer Onboarding Assignment

## Fixed Issues
* [Issue 1:](https://github.com/Jhr-4/IS218_HW10/issues/1) Registration nickname was always randomly gernated, instead of being what the user picked. Fixed nickname to match what user types.
* [Issue 2:](https://github.com/Jhr-4/IS218_HW10/issues/3) There was no good password validation. This can be a major security problem.
* [Issue 3:](https://github.com/Jhr-4/IS218_HW10/issues/5) There was no check to make sure Github and LinkedIn are correct links from those platforms. Added validation for both.
* [Issue 4:](https://github.com/Jhr-4/IS218_HW10/issues/7) Login asks for username, but only accepted email. Fixed to accept both.
* [Issue 5:](https://github.com/Jhr-4/IS218_HW10/issues/9) Nicknames in each example was differet. This creates confusion and isn't consistant.
* [Issue 6:](https://github.com/Jhr-4/IS218_HW10/issues/14) Inconsistant UUID's in examples & List Users schemas example had hard to read code with missing items.

## Docker Hub
![DockerHub Deployed Image]()

## Reflection 
This assignment taught me a lot. Not only did I learn more about using technologies like FastAPI and the Postgres database, but also what occurs in the role of a QA. I learned how to finding bugs/errors and how to go about fixing them. This fixing error process also continued with the pytests as some were broken as the tokens in confest weren't there and some stuff was changed with the validations I added. Initially, when trying to fix the bugs I ran into many problems as I didn't know how the application worked. However, as I read through functions and figured out how they all connect, I was able to figure out how to fix a bug and locate it. For example, at the start when I went to fix the random nickname in registration, I wasn't sure which file was responsible for it: the user schemas or services. But, after working with the code and doing basic debugging with logging & printing, I was able to locate it and understand what the code was doing. 

Additionally, through this assignment, I got more insight into how user registration actually works and how to go about in creating the functionality ensuring security and validation. It was also interesting to use the email verify website as I didn't know a website exists to just have test emails. After making these changes, the process of creating issues and branches also was important. It helped enhance my workflow by allowing me to see my progress while being documented as usually I just do everything in one commit/branch and push it at the end.


## Useage: 
* Create an account on [mailtrap](https://mailtrap.io/), Create a SMTP Email Testing, Copy the username & password.
* Create .env in the format of [.env.sample](https://github.com/Jhr-4/IS218_HW10/blob/main/.env.sample) and paste the SMTP credentails. 
* Start & Build Containers: `docker compose up --build`
* [API Endpoints](http://localhost/docs)
* [Postgres DB](http://localhost:5050/browser/) 
* Create DB migration `docker compose exec fastapi alembic revision --autogenerate -m 'added admin'`
* Apply DB migration `docker compose exec fastapi alembic upgrade head`
* Run Tests: `docker compose exec fastapi pytest` -- Will drop db tables
* Get tables back by manually deleting the alembic version table & running migrations again