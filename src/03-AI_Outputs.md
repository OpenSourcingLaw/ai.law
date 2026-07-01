# 3. AI Outputs

Machine learning systems are trained to generate outputs — predictions, scores, recommendations, decisions, and generated content. This chapter examines the legal frameworks that apply to the most significant categories of AI output in Australia: profiling and targeting of individuals, algorithmic pricing, automated decisioning, and AI-generated content. A unifying theme is that Australian law is technology-neutral: the same obligations that apply to human decisions and human-created content apply equally to AI-generated equivalents. The use of AI does not reduce legal exposure; in some respects it creates new risks that require specific management.

<TOC>

## 3.1 Profiling and targeting

A common application of machine learning is to categorise individuals based on available data — creating profiles — and to target communications, offers, or services at individuals based on those profiles. This section examines the consumer protection and financial services law that applies to such systems.

### 3.1.1 Unconscionable conduct

When designing a profiling or targeting system, the nature of the segment being created must be assessed against legal prohibitions on unconscionable conduct. The term "unconscionable" has a specific legal meaning: conduct so contrary to good conscience that equity will not permit it to stand.

Section 21 of the _Australian Consumer Law_ (sch 2 to the _Competition and Consumer Act 2010_ (Cth)) (ACL) prohibits unconscionable conduct in trade or commerce. Section 12CB(1) of the _Australian Securities and Investments Commission Act 2001_ (Cth) (ASIC Act) contains an equivalent prohibition applying to financial services. Courts assess unconscionability by reference to all the circumstances, including: the relative bargaining positions of the parties; whether any undue influence, pressure or unfair tactics were used; whether the terms of any transaction were explained to the affected party; whether the individual had a disability, infirmity or other condition affecting their capacity; and whether the conduct was in good faith.

Consider a machine learning model that identifies individuals as exhibiting characteristics associated with problem gambling, inferred from behavioural data. Targeting that segment with advertisements for gambling services or exploitative credit products may constitute unconscionable conduct: the operator has identified the vulnerability and is exploiting it for commercial gain. Targeting the same segment with problem-gambling support services would be regarded very differently.

In _Australian Competition and Consumer Commission v Equifax Australia Information Services Pty Ltd_ [2018] FCA 1637, the Federal Court found that Equifax had engaged in unconscionable conduct by using unfair sales tactics on consumers who were in financial distress — precisely the population whose vulnerability the company had identified and then exploited. This case illustrates that identifying vulnerability through data analytics and then targeting the vulnerable with unsuitable products is the factual pattern that engages the unconscionable conduct prohibition.

In _Australian Securities and Investments Commission v Kobelt_ [2019] HCA 18, the High Court held by majority that unconscionable conduct was not established on the facts — the arrangement was entered voluntarily and the participants had a basic understanding of it. The minority would have found otherwise. The case is a reminder that unconscionability is intensely fact-specific; a voluntary arrangement between parties with some understanding of the terms is not automatically unconscionable even where their positions are unequal.

For data scientists and product designers, the implications are: the nature of the segments being built matters; targeting vulnerable populations with products that exploit their vulnerability is legally risky; and the fact that targeting is algorithmic rather than human-directed provides no legal protection.

### 3.1.2 Financial services: personal advice and the Westpac case

In financial services, whether an AI-driven system provides "personal advice" or "general advice" under Chapter 7 of the _Corporations Act 2001_ (Cth) is a question with major regulatory consequences.

**Personal advice** is financial product advice given to a retail client where the adviser has considered one or more of the client's objectives, financial situation or needs, or where a reasonable person might expect the adviser to have done so. Personal advice triggers requirements for an Australian Financial Services Licence (AFSL), a best interests duty (s 961B of the _Corporations Act 2001_ (Cth)), and a Statement of Advice.

**General advice** is all other financial product advice — advice given without consideration of individual circumstances. General advice requires a lesser licence and a warning that it does not take the client's personal circumstances into account.

In _Westpac Securities Administration Ltd v Australian Securities and Investments Commission_ [2021] HCA 3, the High Court unanimously held that Westpac had provided personal advice when its Super Activation Team telephoned existing BT superannuation fund members to encourage them to roll over external superannuation funds. Despite verbal "general advice" disclaimers, the Court held that immediately after the disclaimer, Westpac representatives elicited information about members' objectives and used social proofing techniques implying that the representatives had considered the member's individual circumstances. A reasonable person in the member's position would expect their objectives to have been considered.

**The AI implication is direct.** An AI system that uses personal data — account balances, transaction history, product holdings — to generate recommendations tailored to an individual's circumstances, and communicates those recommendations to the individual, risks characterisation as personal advice regardless of any automated disclaimer. The statutory test focuses on the reasonable perception of the client, not the internal design of the algorithm. Financial services organisations deploying AI recommendation engines must ensure they hold the necessary AFSL authorisation for personal advice and meet the full suite of associated obligations.

## 3.2 Algorithmic pricing

Algorithmic pricing services continuously monitor market conditions, competitor prices, and demand signals to set optimal prices in real time. Their widespread adoption has attracted competition law concern as a potential mechanism for price coordination without explicit agreement.

### 3.2.1 Competition law and algorithmic collusion

The _Competition and Consumer Act 2010_ (Cth) (CCA) prohibits cartels — including price-fixing, market allocation and bid rigging — under ss 45 and 45AD. The 2017 amendment introduced a prohibition on "concerted practices" that have the purpose or effect of substantially lessening competition (s 45 CCA). This provision requires less coordination than cartel conduct: it can be engaged by parallel conduct that is not coincidental and not independently arrived at.

Research literature identifies two specific scenarios of concern:

**The hub-and-spoke scenario.** Competing businesses independently adopt the same third-party pricing algorithm. Even without any communication between competitors, the businesses using the same algorithm may converge on similar pricing outcomes. The algorithm provider is the "hub" and the competing businesses are the "spokes." This structure may achieve price coordination without explicit agreement, potentially engaging the concerted practices prohibition.

**The reinforcement learning scenario.** An algorithm trained using reinforcement learning discovers that sustained high prices — tacit collusion — maximise its reward function. It learns this without any human instruction to collude, and other algorithms in the same market converge on the same strategy. The resulting supra-competitive pricing is a product of the algorithm's learning, not any human agreement. This makes detection and enforcement difficult under existing legal frameworks.

The ACCC has publicly noted that the concerted practices provision in the CCA was introduced partly to address big data e-collusion, and its five-year Digital Platform Services Inquiry (2020–2025) examined whether existing law is adequate to address algorithmic market conduct. As at July 2026, there has been no contested court case on the concerted practices provision in Australia, and no specific algorithmic pricing enforcement action. For data scientists designing pricing algorithms, the key risk is that algorithm design choices — objective functions, training environments, competitor data inputs — may produce coordination outcomes that engage competition law.

## 3.3 Decisioning

AI systems are increasingly used to make or substantially inform consequential decisions affecting individuals: loan approvals, insurance underwriting, employment screening, welfare eligibility assessments, and credit scoring. This section addresses the two most significant legal frameworks for such systems: anti-discrimination law and the automated decision-making transparency requirements introduced in 2024.

### 3.3.1 Federal anti-discrimination law

Australia's federal anti-discrimination legislation prohibits discrimination on protected grounds in specified areas of public life — including employment, education, and the provision of goods and services. The principal Acts are the _Age Discrimination Act 2004_ (Cth), _Disability Discrimination Act 1992_ (Cth), _Racial Discrimination Act 1975_ (Cth), and _Sex Discrimination Act 1984_ (Cth). Protected attributes include age, disability, race, colour, national or ethnic origin, sex, marital status, pregnancy, gender identity, intersex status, and sexual orientation.

**Direct discrimination** occurs where a person is treated less favourably because of a protected attribute. An AI system that uses race or sex as input features and generates systematically different outcomes for different groups directly discriminates. The fact that the discrimination is algorithmic rather than human does not prevent it from being unlawful.

**Indirect discrimination** — of particular relevance to AI — occurs where a condition, requirement, or practice that appears neutral on its face has a disproportionately adverse effect on persons with a protected attribute, in circumstances where the requirement is not reasonable. A model need not use any protected attributes as features to produce discriminatory outcomes. This arises because many variables are statistically correlated with protected attributes — postcode with race, employment history with disability, credit history with age. A model trained on historical data that reflects past discriminatory patterns may perpetuate and amplify those patterns without anyone intending to discriminate.

For data scientists, compliance with indirect discrimination law requires more than removing protected attributes from the feature set. It requires testing model outputs across protected groups — measuring whether approval rates, error rates, or other outcome metrics differ systematically — and being able to justify any differences by reference to legitimate actuarial, risk, or business factors. The technical field of algorithmic fairness offers metrics including demographic parity, equalised odds, and calibration for this purpose, but no single metric captures all legal requirements in all contexts.

### 3.3.2 Automated decision-making transparency: APP 1.7 and APP 1.8

From 10 December 2026, the _Privacy and Other Legislation Amendment Act 2024_ (Cth) introduces transparency requirements for substantially automated decision-making. APP entities that use computer programs to make or directly support decisions that could significantly affect individuals' rights or interests must disclose this in their privacy policies. APP 1.8 requires the privacy policy to describe: the kinds of personal information used; the kinds of decisions made solely by automated systems; and the kinds of decisions in which automated systems play a substantially assisting role.

These are transparency obligations only. Unlike GDPR Article 22, they do not confer a right to contest an automated decision or demand human review. This gap is widely noted by privacy scholars and is subject to ongoing reform consideration.

### 3.3.3 AI and professional liability: the Dayal and Helmold cases

The use of AI to assist in generating professional advice, research, or submissions has created a new category of professional liability risk: the risk that AI hallucinations — confident, plausible-sounding, but factually false outputs — are passed on to clients or courts without adequate verification.

In _Dayal_ [2024] FedCFamC2F 1166, a Victorian solicitor submitted court documents containing case citations generated by an AI research tool embedded in a practice management system. The cases did not exist. The Federal Circuit and Family Court of Australia referred the matter to the Victorian Legal Services Board. On 19 August 2025, the Board varied the solicitor's practising certificate so that he could no longer practise as a principal lawyer, and required quarterly reporting to the Board.

In _Helmold & Mariya (No 2)_ (2025) FLC 94-272, a court warned that "reliance upon unverified research generated by AI has the capacity to confuse, mislead, and waste judicial time", and that it would be negligent for a barrister to allow AI-generated but unverified authorities to appear in pleadings.

The principle established by these cases is clear: **a professional who uses AI to assist in producing advice, research, or submissions remains personally responsible for verifying the accuracy and reliability of that output.** The use of AI does not reduce the professional's duty of care to their client or to the court — it creates an additional obligation of supervision and verification.

## 3.4 AI-generated content: misleading representations and AI-washing

### 3.4.1 Section 18 ACL: misleading and deceptive conduct

Section 18 of the ACL prohibits conduct in trade or commerce that is misleading or deceptive, or likely to mislead or deceive. This is a strict liability provision: it is breached by the effect of the conduct on a reasonable person, regardless of intent. Maximum civil penalties for corporate breaches were increased from $50 million to **$100 million** per contravention from 28 March 2026, by the _Treasury Laws Amendment (Doubling Penalties for ACCC Enforcement) Act 2026_ (Cth) — calculated as the greater of $100 million, three times the benefit obtained, or 30 per cent of adjusted turnover.

**AI hallucinations and s 18.** When an AI-powered customer-facing system — a chatbot, virtual assistant, or automated advice tool — generates a hallucination (a confident, false output about a real matter) and a consumer relies on that false information to their detriment, the business operating the AI may be liable for misleading or deceptive conduct. The business's lack of knowledge that the AI would hallucinate is not a defence.

**AI-washing.** The ACCC has identified AI-washing — making false or exaggerated representations about an AI system's capabilities — as an enforcement priority for 2025–26. Claiming a system "uses AI" when it uses simpler automation, claiming AI-generated outputs are "unbiased" when the model encodes historical bias, or claiming an AI system has capabilities it lacks, may each constitute misleading representations under s 18. The heightened penalties make this a material financial risk.

## 3.5 Responsible AI: the regulatory framework

As at July 2026, Australia has not enacted dedicated AI legislation. The Government's December 2025 National AI Plan confirmed that Australia will rely on existing technology-neutral legal frameworks, supplemented by voluntary AI ethics guidance and the new **Australian Artificial Intelligence Safety Institute** (AISI). Established to become operational in early 2026, the AISI has advisory rather than regulatory functions — it provides independent technical guidance on AI risks but does not have enforcement powers.

By contrast, the EU's _AI Act_ (Regulation (EU) 2024/1689) — in force since August 2024 — takes a risk-based regulatory approach, imposing specific documentation, transparency and accuracy requirements on high-risk AI systems with significant penalties for non-compliance. Australian organisations with European operations must comply with the EU AI Act for in-scope systems regardless of Australian law.

The Department of Industry, Science and Resources published Australia's AI Ethics Principles — eight voluntary principles including human-centred values, fairness, transparency and explainability, accountability, and privacy protection. These are mandatory for Commonwealth agencies and represent the standard that government and regulated industry increasingly expect from AI deployments.

---

## References

*Age Discrimination Act 2004* (Cth)

*Australian Securities and Investments Commission Act 2001* (Cth)

*Competition and Consumer Act 2010* (Cth) sch 2 (*Australian Consumer Law*)

*Corporations Act 2001* (Cth)

*Disability Discrimination Act 1992* (Cth)

*Privacy Act 1988* (Cth)

*Privacy and Other Legislation Amendment Act 2024* (Cth)

*Racial Discrimination Act 1975* (Cth)

*Sex Discrimination Act 1984* (Cth)

*Treasury Laws Amendment (Doubling Penalties for ACCC Enforcement) Act 2026* (Cth)

*Australian Competition and Consumer Commission v Equifax Australia Information Services Pty Ltd* [2018] FCA 1637

*Australian Securities and Investments Commission v Kobelt* [2019] HCA 18

*Dayal* [2024] FedCFamC2F 1166

*Helmold & Mariya (No 2)* (2025) FLC 94-272

*Westpac Securities Administration Ltd v Australian Securities and Investments Commission* [2021] HCA 3

Regulation (EU) 2024/1689 of the European Parliament and of the Council of 13 June 2024 laying down harmonised rules on artificial intelligence (*Artificial Intelligence Act*) [2024] OJ L 1689 (comparative)

Australia, Department of Industry Science and Resources, *Australia's Artificial Intelligence Ethics Principles* (Web Page, 2019) <https://www.industry.gov.au/publications/australias-artificial-intelligence-ethics-principles> accessed 1 July 2026

Australian Competition and Consumer Commission, 'New Competition Laws a Protection Against Big Data E-Collusion' (Media Release, 2017) <https://www.accc.gov.au/media-release/new-competition-laws-a-protection-against-big-data-e-collusion> accessed 1 July 2026

Victorian Legal Services Board and Commissioner, 'Statement on the "Mr Dayal" Matter' (19 August 2025) <https://lsbc.vic.gov.au/news-updates/news/statement-mr-dayal-matter> accessed 1 July 2026

Gilbert + Tobin, 'New $100 Million Maximum Penalty for Competition and Consumer Law Contraventions' (2026) <https://www.gtlaw.com.au/insights/new-$100-million-maximum-penalty-for-competition-and-consumer-law-contraventions> accessed 1 July 2026
