# Job Matching using ChatGPT

## The Problem
Nowdays it can be challenging for a tech worker to find the right job due to the increasing number of platforms and the vast number of job offers available. We have identified two specific problems that need to be addressed:

1* Job offers often come with very specific requirements that may not fully align with the worker's experience. Verifying these requirements manually can be very time-consuming.
2* Job offers usually do not adhere to any particular template or writing style, making problem 1 even more frustrating and ultimately exhausting.

## Goal
Explore ChatGPT capabilities to help accelerate an applicant's job search.

## Scope of this POC
### In Scope
- Process a preselected set of job descriptions and compare against the applicant's profile summary
- Provide for each job description: list of requirements met and unmet, % match
- Basic validations and error handling

### Out of Scope
- Job Search Engine Integrations (e.g.: linkedin, glassdoor, indeed, etc) -> these integrations although technically possible they will only work once the engines have validated the integration (i.e.: becoming a partner integration) 


## Project
The project is based around a single JPNotebook that process a set of job offers (```job_offers_csv_file``` provided in CSV format), compares them against the applicants profile summary (

## Conclusion
This POC 

- Results -> 20 provided, how many accurate?
- good if integration -> better if integrate w/ applicant profile as with a limited summary the bot makes certain assumptions that might not be 100% correct
- future features -> custom filters that chatgpt can analyze (e.g. fully remote or not?)
- exec time
