[Return to "Fallacies"][Fallacies-Url]  

Development methodologies aka "how to write software". Here are two that are  
somewhat popular, TDD being the most "in favor" at the moment. Why? Managers  
love TDD for showing "productivity".  

- UTDD (Unit Test Driven Development). Not my name, I prefer "ADD"  
  (Algorithmic Driven Development) but one must understand where I am coming  
  from to understand just what that actually means so I'll stick with the former  
  for the purposes of this paper. Sadly, there is no Wikipedia reference for  
  UTDD so I'll put together one based on my own experience (now you know how I  
  approach "writing excellent code").  
  - The UTDD (ADD) process goes as follows:
    - Acquire and examine, *in depth*, a single requirement. If any part of said  
      requirement doesn't make sense, acquire additional information, etc.  
      until the requirement is fully understood and that your supervisor is  
      under the (correct) impression that you also understand, fully, the  
      requirement.  
    - Write the necessary code as efficiently and elegantly as possible within  
      reasonable time restraints (Your PM will see to this because you gotta  
      release sometime) to meet the requirement as understood by the developer.  
      This is key as the focus is completely on the algorithm that will meet  
      the needs of the requirement ***and nothing else***. The engineer may  
      need to take additional time researching the best possible algorithm to  
      meet that need, confer with others, go learn new things, take classes,  
      etc. In short, write the best possible code to meet the needs of the  
      requirement.  
    - Write the first unit test aka "The Golden Path" to ensure that the  
      algorithm performs as expected when all parameters are within acceptable  
      range. In short, does the algorithm do what the developer thinks it  
      should do under ideal conditions.  
    - If the algorithm performs as expected, evaluate if the algorithm now  
      answers the needs of the requirement. If so, continue to the next step,  
      if not, modify the algorithm such that the golden path test continues  
      to pass and the algorithm performs the actions necessary to meet the  
      needs of the requirement.  
    - Having now met the needs of the requirement and now having a method of  
      verifying that the algorithm meets the needs of the requirement under  
      ideal conditions, start examining conditions ***other than ideal*** and  
      for those appropriate conditions, ensure that the algorithm handles the  
      adverse conditions gracefully. In other words, does the algorithm fail  
      gracefully under the stated conditions. Fix until it does.  
    - Repeat for all applicable adverse conditions.  

- TDD (Test Driven Development). A nasty methodology "sold" to the development  
  community by managers aka "management" to foster greater "productivity".   
  
    - Opinion: It should be obvious that, NO, I don't like TDD, for reasons that  
      I'll explain further along in the paper. Feel free to disagree with me,  
      there exists a significant portion of the developer world that does.  
      That's OK by me, I won't be changing my mind and you won't change it  
      either.  
      My intention is ***NOT*** to spark a debate or a flame war, the intention  
      of this user group, as always, is to foster ***conversation***.  
      Your opinions are just that - yours, I recommend that you remember that,  
      no proselytizing!  

  - The TDD process can be summed up as follows (I'm quoting my source here):  
    - Add a test  
      - The adding of a new feature begins by writing a test that passes iff the  
        feature's specifications are met. The developer can discover these  
        specifications by asking about use cases and user stories. A key  
        benefit of test-driven development is that it makes the developer focus  
        on requirements before writing code. This is in contrast with the usual  
        practice, where unit tests are only written after code.
    - Run all tests. The new test should fail for expected reasons.    
      - This shows that new code is actually needed for the desired feature.  
        It validates that the test harness is working correctly. It rules out  
        the possibility that the new test is flawed and will always pass.  
    - Write the simplest code that passes the new test.  
      - Inelegant or hard code is acceptable, as long as it passes the test.  
        The code will be honed anyway in Step 5. No code should be added beyond  
        the tested functionality.  
    - All tests should now pass.
      - If any fail, the new code must be revised until they pass. This ensures  
        the new code meets the test requirements and does not break existing  
        features.  
    - Refactor as needed, using tests after each refactor to ensure that  
       functionality is preserved.  
       - Code is refactored for readability and maintainability. In particular,  
         hard-coded test data should be removed. Running the test suite after  
         each refactor helps ensure that no existing functionality is broken.  
        - Examples of refactoring:
          - moving code to where it most logically belongs
          - removing duplicate code
          - making names self-documenting
          - splitting methods into smaller pieces
          - re-arranging inheritance hierarchies
    - Repeat steps 1-5 for each piece of functionality.  

Summary of the differences between UTDD and TDD:  
- One thing that UTDD and TDD agree on: One should start with a requirement.  
  However, the description for TDD **does not focus on understanding the**  
  **nature of the requirement in depth**, one need only read it and presume  
  that it is understood. The focus is on getting that first test written.  
  UTDD **focuses on the requirement**, demanding that it be fully understood  
  before continuing as the requirement guides the development of the *algorithm*  
  which is the focus of UTDD - the engineer should be writing excellent code,  
  ***to meet the needs of the requirement, not the test***!
- UTDD is all about the algorithm, TDD is all about the test.  
  How can I justify saying this? It's in the quoted description above and, I  
  quote: "Inelegant or hard code is acceptable, as long as it passes the test."  
  In short, ***PRODUCTION code efficiency does not matter so long as***  
  ***the test passes!*** Yes, this is addressed later but the focus is on the  
  test, not the production code. It's as if the production code is an  
  afterthought rather than the focus of the endeavor.  

  How is this addressed "later" you might ask? Step 5 (Refactoring). Once the  
  test passes, fix the production code to be not so ugly. However, management  
  will usually decree, because of "time restraints", "optimal resource  
  allocation" and "workload", "fix it later,  we gotta get this thing shipped"  
  and "later" never happens so crap code goes into production and stays there  
  for years, sometimes actual *decades* (see the TDWTF.com) for endless examples  
  of this.  

  Again, the watchword of management is "productivity" so if you get "green bar"  
  on your test, the follow-on is usually ***SHIP IT! We'll fix it later*** and,  
  sadly, later never arrives.  
  - Opinion: I put it to you that the activities outlined in step 5  
    (refactoring) should ***NOT*** be an "afterthought" but as an engineer that  
    strives to ***always*** "write excellent code", then ***THOSE ACTIVITIES***  
    ***SHOULD BE AT THE FOREFRONT OF ALL YOUR CODE WRITING ALL THE TIME!***  
    You should ***NEVER*** "fix your code later", you should ***WRITE IT***  
    ***CORRECTLY THE FIRST TIME***, that way if "later" never comes,  
    ***SO WHAT!?*** "Later" never needed to arrive!  
- As a software engineer, your focus should be on your career as a developer.  
  - UTDD encourages you to become excellent working with the languages you  
    choose to master and excel writing.  
  - TDD encourages you to focus on writing good *tests*.  

And here we come to the first point of real contention. There are two reasons  
I don't like TDD, one, the focus on the test vs the algorithm, the other is the  
perceived mental health aspect of UTDD vs TDD and I see it as this:
- Opinion: UTDD asks that you start with an unknown - the requirement. It then  
  asks that you do your research to look for and find the best possible  
  expression of the algorithm that you can within the given time restraints.  
  In short, start with focusing on becoming a better engineer by learning more  
  about algorithms and how they are implemented before ever writing a single  
  line of code.  

  So, having researched your algorithm, you should still be in a "good place"  
  mentally and may now, with greater confidence, begin writing your  
  implementation of the algorithm. You can stop, do more research, ask for  
  opinions of others, work with the system architect, etc. to ensure that  
  what you are writing is the best possible answer you can write.  
  
  Having completed your algorithm, you *know* what it needs to do so you can  
  now write your first, golden path, unit test, looking for the desired  
  results from the git-go. If you paid attention and wrote your code with all  
  those things that TDD says are mere "refactoring", then you have written  
  excellent code to the best of your ability *to begin with* and the golden  
  path unit test will, in all probability, ***pass the first time***. If not, it  
  will be a trivial fix because you will understand, ***in depth***, the  
  algorithm you are testing. Again, you may proceed with confidence in what you  
  are doing.  
  
  Having now got your golden path running and ensured that the algorithm does  
  indeed answer the need of the requirement, you can now chuckle evilly and  
  begin the endeavor to "destroy" your algorithm by giving it all the adverse  
  tests you can come up with but, again, you know that in the back of your  
  mind, your algorithm does indeed do what it is supposed to do, you are now  
  simply on the path of making said *working algorithm* more robust, a positive  
  thing. The whole YAGNI thing never comes into it because the focus is on  
  making your algorithm more robust, not adding needless frills.   
  ***At no time was there ever a sense of failure because you never failed.***  
  
  You started with designing the best answer to the requirement you could and  
  then "proved" that you were correct by designing a golden path unit test  
  that also passed. Then you made your already-working algorithm more robust by  
  testing it to destruction repeatedly and adding strength and resilience with  
  every new destructive test.  Nothing ever failed, it might not have met your  
  initial goals but as time passes, you'll get better and better at this so that  
  "failure is not an option" anymore, you just write excellent code.  
  So, your test suite grows only to add more adverse conditions to your  
  algorithm to make it ever more robust ***and nothing more***.  

  TDD, on the other hand, has you start by examining the requirement, but does  
  ***NOT*** focus on designing the best solution, TDD just requires that you  
  believe that you understand the requirement.  

  Then, your very first action is to test the ***test harness***. How? By  
  writing a test and executing it, ***knowing full well that it will fail!***  
  Why? ***There isn't any algorithm to test! It's just an empty test to***  
  ***ensure that the test harness works!***  
  
  Well, we already know the bloody test harness works! Silliness!  
  Come on people, the code for most test harnesses is open source and  
  ...wait for it...  
  ***They have unit tests of their own that indicate whether or not the***  
  ***test harness code is functioning correctly before it's ever released***  
  ***out into the world!***  
  
  It's not like someone is going to sneak in during the night and change the  
  test harness on your machine with evil intent in mind so that all your TDD  
  activities will now be forever corrupted by an "evil" test harness.  

  So, now you throw something together that will meet the needs of the  
  requirement and run the test again. Difficult to understand code, bloated  
  code, inefficient code, inelegant code, so-called "clever" code is all  
  acceptable so long as what you wrote passes the test, which means,  
  ***you win! You made the test pass!***  
  
  Now, keep going, writing more and mores tests to accommodate adverse  
  conditions until some manager says "that's good enough, we need to ship".  
  
  If there is time, you may now begin to refactor your thrown together thing  
  to make it less ugly ***if there is time and resources to do so***.  

  And just how often is that the case? Managers are worried about "productivity"  
  not excellent code. They have budgets to consider, time constraints to meet,  
  "resources" (that's you) to re-allocate, etc. so the possibility of actually  
  going in and "refactoring" ***working code*** (and observe what I said -  
  *working* code, not *excellent* code) before it ships is most likely nil.  
  
  The result of this is the sad fact is that, mentally, you will start from and  
  continue to be, working from a position of ***FAILURE***. You ***start*** by  
  writing code that ***FAILS***. You continue to hope that you got something  
  close to the correct answer by dumping anything in your algorithm code that  
  works and re-running the test until it passes. ***NEVER MIND IF IT'S GOOD***  
  ***CODE, JUST ENSURE THE TEST PASSES.***  
  
  Don't believe me? Go re-read the description of the TDD process again.  
  And, no, the description is not my jaundiced opinion, it's quoted, verbatim,  
  from Wikipedia.  
  
  So, this constantly starting from a place of failure will eventually eat away  
  at some folks and, if you have a "manager" vice a "leader", that manager will  
  oft-times take advantage of that to further destroy your self-confidence and  
  belief in yourself. I watched as a manager reduced a female engineer to  
  tears by simply commenting on how often her code failed before she had  
  something that passed the test, never mind actually worked and how long it  
  was taking her to complete a task.    
  
  She was a newbie and the manager took great pleasure in tearing her down.  
  She quit soon after.  
  
  Some will say "Oh, she was just too sensitive". EEEHHHH, Wrong! There should  
  ***NEVER*** be a situation, ***especially between manager and worker***, where  
  an individuals level of "sensitivity" should be tested. ***NEVER!***  
  I ***really*** dislike TDD for that reason alone, never mind the crap code  
  that ends up in production because "there isn't time to fix it".

  So, to sum up, UTDD is an engineering tool designed to promote excellent  
  code and good morale, whereas TDD is a management tool designed to maximize  
  productivity ***at the expense of excellent code and good morale***.   
  Kent Beck, et. al., be damned!  

  If you are still reading, good for you! I will say this, TDD can have its  
  merits ***if applied properly and implemented correctly***. Sadly, as is so  
  often the case, "design" and "implementation" differ, radically, and that can  
  usually be laid at the feet of the "manager" in charge.  

  I have yet to work in a "good" TDD shop and now avoid them like the proverbial  
  plague.  

[Fallacies-Url]: ./The%20Fallacies%20of%20the%20Software%20Development%20Process.md  