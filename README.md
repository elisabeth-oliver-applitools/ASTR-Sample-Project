The following is a summary of key points in working with ASTR. 
Please see the official documentation for further details : 
https://docs.google.com/document/d/1Gradtg5pNCIGh-7bB7u_PImmGam7lof-duqbVxmDYdU/edit?usp=sharing

ASTR Projects are made up of 3 core files:
1. A "job" file (in this case job.xml) which contains the
    testing flow
2. The applitoolsConf.xml which contains specific information about the testing environment,
    specifically your API key
    - See "Applitools Configuration Settings" in the documentation for more details on these options.
3. The ApplitoolsSimpleTestRunner.jar - the java program which will run the previously mentioned job.
    - Links to the most recent version of ASTR (as well as a record of past versions) can be found at 
      the bottom of the ASTR documentation under "Versions"

Everything else is optiononal, but generally recomended.
Among these recomended files are:
- configurations.xml : contains reusable test runner and webdriver configurations.
    - This is where one should define whether on wants to use the UFG, what environments one want to render 
    their checkpoints on, what browser they wish to locally run their tests from, and to set any browser options 
    on chrome or firefox browsers (headless mode, for example) 
    - See "Cleaner & Modular Coding" - "Using Predefined variables/Configurations/Configuration Groups" - 
    "2) Defining External Configurations and Configuration Groups" for more details.
- definitions.xml : contains reusable job actions and variables. 
    - I think of this as being where one's functions and one's data live. 
    - See "Cleaner & Modular Coding" - "Using Predefined variables/Configurations/Configuration Groups" - "1) Defining Variables"
    and "Cleaner & Modular Coding" - "Action Blocks" for more information on how to set variables and 
    reusable instructions respecively.
> It should be noted that ASTR makes no distinction between what I have described as a "definitions" file 
  and a "configurations" file and these can be named whatever you please, this is however an organization 
  split I find helpful as it seperates runner and browser specific configuration from the business logic of running your tests. 
- sitemap.xml : contains a list of urls for a "crawl" action to explore.
    - See "Supported Actions" - "Iterative Actions" - "Crawl a sitemap.xml file" for more information on how to call a crawl action. 
    - See "sitemap.xml" in this project for an example of a valid sitemap.xml file. 


Run this ASTR project from the command line with the command: 

    java  -jar ApplitoolsSimpleTestRunner-4.0.2.jar job.xml
