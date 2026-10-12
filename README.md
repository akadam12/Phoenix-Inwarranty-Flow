# Postman API Automation Integration with Github Actions #

This repository is a demonstration for POC for integrating postman tests with github actions. The Tests are written in Postman and they are executed on the VM with the help of newman and newman-reporter-htmlextra.
Github Actions will trigger the project execution on every push to the main branch. you can also execute the project manually using workflow_dispatch. The project runs on a scheduled time with the help of the cron job.

The HTML report is archived and kept in the artifact section for the team to download it. Along with that they can view the report directly from the github page : https://akadam12.github.io/Phoenix-Inwarranty-Flow/ .
The latest report is mailed to the team members using GMAIL SMTP.

## Testing Coverage ##
1. Happy Flow Testing
2. Negative testing with Edge case testing
3. Token testing
4. Data driven testing with CSV
5. Schema Validation
6. Secrets management with Github secrets 

## Tech Stack ##
1. Postman
2. Nodejs
3. Newman
4. Newman-Reporter-Htmlextra
5. Github Actions
6. GMAIL SMTP
7. Github Pages
8. CSV for Data Driven Testing
9. AWS-EC2 instance for self hosted github runner.


## Github Pages ##
You can directly view the latest test report of the postman test at the github page link : https://akadam12.github.io/Phoenix-Inwarranty-Flow/


## HTML Report ##
The report will be created in the Newman folder
![Postman Report](https://github.com/akadam12/Phoenix-Inwarranty-Flow/blob/static-content/newman-report.png)

## Project Structure ##
```
Phoenix Inwarranty Flow
├─ Inwarranty-flow Collection.postman_collection.json
├─ QA.postman_environment.json
└─ testData.csv

```

## How to run the Project ? ##
You can run the project at your local system for that :
1. Clone the Project on local System : https://github.com/akadam12/Phoenix-Inwarranty-Flow.git
2. Install Nodejs and NPM from this : https://nodejs.org/en
3. Install Newman using : ```npm install -g newman```
4. Install Newman-Reporter-Htmlextra : ```npm install -g newman-reporter-html```
5. Run the Newman command :
             ```newman run 'Inwarranty-flow Collection.postman_collection.json' \
             -e QA.postman_environment.json \
             -d testData.csv \
             -r cli,htmlextra \
             --reporter-htmlextra-export ./newman/index.html```

