# 2. AI Inputs

This section considers the legal responsibilities for AI modelling inputs. AI model inputs are typically in the form of data. That data may be about different subjects, be from various sources, exist in different forms and undergo further processing or transformations. Depending on the subject, source and format, different aspects of legal responsibility and liability arise. These are considered in the following sub-sections: subject, source and format. Emerging norms on data processing are also discussed.

<TOC>

## 2.1 Subject

### 2.1.1 About an individual

When working with data about an individual, an understanding of information privacy laws forms part of the responsibility of the work. In Australia, information privacy laws that regulate the private sector and Federal Government agencies are found in the _Privacy Act 1988_ (Cth) (the _Privacy Act_). The definition of "about" an individual is a threshold question considered by the Courts in the application of the _Privacy Act_.

In _Privacy Commissioner v Telstra Corporation Limited_ [2017] FCAFC 4, the Full Federal Court affirmed that just because a person's identity is reasonably ascertainable from a piece of information it does not mean it is personal information under the _Privacy Act_. The definition requires it must also be "about" an individual. In that case, journalist Ben Grubb asked Telstra for all the metadata that it held about him (around the same time the mandatory metadata retention laws were being debated). Telstra initially gave Mr Grubb some information, but refused to give him access to its mobile network data, which included metadata such as IP addresses and geolocation data. Mr Grubb then complained to the Privacy Commissioner. The Privacy Commissioner determined the mobile network data was "personal information" as Mr Grubb's identity could be reasonably ascertained from the information by using other information held by Telstra. Telstra appealed to the Administrative Appeals Tribunal, which formed the view that mobile network data was about connections between mobile devices and not "about" Mr Grubb. This was upheld by the Full Federal Court, which did not find it necessary to consider whether mobile network data was personal information because the threshold question had not been met.

At the same time, the mandatory data retention provisions in the _Telecommunications (Interception and Access) Act 1979_ (Cth) s 187LA deem information that must be retained by telecommunications companies as being personal information "about an individual" if the information relates to the individual or a communication to which the individual is a party.

### 2.1.2 Definition of personal information

Once the threshold consideration of "about" an individual is met, it becomes relevant to consider if the data you are working with is personal information and, therefore, whether the responsibilities defined in the _Privacy Act 1988_ (Cth) will apply.

Section 6 of the _Privacy Act 1988_ (Cth) defines "personal information" as:

> "Information or an opinion about an identified individual, or an individual who is reasonably identifiable: whether the information or opinion is true or not; and whether the information or opinion is recorded in a material form or not."

A key concept here is "reasonably identifiable." Information that appears on its face to be anonymous may still qualify as personal information if a person can be identified by combining it with other readily available data. This so-called "jigsaw identification" risk is particularly relevant in data science, where large datasets are routinely merged and enriched.

Examples of personal information include a person's name, date of birth, home address, email address, and device identifiers such as cookies or IP addresses. Examples of information that may not be personal information on its own, but may become so when combined with other data, include anonymised transaction records, de-identified geolocation traces, and device sensor data.

### 2.1.3 Principles for handling personal information

If the data could be characterised as personal information, Schedule 1 of the _Privacy Act 1988_ (Cth) defines the Australian Privacy Principles (APPs) to be observed by "APP entities" — a term covering Federal Government agencies, private sector organisations with an annual turnover of more than $3 million, all private health service providers, and certain other organisations.

| APP | Short Description | Key obligations |
|-----|---------------------------------------------------------------|-----------------|
| 1 | Open and transparent management | Maintain a clear, accessible privacy policy covering: the kinds of information collected; how it is held; how it can be accessed and corrected; the complaints process; and whether information is likely to be disclosed overseas. |
| 2 | Anonymity and pseudonymity | Give individuals the option to interact without identifying themselves, where practicable. |
| 3 | Collection of solicited information | May only collect personal information that is reasonably necessary for the entity's functions or activities (the "primary purpose"). Sensitive information requires consent. |
| 4 | Dealing with unsolicited information | On receiving information not actively sought, the entity must determine whether it could have collected it under APP 3; if not, the information must be destroyed or de-identified. |
| 5 | Notification of collection | Notify individuals of the fact of collection, the purposes for which information is collected, and how they can access or correct it. |
| 6 | Use or disclosure | Personal information collected for a primary purpose must not be used for another (secondary) purpose unless an exception applies — most relevantly, with the individual's consent, or where they would reasonably expect such use and it is related to the primary purpose. |
| 7 | Direct marketing | Personal information may only be used to market directly to individuals in specified circumstances; individuals must be given a clear opt-out mechanism, which must be honoured. |
| 8 | Cross-border disclosure | Before disclosing personal information to an overseas recipient, the entity must take reasonable steps to ensure the recipient will handle it in accordance with the APPs. |
| 9 | Government-related identifiers | Limits on adoption, use or disclosure of government identifiers such as Medicare numbers, Tax File Numbers, and Australian passport numbers. |
| 10 | Quality | Reasonable steps must be taken to ensure personal information is accurate, up to date and complete. |
| 11 | Security | Reasonable steps must be taken to protect personal information from misuse, interference, loss, and unauthorised access, modification or disclosure. When the information is no longer needed, it must be destroyed or de-identified. |
| 12 | Access | Individuals must be given access to their personal information on request, subject to limited exceptions. |
| 13 | Correction | Individuals must be able to request correction of their personal information. |

### 2.1.4 Issues arising in AI and ML

#### Secondary uses of personal information

The _Privacy Act_ makes a distinction between primary and secondary uses of data, and this has significant implications for AI inputs. The primary purpose for which an organisation gathers data is likely to be operational — for example, to provide a service to a customer. Each use of that service may be logged as a transaction record. The re-use of that database (or an extract of it) for training a machine learning model is likely to be a secondary use of personal information.

A secondary use is not permitted unless it falls within an exception in APP 6. The exceptions most relevant to machine learning include: use with the individual's consent; or use where the individual would reasonably expect the secondary purpose and it is related to the primary purpose. For large datasets, obtaining individual consent is often impractical. Accordingly, organisations must carefully assess whether their data subjects would reasonably expect their information to be used in AI model training before proceeding.

#### Creation of personal information

Preparing data inputs for AI can involve the combination of multiple datasets, which poses the risk of creating new personal information through what is sometimes called the "jigsaw effect." Where datasets are individually innocuous, their combination may render individuals reasonably identifiable. This risk must be assessed before joining data sources, and any unexpected creation of personal information must be managed in accordance with the APPs — including notification obligations under APP 5 and the security and destruction obligations under APP 11.

#### ACCC v Google LLC (No 2) [2021] FCA 367

In April 2021, the Federal Court found that Google LLC and Google Australia Pty Ltd had breached the _Australian Consumer Law_ (sch 2 of the _Competition and Consumer Act 2010_ (Cth)) by making misleading representations to Android users about the collection and use of their personal location data. Google told users that "Location History" was the only setting controlling whether Google collected and used personally identifiable location data. In fact, a separate "Web & App Activity" setting — which was turned on by default — also enabled Google to collect and use location data. The Court found Google had breached ss 18, 29(1)(g) and 34 of the ACL. In August 2022, the Federal Court ordered Google to pay penalties of AUD $60 million. This enforcement action, the first public outcome of the ACCC's Digital Platforms Inquiry, illustrates that APP 1 — the requirement to maintain a privacy policy that accurately explains how data is collected, used and held — is actively enforced by regulators, and that data practices must match privacy disclosures.

#### Automated decision-making: transparency obligations from 2026

The _Privacy and Other Legislation Amendment Act 2024_ (Cth), which received Royal Assent on 10 December 2024, introduced transparency requirements for automated decision-making that will commence on 10 December 2026. Entities covered by the _Privacy Act_ will be required to include information in their APP 1 privacy policy about the use of computer programs to make, or substantially assist in making, decisions that could reasonably be expected to significantly affect an individual's rights or interests. This disclosure obligation requires entities to describe the kinds of decisions that are substantially automated and the kinds of personal information used in those decisions. The definition is broad and encompasses both fully automated decisions and decisions where a computer program plays a substantial role alongside human judgement. For data scientists building decision-support or decisioning systems, this means the privacy policy — not just internal documentation — must describe what personal information is used and what types of decisions the system produces.

### 2.1.5 Protected classes of information

Australia's federal anti-discrimination legislation designates certain personal attributes as "protected." It is unlawful to discriminate on the basis of a protected attribute in prescribed areas of public life including employment, education, the provision of goods and services, and accommodation. The principal Commonwealth anti-discrimination Acts are:

- _Age Discrimination Act 2004_ (Cth)
- _Disability Discrimination Act 1992_ (Cth)
- _Racial Discrimination Act 1975_ (Cth)
- _Sex Discrimination Act 1984_ (Cth)

The protected attributes recognised across these Acts include: age; disability; race, colour, national or ethnic origin and descent; sex; marital or relationship status; pregnancy and potential pregnancy; breastfeeding; gender identity; intersex status; and sexual orientation.

In addition, the _Privacy Act 1988_ (Cth) s 6 designates a sub-category of personal information as "sensitive information," to which higher protections apply. Sensitive information includes information or an opinion about a person's racial or ethnic origin, political opinions, membership of a political association, religious beliefs or affiliations, philosophical beliefs, membership of a professional or trade association, membership of a trade union, sexual orientation or practices, criminal record, health information, genetic information, and biometric information used for certain purposes.

The relevance of protected classes and sensitive information to AI inputs is twofold. First, when training data includes sensitive information, the higher collection and consent obligations in APP 3 and APP 6 apply. Second, even where protected attributes are excluded from a model's input features, they may be present in correlated variables — a phenomenon that can lead to indirect discrimination in model outputs. This indirect discrimination risk is discussed further in Chapter 3.

### 2.1.6 Best practice for handling personal information in data science

There is an excellent [Guide to data analytics and the Australian Privacy Principles](https://www.oaic.gov.au/privacy/guidance-and-advice/guide-to-data-analytics-and-the-australian-privacy-principles/) published by the Office of the Australian Information Commissioner (OAIC), which offers advice to minimise the use of personal information and the risks of working with it including:

- Use de-identified data where possible (the OAIC also provides a guide on de-identification [here](https://www.oaic.gov.au/privacy/guidance-and-advice/de-identification-and-the-privacy-act/));
- Ensure the accuracy of the data you are working with (this may involve taking extra steps to check the quality of data provided by third parties);
- Be open and transparent about privacy practices;
- Organisations undertaking data analytics activities should include general information about those activities in their APP privacy policy;
- Avoid collecting "all the data" for "unknown purposes" — this will expose organisations to privacy compliance risks.

Other methods to minimise the use of personal information include the use of age ranges in place of specific ages, and geographic aggregates in place of precise addresses. The benefit of working with voluminous transactional and behavioural data is that patterns in the data itself can be more insightful than crude personal attributes such as age and gender, and modelling on aggregate patterns may achieve equivalent or superior accuracy without reliance on protected or sensitive information.

## 2.2 Sources

Digital formats revolutionised many industries where the act of copying, once laborious and time consuming in printed formats, became instantaneous, cheap and even incidental. Data in digital form is ubiquitous and is capable of being used for various purposes by various parties. This section contemplates the different mechanisms by which access to, and use of, potential data sources are governed. For content found on online platforms and websites, both contractual restrictions (terms of use) and intellectual property law impose limits on use.

### 2.2.1 Understanding terms of use

Gathering data from online platforms is a common first step in data science projects. When working with such data, an understanding of the applicable terms of service forms part of the responsibility of the work. Breach of platform terms of service may constitute a breach of contract, expose an organisation to civil liability, and in some circumstances may engage other legal frameworks. Where terms of service prohibit automated access, scraping may also engage the tort of trespass to chattels or relevant computer-access offences under the _Criminal Code Act 1995_ (Cth) and state equivalents, depending on how it is carried out.

#### LinkedIn

LinkedIn is a professional networking site with over 800 million members. The platform allows members to post résumés, job listings and professional content, and to build professional networks. LinkedIn's [terms of use prohibit automated scraping](https://www.linkedin.com/help/linkedin/answer/56347). The legality of scraping publicly available LinkedIn profiles was considered by US courts in _hiQ Labs, Inc v LinkedIn Corporation_ 938 F 3d 985 (9th Cir, 2019), in which the Ninth Circuit Court of Appeals upheld an injunction preventing LinkedIn from blocking hiQ Labs' scraping of publicly available profile data, on the basis that scraping publicly available websites did not constitute unauthorised access under the Computer Fraud and Abuse Act. It should be noted that this is a decision of a United States court applying United States law, and does not determine the legality of scraping LinkedIn profiles under Australian law. The commercial and research applications of LinkedIn member data include analysis of workforce supply and demand across industries, job types and educational qualifications.

#### X (formerly Twitter)

X (formerly Twitter) is a social media platform with hundreds of millions of active users. The platform allows users to post short messages. As a data source, X is used across disciplines including sociology, computer science, media and political science. X makes data available via a number of Application Programming Interfaces (APIs), and its [terms of service expressly prohibit scraping](https://twitter.com/en/tos). In contrast to LinkedIn, where professional résumés may be characterised as collections of facts, the strings of text and images available in posts may be characterised as copyright material depending on the circumstances. This content-level analysis is discussed below at section 2.3.2.

#### Facebook

Facebook is a social media platform operated by Meta Platforms, with over three billion active users. Facebook's [terms of service expressly prohibit scraping](https://www.facebook.com/apps/site_scraping_tos_terms.php). In 2018, whistleblower Christopher Wylie revealed the harvesting of millions of Facebook user profiles by Cambridge Analytica for use in targeted US political campaigning. The data was gathered through a third-party personality quiz application that exploited the Graph API to access profile information of the friends of quiz users — outside the developer terms of service — without Facebook taking active steps to prevent this misuse. In 2019, the US Federal Trade Commission fined Facebook USD $5 billion for repeated failures to protect user privacy.

#### Best practice for terms of use

Best practice requires adherence to terms of service, clear acknowledgement of the distinction between private and public information, and preference for well-maintained open data sources. When evaluating online data sources, practitioners should prioritise datasets that are clearly labelled as available for use — for example, those carrying Creative Commons licences. The unifying thread in the enforcement cases discussed above — LinkedIn, Facebook and Google — is the nature of the underlying information: whether data subjects had a reasonable expectation of privacy in the data, and whether the collector accurately disclosed how it would be used.

### 2.2.2 Datasets and license types

Datasets available online frequently carry licensing conditions. There are six broad categories of open data licences relevant to data science practice.

#### Public Domain

For data scientists, a public domain designation signals that the dataset can be used freely for both commercial and non-commercial purposes without restriction. The owner has waived all rights to the work worldwide. Examples include:
- *Public Domain Mark* — the work is in the public domain;
- *CC-0* — Creative Commons Public Domain Dedication; and
- *PDDL* — Open Data Commons Public Domain Dedication and Licence.

#### Attribution

Use of the dataset requires giving appropriate credit to the dataset owner, providing a link to the licence, and indicating if changes were made. Attribution may be made in any reasonable manner, but the licence does not permit suggestions that the licensor endorses the derivative use. Examples include:
- *CC-BY* — Creative Commons Attribution;
- *CDLA-Permissive-1.0* — Community Data Licence Agreement, Permissive Version 1.0; and
- *ODC-BY* — Open Data Commons Attribution Licence.

#### Share-Alike

Any use of the dataset must be attributed to the original, and derivative works must be distributed under the same licence. Examples include:
- *CC-BY-SA* — Creative Commons Attribution-ShareAlike;
- *CDLA-Sharing-1.0* — Community Data Licence Agreement, Sharing Version 1.0; and
- *ODC-ODbL* — Open Data Commons Open Database Licence.

Note that *CDLA-Sharing-1.0* does not impose obligations or restrictions on results obtained from computational use of the data. In contrast, *ODC-ODbL* requires the distribution of any additions, transformations or changes to the dataset.

#### Non-Commercial

The work may be used for non-commercial purposes only. Examples include:
- *CC-BY-NC* — Creative Commons Attribution-NonCommercial; and
- *CC-BY-NC-SA* — Creative Commons Attribution-NonCommercial-ShareAlike.

#### Database Only

The licence applies to the database structure only, not its contents. This means the underlying data may be usable, while the particular selection and arrangement of data remains protected.

#### No Derivatives

The work may not be altered, transformed or built upon. Examples include:
- *CC-BY-ND* — Creative Commons Attribution-NoDerivatives; and
- *CC-BY-NC-ND* — Creative Commons Attribution-NonCommercial-NoDerivatives.

#### Open Data

Open data is a resource whose terms of service expressly enable use by others. The open data movement is a practical realisation of freedom of information principles, through which governments make administrative data publicly available. The Geocoded National Address File (G-NAF) is an example of a freely available, well-maintained government geocoding dataset containing all physical addresses in Australia (over 14 million). It is available on [data.gov.au](https://data.gov.au/dataset/ds-dga-19432f89-dc3a-4ef3-b943-5326ef1dbecc/details) under a [Creative Commons Attribution 4.0 International licence](https://creativecommons.org/licenses/by/4.0/), with one restriction: G-NAF must not be used to compile mailing lists for physical mail unless a second source verifies the address can receive physical mail.

### 2.2.3 Copyright in AI training data

A question of growing legal and commercial significance in Australia is whether using copyright-protected material to train AI models constitutes copyright infringement under the _Copyright Act 1968_ (Cth).

Under the _Copyright Act 1968_ (Cth), copyright subsists automatically in original literary, dramatic, musical and artistic works. Copyright is infringed where a person reproduces a substantial part of a work without the licence of the copyright owner. Training a large language model or image generation model typically involves copying vast quantities of text, images or other content into the model's training pipeline. To the extent this involves reproduction of a substantial part of a copyrighted work, it may constitute infringement.

Australia does not currently have a text and data mining (TDM) exception equivalent to those found in the European Union's Directive on Copyright in the Digital Single Market or the United Kingdom's Computer Programs Directive. In October 2025, the Australian Government announced it would not introduce a TDM exception, citing the need to protect Australian creators and ensure they are fairly remunerated for providing content for AI training. The Government indicated it would pursue a regime requiring AI developers to operate under "fair terms of use" for Australian copyright material. This remains an area of active law reform as at the date of this edition.

In the absence of a TDM exception, AI developers and data scientists in Australia must assess whether a licence or other authority exists before using copyright-protected material in training datasets. This includes reviewing the terms of service of any platform from which data is sourced, the licensing conditions of any dataset, and whether any other exception under the _Copyright Act 1968_ (Cth) — such as research or study, or fair dealing for criticism or review — might apply. None of these existing exceptions was designed with AI training in mind, and their application to this context is uncertain.

For data scientists, the practical implications are:
1. Prioritise openly licensed or public domain training datasets;
2. Review terms of service before scraping platform content for training purposes;
3. Seek legal advice before using substantial quantities of commercially published material in model training; and
4. Monitor law reform developments closely, as the legal position may change.

## 2.3 Format

Data formats have the potential to attract different legal considerations. For structured data, it is the selection and arrangement of data, including the data model itself, that can give rise to IP claims. For unstructured data, the legal considerations typically concern the contents of the data and whether they attract copyright or other protections.

### 2.3.1 Structured data

Structured data is data organised in a predefined format — typically rows and columns — such as relational databases, spreadsheets and CSV files. In law, two questions commonly arise regarding structured data: who owns it, and what obligations attach to the way it is used.

On the question of ownership, the _Copyright Act 1968_ (Cth) does not recognise a separate "database right" of the kind that exists in the European Union. In Australia, a database may attract copyright protection if it qualifies as a compilation — a work that exhibits authorial creativity in the selection or arrangement of its contents. A purely mechanical collation of data, with no creative selection, is unlikely to attract copyright. This means that raw transactional data exported from a production database may not be protected as a copyright work in its own right, though the underlying software and schema may be.

On the question of obligations, when structured data includes personal information, all of the APPs discussed in section 2.1 apply. The format of data does not alter these obligations.

From a data science perspective, structured data often requires considerable preparation — normalisation, imputation of missing values, encoding of categorical variables — before it is suitable for use in model training. These transformations do not affect ownership of the underlying data, but may create new works (such as data processing scripts) that attract their own copyright.

### 2.3.2 Unstructured data

Unstructured data is data that does not conform to a predefined data model, such as free text, images, audio recordings and video. Unstructured data constitutes the majority of data generated by human activity and is increasingly the input of choice for modern AI systems including large language models and image recognition systems.

Unstructured data is more likely to attract copyright than structured data because it is more likely to exhibit the originality required for copyright protection. A newspaper article, a social media post of sufficient length and creativity, a photograph, a piece of music and a recorded conversation may all be protected by copyright. Where an AI system is trained on such content without the licence of the copyright owner, infringement may occur (see section 2.2.3).

Unstructured data that relates to individuals may also be personal information under the _Privacy Act 1988_ (Cth). A voice recording, photograph or piece of text that identifies or is reasonably capable of identifying a person will be personal information, regardless of the format in which it is stored.

From a data science perspective, the key obligations when working with unstructured data are: to identify whether the content is protected by copyright and whether a licence or exception applies; to assess whether the content includes personal information and comply with the APPs accordingly; and to assess whether the content constitutes sensitive information, in which case the higher protections under the _Privacy Act_ apply.

## 2.4 Data processing

### 2.4.1 The GDPR and its relevance to Australian organisations

The General Data Protection Regulation (GDPR) is a European Union data protection regulation that has been in force since May 2018. The GDPR imposes detailed obligations on the collection, use, storage and transfer of personal data relating to individuals in the EU. Unlike the Australian APPs, which are principles-based, the GDPR is highly prescriptive: it requires a specific lawful basis for every processing activity, imposes strict data subject rights including rights of access, erasure and portability, and mandates the appointment of a Data Protection Officer in certain circumstances.

The GDPR applies to any organisation — regardless of where it is based — that processes personal data of EU residents in connection with offering goods or services to them or monitoring their behaviour. Australian organisations that have European customers, users or employees must therefore comply with the GDPR in addition to the Australian _Privacy Act_. Where the GDPR imposes a higher standard than the APPs, the GDPR standard will apply to that data.

For data scientists working on AI systems with European data subjects in scope, this means ensuring that a valid lawful basis exists for each processing activity — typically consent, legitimate interest, or contractual necessity — and that data minimisation, purpose limitation and accuracy principles are observed. The GDPR's prohibition on solely automated decision-making with significant effects (Article 22) is also directly relevant to AI systems that make decisions about individuals without human review.

### 2.4.2 The Consumer Data Right

The Consumer Data Right (CDR) is an Australian framework established by the _Competition and Consumer Act 2010_ (Cth) (as amended by the _Consumer Data Right Act 2019_ (Cth)) that gives consumers the right to require data about them to be shared with third parties of their choice. The CDR is currently operational in the banking and energy sectors, with further sectors planned. In the banking sector (Open Banking), the CDR allows consumers to direct their bank to share their financial transaction data with accredited third parties — such as budgeting apps, comparison services and AI-driven financial tools — in a standardised format.

For data scientists, the CDR represents both a legal obligation and an opportunity. As an obligation, organisations receiving CDR data must comply with detailed rules about how it may be used and held, including purpose limitations that may restrict its use in AI model training. As an opportunity, the CDR creates a new class of richly structured, consented financial and energy data that can be used — within those rules — to power AI applications.

The CDR Privacy Safeguards, contained in the _Competition and Consumer Act 2010_ (Cth), operate in addition to — and in some respects more restrictively than — the APPs. Data scientists working with CDR data should be aware that its use for purposes beyond those consented to by the consumer is not permitted.

---

## References

*Age Discrimination Act 2004* (Cth)

*Competition and Consumer Act 2010* (Cth) sch 2 (*Australian Consumer Law*)

*Consumer Data Right Act 2019* (Cth)

*Copyright Act 1968* (Cth)

*Criminal Code Act 1995* (Cth)

*Disability Discrimination Act 1992* (Cth)

*Privacy Act 1988* (Cth)

*Privacy and Other Legislation Amendment Act 2024* (Cth)

*Racial Discrimination Act 1975* (Cth)

*Sex Discrimination Act 1984* (Cth)

*Telecommunications (Interception and Access) Act 1979* (Cth)

*Australian Competition and Consumer Commission v Google LLC (No 2)* [2021] FCA 367

*Privacy Commissioner v Telstra Corporation Limited* [2017] FCAFC 4

*hiQ Labs, Inc v LinkedIn Corporation* 938 F 3d 985 (9th Cir, 2019) [United States]

Australia, Attorney-General's Department, *Privacy Act Review Report* (Report, February 2023) <https://www.ag.gov.au/rights-and-protections/publications/privacy-act-review-report> accessed 1 July 2026

Australian Competition and Consumer Commission, 'Google LLC to Pay $60 Million for Misleading Representations' (Media Release, 12 August 2022) <https://www.accc.gov.au/media-release/google-llc-to-pay-60-million-for-misleading-representations> accessed 1 July 2026

Office of the Australian Information Commissioner, *Guide to Data Analytics and the Australian Privacy Principles* (Web Page, 2018) <https://www.oaic.gov.au/privacy/guidance-and-advice/guide-to-data-analytics-and-the-australian-privacy-principles/> accessed 1 July 2026

Office of the Australian Information Commissioner, *De-identification and the Privacy Act* (Web Page, 2020) <https://www.oaic.gov.au/privacy/guidance-and-advice/de-identification-and-the-privacy-act/> accessed 1 July 2026

Hernandez-Suarez A et al, 'A Web Scraping Methodology for Bypassing Twitter API Restrictions' (2018) arXiv:1803.09875 [cs.IR] <https://arxiv.org/pdf/1803.09875.pdf> accessed 1 July 2026
