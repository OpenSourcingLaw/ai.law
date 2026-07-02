# Industry specific advice

This chapter provides focused legal guidance for practitioners working in two heavily regulated sectors: insurance and banking and financial services. Each sector has statutory frameworks that modify the general legal rules described in earlier chapters, and each presents recurring AI use cases that require specific legal consideration.

<TOC>

## Insurance Industry

### AI use cases in insurance

Machine learning is used across the insurance value chain: underwriting (risk assessment and premium setting), claims processing (automated assessment and fraud detection), and customer lifecycle management (product targeting, renewal, and retention). Each use case involves processing personal data — frequently including sensitive information about health, disability, driving behaviour, location, and financial circumstances — to make decisions that directly affect individuals. The legal framework that governs these uses reflects a deliberate balance: insurers must be able to differentiate between risks to price and underwrite insurance products, but cannot use protected attributes to discriminate without foundation.

### The anti-discrimination exception framework

Australia's federal anti-discrimination legislation prohibits discrimination on protected grounds in the provision of goods and services, including insurance. However, each of the principal Acts contains a specific exception for insurance and superannuation, recognising that actuarial risk classification is inherent to the insurance business. These exceptions impose substantive requirements; they are not a blank licence to discriminate.

#### Disability Discrimination Act 1992 (Cth) — section 46

Section 46 of the _Disability Discrimination Act 1992_ (Cth) (DDA) provides that discrimination on the ground of disability in the provision of insurance or superannuation is not unlawful if:

> (a) the discrimination is based on actuarial or statistical data on which it is reasonable for the person to rely; and it is reasonable having regard to the matter of the data and other relevant factors; or
> (b) where no such actuarial or statistical data is available and cannot reasonably be obtained — the discrimination is reasonable having regard to any other relevant factors.

This exception has three key requirements. First, where relevant actuarial or statistical data exists or can reasonably be obtained, the insurer must rely on it — it cannot fall back on assumptions or intuitions. Second, the insurer must be able to demonstrate that reliance on the data was reasonable in the circumstances. Third, an individualised assessment of the specific applicant's risk, grounded in that data, is required: section 46 does not authorise blanket categorical exclusions unsupported by data.

For AI-driven underwriting models, this exception requires that: differential treatment based on disability-related inputs be traceable to actuarial or statistical data; the data be current and relevant; and the model's use of that data be demonstrably reasonable. Where the model relies on proxy variables correlated with disability but not expressly disability-specific, whether the exception is engaged is a more nuanced question that should be addressed with legal advice. [VERIFY: checked July 2026 — no new case law. Review each iteration.]

#### Sex Discrimination Act 1984 (Cth) — section 41

Section 41 of the _Sex Discrimination Act 1984_ (Cth) (SDA) provides a comparable exception: discrimination on the basis of sex, pregnancy, potential pregnancy, breastfeeding, marital or relationship status, or family responsibilities in the provision of insurance is not unlawful if the discrimination is based on actuarial or statistical data on which it is reasonable to rely, and is reasonable having regard to the data and any other relevant factors.

A distinctive feature of the SDA exception is a **disclosure obligation**: where the exception is invoked, the insurer must, if requested by the customer, provide the actuarial or statistical data on which the discrimination is based. This creates a transparency requirement directly relevant to AI underwriting. An insurer using a machine learning model for sex-differentiated pricing must maintain records of the actuarial data underlying the model's differentiations and be able to produce and explain that data if a customer requests it. A model whose differentiated outputs cannot be traced to specific actuarial data — a "black box" model — cannot satisfy this obligation.

#### Age Discrimination Act 2004 (Cth) — section 37

Section 37 of the _Age Discrimination Act 2004_ (Cth) (ADA) permits age-based differentiation in insurance and superannuation where the differentiation is based on reasonable actuarial or statistical data, or — where such data is unavailable — is otherwise reasonable. Age is among the most common variables in actuarial models and age-differentiated insurance is standard across life, health, and general insurance markets.

#### Racial Discrimination Act 1975 (Cth) — no insurance exception

The _Racial Discrimination Act 1975_ (Cth) (RDA) prohibits discrimination in the provision of services, including insurance, on the ground of race, colour, national or ethnic origin and descent. **There is no insurance exception in the RDA.** No actuarial justification can authorise race-based insurance discrimination. AI underwriting models must not use race, colour, national origin, ethnicity, or descent as features, directly or through closely correlated proxy variables, in setting premiums or assessing eligibility. This prohibition is absolute.

### Best practice for AI underwriting

For data scientists building insurance AI models:

1. **Document the actuarial basis** for every input that correlates with a protected attribute. Section 46 DDA, s 41 SDA, and s 37 ADA all require that differentiation be traceable to actuarial or statistical data.
2. **Maintain disclosure records for SDA purposes**: if sex or related attributes influence outcomes, the underlying actuarial data must be identifiable and producible on request.
3. **No race-based features**: race, ethnicity, national origin, and closely correlated proxies must not be used in underwriting models. There is no exception.
4. **Audit for indirect discrimination**: test model outputs across all protected groups for systematically adverse outcomes — even where no protected attribute is an explicit input feature.
5. **Review the proportionality requirement**: the exception requires differentiation to be "reasonable" having regard to the data — not just statistically supportable. If a risk classification produces large disparate outcomes from a small actuarial basis, reasonableness may not be satisfied.

---

## Banking and Financial Services

### AI use cases in financial services

AI and machine learning are applied across financial services: credit scoring and loan origination, fraud detection, AML/CTF transaction monitoring, market data analysis, customer engagement, and — increasingly — personalised financial guidance and advice. It is this last category — where AI interacts with consumers about their financial products and decisions — that generates the most acute regulatory complexity.

### The personal advice boundary: ASIC v Westpac

Chapter 7 of the _Corporations Act 2001_ (Cth) draws a fundamental distinction between "personal advice" and "general advice."

**Personal advice** is financial product advice given to a retail client where the adviser has considered one or more of the client's objectives, financial situation or needs, or where a reasonable person might expect the adviser to have considered those matters. It requires an Australian Financial Services Licence (AFSL) with personal advice authorisation and triggers a "best interests" duty (s 961B, _Corporations Act 2001_ (Cth)) and the requirement to provide a Statement of Advice.

**General advice** is all other financial product advice — given without consideration of individual circumstances, accompanied by a required warning. It requires a lesser authorisation.

In _Westpac Securities Administration Ltd v Australian Securities and Investments Commission_ [2021] HCA 3, the High Court unanimously held that Westpac had provided personal advice when its Super Activation Team telephoned superannuation fund members. Despite verbal general advice disclaimers, the Court found that immediately after the disclaimer, representatives elicited information about members' objectives and used social proofing techniques — implicitly invoking the member's individual circumstances. A reasonable person in the member's position would expect their circumstances to have been considered.

**The AI implication.** An AI system that: uses a customer's personal data (account balances, transaction history, holdings, stated goals); generates a recommendation tailored to that individual's circumstances; and communicates it to the customer — risks characterisation as personal advice regardless of a generic disclaimer. The statutory test focuses on the reasonable perception of the client, not the internal architecture of the algorithm.

Organisations deploying AI in consumer-facing financial services must:
1. Hold a personal advice AFSL authorisation if their AI system could meet the personal advice test;
2. Comply with the best interests duty — ensuring the AI's recommendation genuinely serves the client's interests;
3. Ensure the AI system does not elicit or use personal circumstances in ways that trigger personal advice obligations unless licensed and compliant; and
4. Obtain specific legal advice before deploying recommendation AI in regulated financial services.

### Professional duty and AI-generated financial advice

The *Dayal* [2024] FedCFamC2F 1166 and *Helmold & Mariya (No 2)* (2025) FLC 94-272 cases (discussed in Chapter 3) are not limited in their implications to the legal profession. Financial advisers and other professionals who rely on AI-generated analysis — credit assessments, investment research, market summaries, due diligence reports — remain personally responsible for the accuracy and reliability of the output. Using AI to generate advice does not reduce the professional's duty of care to their client. It creates an additional verification obligation.

### The Consumer Data Right and AI in financial services

The Consumer Data Right (CDR), established under the _Competition and Consumer Act 2010_ (Cth), allows consumers in the banking sector (Open Banking) to direct their bank to share their transaction data with accredited third parties. By mid-2024, the CDR ecosystem included 99 data holders, approximately 41 accredited data recipients, and nearly 390 million data requests in a six-month period.

For AI applications, CDR data is highly valuable: it is structured, standardised, current, and represents a consumer's actual financial position. AI applications being built on CDR data include personalised budgeting tools, loan eligibility assessments, and — subject to appropriate licensing — automated financial guidance.

CDR data use is governed by strict purpose limitations in the CDR Privacy Safeguards (contained in the _Competition and Consumer Act 2010_ (Cth)):

- CDR data may only be used for the purpose for which the consumer's consent was given. Training a general-purpose AI model on CDR data, beyond the scope of the specific consent, would breach the CDR rules;
- Data minimisation applies: only the data needed for the authorised purpose may be requested;
- Retention limits apply: CDR data must be deleted when no longer needed, unless further consent is obtained; and
- Organisations receiving CDR data must be accredited by the ACCC under the CDR framework.

AI product teams building on CDR data must ensure that each use case is captured in the relevant consumer consent, and that CDR data is not repurposed for general model training without separate authorisation.

### Anti-money laundering, counter-terrorism financing, and AI

Financial institutions are subject to the _Anti-Money Laundering and Counter-Terrorism Financing Act 2006_ (Cth) (AML/CTF Act), which requires reporting entities — including banks and financial institutions — to implement AML/CTF programs, conduct customer due diligence (KYC), and report suspicious matters to AUSTRAC.

AI and machine learning are now standard in AML/CTF compliance: transaction monitoring, customer risk scoring, and suspicious matter detection routinely use ML models. This is permissible and encouraged — but it does not displace the legal obligation. A reporting entity cannot rely on an algorithmic false negative (a suspicious transaction the model failed to flag) as a defence against failure to report. The statutory obligation rests with the reporting entity, not the algorithm. AML/CTF programs that rely on AI must also ensure that the AI component is tested, monitored, and subject to human oversight sufficient to meet the entity's statutory obligations.

---

## References

*Age Discrimination Act 2004* (Cth)

*Anti-Money Laundering and Counter-Terrorism Financing Act 2006* (Cth)

*Competition and Consumer Act 2010* (Cth)

*Corporations Act 2001* (Cth)

*Disability Discrimination Act 1992* (Cth)

*Privacy Act 1988* (Cth)

*Racial Discrimination Act 1975* (Cth)

*Sex Discrimination Act 1984* (Cth)

*Dayal* [2024] FedCFamC2F 1166

*Helmold & Mariya (No 2)* (2025) FLC 94-272

*Westpac Securities Administration Ltd v Australian Securities and Investments Commission* [2021] HCA 3

Australian Human Rights Commission, *Guidelines for Providers of Insurance and Superannuation Under the Disability Discrimination Act 1992* (Australian Human Rights Commission, 2016) <https://humanrights.gov.au/our-work/disability-rights/guidelines-providers-insurance-and-superannuation-under-disability> accessed 1 July 2026

Australian Securities and Investments Commission, 'ASIC Annual Forum 2023: Impact of AI on Financial Services' (ASIC, 2023) <https://www.asic.gov.au/about-asic/news-centre/news-items/asic-annual-forum-2023-impact-of-ai-on-financial-services/> accessed 1 July 2026

Assured Support, 'Guide for Advisers and Licensees: Navigating AI in Financial Services' (2026) <https://assuredsupport.com.au/articles/guide-for-advisers-and-licensees-navigating-ai-in-financial-services/> accessed 1 July 2026
