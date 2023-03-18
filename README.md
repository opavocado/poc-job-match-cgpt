# Job Matching using ChatGPT

## The Problem
Nowdays it can be challenging for a tech worker to find the right job as there is an increasing number of platforms and a vast amount of job offers available. These offers often come with very specific requirements that may not fully align with the worker's experience, making it this task very time consuming and ultimately exhausting.

## Goal
Explore ChatGPT capabilities to help accelerate an applicant's job search.

## Scope of this POC
### In Scope
- Process a preselected set of job descriptions and compare against the applicant's profile summary
- Provide for each job description: list of requirements met and unmet, % match
- Basic validations and error handling

### Out of Scope
- Job Search Engine Integrations (e.g.: linkedin, glassdoor, indeed, etc) -> these integrations although technically possible they will only work once the engines have validated the integration (i.e.: becoming a parter integration)

## Project
The project is based around a single JPNotebook that process a set of job offers (```job_offers.csv``` provided in CSV format), compares them against the applicants profile summary (```summarized_cv.txt``` provided in TXT format) using ChatGPT (```gpt-api.key``` replace with your api key) and generates a CSV detailing the matching requirements for each job profile (```processed_job_offers.csv```).

The prompt used for evaluation is simple:
```prompt = "Given my profile and this job offer, list which requirements are met or not. Provide the results in csv format with columns separated by a pipe: requirement|status (met/unmet) \n - my profile: " + summarized_cv + " \n - job offer: " + job[column_names.index('description')]```   

## Results
<PENDING> e.g. - Results -> 20 provided, how many accurate? 

## Conclusion
This POC has shown promising results with a <PENDING> of positive outcomes.
With just the implementation of a simple prompt it was possible to obtain a filtered set of job offers that the applicant could easily digest.
    
## Opportunities and Future Features
- 


- good if integration -> better if integrate w/ applicant profile as with a limited summary the bot makes certain assumptions that might not be 100% correct
- future features -> custom filters that chatgpt can analyze (e.g. fully remote or not?)
- exec time