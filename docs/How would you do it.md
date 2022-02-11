
Ok, this document will be all about how I would approach my job as a senior  
software engineer (which I am).  

The first order of business, let's define the various job roles that a  
successful development team will require.  

The first implication is that this is a cross-functional team meaning that the  
folks will come from a wide variety of disciplines, each one a full-time  
career, not something one can do for an hour or two a week and be good at.  

The major roles in any good software development team are these:  
- Stakeholder - This is the person that has noted the deficiency in the current  
  environment and is the one to whom the progress of the resulting solution  
  will ultimately be reported to.  
  Why is the stakeholder part of the team? They are the ones that will  
  ultimately "sign off" on the solution and allow it to pass into production  
  as "the answer" to the original deficiency.  
  This person/these people will work with the BA to turn vague "concerns" into  
  proper, single-responsibility-oriented, deficiencies that may be documented  
  in a "request for solution".  
  It's important at this step to understand that the more clearly the noted  
  deficiencies are defined, the quicker the solution will ultimately present  
  itself.  
  Vagueness in deficiency definition will lead to wasted time in development  
  for a myriad of reasons, the least of which will be coding something that  
  doesn't need to be in the system and all the wasted time that goes with that.  

- BA -  Business Analyst. Person whose knowledge encompasses the business view  
        of the organization but can "speak" a little "tech". In short, this  
        person is a business process-oriented individual with little actual  
        engineering acumen but is intimately familiar with "how the business  
        works" and thus understands, at a business level, the impact of the  
        current deficiency and the resulting benefit of an implemented  
        solution.  
        Assists in creating a development dictionary and associated DSL as  
        needed.  

- SA -  System Architect. The opposite of the BA - this person is well versed in  
        technology but has little knowledge of the details of the business. The  
        primary role of the SA is to translate the business-oriented  
        statement(s) of a deficiency and convert that "business-speak" into  
        technology terms that the rest of the development team may use to  
        implement a solution.  
        A big portion of this job is maintaining a sense of the "Big Picture".  
        It is the job of the SA to determine the impact of any new software  
        on the current system and *guide* the development of the overall system  
        to ensure the use of all new technologies as is appropriate and to  
        ensure a minimum of "technical debt".  
        ***The System Architect does --NOT-- write software!***  
        
        At a minimum, the SA will:  

        - Determine which emerging technologies should be integrated into the  
          current system to continually lower technical debt and ensure that  
          the overall system remains current with technology.  

        - Ensure the Development Managers are made familiar with said new  
          technologies.  

        - Ensures Lead Engineers understand (after appropriate training) the  
          impact of the new technologies and what might be necessary to perform  
          the necessary integration of the new tech into the current system.  
          In short, help the LE's with the implementation details from a  
          *design* point of view and pass approval on the selected  
          implementation from a system impact point of view.  

        - Create a dictionary and associated DSL (Domain Specific Language)  
          with the assistance of the BA such that all deficiency definitions  
          will use a common language so the possibility of misunderstanding is  
          reduced significantly.  

        - Assist in the building of requirements based on the BA-generated  
          functionality item requests/issues/bugs.

        - Assist with the creation of development milestones as metrics for  
          managers to use to gauge progress.  
    
- DM - Development Manager. Person who is familiar with the abilities or lack  
       thereof of personnel attached to a particular project.  
       Serves as the "gatekeeper" for code integration into the code  
       repository based on feedback from the engineers and QA managers.  

       At a minimum, the DM will:  

       - Ensure the availability of training materials in whatever form is most  
         appropriate for the need and ensures that personnel are given time and  
         resources to obtain said training. In other words, the training must not  
         only be available but must be integrated into the day-to-day schedule  
         of the engineers such that training is just "part of the job" as  
         opposed to being some "special" thing that serves as a perceived  
         "interruption" in the on-going solution development process.  
         Training should ***not*** affect the nominal work-life balance, nor  
         should training be an occasional, exceptional "reward" for engineers.  
         Training should be an integral part of the engineer's working day.  

      - Serves as the person tasked with leading code reviews and is the final
        arbiter as to the acceptability of reviewed code.  

      - Monitor the availability of the code repositories, ensure proper SDLC  
        practices are maintained and control access to said repositories.  

- PM -  Project Manager. Person whose purpose is to arrange order of  
        precedence for the derived tasks as generated from the  
        requirements/features.  
        This person doesn't need to know who will perform the work, just in what  
        order the work will be performed. This knowledge will come from working  
        with the BA to determine priority based on business needs and,  
        ultimately, the demands of the stake holders.  
        Will work with the DM to match tasks with engineers.  

- Engineer - the person responsible for creating the software solution if  
  software is indeed part of the solution based on tasks as assigned by the PM.  
  The ***one*** job of the Engineer is to ***Write Excellent Code***  
  *and nothing else!*  

- Lead Engineer - this is the "go-to" person when a question concerning a new  
  technology comes up during the development process. Should be well-versed in  
  all new technologies as chosen by the SA but at an implementation level vs  
  an integration level. In other words, the SA choses the new tech based on  
  what it does, the Lead Engineer learns how it does it and therefore how to  
  implement that choice and integrate it into the current system.  
  May or may not be a "Team Lead" in so much as they would be responsible for  
  overseeing the activities of fellow engineers, this role is not such much a  
  role concerned with *management* as it is ***knowledge***.  
  Interfaces with the SA to stay up on selected new technologies as seen from an  
  ***implementation*** viewpoint aka "*how* to make it go" as opposed to "why".  

- QA - person responsible for testing the software solution to ensure that  
  it meets the requirements from a user point of view.  
  Much of this role can be performed by automation, however, in the final  
  analysis, it takes a human user to determine of the solution meets the  
  minimum "non-annoyance" metric. The software might do what it needs to but if  
  it annoys the users, it's not an actual "solution".  

- QAM - QA manager. Person serving equivalent role to DM but for testers and  
  issue/bug resolution evaluation.  
  Works with the DM to validate status of development progress as to code  
  acceptance/rejection and the "why's" and "wherefores" of rejection should  
  such be necessary.  

- User - Person who actually uses the software on a day to day basis. This  
  person will have insight into the necessary application flow and how things  
  "should" work. WIll most often be the source of motivation for changes in the  
  current system.  
  Should ***not*** be the source of the desired solution.  

- Ops - Person responsible for overseeing deployment of the software solution to  
  both a testing/QA environment and to Production.  

- UX - User interface specialist. Includes a "copywriter", a person that is  
  responsible for making the user interface more palatable (understandable)  
  to the rest of the universe. This individual will be something of an artist  
  focused on user interfaces (a task which most regular developers suck at).  
  Provides input/feedback from/to users to effect a desired user interface and  
  corresponding flow of the business process said UI is to effect.  
  Provides input for the technical writer such that the documentation for the  
  system is both up-to-date and accurate such that new users have a reliable  
  resource to call upon to learn the business processes via the interface.    

- TW - Technical Writer aka "technical documentation specialist". Person that  
  documents the "how" and "why" of the solution and integrates that  
  information into the current system documentation.  

It should be noted that ***each*** of the above listed roles is a full-time  
***career*** and not just a one-off that can be performed in a few hours a  
week as managers are wont to imply.  

<hr>  

The following are just two of the myriad job offers I receive every day. These  
jobs are typical in their "required skills", I did not single them out for  
anything save that their job description was a little better than most as they  
contain a bit more detail as to what the job entails.  

Job Role: Senior .NET Developer

- Experience of leading team in all aspects of .NET

- Experience of AGILE methodology

- Must have strong communication skills

- Experience in onshore offshore communication 

- Experience in DOT NET CORE , C#, MVC, jQuery, Javascript

- Adaptable and quick in terms of changing situations.

- Hands on working experience in designing, solutioning and leading distributed  
  technologies like .NET, JavaScript, jQuery, linQ, etc

- Knowledge of Mulesoft API will be a bonus

- Confident and independent                    

- Experienced in SAFE, Scrum AGILE methodologies

- Vast experience in Design and requirement elicitation.

- Experienced .NET resource with Tech Leading experience (MUST)

- Should be experienced of handling offshore team and guide the team from  
  Technical standpoint.

- Communicate issues/risks/status to project stakeholders throughout the  
  engagement 

- Execute various phases of software development life cycle such as analysis,  
  design, technical writing, implementation, testing and deployment            

- Prepare requirement understanding document, test execution and defects  
  management           

- Providing subject matter expertise and technical guidance to the team

- Review Code and Test results of the team.  

### Summary of the "Senior .NET Developer" role:  
- Must be not only a developer, but must be a Team/technical (MUST) Lead  
- Familiar with Agile (which one?) - oh, wait, with SAFE Agile.
- Work with offshore teams (might need to be multi-lingual, certainly will be  
  working odd hours, not the standard 9-5)  
- Must be familiar with the following languages:  
  - C#  
    - ASP.NET's MVC (is that with Blazor or not?)  
  - JQuery (javascript)
  - javascript in general (so I guess no Blazor)  
- Mulesoft? It's an integration platform. So you also need to be:  
  - a Functional programmer (vs OOP)
    - Know the DataWeave language for Mulesoft integrations  
    Which language is used for MuleSoft? From their docs:  
      "DataWeave is a functional language used in Mule applications to perform  
      data transformations. Before you begin to use DataWeave to code your own  
      powerful and complex data transformations, you must understand the basic  
      concepts of programming and the core features of functional programming  
      languages."  
- Not only writing code, must be able to interface with stakeholders concerning  
  risks/status/issues as the project develops. (hint: This is the job of the PM)  
- Manage all phases of the SDLC (wait, what!?):  
  - Analysis (Job of the Business Analyst)
  - Design (Job of the Systems Architect)  
  - Technical writing (Technical document writer)  
  - implementation (NOW I get to write C# code)
  - Testing (Job of the QA specialist)  
  - Deployment (Job of the DevOps folks)  
  - Document all phases of the project (Tech writer again):
    - How to use the application
    - How to test the application
    - How to manage and alleviate defects in the application  
- Be the onsite technical lead to teach and provide guidance to the rest of the  
  team.
- Be the Development Manager to perform code reviews  
- Be the QA manager to perform test reviews.  

In short, the above summary requires that I be an expert in the following:  
- Developer (OOP and Functional, multi-lingual e.g. C#, javascript, DataWeave)  
- Team Lead
- Technical Lead (Systems Architect)  
- Project Manager
- Business Analyst
- Technical writer  
- QA tester
- QA manager
- DevOps engineer
- Cloud specialist (why use SAAS integration if not in the cloud?)

In other words, I just hit ***TEN different, full-time, career-level*** job  
descriptions, each one of which I am to be something of an expert, certainly  
competent to perform.  
As I see it, my so-called "work-life balance" just went out the window for  
multiple reasons (think off-short time zones and emerging "emergencies"), I  
will be *constantly* trying to keep up with 10 different fields of endeavour,  
I must constantly provide training to my peers, etc. etc. etc.  
And all for the lofty salary of...67K. Yep, sixty-seven thousand dollars a year.  

<hr>  

Position: .NET Developer

- Strong fundamentals including an understanding of data structures, concurrent  
  programming, and design patterns.

- Min 10+ years’ experience with .Net Technologies – Asp.Net, Console based App,  
  PowerShell & Web API Rest Services.

- Min 10+ years’ experience in the web development process (Design, Development,  
  and deployment) across the UI stack covering HTML5, CSS3, JavaScript (ES6),  
  and JavaScript/jQuery to develop user-friendly interfaces and dashboards.

- Should have good understanding of repository tool like GIT and DB deployment  
  tool like Liquibase.

- Should have good understanding of project management and issues tracking tool  
  like Odyssey Confluence and JIRA.

- Should have hands-on on designing web architecture.

- Should have excellent Oracle PL/SQL Programming, Indexing and Performance  
  tuning, Partitions understanding with very good Data Analysis skill.

- Preferable to have good understanding of IB reference data and transactional  
  (e.g., trade life cycle) data

- Should have good understanding of Control-M Scheduling tool.

- You are ambitious, dedicated, hardworking and can work on own initiative  
  whilst also working collaboratively and deliver on time with a high level of  
  integrity, sense of urgency, attention to -detail and quality standards.

- Ability to transform customer requirements into a workable design at the  
  functional and/or technical levels.

- Excellent problem-solving skills.

- Should have good communication skills for very frequent interaction with  
  business and production support team daily.Database knowledge
 
 Summary of ".NET Developer" position:
 - Must know what "IB" stands for (Investment Banking)