# Privacy

This chapter provides a deeper treatment of Australian information privacy law than Chapter 2, tracing its historical origins, explaining its current structure, and surveying the 2024 reforms that are reshaping the framework. It also addresses related causes of action: the Notifiable Data Breaches scheme and the new statutory tort for serious invasions of privacy. Practitioners should read this chapter alongside Chapter 2, which addresses privacy law as it applies specifically to AI inputs.

<TOC>

## Information Privacy Law

### Origins

Australia's _Privacy Act 1988_ (Cth) (the Act) is the central instrument of information privacy law at the Commonwealth level. Its origins lie in a convergence of international human rights law, domestic political events, and the work of a single individual who shaped both.

**The international human rights framework.** Privacy's place in international law was established in the aftermath of the Second World War's atrocities. The _Universal Declaration of Human Rights_ (1948) recognised privacy as a fundamental right. Article 17 of the _International Covenant on Civil and Political Rights_ (ICCPR) (1966), to which Australia is a party, provides:

> 1. No one shall be subjected to arbitrary or unlawful interference with his privacy, family, home or correspondence, nor to unlawful attacks on his honour and reputation.
> 2. Everyone has the right to the protection of the law against such interference or attacks.

**The computerisation threat.** The second stimulus for data protection legislation was the expansion of government use of computerised systems from the 1960s onward. The storage of information migrated from paper to the stored-program computer, giving rise to public concern about automated surveillance and data processing by the state. The United States responded with the _Privacy Act of 1974_, 5 USC § 552(a). European nations responded with data protection laws from the late 1970s.

**The OECD Guidelines.** The proliferation of national legislation, with varying standards, raised concern about inconsistent cross-border data flow requirements. The Organisation for Economic Co-operation and Development (OECD) responded with the _Guidelines Governing the Protection of Privacy and Transborder Flows of Personal Data_ 1980 (the OECD Guidelines), which articulated eight core principles: collection limitation; data quality; purpose specification; use limitation; security safeguards; openness; individual participation (access and correction); and accountability. The OECD Guidelines became the international template for information privacy legislation.

**Michael Kirby and Australia's path.** Michael Kirby chaired both the OECD Expert Group that drafted the Guidelines and the Australian Law Reform Commission (ALRC), which in 1983 tabled _Privacy_, Report No 22 — recommending a Privacy Act establishing information privacy principles and a Privacy Commissioner. Australia acceded to the OECD Guidelines in 1984.

**The Australia Card and the Privacy Act 1988.** Momentum for domestic legislation crystallised around a politically contentious proposal: the "Australia Card," a proposed national identity number to combat tax and welfare fraud. Initial public support — as high as 68 per cent before the 1987 federal election — fell sharply to 39 per cent by September 1987. The proposal was abandoned. In its place, the Government strengthened the Tax File Number (TFN) scheme. To secure Senate support for TFN legislation, the Government introduced the _Privacy Bill 1988_, which explicitly referenced the ICCPR, the OECD Guidelines, and the ALRC's Report No 22 in its Second Reading Speech. The _Privacy Act 1988_ (Cth) passed.

### Application

The Act applies to:

- All Commonwealth Government agencies, regardless of size;
- Private sector organisations and not-for-profit organisations with an annual turnover of more than $3 million;
- All private sector health service providers, regardless of turnover; and
- Certain other organisations regardless of size, including credit reporting bodies and organisations that trade in personal information.

These entities are collectively referred to as "APP entities." Unlike the EU's GDPR, the Act does not distinguish between "data controllers" (organisations that own or determine the use of data) and "data processors" (organisations that process data on behalf of controllers). This means the Act reaches to cloud computing providers, AI development contractors, and analytics service providers that handle personal information on behalf of APP entities — the entity that is the APP entity retains responsibility, but so may the service provider.

State and territory government agencies are regulated by state equivalents: in New South Wales, the _Privacy and Personal Information Protection Act 1998_ (NSW) and the _Health Records and Information Privacy Act 2002_ (NSW); in Victoria, the _Privacy and Data Protection Act 2014_ (Vic); in Queensland, the _Information Privacy Act 2009_ (Qld); and so forth.

#### Definition of personal information

The Act applies to "personal information," defined in s 6(1) as:

> Information or an opinion about an identified individual, or an individual who is reasonably identifiable: whether the information or opinion is true or not; and whether the information or opinion is recorded in a material form or not.

Key features of this definition for AI practitioners: first, it covers false information — including AI-generated hallucinations about a real person; second, it is not limited to recorded information; third, "reasonably identifiable" captures the jigsaw risk where combining individually innocuous datasets renders individuals identifiable. See _Privacy Commissioner v Telstra Corporation Limited_ [2017] FCAFC 4 on the threshold "about" question.

#### Sensitive information

"Sensitive information" — defined in s 6(1) and attracting higher protections — includes information or an opinion about a person's racial or ethnic origin, political opinions, religious beliefs, philosophical beliefs, trade union membership, sexual orientation or practices, criminal record, health information, genetic information, and biometric information. Sensitive information may generally only be collected with the individual's consent and if reasonably necessary for the entity's functions. AI systems that generate inferences about these categories are processing sensitive information even if they do not collect it directly.

### The OAIC and AI regulation

The Office of the Australian Information Commissioner (OAIC) is the independent regulator charged with overseeing compliance with the Act. In October 2024, the OAIC issued two sets of guidance specifically addressing AI — the first such guidance since the Act's enactment.

**Guidance on privacy and the use of commercially available AI products** addresses entities using large language model chatbots, productivity assistants, transcription tools, and similar commercial AI products. The guidance confirms that inputting personal information into a commercial AI tool constitutes a "use" under APP 6, requiring consent or a secondary-use exception. It recommends Privacy Impact Assessments (PIAs) before deploying AI tools, and vendor due diligence to ensure overseas AI providers handle data consistently with the APPs.

**Guidance on privacy and developing and training generative AI models** characterises the development of a generative AI model on personal data as a high privacy risk activity, requiring Privacy by Design from the outset. It confirms that web-scraped training data almost certainly contains personal information, that using it for AI training is regulated by APP 3 and APP 6, and that AI-generated hallucinations about real people can themselves constitute personal information.

The OAIC's **regulatory action priorities for 2025–26** expressly designate AI and automated decision-making — particularly government use of AI — as a priority enforcement area. The OAIC is monitoring how government agencies use automated decision-making and whether they are transparent about it.

### The Privacy and Other Legislation Amendment Act 2024

The _Privacy and Other Legislation Amendment Act 2024_ (Cth) (the Amendment Act) received Royal Assent on 10 December 2024, implementing 23 of 25 recommendations from the Attorney-General's _Privacy Act Review Report_ (February 2023).

#### Automated decision-making transparency (commencing 10 December 2026)

The Amendment Act introduces new APP 1.7 and APP 1.8, commencing on 10 December 2026. APP 1.7 requires an APP entity to comply with transparency obligations where it uses a computer program to make or directly support a decision that could reasonably be expected to significantly affect an individual's rights or interests. APP 1.8 requires the entity's privacy policy to disclose: the kinds of personal information used in such systems; the kinds of decisions made solely by such systems; and the kinds of decisions in which such systems play a substantially assisting role.

These are **transparency obligations only.** Unlike the EU GDPR's Article 22 — which gives individuals a right to contest automated decisions and require a human review — Australia's provisions require disclosure but do not confer substantive individual rights. This gap is widely noted. Entities should, before December 2026: audit their automated decision-making systems; assess whether they could significantly affect individual rights or interests; and update their privacy policies accordingly.

#### Statutory tort for serious invasions of privacy (in force from 10 June 2025)

The Amendment Act introduced a statutory cause of action for serious invasions of privacy, which came into force on 10 June 2025. This tort is a landmark development: Australian courts had previously declined to recognise a general common law tort of invasion of privacy (cf _Australian Broadcasting Corporation v Lenah Game Meats Pty Ltd_ [2001] HCA 63), and the equitable doctrine of breach of confidence was the closest available remedy.

The statutory tort requires: an invasion of privacy by intrusion upon seclusion or by misuse of information; that the invasion was intentional or reckless; that the plaintiff had a reasonable expectation of privacy; that the invasion was serious; and that the public interest in privacy outweighs any competing public interest. Notably, the tort operates independently of the APPs and can be brought against individuals and organisations not regulated by the Act — including small businesses below the $3 million threshold.

For AI systems: the tort may be engaged where AI is used to surveil individuals, to aggregate publicly available information in ways that violate reasonable privacy expectations (the "mosaic" effect), or to generate deepfakes. The statutory tort creates litigation risk for AI systems that handle personal information intrusively, beyond and independent of regulatory enforcement.

#### Penalties

The Amendment Act substantially increased maximum civil penalties for serious and repeated interference with privacy. For body corporates: the greater of $50 million, three times the value of the benefit obtained, or 30 per cent of adjusted turnover. For individuals: $2.5 million. These penalties apply to serious or repeated privacy breaches and represent a significant escalation from the prior maximum of $2.22 million.

#### Children's Online Privacy Code

The Amendment Act mandates the OAIC to develop a Children's Online Privacy Code (the Code), applicable to online services likely to be accessed by children — including social media, apps, games, and websites. The Code must be finalised by 10 December 2026. The draft Code, released on 31 March 2026, proposes obligations for child-facing digital services including data minimisation, prohibition on profiling children for advertising without parental consent, and enhanced access and deletion rights. AI-driven platforms serving minors will face significant compliance obligations under the Code.

### Pending reforms: the second tranche

Several recommendations from the _Privacy Act Review Report_ (2023) were not included in the 2024 Act:

- **Removal of the small business exemption**: the Review recommended removing the $3 million turnover threshold that exempts many small businesses and AI startups from the Act, subject to an appropriate transition period and proportionate compliance pathways. Not yet legislated.
- **The "fair and reasonable" test**: the Review recommended a general obligation that collection, use, and disclosure of personal information be "fair and reasonable," which is a broader and more rights-protective standard than the current "reasonably necessary" test. Not yet legislated.
- **Right to erasure**: stronger individual rights to request deletion of personal information in specified circumstances. Not yet legislated.

### Notifiable Data Breaches scheme

The _Privacy Amendment (Notifiable Data Breaches) Act 2017_ (Cth) introduced the Notifiable Data Breaches (NDB) scheme, in force from 22 February 2018. The scheme requires APP entities to notify the OAIC and affected individuals when an "eligible data breach" occurs.

An eligible data breach occurs when: there is unauthorised access to, or disclosure of, personal information (or personal information is lost and such access or disclosure is likely); and a reasonable person would conclude that this is likely to result in **serious harm** to any affected individual.

Serious harm is assessed by reference to: the sensitivity of the information; whether it is protected by security measures; the nature of the likely harm (financial, psychological, physical, reputational); and whether a malicious actor was involved. An entity that suspects an eligible data breach must conduct an assessment within 30 days. If confirmed, it must notify the OAIC and the affected individuals.

For AI systems, the NDB scheme is directly relevant: a breach of an AI training dataset, a breach of data used for inference, or an AI system that inadvertently reconstructs and exposes training data (model inversion) may each constitute an eligible data breach. Post-deployment monitoring of AI systems should include monitoring for data exposure events that would trigger NDB obligations.

### Breach of confidence

The equitable doctrine of breach of confidence protects confidential information — including trade secrets, commercially sensitive data, and personal information — independently of the _Privacy Act_. The elements (from _Coco v AN Clark (Engineers) Ltd_ [1969] RPC 41, as received into Australian law) are: the information has the necessary quality of confidence; it was communicated in circumstances importing an obligation of confidence; and it was used or disclosed without authority.

For AI creators, breach of confidence is relevant in two ways. First, trained models — whose weights encode the learning from large, expensive datasets — are typically protected as confidential information. Employees and contractors with access to trained models are bound by confidence obligations both under their contracts and under the general equitable doctrine. Second, in the absence of a common law privacy tort, breach of confidence has historically been the closest available remedy for misuse of personal information. The 2024 statutory tort now provides an alternative, but breach of confidence retains independent vitality, particularly where an obligation of confidence can be established.

---

## References

*Health Records and Information Privacy Act 2002* (NSW)

*Information Privacy Act 2009* (Qld)

*Privacy Act 1988* (Cth)

*Privacy Amendment (Notifiable Data Breaches) Act 2017* (Cth)

*Privacy and Data Protection Act 2014* (Vic)

*Privacy and Other Legislation Amendment Act 2024* (Cth)

*Privacy and Personal Information Protection Act 1998* (NSW)

*International Covenant on Civil and Political Rights*, opened for signature 16 December 1966, 999 UNTS 171 (entered into force 23 March 1976) art 17

*Universal Declaration of Human Rights*, GA Res 217A (III), UN Doc A/810 (10 December 1948) art 12

*Australian Broadcasting Corporation v Lenah Game Meats Pty Ltd* [2001] HCA 63

*Coco v AN Clark (Engineers) Ltd* [1969] RPC 41

*Dayal* [2024] FedCFamC2F 1166

*Privacy Commissioner v Telstra Corporation Limited* [2017] FCAFC 4

Organisation for Economic Co-operation and Development, *Guidelines Governing the Protection of Privacy and Transborder Flows of Personal Data* (OECD, 1980)

Australia, Attorney-General's Department, *Privacy Act Review Report* (Report, February 2023) <https://www.ag.gov.au/rights-and-protections/publications/privacy-act-review-report> accessed 1 July 2026

Australian Law Reform Commission, *Privacy*, Report No 22 (ALRC, 1983)

Office of the Australian Information Commissioner, *Guidance on Privacy and the Use of Commercially Available AI Products* (October 2024) <https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-the-use-of-commercially-available-ai-products> accessed 1 July 2026

Office of the Australian Information Commissioner, *Guidance on Privacy and Developing and Training Generative AI Models* (October 2024) <https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-developing-and-training-generative-ai-models> accessed 1 July 2026

Office of the Australian Information Commissioner, *OAIC Regulatory Action Priorities 2025–26* (2025) <https://www.oaic.gov.au/news/media-centre/oaic-releases-regulatory-action-priorities-for-2025-26> accessed 1 July 2026

Office of the Australian Information Commissioner, 'Better Privacy Protections for Children are Coming' (Web Page, 2026) <https://www.oaic.gov.au/news/blog/better-privacy-protections-for-children-are-coming> accessed 1 July 2026

Norton Rose Fulbright, 'Australian Privacy Alert: Parliament Passes Major and Meaningful Privacy Law Reform' (December 2024) <https://www.nortonrosefulbright.com/en-au/knowledge/publications/be98b0ff/australian-privacy-alert-parliament-passes-major-and-meaningful-privacy-law-reform> accessed 1 July 2026
