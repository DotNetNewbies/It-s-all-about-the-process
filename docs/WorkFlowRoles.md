### The work flow roles:  

The major roles in any good software development team are these:  

<details>
  <summary>Stakeholder</summary>  

  This is the person that has noted the deficiency in the current  
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
  
</details>  

<details>
  <summary>Business Analyst (BA)</summary>  

  Person whose knowledge encompasses the business view  
  of the organization but can "speak" a little "tech". In short, this  
  person is a business process-oriented individual with little actual  
  engineering acumen but is intimately familiar with "how the business  
  works" and thus understands, at a business level, the impact of the  
  current deficiency and the resulting benefit of an implemented  
  solution.  

  Assists in creating a development dictionary and associated DSL as  
  needed.  

</details>  

<details>
  <summary>System Architect (SA)</summary>  

  The opposite of the BA - this person is well versed in  
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

</details>  

<details>
  <summary>Development Manager (DM)</summary>  

  Person who is familiar with the abilities or lack  
  thereof of personnel attached to a particular project.  
  Serves as the "gatekeeper" for code integration into the code  
  repository based on feedback from the engineers and QA managers.  

  At a minimum, the DM will:  

  - Ensure the availability of training materials in whatever form is most  
    appropriate for the need and ensures that personnel are given time and  
    resources to obtain said training. In other words, the training must  
    not only be available but must be integrated into the day-to-day  
    schedule of the engineers such that training is just "part of the job"  
    as opposed to being some "special" thing that serves as a perceived  
    "interruption" in the on-going solution development process.  
    Training should ***not*** affect the nominal work-life balance, nor  
    should training be an occasional, exceptional "reward" for engineers.  
    Training should be an integral part of the engineer's working day.  

- Serves as the person tasked with leading code reviews and is the final
  arbiter as to the acceptability of reviewed code.  

- Monitor the availability of the code repositories, ensure proper SDLC  
  practices are maintained and control access to said repositories.  

</details>  

<details>
  <summary>Project Manager (PM)</summary>  

  Person whose purpose is to arrange order of  
  precedence for the derived tasks as generated from the  
  requirements/features.  

  This person doesn't need to know who will perform the work, just in what  
  order the work will be performed. This knowledge will come from working  
  with the BA to determine priority based on business needs and,  
  ultimately, the demands of the stake holders.  
  Will work with the DM to match tasks with engineers.  

</details>  

<details>
  <summary>Engineer</summary>  

  The person responsible for creating the software solution if  
  software is indeed part of the solution based on tasks as assigned by the PM.  
  The ***one*** job of the Engineer is to ***Write Excellent Code***  
  *and nothing else!*  

</details>  

<details>
  <summary>Lead Engineer (LE)</summary>  

  This is the "go-to" person when a question concerning a new  
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

</details>  

<details>
  <summary>Quality Assurance (QA)</summary>  

  Person responsible for testing the software solution to ensure that  
  it meets the requirements from a user point of view.  

  Much of this role can be performed by automation, however, in the final  
  analysis, it takes a human user to determine of the solution meets the  
  minimum "non-annoyance" metric. The software might do what it needs to but if  
  it annoys the users, it's not an actual "solution".  

</details>  

<details>
  <summary>Quality Assurance Manager (QAM)</summary>  
  
  Person serving equivalent role to DM but for testers and  
  issue/bug resolution evaluation.  

  Works with the DM to validate status of development progress as to code  
  acceptance/rejection and the "why's" and "wherefores" of rejection should  
  such be necessary.  

</details>  

<details>
  <summary>User</summary>  

  Person who actually uses the software on a day to day basis. This  
  person will have insight into the necessary application flow and how things  
  "should" work. WIll most often be the source of motivation for changes in the  
  current system.  

  Should ***not*** be the source of the desired solution.  

</details>  

<details>
  <summary>Ops aka DevOps</summary>  

  Person responsible for overseeing deployment of the software solution to  
  both a testing/QA environment and to Production.  

</details>  

<details>
  <summary>User Experience Specialist (UX)</summary>  

  User interface specialist. Includes a "copywriter", a person that is  
  responsible for making the user interface more palatable (understandable)  
  to the rest of the universe. This individual will be something of an artist  
  focused on user interfaces (a task which most regular developers suck at).  
  Provides input/feedback from/to users to effect a desired user interface and  
  corresponding flow of the business process said UI is to effect.  

  Provides input for the technical writer such that the documentation for the  
  system is both up-to-date and accurate such that new users have a reliable  
  resource to call upon to learn the business processes via the interface.    

</details>  

<details>
  <summary>Technical Writer (TW)</summary>  
  
  Technical Writer aka "technical documentation specialist". Person that  
  documents the "how" and "why" of the solution and integrates that  
  information into the current system documentation.  

</details>  

It should be noted that ***each*** of the above listed roles is a full-time  
***career*** and not just a one-off that can be performed in a few hours a  
week as managers are wont to imply.  

<hr>  

[Return to How Would you do it][ReturnToHowWouldIDoIt-Url]  

[ReturnToHowWouldIDoIt-Url]: ./How%20would%20you%20do%20it.md    