
class: center, middle, theBackground

## Your Company Cares About **FOSS Sustainability**
## But Are You **Measuring** Your Contributions?
&nbsp;
### **Duane O'Brien**
### **Dani Gellis**
### indeed.com
&nbsp;
### **Permissions** Granted : 📸  📹  📰  📬  🐦

---

layout: true
class: theBackground

.footnote-bg[]

.footnote[@DuaneOBrien | @DanisYellis | Made with [Remark](http://remarkjs.com/)]

---

# About **Duane**


* Past Lives :

--

 * 🧙‍♂️ DevsOps-ish **Perl** Guy
--

 * 🧟‍♂️ **Javascript** Ruiner
--

 * 🤹‍♂️ **Agile** Facilitator
--

 * 👨‍🏭 Open Source **Enabler**
--


* Current Life : 👨‍🔧 Head Of Open Source at **Indeed**
--


* Next Life : 👨‍🎤+ 🧛 + 🧙‍♂️ +  🤖 = ?


---

# About **Dani**


* Past Lives :

--

 * 👩‍🚒 AmeriCorps Member
--

 * 🌲 Backpacking Trip Leader and Outdoor Educator
--

 * 👩🏻‍💻 Software Engineering Intern
--

 * 🙋🏻‍♀️ Coding Instructor
--


* Current Life : 👧🏻 Tools Engineer for Indeed Open Source
--


* Next Life : 👩🏼‍🎤+ 👩‍🚀 + 🧚‍♀️ +  🤖 = ?


---
# Overview

--
* ### Program **Overview**

--
* ### What We Decided To Measure And **Why**

--
* ### Tools We Looked At, Implemented, And **Built**

--
* ### What We Learned **So Far**

--
* ### What We'll Measure And Build **Next**

---
# Indeed's **Open Source** Program
--

* ### Open Source Is **More** Than Software

--

* ### We **Meet You** Where You Are

--

* ### Predictable, **Long Term Support** Is The Ideal

---

class: center, middle, theEmphatic

# To build a culture of **active** and **recurring** open source **participation**

---

class: middle, theEmphatic

# If you can't measure it, you can't improve it - **Peter Drucker**

---

class: center, middle, theEmphatic

<img src="Images/LordKelvin.jpg" width="80%"  />

???

“I often say that when you can measure what you are speaking about, and express it in numbers, you know something about it; but when you cannot measure it, when you cannot express it in numbers, your knowledge is of a meagre and unsatisfactory kind; it may be the beginning of knowledge, but you have scarcely, in your thoughts, advanced to the stage of science, whatever the matter may be.” - Lord Kelvin

---

class: center, middle, theEmphatic

# What Counts As A **Contribution?**

---

# What **Not** To Measure And **Why**

--

## Lines of Code

--

 * ### Encourages Code Quantity With No Eye Toward Quality

--

## Contribution Counts

--

 * ### Competition Discourages New Contributors

--

 * ### Projects Have To Manage Low Quality Contributions

---

# Other **Important** Considerations

--

## Sharing **Raw** Numbers
--

## How To Account For **Personal** Projects

--

## What Does **"Company Related"** Mean?

---


class: center, middle, theEmphatic

# Active **Recurring** Participants

---

# Active **Recurring** Participants

* ## **Active** - triggered an event that we care about

--

* ## **Recurring** - two or more days of activity

--

* ## **Participation** - a broad category of events

---

class: center, middle, theEmphatic

<img src="Images/ActivityIndicator1.png" /><img src="Images/ActivityIndicator2.png" />

---

class: center, middle, theEmphatic

<img src="Images/PeltingWithStones.jpg" width="80%"/>

???

Not all open source activity is on GitHub
I have a whole talk about it.
But it can give us an Accurate read, even if it's not very precise


---

class: center, middle, theEmphatic

<img src="Images/GitHubTalk.png" width="80%"/>

???

Not all open source activity is on GitHub
I have a whole talk about it.
But it can give us an Accurate read, even if it's not very precise


---

class: center, middle, theEmphatic

<img src="Images/AccuracyAndPrecision.png" width="70%"/>

???

Potato Metrics

---

class: center, middle, theEmphatic

<img src="Images/GoodOldGoogleForms.png" width="70%"/>

???

How we captured/capture non-github requests (and why)
---
class: center, middle, theEmphatic

# Tooling
--

 ## The Challenge (and opportunity)
 ### We’re measuring something different

---
class: center, middle, theEmphatic
## We’re measuring something different
### Indeed Employee (User) contributions
### vs.
### Indeed's Open Source (Org/Repo) health

####Many open source tools for measuring the latter, but None for the former
???
How can we help the Open Source community vs. how much does the Open Source community care about our project

Everyone else is measuring their projects and contribution activity for them.

We care about Indeedians contributing out. Want to measure contributions


---
class: center, middle, theEmphatic

# Existing Tools

<img src="Images/XKCDstandards.png"  />


#### None of these tools do what we want- but can they be adapted?

???
Looked at 4 or 5 different tools- Netflix OSS Dashboard, Amazon's OSS Dashboard, Bitergia
  They are all Org/Project oriented, not User
    Getting all users for an ORG gives us some people we don't care about
    And misses some indeed employees
      who contribute to OS, but not with Indeed
---
# Microsoft’s Github Crawler
### Gets information about events on GitHub
#### But, it's Org/Repo focused
####  Yes, we _CAN_ adapt it
##### Pros and Cons
???
Started with github because there are lots of tools for it, it has a robust API, and it’s where most, though not all, of the contributing is happening anyway
Bitergia has a solution that looks at more than just github, but,
 crawler seemed easiest. In JS, which is what I know and I was the only engineer (growing team)

 Positives:
 	- Extensibility. Some day we’ll care about our org/repo health too and it will be easy to add
  - Queueing and rate limiting are handled
  - Adding to an existing, used open source project
Negatives:
  - Figuring out a large, involved codebase
  - Can't use webhooks (probably the coolest feature) for user events which is one of the coolest parts of the crawler (only crawls when there are new events)
---
# The "Interim Dashboard"
## This came first to get us some numbers
### Nothing to look at, but very useful!

???

before figured out how crawler works - just get us some numbers
basically just poking the github api for user events and filtering them by events we care about
  and then just put the output into a google sheet
was VERY useful for counting Hacktoberfest contribs, getting a baseline, etc.
  -Duane will be talking about an intitiative for which we need to know who's contributed in a given month. If that's all you need, this is really all you need to do. And I'm happy to share that code (I'll open source it soon)

---
# Events we’re measuring, and why

##Events we are measuring:
* Comments
* Pull Requests
* Issues
* Code Reviews

## Events we’re not:
* Push Events

???
Not just code, also comments and Reviews
Not push events because
  - probably personal projects
  - not good open source hygiene
---
# Dashboard Solutions
## Tried MeasureOSS
### It was also Org/Repo focused
#### and adding user views would have made everything more confusing
???
Once we had the contribs, need to show them somehow
Measure:
An important part of open source work- make sure the upstream wants the change!
They were interested in the concept, but not in changing their project
---
# Dashboard Solutions
## Use Imhotep and IQL (Imhotep Query Language)
* 2 Different Dashboards
  * Individual Contributor Dashboard
  * Aggregate Dashboard

???
decided to use Indeed's OS project
  - allows you to build and query large datasets, and build tools for analysis and dashboards
  - at Indeed, it came with a dashboard maker
---
# **Contributor** Dashboard

## Used by **Individuals**

--
## Provides **Contribution** Insights

--
## Useful For **Quarterly Reviews**

---
class: center, middle, theEmphatic

<img src="Images/IndividualDashboard.png" width="90%" />

???
our contributors are happy to have it for reviews
shows: weekly and total contribs, where you're contributing
---
# **Aggregate** Dashboard

## Used by the **Open Source Program Office**

--
## Provides **Program** Insights

--
## Useful For **Improving The Program**

???
Are our initiatives working?

---
class: center, middle, theEmphatic

<img src="Images/AggregateDashboard.png" width="90%" />

???
All contribs, contribs by month, which projects, Active Recurring Participants
---
# What’s next
1. Adding other online code repositories (Bitbucket, Apache, etc.) and organization tools (Jira, Slack, etc.)
### Important for 2 reasons:
* Encouraging and tracking non-code contributions
* Tracking all contributions, not just the ones on GitHub
???
so many other things are helpful besides just code- design, project management, legal, etc.
However, we do have a form for people to tell us about their other contribs
---
# What’s next
1. Adding Bitbucket, Apache, Jira, Slack, etc.

--
2. Counting PushEvents to our own (IndeedEng) repos?

--
3. Tracking IndeedEng repo and org health

--
4. More filtering of events (do some repos have more weight?)
 * Projects Indeed uses
 * Stop measuring a user's personal practice projects on GitHub

--
5. A toggle to put in and take out Indeed-owned projects


???
(the metric everyone else is tracking) - we do care if we’re contributing to the OS community that way
- Track inbound requests, for example

---

class: center, middle, theEmphatic

# What Have We Learned **So Far**

---

# Highly Active Users : **Outliers**

--

## How Active? **10x?**
---

# Highly Active Users : **Outliers**

## How Active? ~~10x?~~ **100x!!!**

--
## Competition Discourages **New Contributors**

--
## Don't Build For **Edge Cases**

--

## Should Even Out **Over Time**

---

class: center, middle, theEmphatic

# Measuring The Effect Of **Initiatives**

---
class: center, middle, theEmphatic

<img src="Images/Hacktoberfest-2018.png" width="80%"  />

---
class: center, middle, theEmphatic

<img src="Images/contributions-october-2018.png" width="80%" />

---

class: center, middle, theEmphatic

# The **November** Lull

---
class: center, middle, theEmphatic

<img src="Images/contributions-november-2018.png" width="80%" />

---
class: center, middle, theEmphatic

<img src="Images/24PullRequests.png" width="80%"  />

---
class: center, middle, theEmphatic

<img src="Images/contributions-december-2018.png" width="80%" />

---
class: center, middle, theEmphatic

<img src="Images/FOSSContributorFund-Rectangle.png"  />

---
# FOSS **Contributor** Fund

## **Dedicated** Budget Unrelated To Orgs/Confs
--

## Projects Are **Nominated** By Employees
--

## Projects Must Meet **Selection Criteria**
--

## Contributors **Vote** On Allocation : $10,000 / 🗓
---

# FOSS **Contributor** Fund : **January**

## January Contributions: Went **Up!** 📈

---

class: center, middle, theEmphatic


<img src="Images/contributions-january-2019.png" width="80%" />


---

# FOSS **Contributor** Fund : **January**

## January Contributions: Went **Up!** 📈

## Nominated Projects: **20** Total - 5 **Unknown** 🕵️‍♀️

---

# FOSS **Contributor** Fund : **February**

## February Contributions: Went **Down...** 📉

---

class: center, middle, theEmphatic


<img src="Images/contributions-february-2019.png" width="80%" />

---

# FOSS **Contributor** Fund : **February**

## February Contributions: Went **Down...** 📉

## Nominated Projects: **5**

???

october - 34
november - 23
december - 27
january - 32
february - 26
march - 17 (but on track with Jan)


---

# FOSS **Contributor** Fund : **March**

## March Contributions: **TBD** 🤷‍♂️

---

class: center, middle, theEmphatic


<img src="Images/contributions-march-2019.png" width="80%" />
---

class: center, middle, theEmphatic

# What We **Measure** And **Build** Next

---

# What We **Measure** And **Build** Next

## Are We **Creating** New Contributors?

--
* ### First Time Contributors Events

--
* ### Onboarding Training

--

## Are We **Sustaining** Projects We Use?

--
* ### OSS Compliance + Contribution Measurement = 🎉

---
# Review

--
* ### **Values** First. **Goals** Second. **Tooling** When You **Need** It.

--
* ### Be **Mindful** About What You **Measure**

--
* ### Know **Why** Before Building The **How**

--
* ### **Start** With What Exists

--
* ### The **Measurement** Is Not The **Goal**

---

class: center, middle, theEmphatic

### **If you can't** MEASURE **it, you can't improve it** - Peter Drucker

<img src="Images/LordKelvin.jpg" width="60%"  />

---

class: center, middle, theEmphatic

### **If you can't** MEASURE **it, you can't** IMPROVE **it** - Peter Drucker

<img src="Images/LordKelvin.jpg" width="60%"  />

???

“I often say that when you can measure what you are speaking about, and express it in numbers, you know something about it; but when you cannot measure it, when you cannot express it in numbers, your knowledge is of a meagre and unsatisfactory kind; it may be the beginning of knowledge, but you have scarcely, in your thoughts, advanced to the stage of science, whatever the matter may be.” - Lord Kelvin

---
class: center, middle, theEmphatic

# Questions?

---
class: center, middle, theEmphatic

# Thank You
