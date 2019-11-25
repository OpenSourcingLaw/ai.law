# 2. AI Inputs

This section considers the legal responsibilities for AI modelling inputs. AI model inputs are typically in the form of data. That data may be about different subjects, be from various sources, exist in different forms and undergo further processing or transformations. Depending on the subject, source and format different aspects of legal responsibility and liability arise. These are considered in the following sub-sections, subject; source and format. Emerging norms on data processing are also discussed. 

## 2.1 Subject 

### 2.1.1 About an individual  
When working with data about an individual, an understanding of information privacy laws forms part of the responsibility of the work. In Australia, information privacy laws that regulate the private sector and Federal Government agencies are found in the _Privacy Act 1988_ (Cth) (the _Privacy Act_). The definition of "about" an individual is a threshold quesiton considered by the Courts in the application of the _Privacy Act_. 

In _Privacy Commissioner v Telstra Corporation Limited [2017] FCAFC 4_ the full Federal Court affirmed that just because a person's identity is reasonably ascertainable from a piece of information it does not mean it is personal information under the _Privacy Act_. The defintion requires it must also be "about" a individual. In that case, journalist Ben Grubb asked Telstra for all the metadata that it held about him (around the same time the mandatory metadata retention laws were being debated). Telstra initially gave Mr Grubb some information, but refused to give him access to its mobile network data, which included metadata such as IP addresses and geolocation data. Mr Grubb then complained to the Privacy Commissioner. The Privacy Commissioner determined the mobile network data information in question was "personal information" as Mr Grubb’s identity could be reasonably ascertained from the information by using other information held by Telstra. Telstra appealed to the Administrative Appeals Tribunal which formed the view that mobile network data was about connections between mobile devices and not "about" Mr Grubb. This was upheld by the Full Federal Court that did not find it necessay to consider if mobile network data was personal information because the threshold question has not been met.

At the same time, the mandatory data retention provisions in the _Telecommunications (Interception and Access) Act 1979_ (Cth) section 187LA  deems information that must be retained by telecommunications companies as being personal information “about an individual” if the information relates to the individual or a communication to which the individual is a party.

### 2.1.2 Definition of personal information  
Once the threshold consideration of "about" an indivdual is met, it becomes relevant to consider if the data you are working with is personal information and, therefore, whether the responsibilities defined in the Privacy Act 1988 (Cth) will apply.  

> "Information or an opinion about an identified individual, or an individual who is reasonably identifiable: whether the information or opinion is true or not; whether the information or opinion is recorded in a material form or not."


### 2.1.3 Principles for handling personal information   
If the data could be characterised as personal information, Schedule 1 of the Privacy Act 1988 (Cth) defines the Australian Privacy Principles (APPs) to be observed.  


| APP | Short Description | Details |
|-----|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 | Transparency and Privacy policies | A requirement for a clear, legible, accessible, privacy policy that explains: <ul><li>the kind of information collected; </li> <li>how it is held; </li> <li>how it can be accessed to be corrected;</li>  <li>process for complaints on breach of APPs;</li>  <li>if it is likely to be disclosed overseas.</li> |
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
  
### 2.1.4 Issues arising in AI and ML

#### ACCC v Google
On October 29, 2019 The Australian Competition and Consumer Commission (ACCC) started proceedings in the Federal Court against Google, alleging they engaged in misleading conduct and made false or misleading representations to consumers about the personal location data Google collects, keeps and uses. This is an example of a regulator enforcing APP1, which requires a privacy policy clearly explain how data is collected, used, held and disclosed (if applicable).


#### Secondary uses of personal information
The _Privacy Act_ makes a distinction beween primary and secondary uses of data and this has implications for AI inputs. [insert defintion of primary purpose here] The datasets on which ML is trained are likely to have been collected in the first place for a primary operational purpose related to the individual (e.g. to provide a service, to transport a passenger, to connect to a mobile network) (Salinger 2019).  Re-use of that dataset for training ML is potentially a secondary use, unrelated to the primary purpose.  The starting point in privacy law is that secondary uses are not allowed, unless an exception to that rule applies. "With the consent of the individual" is one such exception, but is generally not practical for large datasets.  There are other exceptions such as "for law enforcement purposes" which will generally not apply, which leaves research exceptions as the most likely path for the development of AI.  However, research exceptions (which differ in scope between the federal Privacy Act and State and Territory-based privacy laws) typically define "research" narrowly; requiring elaborate processes to balance and test the ethical implications of allowing the secondary use or disclosure of personal information without consent (such as Human Ethics Review Committees) and raise additional questions about whether the proposed research is in the public interest, such as beneficence and impact on vulnerable populations. Use of information about individuals in AI requires careful observance of the APPs and where it is a secondary use of data it requires extra steps to ensure its use is lawful.

#### Creation of personal information
The creation of

### 2.1.5 Best practice for handling personal information in data science  
There is an excellent [Guide to data analytics and the Australian Privacy Principles](https://www.oaic.gov.au/privacy/guidance-and-advice/guide-to-data-analytics-and-the-australian-privacy-principles/) which offers advice to minimise the use of personal information and the risks of working with it including:  
* Use de-identified data where possible (the OAIC also provides a guide on de-identfication [here](https://www.oaic.gov.au/privacy/guidance-and-advice/de-identification-and-the-privacy-act/));
* Ensure the accuracy of the data you are working with (this may involve taking extra steps to check the quality of data provided by third parties);
* Be open and transparent about privacy practices;
* Organisations undertaking data analytics activities should include general information abou those activities in their APP privacy policy;
* Using ‘all the data’ for ‘unknown purposes’ will expose organisations to privacy compliance risks.
Other methods to minimise the use of personal information include the use of age ranges in place of a specific age. The benefit of working with volumnous and granular, transactional and behaviourial data is that patterns in such data itself can be more insightful than crude measures such as age and gender, and may even lead to greater accuracy than the use of personal information.

## 2.2 Sources 
### 2.2.1 Understanding terms of use  
Digital formats revolutionised many industries where the act of copying, that was once laborious and time consuming in printed formats, became instantaneous, cheap and even incidental. Data in digital form is ubiquitous and is capable of being used for various purposes by various parties. When working with data, an understanding of the terms of its use forms part of the responsibility of the work. 

### 2.2.2 LinkedIn  
LinkedIn is a professional networking site with over 500million members. The platform allows members to post resumes, job listings, statuses and build profesional networks by making "connections" with other LinkedIn members. LinkedIn offers additional services including news feeds, messaging, short form publishing, online learning and from analysis of its members generates insights into [top employers](https://www.linkedin.com/pulse/top-companies-2019-where-australia-wants-work-now-natalie-macdonald/) and [workplace learning](https://learning.linkedin.com/content/dam/me/business/en-us/amp/learning-solutions/images/workplace-learning-report-2019/pdf/workplace-learning-report-2019.pdf). The commercial and research applications of LinkedIn member data include analysis of workforce data, sincluding supply and demand across industries, job types and educational qualifications.

The legality of webscraping LinkedIn user profiles has been considered by US Courts in 2017 and again in 2019. HiQ Labs harvests user profiles from LinkedIn and uses them for analysis including, for example, *predicting* when employees are likely to leave their jobs. LinkedIn's [terms of use prohibits webscraping](https://www.linkedin.com/help/linkedin/answer/56347/prohibition-of-scraping-software?lang=en). On May 23, 2017, LinkedIn sent hiQ Labs a letter demanding that the company cease scraping activities and threatened legal action under the Computer Fraud and Abuse Act (CFAA). HiQ Labs sued LinkedIn, accusing the company of anticompetitive behavior and of violating the company's free speech right to access publicly available information. The US federal judge held LinkedIn cannot block third party web scrapers from scraping data from publicly available profiles.

LinkedIn appealed the decision and on September 9, 2019 the Ninth Circuit upheld the decision of the lower Court, granting an injunction against LinkedIn clocking hiQ from accessing and scraping publicly available websites, [HiQ Labs V. LinkedIn](http://cdn.ca9.uscourts.gov/datastore/opinions/2019/09/09/17-16783.pdf). 

### 2.2.3 Twitter  
Twitter is a social media application with over 300million active users. The platfor allows users to post short messages (of either 280 or 140 characters, dependent on the language) known as "tweets". As a data source, Twitter is used in research across a number of disciplines, such as sociology, computer science, media and communication, political science and engineering. Twitter makes it data available via a [number of Application Programming Interfaces (API)](https://help.twitter.com/en/rules-and-policies/twitter-api). The freely available ['Standard' API](https://developer.twitter.com/en/docs/tweets/search/overview) returns data from the past 7 days. Twitter's [terms of use expressly prohibit scraping](https://twitter.com/en/tos). 

In contrast to LinkedIn, where professional resumes may be considered collections of facts, the strings of text and images available in tweets may be characterised as copyright material, depnding on the circumstances. This legality of these forms of content is discussed below in formats.

### 2.2.4 Facebook  
Facebook is a social media platform with over 2 billion active users. Users connect with friends, post and interact with status updates and use instant messaging amongst other free features. Facebook's [terms of use expressly prohibit scraping](https://www.facebook.com/apps/site_scraping_tos_terms.php). 

In April 2010, Facebook launched an initial version of the Graph API, which allowed third-party developers to access and collect data about Facebook App Users. Graph API also allowed third-party developers to access and collect data about
Affected Friends. The complaint [_United States v Facebook_ filed in July 2019](https://www.ftc.gov/system/files/documents/cases/182_3109_facebook_complaint_filed_7-24-19.pdf) revealed, for years, when Facebook asked “who do you want to see your post?” and users chose to share information only with your "friends," Facebook provided that data not only to friends but also to any of the millions of third-party apps that those friends used. 

In 2018 whistleblower Chritsopher Wylie revealed the details of the harvesting of millions of facebook users profiles by Cambridge Analytica for use in targeted US political campaigning. The data was gathered by a third party application, a personality quiz app, that utilised the Graph API vulernability to access profile information of friends of the quiz users. This harvesting was outside the terms of use of third party developers and Facebook did not take active steps to deter or prevent such misuse. 

In 2019 Facebook was fined USD$50billion by the US Federal Trade Commission for repeated, continued failures to protect privacy of its users.

A typical permitted use of Facebook data is [??? is there one??? e.g. a business page that can use the data of its 'followers'?].


### 2.2.5 Google geo-coding
Google offers a geocoding service 

### 2.2.6 Geocoded National Address File (G-NAF)
G-NAF dataset contains all physical addresses in Australia, over 14 million. It’s the most trusted source of geocoded addresses for Australian businesses and governments. G-NAF has a varitey of uses including building suburb profiles, locating nearby services and the management of emergencies through identificaiton of evacuation routes.  A freely available and well-mainatined version is available on [data.gov.au](https://data.gov.au/dataset/ds-dga-19432f89-dc3a-4ef3-b943-5326ef1dbecc/details?q=G-NAF). G-NAF's terms of use are described as [Creative Commons Attribution 4.0 International license](https://creativecommons.org/licenses/by/4.0/), that allows the work to be shared and adapted with the requirement of attributing the source. There is [one restriction to these terms of use](https://data.gov.au/data/dataset/19432f89-dc3a-4ef3-b943-5326ef1dbecc/resource/9a8f6baa-f790-49a0-84b1-3cb39a6a1b88/download/fact-sheet-open-g-naf-use-restriction.pdf), the data base must not be used to compile lists of addresses for the sending of phyical mail or mailouts, unless a second source has been used to verify the address(es) are capable of receiving physical mail.

### 2.2.7 Best practice for terms of use in data science  
Best practice requires adherence to terms of service, acknowledgement of the distinction between private and public information, and use of quality open data. When the legality of webscraping was considered by US Courts in HiQ v Linkedin, LinkedIn was prohibited from enforcing its anti-webscraping terms of use. In contrast, Facebook was penalised by the regulator (the FTC) for _not_ enforcing its terms of service with respect to third parties accessing friend's profiles. The unifying thread between each of these factual scenarios, _at their very heart_, is the nature of the information concerned, specifcially, private or public data. In the LinkedIn case, users clearly marked profiles as 'public'. In the Facebook investigation, users who had selected 'private' settings were not protected. When looking online for data sources, seek well-maintained, labelled clearly as intended for use, for example with Creative Commons licenses as shown with the G-NAF example dataset.

## 2.3 Format: Text, Pictures, video and, copyright


## 2.4 Data processing
The General Data Proection Regulation is a set of European information privacy laws

#### References for this chapter
Gathering data from online social media platforms is described as "a primordial step in many data science fields" (Hernandez-Suarez _et al_ 2018).

A. Hernandez-Suarez, A., Sanchez-Perez, G., Toscano-Medina, K., Martinez-Hernandez, V., Sanchez, V. and Perez-Meana H., (2018) 'A web scraping methodology for bypassing Twitter API restrictions', arXiv:1803.09875 [cs.IR], <https://arxiv.org/pdf/1803.09875.pdf>
