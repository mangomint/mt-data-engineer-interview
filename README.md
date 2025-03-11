# mt-data-engineer-interview

### Project
You are tasked with pulling data about the status of onboarding customers from an API to load to Snowflake and model in dbt. Ultimately you will help create a dashboard from the dbt models to visualize this information for the onboarding team.

The onboarding team is interested in tracking the status of companies in the onboarding process. The questions they are most interested in being able to answer are:

 - How many companies are currently onboarding?
 - Which products take the longest to onboard?
 - What is the average amount of time it takes to onboard?
 - Our target onboarding time is 14 days. How many companies are exceeding this over time.
 - They want to be able to slice the data by onboarding manager, vertical, etc.

### Tasks
1. Examine the data from the API at https://suzcamnu65hid4pw4qo66azao40dyusc.lambda-url.us-east-1.on.aws/. You will be provided an API Key that is passed as the header `mt-api-key`.

2. Write a Python script in `response/flow.py` to pull the data from the API, transform it as needed, and save to an S3 Bucket in a directory for your name. This S3 bucket is set up as stage in Snowflake and you will be tasked with loading the data from this stage to Snowflake. We typically load data from stages in AVRO, JSON, and CSV formats. You will be provided AWS credentials to upload to the bucket.

3. Write the SQL to create a destination table to load the data to in a file called `response/destination_table.sql`

4. Write the SQL to merge data from the stage to the destination table in a file called `response/merge.sql` 

5. Write a dbt Model(s) to that will be used to build dashboards for the team to answer the questions above. Save this file(s) with the prefix `response/dbt_{model_name}.sql`. Please also include dbt docs for the models.