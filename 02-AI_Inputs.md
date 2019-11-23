# AI Inputs

This section considers the legal responsibilities for AI modelling inputs. AI model inputs are typically in the form of data. That data may be about different subjects, be from various sources and exist in different forms. Depending on the subject, source and format different aspects of legal responsibility and liability arise. This are considered in the following sub-sections, subject; source and format.  

## Subject 
### About an individual  
When working with data about an individual, an understanding of information privacy laws forms part of the responsibility of the work. In Australia, information privacy laws that regulate the private sector and Federal Government agencies are found in the _Privacy Act 1988_ (Cth) (the _Privacy Act_). The definition of "about" an individual is a threshold quesiton considered by the Courts in the application of the _Privacy Act_. 

In _Privacy Commissioner v Telstra Corporation Limited [2017] FCAFC 4_ the full Federal Court affirmed that just because a person's identity is reasonably ascertainable from a piece of information it does not mean it is personal information under the _Privacy Act_. The defintion requires it must also be "about" a individual. In that case, journalist Ben Grubb asked Telstra for all the metadata that it held about him (around the same time the mandatory metadata retention laws were being debated). Telstra initially gave Mr Grubb some information, but refused to give him access to its mobile network data, which included metadata such as IP addresses and geolocation data. Mr Grubb then complained to the Privacy Commissioner. The Privacy Commissioner determined the mobile network data information in question was "personal information" as Mr Grubb’s identity could be reasonably ascertained from the information by using other information held by Telstra. Telstra appealed to the Administrative Appeals Tribunal which formed the view that mobile network data was about connections between mobile devices and not "about" Mr Grubb. This was upheld by the Full Federal Court that did not find it necessay to consider if mobile network data was personal information because the threshold question has not been met.

At the same time, the mandatory data retention provisions in the _Telecommunications (Interception and Access) Act 1979_ (Cth) section 187LA  deems information that must be retained by telecommunications companies as being personal information “about an individual” if the information relates to the individual or a communication to which the individual is a party.

### Definition of personal information  
Once the threshold consideration of "about" an indivdual is met, it becomes relevant to consider if the data you are working with is personal information and, therefore, whether the responsibilities defined in the Privacy Act 1988 (Cth) will apply.  

> "Information or an opinion about an identified individual, or an individual who is reasonably identifiable: whether the information or opinion is true or not; whether the information or opinion is recorded in a material form or not."


### Principles for handling personal information   
If the data could be characterised as personal information, Schedule 1 of the Privacy Act 1988 (Cth) defines the principles to be observed.  


| APP | Short Description | Details |
|-----|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 | Transparency and Privacy policies | Clear, legible, accessible, APP Privacy policy that explains : <ul><li> the kind of information collected; </li> <li> how it is held; </li> <li> how it can be accessed to be corrected;</li>  <li> process for complaints on breach of APPs.</li>  <li> if it is likely to be disclosed overseas</li> |
| 2 | Anonymity and Psuedonymity | Reflects 'right to be anonymous' and gives individuals the option of not identifying themselves. |
| 3 | Collection of solicited information | Provides when and how an organisation may collect personal and sensitive information. Must not be collected unless it is reasonably necessary to an organisations activities (service it delivers) . |
| 4 | Unsolicited information | Obligations on receipt of information it did not solicit. Would the organisation have been able to collect the information under APP 3 (reasonably necessary to its activities); if so APPs 5-13 will apply to the info. If there is no reasonable grounds for having the info it must be destroyed or de-identified. |
| 5 | Notification of the collection of personal information | Provides that organisation must make individuals aware of the practices of their privacy policy: <ul><li> what is collected; </li> <li> how it is used (if it is disclosed);</li> <li>  how it can be corrected;</li> <li> how it is secured; </li> <li> contact details of the APP entity; </li><li> if data is collected about the individual from anyone other than the individual themselves (e.g. another organisation / credit reporting);</li> <li> if the collection is required by law (if so which law) Consequences to the individual if the info is not collected;</li> <li> how it can be accessed by the individual </li> |
| 6 | Use or disclosure of personal information | If an organisation collects information for a purpose (the primary purpose – by APP3 we know that purpose being reasonably necessary for the organisations activities) it must not use the information for another purpose (a secondary purpose). Other uses are only available by obtaining consent |
| 7 | Direct marketing | Governs the use of PI to communicate directly with an individual to promote goods. It provides tha PI can only be used for this purpose in certain circumstances/ conditions: <ul><li> where an individual would reasonably expect it (such as with informed consent); </li> <li> must have a clear option to opt out; </li> <li> must stop when an individual opts out. </li> |
| 8 | Cross border disclosure of personal information | Limits on disclosure of personal information outside Australia – generally only to recipients with information privacy laws substantially similar to our own. |
| 9 | Adoption, use or disclosure of government related identifiers |Limits when organisations may adopt use or disclose govt identifiers: <ul><li> Medicare numbers;</li> <li> Tax File Numbers;</li> <li> Australian passport numbers</li> <li> [NB separate legislation also governs use of these identifiers] </li> |
| 10 | Quality of personal information | Reasonable steps that the information is accurate up to date and complete. |
| 11 | Security of personal information | Reasonable steps to protect the information. |
| 12 | Access to personal information | Must provide access when requested by an individual (to their own info). |
| 13 | Correction of personal information | Must facilitate requests by individuals to have their information corrrected. |
  
### Best practice for handling personal information in data science  
## Sources 
### Understanding terms of use  
Gathering data from online social media platforms is described as "a primordial step in many data science fields" (Hernandez-Suarez _et al_ 2018). Digital formats revolutionised many industries where the act of copying, that was once laborious and time consuming in printed formats, became instantaneous, cheap and even incidental. Data in digital form is ubiquitous and is capable of being used for various purposes by various parties. When working with data, an understanding of the terms of its use forms part of the responsibility of the work. 

### LinkedIn  
LinkedIn is a professional networking site with over 500million members. The platform allows members to post resumes, job listings, statuses and build profesional networks by making "connections" with other LinkedIn members. LinkedIn offers additional services including news feeds, messaging, short form publishing, online learning and from analysis of its members generates insights into [top employers](https://www.linkedin.com/pulse/top-companies-2019-where-australia-wants-work-now-natalie-macdonald/) and [workplace learning](https://learning.linkedin.com/content/dam/me/business/en-us/amp/learning-solutions/images/workplace-learning-report-2019/pdf/workplace-learning-report-2019.pdf). The commercial and research applications of LinkedIn member data include analysis of workforce data, sincluding supply and demand across industries, job types and educational qualifications.

The legality of webscraping LinkedIn user profiles has been considered by US Courts in 2017 and again in 2019. In 2017  claiming it was an invasion of the privacy of its members and breached the terms of use of its site. hiQ Labs harvests user profiles from LinkedIn and uses them for analysis including, for example, *predicting* when employees are likely to leave their jobs. LinkedIn's [terms of use prohibits webscraping](https://www.linkedin.com/help/linkedin/answer/56347/prohibition-of-scraping-software?lang=en). On May 23, 2017, LinkedIn sent hiQ Labs a letter demanding that the company cease scraping activities and threatened legal action under the Computer Fraud and Abuse Act (CFAA). HiQ Labs sued LinkedIn, accusing the company of anticompetitive behavior and of violating the company's free speech right to access publicly available information. The US federal judge held LinkedIn cannot block third party web scrapers from scraping data from publicly available profiles.

LinkedIn appealed the decision and on September 9, 2019 the Ninth Circuit upheld the decision of the lower Court, granting an injunction against LinkedIn clocking hiQ from accessing and scraping publicly available websites, [HiQ Labs V. LinkedIn](http://cdn.ca9.uscourts.gov/datastore/opinions/2019/09/09/17-16783.pdf). 

### Twitter  
Twitter is a social media application with over 300million active users. The platfor allows users to post short messages (of either 280 or 140 characters, dependent on the language) known as "tweets". As a data source, Twitter is used in research across a number of disciplines, such as sociology, computer science, media and communication, political science and engineering. Twitter makes it data available via a [number of Application Programming Interfaces (API)](https://help.twitter.com/en/rules-and-policies/twitter-api). The freely available ['Standard' API](https://developer.twitter.com/en/docs/tweets/search/overview) returns data from the past 7 days. Twitter's [terms of use expressly prohibit scraping](https://twitter.com/en/tos). 

In contrast to LinkedIn, where professional resumes may be considered collections of facts, the strings of text and images available in tweets may be characterised as copyright material, depnding on the circumstances. This legality of these forms of content is discussed below in formats.

### Facebook  


### Google geo-coding


## Format: Text, Pictures, video and, copyright

#### References for this chapter
A. Hernandez-Suarez, A., Sanchez-Perez, G., Toscano-Medina, K., Martinez-Hernandez, V., Sanchez, V. and Perez-Meana H., (2018) 'A web scraping methodology for bypassing Twitter API restrictions', arXiv:1803.09875 [cs.IR], <https://arxiv.org/pdf/1803.09875.pdf>
