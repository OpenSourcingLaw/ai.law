# 2. AI Inputs

This chapter considers the legal responsibilities that attach to the inputs of AI systems. AI inputs are typically data — about different subjects, from various sources, in different formats. Depending on the subject, source and format, different legal frameworks apply. The chapter covers information privacy law as it applies to data subjects, the rules governing data sources (platform terms and dataset licences), the legal treatment of different data formats, and the framework for data processing. It concludes with the current position on copyright in AI training data — one of the most contested areas of Australian law in 2025–26.

<TOC>

## 2.1 Subject

### 2.1.1 The threshold question: "about" an individual

When working with data that concerns individuals, information privacy law is the first legal framework to engage. In Australia, the primary instrument is the _Privacy Act 1988_ (Cth) (the Act), administered by the Office of the Australian Information Commissioner (OAIC). The Act applies to Federal Government agencies and to "APP entities" in the private sector — organisations with an annual turnover of more than $3 million, all private health service providers, and certain other organisations regardless of size.

Before the Act applies, a threshold question must be answered: is the data "about" an individual? In _Privacy Commissioner v Telstra Corporation Limited_ [2017] FCAFC 4, the Full Federal Court affirmed that the mere fact that a person's identity is reasonably ascertainable from a piece of information does not make that information personal information. The information must also be "about" that individual. In that case, journalist Ben Grubb sought access to his mobile network metadata from Telstra. The Full Court held that mobile network data was about connections between devices, not about Mr Grubb, so it did not constitute personal information, regardless of whether his identity could be ascertained from it.

This case is directly relevant to AI practitioners: metadata, connection logs, and device-level data commonly used as AI inputs may not constitute personal information if they are about technical events rather than individuals. However, the analysis is context-sensitive, and the same data may be characterised differently depending on how it is processed and combined.

### 2.1.2 Definition of personal information

Once the "about" threshold is satisfied, the Act's definition of "personal information" applies. Under s 6(1) of the _Privacy Act 1988_ (Cth), personal information means:

> Information or an opinion about an identified individual, or an individual who is reasonably identifiable: whether the information or opinion is true or not; and whether the information or opinion is recorded in a material form or not.

Several features of this definition are critical for AI practitioners. First, it covers information that is false — meaning that AI-generated "hallucinations" (factually incorrect outputs about a real person) can constitute personal information about that person if the person is identified or reasonably identifiable from the output. Second, it is not limited to recorded information — information can be personal even before it is written down. Third, the breadth of "reasonably identifiable" creates a jigsaw risk: information that is individually anonymous may become personal information when combined with other data.

### 2.1.3 Sensitive information

Section 6(1) of the Act defines a sub-category, "sensitive information," which attracts higher-level protections. Sensitive information includes information or an opinion about an individual's:

- racial or ethnic origin
- political opinions or association
- religious beliefs or affiliations
- philosophical beliefs
- membership of a professional or trade association or trade union
- sexual orientation or practices
- criminal record
- health information
- genetic information
- biometric information or biometric templates

Where a dataset contains or could be used to infer sensitive information, the stricter requirements apply: sensitive information may generally only be collected with the individual's consent (APP 3), and any use or disclosure for secondary purposes requires consent or a specific exception (APP 6). AI systems that use behavioural data to infer health conditions, sexual orientation, or political beliefs from training data are processing sensitive information even if they do not collect it directly.

### 2.1.4 The Australian Privacy Principles

The thirteen Australian Privacy Principles (APPs), set out in Schedule 1 of the Act, govern the full lifecycle of personal information. The following table identifies the APPs most directly relevant to AI inputs.

| APP | Short description | AI-relevant obligations |
|-----|-------------------|-----------------------|
| 1 | Open and transparent management | Maintain an up-to-date privacy policy. From 10 December 2026, disclose substantially automated decision-making systems under new APP 1.7 and 1.8. |
| 3 | Collection of solicited information | Collect only personal information that is reasonably necessary for the entity's functions or activities. Sensitive information requires consent. Bulk collection for AI training "just in case" fails this test. |
| 4 | Unsolicited information | Destroy or de-identify personal information that arrives unsolicited and that could not have been collected under APP 3. |
| 5 | Notification | Notify individuals at or before the time of collection of the fact of collection, its purposes, and their rights. |
| 6 | Use or disclosure | Do not use personal information for a purpose other than the primary collection purpose unless an exception applies (most importantly: consent, or reasonable expectation tied to a related purpose). Training a model on customer service data is ordinarily a secondary use. |
| 8 | Cross-border disclosure | Take reasonable steps before sending personal information to overseas AI infrastructure to ensure the recipient complies with the APPs. The entity remains liable if the overseas AI vendor mishandles the data. |
| 10 | Quality | Take reasonable steps to ensure personal information is accurate, up to date and complete. AI systems trained on or generating inaccurate data engage this obligation. |
| 11 | Security | Take reasonable steps to protect personal information from misuse, interference, loss, and unauthorised access. AI-specific risks include model inversion attacks (extracting training data from a model's weights), membership inference attacks (determining whether a person's data was in the training set), and prompt injection attacks. |
| 12 | Access | Provide individuals access to their personal information on request. |
| 13 | Correction | Facilitate requests to correct personal information. |

### 2.1.5 Issues arising in AI — secondary uses and creation of new personal information

**Secondary uses.** The distinction between primary and secondary uses of personal information is fundamental to AI input compliance. When an organisation collects data for one purpose — say, conducting a commercial transaction — and then uses that data to train a machine learning model, the training use is almost certainly a secondary use. APP 6 permits secondary use only with consent, or where the individual would reasonably expect the use and it is related to the primary purpose. A customer who provides contact details to make a purchase would not ordinarily expect those details to be used to train a language model. For large datasets, individual consent to AI training is often impractical, which means organisations must rely on the reasonable expectation exception with care — and in many cases cannot.

The OAIC's October 2024 guidance on privacy and developing and training generative AI models confirms that using personal information to train or fine-tune AI models is frequently a secondary use that requires either fresh consent or a specific exception.

**Creation of new personal information.** Combining multiple datasets creates a jigsaw risk: each source may be innocuous individually, but together they may render individuals reasonably identifiable. This is the "mosaic effect." Data scientists joining datasets for AI training must assess whether their combined dataset creates new personal information that did not exist in either source alone, and comply with the APPs accordingly.

### 2.1.6 OAIC guidance on AI — October 2024

In October 2024, the OAIC released two sets of guidance specifically addressing AI, making privacy obligations in this space considerably more concrete.

**Guidance on privacy and the use of commercially available AI products** applies to organisations using AI tools such as large language model chatbots, productivity assistants, transcription tools, and coding assistants. Key obligations:

- Entering personal information into a commercial AI tool constitutes a "use" of that information under APP 6 and may require consent or a specific secondary-use exception;
- Before deploying any commercial AI tool that processes personal information, organisations should conduct a **Privacy Impact Assessment (PIA)**;
- Vendor contracts must be structured so that the AI provider handles personal information consistently with the APPs — the client organisation remains accountable under APP 8 if the overseas vendor mishandles the data; and
- Be alert to the risk that personal information entered into a commercial AI tool may be used by the provider to train or improve its own models.

**Guidance on privacy and developing and training generative AI models** applies to entities that develop, train, or fine-tune generative AI models using personal information. Key points:

- Developing a generative AI model on personal information is characterised as a **high privacy risk activity** that requires Privacy by Design from the outset;
- Web-scraped training data almost certainly contains personal information — collection for training purposes is regulated by APP 3 and must be reasonably necessary for the entity's functions;
- Generating information about an individual — including AI hallucinations about a real person — can itself constitute personal information; and
- The OAIC expects entities to consider and document their privacy obligations throughout the model development lifecycle.

The OAIC's regulatory action priorities for 2025–26 expressly identify AI and automated decision-making — particularly government use of AI — as a priority enforcement area.

### 2.1.7 Automated decision-making transparency from 2026

The _Privacy and Other Legislation Amendment Act 2024_ (Cth), which received Royal Assent on 10 December 2024, introduces new transparency requirements for automated decision-making commencing on 10 December 2026.

Two new sub-provisions of APP 1 take effect on that date. **APP 1.7** requires an APP entity to comply with transparency obligations where it uses a computer program to make or directly support a decision using personal information, if that decision could reasonably be expected to significantly affect the rights or interests of an individual. **APP 1.8** requires the entity's privacy policy to state: the kinds of personal information used in such systems; the kinds of decisions made solely by automated systems; and the kinds of decisions in which automated systems perform a function substantially and directly related to making a decision.

These are transparency-only obligations. Unlike the EU General Data Protection Regulation's Article 22, which gives individuals a right to contest automated decisions and require human review, Australia's provisions require disclosure but do not confer substantive individual rights to challenge an automated decision. This is widely regarded as a significant gap in the Australian framework.

For data scientists, the practical implication is that model documentation — descriptions of what personal information is used and what decisions the model produces — must be prepared in sufficient detail to support public disclosure in the privacy policy, with sufficient lead time before December 2026.

### 2.1.8 Protected attributes and anti-discrimination

Australia's federal anti-discrimination legislation designates certain attributes as "protected," and prohibits discrimination on these grounds in employment, education, the provision of goods and services, and accommodation. The principal Acts are the _Age Discrimination Act 2004_ (Cth), _Disability Discrimination Act 1992_ (Cth), _Racial Discrimination Act 1975_ (Cth), and _Sex Discrimination Act 1984_ (Cth).

Protected attributes include: age; disability; race, colour, national or ethnic origin and descent; sex; marital or relationship status; pregnancy; gender identity; intersex status; and sexual orientation. These overlap significantly with the category of "sensitive information" under the _Privacy Act 1988_ (Cth).

The relevance of protected attributes to AI inputs is twofold. First, where training data includes information about protected attributes, the APPs' heightened requirements for sensitive information may apply. Second — and more subtly — protected attributes may be encoded in training data not explicitly but through correlated proxy variables (postcode correlated with race; employment gaps correlated with pregnancy). A model trained on such data may amplify these correlations, resulting in indirect discrimination in its outputs. This risk is addressed in Chapter 3.

### 2.1.9 Best practice for handling personal information in data science

The OAIC's [Guide to data analytics and the Australian Privacy Principles](https://www.oaic.gov.au/privacy/guidance-and-advice/guide-to-data-analytics-and-the-australian-privacy-principles/) recommends:

- **De-identify data** wherever possible before use in analytics or model training (see also the OAIC guide on de-identification);
- **Minimise collection** — avoid the "collect all the data" approach; collect only what is reasonably necessary;
- **Conduct a Privacy Impact Assessment** before undertaking high-risk data analytics or AI development activities;
- **Be transparent** — document and disclose data practices in a current and accessible privacy policy;
- **Use well-maintained open datasets** where possible — G-NAF (Geocoded National Address File), available at [data.gov.au](https://data.gov.au), is an example of a freely available, accurately maintained government dataset available under a Creative Commons Attribution 4.0 licence.

Beyond compliance, Privacy by Design — building privacy safeguards into system architecture from the start — is both regulatory best practice and sound engineering. Retrofitting privacy controls into a deployed AI system is far more costly and less effective than designing them in from the outset.

## 2.2 Sources

Digital formats transformed data economics: copying, once laborious, became instantaneous, cheap, and incidental. This ubiquity means that potential training data is everywhere — but legal constraints on its collection and use are not uniform. This section examines the legal frameworks that govern the most common data sources.

### 2.2.1 Understanding terms of use

Gathering data from online platforms is a standard first step in data science practice. The legal framework governing this collection has two layers: contractual (platform terms of service) and intellectual property (copyright). Both must be considered.

Breach of a platform's terms of service may constitute breach of contract, expose an organisation to injunctive relief, and in some circumstances may engage computer-access offences under the _Criminal Code Act 1995_ (Cth). Where a platform expressly prohibits automated access or scraping, collecting data in defiance of that prohibition carries legal risk.

#### LinkedIn

LinkedIn is a professional networking platform whose [terms of service prohibit automated scraping](https://www.linkedin.com/help/linkedin/answer/56347). In _hiQ Labs, Inc v LinkedIn Corporation_ 938 F 3d 985 (9th Cir, 2019), a United States Court of Appeals held that scraping publicly available LinkedIn profiles was not unlawful under US federal law. This US decision does not determine the position under Australian law. However, it illustrates the distinction that courts draw between public and private data: the stronger the user's privacy expectation in the data, the stronger the platform's case for enforcing its terms.

#### X (formerly Twitter)

X (formerly Twitter) makes data available via multiple Application Programming Interfaces (APIs) but prohibits scraping under its [terms of service](https://twitter.com/en/tos). Posts of sufficient creative content may attract copyright protection as literary works, which adds an intellectual property dimension to terms-of-service compliance in scraping X data. This copyright analysis is addressed in section 2.3.2.

#### Facebook / Meta

Meta's platform terms expressly prohibit scraping. The Cambridge Analytica affair — in which a personality quiz application exploited the Facebook Graph API to harvest the profile data of users' friends without authorisation — illustrates both the legal and reputational consequences of data collection that exceeds the bounds of platform authorisation. The US Federal Trade Commission fined Facebook USD $5 billion in 2019 for privacy violations connected to this episode.

#### Best practice on terms of use

The unifying principle across these platforms is the public/private distinction: scraping data that users clearly marked as public (and where the platform cannot demonstrate a privacy interest being protected) is more likely to be tolerated than scraping data where users had a reasonable privacy expectation. Practitioners should: read terms of service before using automated collection; prefer openly licensed data sources; treat platform-provided APIs as the intended and permitted access method; and obtain legal advice before deploying large-scale scraping on any platform with anti-scraping terms.

### 2.2.2 Datasets and licence types

Datasets available online carry licensing conditions that determine the scope of permissible use. The following categories are most common in data science practice.

**Public Domain** — the owner has waived all rights. Examples: CC-0 (Creative Commons Public Domain Dedication), PDDL (Open Data Commons Public Domain Dedication). No attribution required; freely usable for commercial and non-commercial purposes.

**Attribution** — requires attribution to the dataset owner. Examples: CC-BY, ODC-BY. The licence does not permit suggesting that the licensor endorses any derivative work.

**Share-Alike** — requires derivative works to be released under the same licence. Examples: CC-BY-SA, ODC-ODbL. Note that CDLA-Sharing-1.0 does not impose obligations on results of computational use; ODC-ODbL does require distribution of database additions and modifications.

**Non-Commercial** — prohibits commercial use. Examples: CC-BY-NC, CC-BY-NC-SA. Organisations building commercial AI products cannot use non-commercial-licensed datasets in training without risking infringement.

**Database Only** — the licence applies to the selection and arrangement of the database, not the individual data entries.

**No Derivatives** — the work may not be modified or built upon. Examples: CC-BY-ND, CC-BY-NC-ND.

**Open Government Data** — Australian governments publish data at [data.gov.au](https://data.gov.au). The Geocoded National Address File (G-NAF), containing over 14 million Australian physical addresses, is an example of a freely available, well-maintained government dataset available under a Creative Commons Attribution 4.0 International licence, with one restriction: it must not be used to compile mailing lists for physical mail unless a second source verifies the address can receive physical mail.

### 2.2.3 Copyright in AI training data

The question of whether using copyright-protected material to train AI models constitutes infringement under the _Copyright Act 1968_ (Cth) is the most actively contested legal question in the Australian AI landscape as at July 2026.

**The reproduction question.** Under s 31(1) of the _Copyright Act 1968_ (Cth), reproducing a substantial part of a copyright work without the owner's licence constitutes infringement. Training a large language model or image generation model involves copying large quantities of text, images, or other content into the training pipeline. To the extent this process reproduces a substantial part of a copyright work, it is an act of infringement unless an exception applies.

**No text and data mining exception.** Australia does not have a text and data mining (TDM) exception comparable to those in the European Union (Directive on Copyright in the Digital Single Market 2019) or Japan. In September 2024, the Australian Productivity Commission's interim report on harnessing data and digital technology proposed introducing a fair dealing exception for TDM. On 26 October 2025, Attorney-General Michelle Rowland announced that the Government would **not** introduce a TDM exception. The Government's stated reason was to protect Australian creators from having their work used without consent or compensation. Instead, the Government is pursuing licensing-based approaches through the Copyright and Artificial Intelligence Reference Group (CAIRG).

**Existing fair dealing exceptions.** The _Copyright Act 1968_ (Cth) contains a set of fair dealing exceptions — for research or study (s 40), criticism or review (s 41), parody or satire (s 41A), reporting news (s 42), and professional advice (s 43). None of these was designed with AI training in mind. The research or study exception is the most frequently raised in the AI context, but it is unlikely to cover commercial AI training: it is intended for personal research by individuals, not industrial-scale reproduction of entire works for commercial model development. Australia also has no general "transformative use" doctrine comparable to the US fair use doctrine under 17 USC § 107.

**The practical position.** Until licensing frameworks are established by CAIRG, AI developers training models on copyright material in Australia without the rights holders' permission face real legal risk. The three practical responses are: licence the training data from rights holders; train only on data published under licences that expressly permit reproduction and training use; or seek specific legal advice on whether any existing exception applies to the particular use.

## 2.3 Format

### 2.3.1 Structured data

Structured data is data organised in a predefined format — typically rows and columns — such as relational databases, spreadsheets, and CSV files. In Australia, the _Copyright Act 1968_ (Cth) does not recognise a separate "database right" as in the European Union. A database may attract copyright as a compilation if it exhibits authorial creativity in the selection or arrangement of its contents (confirmed in _IceTV Pty Ltd v Nine Network Australia Pty Ltd_ [2009] HCA 14 as requiring intellectual effort and creative labour). A purely mechanical collation of data with no creative selection is unlikely to be protected.

When structured data contains personal information, all of the APPs discussed above apply, including the security obligation under APP 11 — which encompasses AI-specific risks such as model inversion (where an attacker reconstructs training records from a deployed model) and membership inference (where an attacker determines whether a specific record was used in training).

### 2.3.2 Unstructured data

Unstructured data — free text, images, audio, video — is increasingly the input of choice for modern AI. It is also more likely than structured data to attract copyright protection, because literary, artistic, dramatic and musical works are among the categories most naturally expressed in unstructured form. A news article, social media post of sufficient length, photograph, piece of music, or audio recording may all be copyright works.

Where an AI system is trained on unstructured content without the licence of the copyright owner, infringement may occur (see section 2.2.3). Where the unstructured content relates to individuals — a voice recording, photograph, or personal correspondence — it may also constitute personal information under the _Privacy Act 1988_ (Cth), triggering APP compliance obligations.

## 2.4 Data processing

### 2.4.1 The GDPR and Australian organisations

The EU General Data Protection Regulation (GDPR) (EU) 2016/679, in force since 25 May 2018, imposes obligations on any organisation that processes personal data of EU residents in connection with offering them goods or services or monitoring their behaviour — regardless of where the organisation is located. Australian organisations with EU users or customers must comply.

The GDPR differs from the Australian Privacy Act in important respects:

| Feature | *Privacy Act 1988* (Cth) / APPs | EU GDPR |
|---|---|---|
| Lawful basis for processing | Reasonably necessary (APP 3) | One of six lawful bases required (Art 6) |
| Automated decisions: right to contest | Transparency only from Dec 2026 (APP 1.7/1.8) | Right to explanation and human review (Art 22) |
| Right to erasure | Correction and destruction under APP 13/11 | Explicit right to erasure (Art 17) |
| Data minimisation | Implicit in "reasonably necessary" | Explicit principle (Art 5(1)(c)) |
| Privacy impact assessments | Recommended by OAIC | Mandatory for high-risk processing (Art 35) |
| Penalties | Up to $50M or 30% of turnover (corps); $2.5M (individuals) | Up to €20M or 4% of global annual turnover |

Where the GDPR imposes a stricter standard than the APPs, the GDPR standard applies to Australian organisations processing EU residents' data. For AI systems with European users, the GDPR's Article 22 prohibition on solely automated decisions with significant effects — and the accompanying right to human review — is directly relevant and has no equivalent in current Australian law.

### 2.4.2 The Consumer Data Right

The Consumer Data Right (CDR), established by the _Competition and Consumer Act 2010_ (Cth) as amended, gives consumers the right to direct their bank (and in time, their energy retailer and other service providers) to share their data with accredited third parties. In banking (Open Banking), this creates a new class of richly structured, standardised financial data that is a valuable input for AI applications including personalised financial tools and credit assessment systems.

CDR data is subject to strict use constraints: accredited data recipients may only use CDR data for the purpose for which the consumer's consent was given. Using CDR data to train general-purpose AI models — beyond the scope of the specific consent — would breach the CDR Privacy Safeguards in the _Competition and Consumer Act 2010_ (Cth). Data scientists working with CDR data must ensure that model training use cases are captured in the original consumer consent.

---

## References

*Age Discrimination Act 2004* (Cth)

*Competition and Consumer Act 2010* (Cth) sch 2 (*Australian Consumer Law*)

*Copyright Act 1968* (Cth)

*Criminal Code Act 1995* (Cth)

*Disability Discrimination Act 1992_ (Cth)

*Privacy Act 1988* (Cth)

*Privacy and Other Legislation Amendment Act 2024* (Cth)

*Racial Discrimination Act 1975* (Cth)

*Sex Discrimination Act 1984* (Cth)

*Telecommunications (Interception and Access) Act 1979* (Cth)

*Australian Competition and Consumer Commission v Google LLC (No 2)* [2021] FCA 367

*IceTV Pty Ltd v Nine Network Australia Pty Ltd* [2009] HCA 14

*Privacy Commissioner v Telstra Corporation Limited* [2017] FCAFC 4

*hiQ Labs, Inc v LinkedIn Corporation* 938 F 3d 985 (9th Cir, 2019) [United States — comparative]

Australia, Attorney-General's Department, *Privacy Act Review Report* (Report, February 2023) <https://www.ag.gov.au/rights-and-protections/publications/privacy-act-review-report> accessed 1 July 2026

Australian Competition and Consumer Commission, 'Google LLC to Pay $60 Million for Misleading Representations' (Media Release, 12 August 2022) <https://www.accc.gov.au/media-release/google-llc-to-pay-60-million-for-misleading-representations> accessed 1 July 2026

Office of the Australian Information Commissioner, *Guidance on Privacy and the Use of Commercially Available AI Products* (October 2024) <https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-the-use-of-commercially-available-ai-products> accessed 1 July 2026

Office of the Australian Information Commissioner, *Guidance on Privacy and Developing and Training Generative AI Models* (October 2024) <https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-developing-and-training-generative-ai-models> accessed 1 July 2026

Office of the Australian Information Commissioner, *OAIC Regulatory Action Priorities 2025–26* (2025) <https://www.oaic.gov.au/news/media-centre/oaic-releases-regulatory-action-priorities-for-2025-26> accessed 1 July 2026

Office of the Australian Information Commissioner, *Guide to Data Analytics and the Australian Privacy Principles* (Web Page, 2018) <https://www.oaic.gov.au/privacy/guidance-and-advice/guide-to-data-analytics-and-the-australian-privacy-principles/> accessed 1 July 2026

Attorney-General Michelle Rowland, announcement on TDM exception (26 October 2025), reported in Bird & Bird, '3 Key Takeaways from Australia's Latest AI Copyright Law Reform Announcement' (2025) <https://www.twobirds.com/en/insights/2025/australia/3-key-takeaways-from-australia%E2%80%99s-latest-ai-copyright-law-reform-announcement> accessed 1 July 2026

Hernandez-Suarez A et al, 'A Web Scraping Methodology for Bypassing Twitter API Restrictions' (2018) arXiv:1803.09875 [cs.IR] <https://arxiv.org/pdf/1803.09875.pdf> accessed 1 July 2026
