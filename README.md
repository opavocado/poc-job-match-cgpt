# Job Matching using ChatGPT

## The Problem
Nowdays it can be challenging for a tech worker to find the right job due to the increasing number of platforms and the vast number of job offers available. We have identified two specific problems that need to be addressed:

1. Job offers often come with very specific requirements that may not fully align with the worker's experience. Verifying these requirements manually can be very time-consuming.
2. Job offers usually do not adhere to any particular template or writing style, making problem 1 even more frustrating and ultimately exhausting.

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
The project is based around a single JPNotebook that process a set of job offers (```job_offers.csv``` provided in CSV format), compares them against the applicants profile summary (```summarized_cv.txt``` provided in TXT format) using ChatGPT (```gpt-api.key``` replace with your api key) and generates a CSV detailing the matching requirements for each job profile (```processed_job_offers.csv```).

The prompt used for evaluation is simple:
```prompt = "Given my profile and this job offer, list which requirements are met or not. Provide the results in csv format with columns separated by a pipe: requirement|status (met/unmet) \n - my profile: " + summarized_cv + " \n - job offer: " + job[column_names.index('description')]```   

## Results
The process run for 20 job offers, these are the overall results:

| Result         | Count |
|----------------|-------|
| Valid          | 9     |
| Somewhat Valid | 8     |
| Invalid        | 3     |

The average execution time for each job offer was ~10 seconds.

    
## Conclusion
This POC has shown promising results with a ~85% of positive outcomes.
With just the implementation of a simple prompt it was possible to obtain a filtered set of job offers that the applicant could easily digest.

### Ambiguous/Invalid Results
We asked the bot to explain the reasons behind certain requirements that were misclassified, the general answer to this prompt is that there is not enough data provided to make sure a certain requirement is ment, so it makes an assumption based on its understanding of the average experience of a professional with a similar background to the applicant.
Based on these results, it would be recommended for the applicant to go through this exercise once, extract the common requirements in their target job offers and make them explicit in their profile summary, and run the process again.
Note that this last task could also be a good candidate feature to be integrated in the process and prompt ChatGPT for input in the profile summary.
    
### Opportunities and Future Features
- Better Input Profile Summary by providing more explicit qualifications that match common job offer requirements
- - Evaluate the possibility of executing that task with ChatGPT
- Facilitate the job offer search by integrating with Job Search Engines (note this in most cases this is not possible without becoming a partner integration - which implies some considerable effort/resources)
- User defined filters that are not supported natively by the search enginges could be introduced to further narrow down the search (e.g.: ability to search for world-wide remote vs country or region-specific remote jobs)
- Execution time is expected to reduce with the Pro Version, however this would require further analysis
