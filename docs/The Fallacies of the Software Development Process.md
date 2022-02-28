The fallacies of the "Software Development Process".

It should be noted from the start that I used Wikipedia as my source for this  
paper, not because I wanted to plagiarize but because I want you, the reader,  
to be able to perform the same research and come to your own conclusions.  

Also, allow me to clarify something. This paper is the result of the musings of  
a grumpy Senior Software Engineer with decades of experience as an engineer  
who has grown weary of seeing his fellow engineers treated like dirt.  

The following paper is ***opinion*** and not hard fact, it is the collected  
observations of a lifetime of engineering and dealing with the environment  
in which said engineering took place and how "management" tried to  
"make it better and more efficient", may the Fates help us all!  

Let's begin by defining a few terms so that everyone knows that which I speak  
of, in other words, let's put together the Ubiquitous Language for tonight's  
session.

[Leaders and Managers and their (vast) differences][LeadersAndManagers-Url]  

- User story: (quoted from Wikipedia): In software development and product  
  management, a user story is an informal, natural language description of  
  features of a software system. They are written from the perspective of an  
  end user or user of a system, and may be recorded on index cards, Post-it  
  notes, or digitally in project management software. Depending on the  
  project, user stories may be written by different stakeholders like client,  
  user, manager, or development team.  

And just as an aside..."Post-It Notes"? "Index Cards"? Are these people  
kidding?  

- Use Case: (quoted from Wikipedia):  A use case is a list of actions or event  
  steps typically defining the interactions between a role (known in the Unified  
  Modeling Language (UML) as an actor) and a system to achieve a goal. The actor  
  can be a human or other external system. In systems engineering, use cases are  
  used at a higher level than within software engineering, often representing  
  missions or stakeholder goals. The detailed requirements may then be captured  
  in the Systems Modeling Language (SysML) or as contractual statements.  

User stories and use cases are the drivers behind TDD (which is ***not*** a good  
thing). We'll look at why this is so later in the paper and we'll also look at  
a methodology that avoids such things entirely yet gets the job done better  
than any other methodology outlined herein.  

- Mental Health: The state of being of an individual worker. The desired state  
  should be "happy" or at the very least "content". If not those, then one is  
  probably dealing with a bad case of "management" and productivity will  
  correspondingly suffer.  

- Job of a Software Engineer: Summed up and explicitly defined in just three  
  words: "Write Excellent Code". A software engineer has ***no other job***.  

  - Opinion: If your supervisor is asking you to do **anything else** other  
    than "write excellent code", then you are being ***prevented from***  
    ***doing your job*** and should justifiably complain or demand a significant  
    raise for doing inter-disciplinary work that covers multiple career paths!  
    This includes but is not limited to gathering requirements, designing  
    pretty web interfaces, tuning database queries, designing devops  
    pipelines, delivering Azure deployments, spending excessive amounts of  
    time documenting your progress ("what did you accomplish to day"-type  
    crap), etc.  

[ UTDD (Unit Test-Driven Design) vs. TDD (Test Driven Design)][UTDD-Url]  

  So...on to the actual software development methodologies themselves.  
  We now know the "how" of writing software, one may choose from a number of  
  different ways, I've outlined two above, there are others, pick the one that  
  works for you.  

  The methods for which we'll take that 50,000 ft view:
  - Waterfall
  - Continuous Integration
  - Incremental Development  
  - Rapid Application Development (RAD)  
  - Spiral  
  - Agile  
  - Other, advanced methodologies  

Let's begin with the old stand-by, the one that is used as the example of how  
*not* to do things, Waterfall.  

In summary, the project is broken up into predictable pieces:  
- Requirements Analysis
- Software Design
- Implementation  
- Testing  
- Integration  
- Deployment  
- Maintenance  

The hallmark of waterfall is that one step is completed, *in it's entirety*  
before moving on to the next step. This makes waterfall *extremely* brittle and  
inflexible and is *NOT* a recommended method for developing software.  
Really, the only good thing about waterfall is that it emphasizes acquiring  
good requirements as the first step. However, there is no formal process for  
gathering said requirements, it's left to the stake holders and users to  
determine what the system needs to do. As outlined later, the *last* people one  
should ask about requirements are *users*! Yes, that statement seems  
contradictory, all will be made clear when "users" are discussed later in the  
paper.  
The big fail for waterfall comes in that once a phase is completed, it is  
*never revisited*. So if customer requirements change, said changes are pushed  
off to the next version of the software regardless of the importance of the  
change.  

Next is "Continuous Integration". The article states that this is a software  
development model. I dis-agree, CI is a *process* that should be part of  
whichever development methodology is chosen. It's tough to implement in some  
circumstances (waterfall really can't make use of CI very well) but CI isn't,  
in my not so humble opinion, a "software development methodology", it's a  
process *used* by said methodologies.  
Nowadays, CI is often coupled with CD (Continuous Deployment) such that new  
code is automatically added to the production branch of source code, compiled  
and deployed as part of an automated process rather than a process in and of  
itself. One need only add code review at the start of the process to vastly  
improve the quality of deployed code.  

Next is Incremental Development. This one grew out of the perceived limitations  
of the standard waterfall approach. Requirements are still gathered but now  
they are broken up into mini-projects and each mini-project is "waterfalled"  
into existence using a similar methodology. Whilst this is better than  
waterfall, it's not much better because it's still brittle and does not respond  
well to changing user requirements.  

Then we have RAD! At one time, a long time ago, a development language, Delphi,  
promoted itself as *the* RAD tool to use. So much so that Microsoft felt  
threatened and came up with its own solution to Delphi - Visual Basic, the other  
RAD tool. So, what's so cool about RAD? The seeming inclusion of the user from  
the beginning of the development process.  
RAD allows the developer to sit down with a user and mock up user interfaces  
and models very quickly (hence the "Rapid" in RAD) and the user gets to apply  
instant approval/disapproval of the design *as it is being constructed*. This  
is great if your goal is to make the user happy. It's *not* great if you want  
to write good software. Why? It's *user driven* (again, I'll explain later).  
Sadly, I have even seen a shop in which the manager observed the creation  
process of some of these mock-ups and when the customer signed off on all of  
them, the next step was **ship it!**  
Yep, ship it. ***Never mind that there was no functional code behind the***  
***mock-ups***, the screens were approved so "obviously" the code was complete  
and it could be shipped! Marvelous "productivity", cut development time in  
half! Fortunately, that "manager" was soon fired for gross incompetence.  

Next is Spiral. What is spiral? A marriage between waterfall (in the form of  
incremental development) and RAD. A design is prototyped, the necessary support  
code is written, tested, etc. in accordance with the waterfall method and the  
development team basically does a "rinse and repeat" until the project is  
completed.  

There are a bunch of other "advanced" methodologies, I'm not going to go into  
all of them for reasons of time and perceived popularity. I will list them:
- BDD (Behavior driven development) - an offshoot of TDD
- Chaos (Fix the most important thing first! (as determined by the users!))
- Incremental funding (see government development idiocy for this one)
- Lightweight (has few rules and practices)
- Structured systems analysis and design (waterfall under a new name)
- Slow Movement (minimal time pressure - get it right the first time)
- V-Model (yet another waterfall)
- Unified Process (iterative process based on UML)
- Big Bang (little or no planning, comes with high risk)  

And finally, the sleeping bear in the room, Agile. This one was saved until  
last because it's a response to waterfall, it's *huge* in that there are entire  
books written about a single aspect of Agile and it's the most popular method  
out there right now.  
How many kinds of Agile are there? Well, the article refers to the following  
list:
- Dynamic Systems (DSDM)
- Kanban
- Scrum
- Crystal
- Atem
- Lean software development

A bit about each:
- DSDM - basically RAD with a bit of discipline thrown in. The main aspect of  
  DSDM is that it fixes cost, quality, time spent *at the outset* and adjusts  
  the projects deliverables to meet these criteria. *Great* management tool!  

- Kanban - an interesting approach in that someone seemingly in the know will  
  post the work items on a board (sometimes literally, otherwise in software)  
  along with the respective "state" of the work item e.g.
  - backlog
  - in progress
  - peer review
  - testing
  - done
  - blocked

  along with a place for defects and fast track items. Kinda looks like a  
  visual version of the afore-mentioned waterfall process only with pictures.   
  Originally developed by Toyota for their manufacturing processes when they  
  switched to a just-in-time production process. The idea was to show the  
  state of production items and what, if anything, was blocking their  
  completion. It's a nice idea and works well for visually displaying status.  

- Scrum - This is the process most often associated with Agile in that a set  
  of goals is broken up into time-boxed iterations called "Sprints" that  
  earmark what needs to be done. The hallmark of Scrum is the "daily standup",  
  a process whereby all the developers and project managers get together on a  
  daily basis and announce their progress or what might be blocking said  
  progress.  

  Theoretically, this allows managers to address blockages and clear them as  
  quickly as possible so that the intended progress can be maintained. It also  
  allows for changes in user requirements to be announced and addressed by  
  by either changing the content of the sprint or incorporating the change into  
  the next sprint thus allowing the project to "respond with agility" to  
  customer demands.  

- Crystal - an agile framework that focuses on individuals and their  
  interactions vice processes and tools. It is a direct outgrowth of one of the  
  core values as found in the "Agile Manifesto", a document well worth reading.  
  The hallmarks are this:
  - Teams can find ways on their own to improve and optimize their workflow
  - Every project is unique and always changing, which is why that projects  
    team is best suited to determine how it will tackle the work.  
    - Opinion: Given that most folks have not heard of Crystal (at least, I had  
      not), it can be presumed that, based on the above premises, management  
      would ***absolutely hate*** Crystal - too much freedom and empowerment  
      of the engineers.  

- Atem - Sorry, I can't find a web reference to Atem so I can't even add a  
  description here.  

OK, that concludes the 50,000 ft view of the software development processes.  
Now, I'll go through and tell you why they all suck.  
Again, allow me to emphasize, ***this is my opinion, colored by decades of***  
***experience*** developing software for everyone from the government to small  
businesses to large corporations, I've worked for them all at one point or  
another.  

Fallacy number one: While not explicitly stated in all the methodologies, there  
is a persistent reference to something collectively called the "user story" or  
"use case". The use case I can work with, the user story is an absolute sham  
and should *never* be used as a basis for software design and implementation.  
SHOCKING! Ok, here's why. I'll allude to a bit of history here in the form of  
an allegorical tale: Henry Ford was giving an interview at one point and was  
asked "How is it that you have such happy customers? How do you know what they  
want?". Henry smiled slyly and answered thus: "I don't give customers what they  
want, I give them what the need. If I were to give the customers what they want,  
I'd be breeding faster horses!".  
And that, my friends, is the secret. Users can only see the world through the  
eyes of their current situation and their first instinct is to "fix what's  
wrong by doing (insert whatever foolishness they think will fix things)" aka  
the "faster horse" syndrome. Software engineers should *never* give the customer  
what they want, they should *always* give the customer what they *need*. This  
is the big reason methodologies like RAD failed miserably - they are all  
customer-focused. This is an outgrowth of viewing the world through the eyes of  
management. "Make the customer happy! The customer is always right!", etc. ad  
nauseam.  
Nothing could be further from the truth! Now, allow me to clarify. The customer  
is indeed the one that drives software development but the viewpoint is all  
wrong and it usually starts out by said customer starting a sentence with a  
phrase similar to: "I need the software to..." and they give you some  
***solution*** that makes sense to them *as they see the world*.  
The epic fail here is that the customer doesn't know what's needed, they only  
know what they want. What's needed is to understand ***the problem***. As in  
the old saying "Half the solution is understanding the problem to begin with",  
was never more true.  
So, how should this be addressed? Get the user stories for sure. Gather the  
use cases as to how the software needs to respond to a given situation but then,  
turn all of that information over to a business analyst and the system architect  
to determine ***what the actual problems with the current environment are***.  
From those, you formulate the actual requirements for the system and go forth  
from there. You don't give the customers what they want, you give them what  
they *need*.  

Fallacy number two: Time. Without exception, all the methodologies above are  
timeline-based. Now, think about this: I put it to you that unless the  
fundamental laws of the universe change, assigning timelines to a process that  
is inherently a *creative* process is an exercise in futility.  
Allow me to pull from another paper of mine and distill my opinion down to the  
essence of the fallacy. And this is where managers will throw a hissy-fit  
because managers ***hate*** things they cannot control. They are seen as  
barriers to "productivity" and thus to be shunned at all costs and treated as  
anathema in the extreme.  

There are three attributes of software development that *no one* can control:
- the Unknown
- the Unforeseen
- the Incalculable  

What do I mean? Examples:
- The unknown: A project I worked on had a method for validating an xsd file  
  and the resulting xml file that was generated. The validation worked just  
  fine in .NET Full Framework. Our architect, not wanting to drown in technical  
  debt, mandated an upgrade to .NET Core. We researched and the method call  
  that performed the validation had not changed, the parameters were the same,  
  the results were reported in the same fashion. There was no documentation  
  that stated that the validation method had changed so we presumed that it  
  would "just work". Oops! Running the same code passed in FF, *failed* in  
  Core. We had *no idea* as to why and when the Lead Engineer (me) went to  
  the project manager and told her about it, the first and only question was:  
  "how long to fix it?". My answer: "I don't know". Her response "Why don't you  
  know!?" and the conversation went downhill rapidly from there.  
  The problem is that we had to look at the calling code, the support code in  
  the validation method itself, the actual validation code itself (thanks  
  Satya for open sourcing .net) and the input xsd and the unit testing harness  
  that had been re-written for .NET Core. How long would that take?  
  As long as it takes. We could not estimate how long as we had *no idea* where  
  to start looking so we had to look at *all of it*.  
  The response: "I can't work with that, I have people to answer to and they  
  want to know when this will be done!". Pure manager-speak. Totally inflexible,  
  totally demeaning in that it was implied that my team was completely  
  incompetent and that we should be able to pull a firm date of completion  
  out of thin air and stick to it or woe betide the consequences.  
  Did we find the flaw? Yes, eventually. It was in the new xsd file thus not  
  even our problem. We rely on valid input from the xsd team. *They* failed, but  
  *we* were held accountable for the delay.  

- The unforeseen: Sadly, the above is not the final aspect of the difficulty.  
  Once  we figured out where the flaw was, we used a tool (open source), called  
  LinqToXSDCore to convert the xsd file to useable .NET c# classes and methods.  
  The tool isn't perfect, the resulting c# needs a tweak or two and it's up to  
  the development team to figure out if it's a flaw in the code or a flaw in  
  the input xsd (sometimes it's even both) but the flaws were few and easy to  
  fix ***if you could edit the resulting output file***.  
  How did we know there were flaws? Simple - the tool generated a .cs file and  
  we went directly from generation to compilation and observed the output  
  window for errors. If there were none, tool did it's job, move on. If there  
  were errors, open the .cs file and fix them.  
  Aye, there's the rub - the output file. Once we fixed the xsd file, the next  
  step was to run it through the gadget and generate the c# file. Notice that  
  I am deliberately saying "file" - singular, not "files" - plural. You might  
  be able to see what's coming here. We ran the xsd and then wanted to go in  
  and fix the errors that came up so, naturally, we opened said .cs file in  
  Visual Studio 2019 ***and promptly crashed Windows!***  
  Oops! Epic fail! And this is repeatable - didn't matter the machine, didn't  
  matter the amount of installed RAM, etc. Open the file, crash Windows. We  
  had *no idea* why at the beginning and reported to that same PM the new  
  problem. Same response: "When will it be fixed?!". Answer: "I don't know".  
  And so it went. I finally tumbled to an obvious answer and tried opening the  
  file in an editor *not* Visual Studio - I used VSCode, a more modern, robust  
  editor environment and viola! It opened just fine and *only then* did I  
  confirm what the problem was - the code generator generated over  
  ***860,000 lines*** of code in a single .cs file. Visual Studio, being a  
  32-bit application, was simply overwhelmed by the file size and crashed and  
  took Windows with it. The fix: Go into the source of LinqToXSDCore and find  
  the code that generated the output file and modify it to generate multiple  
  output files! Easy fix, right? Yeah, save the program itself consists of  
  several ***tens of thousands of lines of code*** and we needed to go in,  
  find the generator code, figure out how to adapt it ***without breaking***  
  ***the rest of the code***, recompile the tool and then test it.  
  PM's response: "How long will that take?!". You can fill in the rest.  
  The unforeseen: The code generator worked flawlessly, did just what it was  
  supposed to do, however, the result was a file that VS could not handle.  

- The incalculable: See above PM question of "how long will it take?". This can  
  be generally broken down as follows:
  - If you have done it before, you *might* have a *rough* idea of how long  
    something might take. I personally am not comfortable doing that sort of  
    estimate on anything larger than a single method. That's called "reducing  
    the Cone of Uncertainty". On a project scale, the best I can do is contract  
    the cone of uncertainty as far as I can and then, pull a WAG (Wild-Assed  
    Guess) out of thin air and use that as the "estimate". How accurate will I  
    be? No idea.
  - If I have never done the algorithm before, I won't even bother with an  
    estimate, my answer is always "it will take as long as it takes".  
  
  You might be thinking "what do you mean!? Tech teams make estimates all the  
  time!". Yep, they do. Now you know where need for and the associated term  
  "Service Pack" comes from. The team will do the best they can to get the  
  code as close to operational as possible but *management* decrees that  
  such-and-such a date as arrived, so ***SHIP IT!*** and be damned to whatever  
  bugs might still exist. "We'll fix it in the Service Pack" aka "Windows  
  Update", aka...you get the idea. The date-based methodology only works if  
  you are willing to release buggy, possibly broken code to your customers.  

  Why do I not do estimates, you might ask? Simple. Software development, as  
  much as it is supposed to fit under the auspices of "Computer Science" is  
  actually *not* a "science" at all. This is an *art*.  
  Sure, we have science to *guide* us, there is Set Theory for databases, we  
  have pattern-based programming to assist us in creating good code, we have  
  Object Oriented Programming to help us model the real world, we have  
  intelligent IDE's to help us write good code but at the end of the day, all  
  of that relies on the *creative* mind of an engineer to make it all work.  
  Think about it. ***Every*** piece of software ever written, no exceptions,  
  began life as an idea in the mind of an engineer. Even AI-generated code,  
  started out as a blank screen and then an engineer had to write the AI  
  software that then generated the code. Software does *not*, contrary to the  
  belief of management, just spring out of thin air, written by some average,  
  every-day, *easily replaced* Joe Schmoe. A creative *expert*, an engineer,  
  has to *create* it and then bring it to life in an environment that will  
  support it.  
  Want a little entertainment that emphasizes the point? Go watch a movie, it's  
  an old one starring Charlton Heston and Rex Harrison called "The Agony and  
  the Ecstasy". It's about Michael Angelo and painting the Sistine Chapel  
  ceiling. Toward the end of the movie the Pope (Rex Harrison) hobbles out and  
  implores of Michael Angelo working way up on his scaffolding "When will you  
  make an end of it!?". Michael Angelo spits out a glob of paint, leans over  
  and answers "When it is finished.", turns over and goes back to painting.  
  I don't think anyone will dispute that Michael Angelo knows how to paint.  
  Thus it is with engineers, we know how to code and things will be done,  
  it's just that the project will be completed "when it is finished".  

  Now, stepping off my soap box, if you are still reading, here is the promised  
  alternative to the above. It's quite simple and I won't go into too much  
  detail as I'm in the process of writing a gadget to support this methodology,  
  but the gist is this:  
  - NO TIMELINES - they're a lie anyway so don't even bother with them. However,  
    I recognize that both leaders and managers need some sort of metric to  
    judge progress, that's dealt with in the process.  
  - Embrace S.O.L.I.D in its entirety, *especially* the "S" (Single  
    Responsibility).  

  You're gonna need several types of personnel on your cross-functional team:
  - Engineers (duh).
  - Business Analyst (BA) (someone that understands the *business* processes)
  - System Architect (SA) (someone that has the "Big Picture" in mind all the  
    time and guides how new software will fit in with the current environment)  
  - Project Manager (PM) (someone to guide and monitor progress)  
  - Development Manager (DM) (someone that knows both the strengths and, more  
    importantly, the weaknesses of the development team)  

In general the process works like this:
- Get together the following folks: the stakeholders (the folks with the  
  problem), the BA and, if not otherwise occupied, the SA.  
- Ask them to describe the deficiencies in the current system or the goals to  
  be achieved in a new system.  
  ***DO NOT ASK THEM HOW IT SHOULD WORK***, the focus is on what's either  
  broken or missing, we do *not* care how they think how it should be fixed!  
- The BA and the SA will sit down and come up with a proposal or two that  
  addresses the concerns of the stake holder.  
- Once a proposal is accepted, now begins the process of applying the "S".  
  The BA and SA will break the proposal down into manageable chunks and from  
  those chunks, generate requirements. The BA will generate acceptance tests  
  (see Gherkin). 
- Once the requirements and acceptance tests are generated, it's up to the PM  
  to determine what gets written in what order. The BA will have input into  
  that but it's the PM's job to make the final decisions.  
- The DM now steps in to make assignments based on the known abilities of the  
  available team.  
- Now, finally, *at this stage* does an actual engineer become aware of the  
  new project. Said engineer is given a task to perform. They will begin  
  coding on that task, sending daily progress reports to the PM as to how far  
  they have progressed towards completion or seek out input from the DM if  
  there is a roadblock to progress.  

The key is the task. It *must* be a Single Responsibility such that it can be  
written by one or at most two engineers in a relatively short amount of time.  
It should be easy to analyze and construct the correct algorithm to support the  
task.  
Since the task will be small, appreciable progress will be easy to show, one  
might write a dashboard web page that shows overall progress, etc. Changes are  
easy to incorporate because the design has been broken down into "S" chunks.  
Thus if a customer has a change in functionality, the entire system is agile in  
it's response simply by going through the chunking process and adding the new  
task(s) to the mix.  
Documentation is kept to an operational minimum, mainly consisting of ensuring  
that the requirements are fully expressed and there is no "mystery" in what  
needs to be done. Queries as to how to proceed, etc. can all go into the  
workflow documentation as desired. New team members need only review the  
workflow to see what's expected, where the project is at and where they will  
fit in.  

Nowhere in the above do you see "timeline", "sprint", "time boxing", "estimate",  
etc. Nor do you see users driving the process. Their input is taken, but only  
as the grist for the mill of the BA and SA to determine what the actual  
solution will look like. User stories become the source of the motivation, not  
the source of the solution. To paraphrase Henry Ford, we aint in the business  
of breeding faster horses.  

Productivity is still a metric as can be observed via the daily progress  
entries. There is no embarassment caused by "daily stand ups" where you get to  
report your ongoing "failure" to move forward or, worse, consider lying and  
not reporting a difficulty because you don't want to look like an idiot to your  
peers (that whole mental health issue again), nor is your chain of thought  
broken by interruption due to these silly meetings. BUT, "productivity" is a  
by-product of code excellence as the focus here is to write excellent code.  
How long will it take? As long as it takes. It'll be completed when it is  
finished. The thing that management doesn't want to acknowledge is that their  
team will do their utmost, bringing all the awesome power of their collective  
creativity to bear on the problem at hand ***and solve it*** without the  
"help" of said manager. Leaders on the other hand not only acknowledge this  
fact, they do *everything in their power* to increase the awesomeness of their  
team at every opportunity that presents itself. Makes them look good to their  
own bosses.  

Productivity is still paid homage and can still be monitored but no more is the  
onus on the engineer to fix *any* mistake made by *anyone*. It is said that  
excrement roles down hill and sadly, the developer engineer is at the bottom  
of the hill and is thus held accountable for *everything* because "the code  
wasn't completed on time!". I have grown weary indeed of being held accountable  
for things that are not only not under my control but not even my purview and  
sometimes not even my bailiwick!  

Leaders can embrace the above process both because they can monitor and show  
progress but they are not required to participate on a daily basis - they need  
step in only when they are needed to supply some expertise. The rest of their  
time can be well spent in garnering additional resources to improve the ability  
of their teams e.g. new classes, books, conferences, etc. They can focus on  
the team as opposed to what the team is doing.  

THAT is how you maintain a happy, productive, progressive, adaptable team!  

[UTDD-Url]: ./UTDD%20versus%20TDD.md  
[LeadersAndManagers-Url]: ./Define%20Leader%20and%20Define%20Manager.md  