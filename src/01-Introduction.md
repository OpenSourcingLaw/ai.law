
# 1. Introduction: A World Remade by Inference

## 1.1 Objective of this work

This text aims to situate legal responsibilities and liabilities in contexts relatable to data scientists and machine learning engineers, including managers and executives of organisations developing AI. Equally, it is a resource for educators and trainers of data scientists. The need for this text arose where legal expositions of the topic of artificial intelligence (AI) law are typically written by lawyers, for lawyers, structured around areas of law familiar to legal professionals and less accessible to practitioners of AI. By structuring legal considerations around tasks, concepts, and processes relatable to data scientists, this work seeks to enable data science best practice.

The text was originally drafted at a time when AI law was — in the words of legal commentators — still "emerging." That is no longer the case. Between 2024 and 2026, the regulatory and judicial landscape underwent a structural shift: binding legislation entered into force, courts issued their first substantive decisions on AI training data and intellectual property, and new liability frameworks began to assign responsibility for AI-caused harm. The Stanford HAI AI Index 2026 found that 47 countries now have active AI legislation, but only 12 have established enforcement mechanisms — meaning the apparatus of law is being constructed in real time, and data scientists are working inside it whether or not they are aware of it (Maslej et al. 2026). This edition reflects that shift.

The dual audience of this text is deliberate and essential. Lawyers who cannot read a confusion matrix cannot meaningfully advise on the performance risks of a model. Data scientists who cannot read a regulatory impact assessment cannot anticipate the compliance obligations their system will face at deployment. The goal is not to turn lawyers into engineers or engineers into lawyers, but to equip each to ask the right questions of the other.

## 1.2 Defining AI

AI is an endeavour of the computer sciences that seeks to create machines that simulate human intelligence and interactions. First developed as early as the 1970s, and hamstrung for decades by the absence of sufficient data and computing power, machine learning (ML) algorithms endured an "AI winter" until the early 21st century.

ML algorithms are distinctly different from algorithms that came before them. Broadly, an algorithm is any process that can be carried out automatically. Prior to ML, these algorithms were manually specified in deterministic programs known as rule-based systems, where explicit logic converts input variables into output variables. In ML algorithms, input and output variables are together fed into a process theoretically demonstrated to be able to "learn" from data — that is, to improve accuracy across successive predictive rounds without being explicitly reprogrammed. The resulting trained model embeds implicit rather than explicit logic. This incomprehensibility is associated with human cognition and earns ML algorithms a place under the heading of AI. It also creates enduring legal problems: when a decision cannot be explained in terms a human can interrogate, it becomes difficult to challenge, audit, or regulate (Edwards and Veale 2017).

The confluence of digital service provision, the proliferation of audio and visual sensors connected to the internet, affordable data storage, and advances in distributed computing have enabled ML to achieve what had previously been aspirational.

In practice, this use of implication creates new forms of automated decision-making that are driven by inference to:

* _anticipate outcomes that are not yet knowable for sure_, such as prediction of a future event or behaviour; or,
* _detect and subjectively classify something unknown but somehow knowable using inference rather than direct measurement_ — such as detecting a propensity to purchase or a potentially fraudulent transaction.

**Generative AI and large language models.** The period from 2022 onwards has been defined by a further shift: the emergence of *generative AI* (GenAI) systems, most visibly large language models (LLMs) such as the GPT series, Claude, and Gemini. Unlike earlier discriminative models, which classify or predict from a fixed set of options, generative models produce novel outputs — text, images, audio, video, and code — that can be indistinguishable from human-created work. This generative capacity introduces legal questions not raised by earlier ML systems: who owns what is generated? Who is responsible when generated content is false, defamatory, or infringing? Can a professional rely on it? For data scientists, the distinction between discriminative and generative models matters legally as well as technically: a fraud-detection classifier produces a score; a generative model produces prose. The liability exposure for each is different, as is the appropriate standard of care in deployment.

**Agentic AI.** A further development — one that regulators are only beginning to grapple with — is *agentic AI*: systems capable of taking sequences of real-world actions (browsing the web, executing code, sending emails, interacting with external services) in pursuit of a goal, with limited or no human oversight at each step. Agentic systems challenge every existing assumption about accountability in AI. When an agent takes an action that causes legal harm, and that action was not explicitly instructed, the allocation of responsibility between developer, deployer, and user is genuinely uncertain. Multi-step AI agents are already in commercial deployment in legal research, contract drafting, and customer service contexts — and the law has begun to respond.

For the purposes of this text, the definition of AI offered by the European Union Artificial Intelligence Act is instructive: an AI system is "a machine-based system designed to operate with varying levels of autonomy, that may exhibit adaptiveness after deployment, and that, for explicit or implicit objectives, infers, from the input it receives, how to generate outputs such as predictions, content, recommendations, or decisions that can influence physical or virtual environments."[^1] That definition is broad enough to capture rule-based systems, ML models, generative AI, and agents — and so provides a workable anchor for this text.

[^1]: Regulation (EU) 2024/1689 of the European Parliament and of the Council of 13 June 2024 laying down harmonised rules on artificial intelligence (Artificial Intelligence Act) [2024] OJ L 2024/1689, Art 3(1) ('EU AI Act').

## 1.3 The Strategic Landscape: Drivers of Change

To understand where AI law is heading, it helps to see where it has come from, and to distinguish the durable forces of change from the events that merely appear significant at the time. Strategic foresight practice distinguishes between *weak signals* (early, fragmented clues about what is possible), *signals* (current evidence of emerging states), *trends* (patterns of directional change synthesised from signals), and *drivers of change* (the underlying forces that make those trends persistent) (Prakash 2021). It also classifies change by horizon: Horizon 1 covers the immediate mainstream (0–2 years), Horizon 2 covers developments gaining traction (2–5 years), and Horizon 3 covers what is speculative but worth watching (5–10 years) (Curry and Hodgson 2008).

Applied to AI and law in mid-2026, six drivers stand out. Four are now in Horizon 1 — that is, they are already shaping legal obligations — while two remain in Horizon 2.

**Driver 1: Regulatory crystallisation (Horizon 1).** The most consequential shift of 2024–2026 has been the movement from voluntary ethics principles to binding rules with enforcement teeth. The EU AI Act entered into force on 1 August 2024 and became fully applicable on 2 August 2026, imposing compliance obligations — including conformity assessments, transparency requirements, and risk-management systems — on any AI system touching European users. Prohibitions on unacceptable-risk AI practices, including social scoring by public authorities and real-time biometric identification in public spaces (with limited exceptions), entered application in February 2025. General Purpose AI (GPAI) model obligations — including transparency requirements for providers of frontier models — became applicable in August 2025. In May–June 2026, the Council and Parliament agreed a simplification package that extended some high-risk compliance deadlines while expanding prohibitions, most notably banning "nudifier" applications generating non-consensual intimate images from 2 December 2026 (Council of the EU 2026).

Australia has taken a markedly different path. The National AI Plan 2025, published in December 2025, rejected a standalone AI Act in favour of applying and reinforcing existing law — the *Privacy Act 1988* (Cth), the Australian Consumer Law, and the *Online Safety Act 2021* (Cth) — supplemented by a newly funded AI Safety Institute, operational from early 2026 with $29.9 million in funding (Australian Government 2025). The United States remains fragmented: federal comprehensive AI legislation has not emerged, but state-level proliferation is significant. California's AB 316, effective 1 January 2026, precludes defendants from using an AI system's autonomous operation as a defence to liability claims. Colorado's AI Act, effective June 2026, requires deployers of high-risk AI systems to conduct regular impact assessments. The Stanford AI Index 2026 records that compliance costs vary eightfold between jurisdictions — creating real arbitrage incentives for AI developers choosing where to locate operations (Maslej et al. 2026).

*For lawyers:* your clients are operating inside binding legal frameworks that carry civil and criminal penalties. Competent AI advice requires understanding which framework applies, not merely what the principles say.

*For data scientists:* regulatory compliance is no longer someone else's concern. Conformity assessments under the EU AI Act require technical documentation, data governance records, and logging capabilities that must be designed into a system, not retrofitted after deployment.

**Driver 2: Liability attribution for AI-caused harm (Horizon 1).** The central legal question raised by automated decision-making — who is responsible when AI gets it wrong? — is now being answered by courts and legislatures rather than ethics committees. The EU's revised Product Liability Directive, to be implemented by member states by 9 December 2026, explicitly includes AI software as a "product" capable of giving rise to strict liability, and shifts the burden of proof toward producers in cases of technical complexity (European Parliament and Council 2024). California's AB 316 eliminates the autonomy defence for AI agents. Under Australia's existing law, the Australian Consumer Law's prohibition on misleading conduct and the forthcoming *Privacy Act* amendments requiring disclosure of substantially automated decisions (effective December 2026) provide parallel liability avenues.

Courts in the United States have also begun imposing direct sanctions on legal professionals who submit AI-generated work product without adequate verification. In February 2026, a US appeals court ordered a $2,500 sanction against an attorney who filed a brief containing fictitious AI-generated case citations — a figure widely understood to mark the floor of what courts will impose as AI use in legal practice matures (National Law Review 2026). The signal for legal practice is unambiguous: AI outputs require professional verification before submission to any court or regulator.

*For lawyers:* professional responsibility rules are catching up with AI adoption faster than anticipated. Supervision of AI-generated work product is a question of professional conduct, not merely professional preference.

*For data scientists:* the documentation and audit-logging choices made during system design determine whether deployers can defend liability claims. Systems that cannot explain outputs, record their reasoning, or surface confidence levels create exposure that is transferred to the organisations that deploy them.

**Driver 3: The intellectual property reckoning (Horizon 1).** Three landmark US decisions in 2025 began to draw the contours of fair use for AI training data. In *Thomson Reuters Enterprise Centre GmbH v Ross Intelligence Inc*, the District of Delaware found in February 2025 that Ross Intelligence's copying of legal headnotes to train a competing AI research tool was not transformative and therefore not fair use. In *Bartz v Anthropic PBC*, the Northern District of California found in June 2025 that training on lawfully acquired books was fair use, but storing pirated source material was not — a "piracy carveout" that fair use cannot overcome. In *Kadrey v Meta Platforms Inc*, decided two days later in the same court, using copyrighted works as analytical training data — treating them as data rather than reproducing their expressive function — was found highly transformative and therefore fair use (Norton Rose Fulbright 2026). Together, the three decisions suggest that the manner of data acquisition and the degree to which training reproduces the original's market function are both material to whether training is lawful. The litigation is far from settled.

For data scientists, the practical consequence is that the source and licensing status of training data is a legal question, not merely a procurement one. A model trained on scraped internet content faces different liability exposure than one trained on licensed datasets. Data due diligence is now an operational requirement.

**Driver 4: The ecological materialisation of compute (Horizon 2).** AI's energy and environmental footprint is crossing from corporate social responsibility discourse into regulatory relevance. Data centre electricity consumption is projected to approach 1,050 TWh globally by 2026 — placing the sector among the world's largest electricity consumers — driven by a 50% surge in AI-focused demand during 2025 (International Energy Agency 2026). In 2025 alone, the largest technology companies collectively committed upwards of USD 400 billion in capital expenditure on AI infrastructure, with a further 75% increase projected in 2026. The European Commission has committed to a Data Centre Energy Efficiency Package in 2026 aimed at carbon-neutral data centres by 2030. As mandatory environmental disclosure obligations expand, organisations deploying AI at scale will face increasing demands to account for the computational cost of training and inference, not only for the functional performance of the model.

**Driver 5: Access asymmetry as a design imperative (Horizon 2).** AI is simultaneously the most promising tool for democratising access to legal services and a source of new legal risk for those who cannot afford professional guidance. Legal aid organisations are adopting AI at twice the rate of commercial law firms (Legal Services Corporation 2025). The Stanford Justice Innovation Lab has documented the use of AI tools to generate first-instance legal documents for self-represented litigants — a genuinely transformative application in jurisdictions where the gap between legal need and legal services is chronic. But the same tools produce unreliable outputs that the legally sophisticated can detect and the legally naive cannot. Hallucination — the confident generation of factually incorrect content — remains an unresolved technical problem in LLMs, with real consequences when a self-represented party relies on a fabricated citation or an incorrect statement of law. The design choices made by data scientists — about output guardrails, confidence disclosure, and interface design — have direct legal and social consequences for the most vulnerable users of these systems.

**Driver 6: The agentic accountability gap (Horizon 1).** The period since late 2025 has been defined by AI's shift from generating content to executing action. Enterprise adoption of *agentic AI* — systems that plan, act, and revise their own behaviour with limited human prompting — reached 35% within two years of the technology's emergence, a faster climb than the eight years traditional AI took to reach comparable adoption, with a further 44% of organisations planning deployment (Ransbotham et al. 2025). The same MIT Sloan Management Review and Boston Consulting Group survey found that 76% of executives regard agentic AI as "more like a coworker than a tool" — a duality that unsettles the substitute-or-complement logic on which most existing liability and employment frameworks rest, since a single system can now automate a step, advise a human expert, and act autonomously within the same workflow. McKinsey's research finds that only 1% of organisations have restructured into a genuinely decentralised "agentic network," while 89% remain in an industrial operating model in which "governance becomes a bottleneck to productivity" unless deliberately scaled (McKinsey & Company 2025). Separately, McKinsey reports that fewer than 10% of enterprises that have experimented with agents have scaled them to deliver tangible value, with 80% citing data governance and access-control limitations as the primary obstacle (McKinsey & Company 2026).

Bain & Company's 2025 Technology Report reaches a parallel conclusion from the architecture side: as enterprises push agent deployment from single-task automation toward "cross-system agentic workflow orchestration" and "multi-agent constellations," interoperability protocols such as Anthropic's Model Context Protocol and Google's Agent2Agent standardise how agents exchange data — but not who is accountable when they act wrongly, an omission Bain likens to the absence of a shared vocabulary for terms as basic as *invoice* or *work order* (Bain & Company 2025). The consequence, in Bain's assessment, is that "walled gardens will take the lead" and "fit-for-purpose custom builds will dominate enterprise-wide architectures for some time" — meaning the accountability gap is unlikely to close through technical standardisation alone.

The accountability question is not merely technical. Accenture, drawing on joint research with the Wharton School, states plainly that "as intelligence becomes scalable, responsibility does not scale in the same way" (Accenture 2026) — a striking concession, from within the industry advising on deployment, that governance is not keeping pace with capability. Deloitte frames the same gap structurally: as "monitoring agents" emerge to supervise the outputs of other agents, human accountability is formally retained but practically diffused across an increasingly automated supervisory chain (Deloitte 2025). PwC goes further, predicting that 2026 will normalise agents from different model providers checking each other's work as a matter of routine quality assurance — a practice that, however useful operationally, leaves unresolved the legal question of where liability sits when a chain of agents jointly produces an erroneous or harmful outcome (PwC 2026). Microsoft's 2026 Work Trend Index documents the operational reality behind these questions: active agents within the Microsoft 365 ecosystem grew fifteenfold year over year, yet only 19% of AI users work at organisations combining both the individual skill and the organisational readiness to deploy agents safely — a mismatch Microsoft's researchers term the "Transformation Paradox" (Microsoft 2026).

*For lawyers:* liability frameworks organised around the question "was this a human decision or an automated one?" do not map cleanly onto systems that plan, act, and adapt with only intermittent human review. Advising a client on an agentic AI deployment increasingly requires asking not merely whether a human supervised an output, but at which point in a multi-agent chain human judgment was actually exercised, and whether that point was documented.

*For data scientists:* the absence of agreed semantic and interoperability standards for agent-to-agent communication is not simply an engineering inconvenience — it is the reason liability, once it arises, becomes difficult to trace to any single component. Systems that log agent identities, permissions, and decision points from first deployment are the systems best placed to later demonstrate where responsibility lay.

## 1.4 Challenges to Society

The drivers above give texture to the conceptual challenges AI poses to society, three of which are central to this text.

The first is the *communication of uncertainty*. AI systems produce probabilistic outputs — likelihood scores, classifications, predictions — that must be translated into decisions with legal or financial effect. How does a data scientist communicate to a compliance team that a fraud-detection model flags a transaction with 82% confidence? What does that figure mean for the customer who is declined? How do threshold choices — the line between flagging and blocking — become liability decisions that regulators can scrutinise? These questions sit at the intersection of statistical reasoning and legal obligation. Specifically, they bear on how organisations communicate with consumers about the performance or reliability of AI-driven products, and on how data scientists communicate with decision-makers about the choices embedded in threshold-setting.

The second is the *maintenance of interdependent systems at scale*. Modern AI deployments are not single models: they are stacks of data pipelines, compute infrastructure, model components, third-party API integrations, and human oversight processes. When such a system causes harm, the responsible party is rarely obvious — particularly where agentic systems chain automated actions across multiple providers, platforms, and jurisdictions before a human becomes aware that something has gone wrong.

The third is *effective regulatory oversight of opaque complexity*. Regulators generally lack the technical capacity to audit AI systems of this complexity at the speed at which they are deployed. The NIST AI Risk Management Framework has matured substantially through 2025–2026 — expanding to address generative AI, supply chain vulnerabilities, and third-party model assessment — but the gap between framework aspiration and operational enforcement capacity remains wide (NIST 2026). This creates a practical obligation for data scientists: because external verification is difficult, organisations that build AI systems bear a greater share of the responsibility for demonstrating their own compliance.

These three challenges are not speculative; they are independently corroborated by five years of the World Economic Forum's *Global Risks Report*, an annual survey of risk experts, business leaders, and policymakers that ranks global risks over two-year and ten-year horizons. In 2022, before generative AI's public release, no AI-specific or misinformation-specific risk appeared among the top ten in either horizon; disinformation featured only as background context within a cybersecurity discussion, and the report's own assessment of governance maturity flagged artificial intelligence as one of the risk areas with the least "established" oversight of any surveyed (World Economic Forum 2022). By 2024, "misinformation and disinformation" — driven by the collision of generative AI's content-creation capacity with a global election year in which close to three billion people voted — became, in the report's own words, "a new leader of the top 10 rankings," ranked the number one global risk over the two-year horizon; "adverse outcomes of AI technologies" entered the top ten over the ten-year horizon for the first time in the same edition (World Economic Forum 2024). Both risks held their positions in 2025, with misinformation and disinformation remaining first over two years and adverse AI outcomes sixth over ten (World Economic Forum 2025). The 2026 report finds that misinformation and disinformation has eased to second place over the two-year horizon — overtaken by a resurgent geoeconomic confrontation — but has risen to fourth place over ten years, while "adverse outcomes of AI technologies" is now the single fastest-rising risk of the 33 tracked, climbing from thirtieth position over two years to fifth over ten, as the report reframes AI as having "shifted from a frontier technology to a systemic force" (World Economic Forum 2026). Read across five editions, the WEF data traces the same arc as the drivers set out above: from a diffuse, unranked governance concern, through an acute information-integrity crisis coinciding with the 2024 election cycle, to a decade-scale risk now judged structurally embedded in the global economy — a trajectory that supports treating AI law as a subject of strategic foresight rather than a narrow compliance exercise. The same five-year window shows societal polarisation entrenched inside the short-term top five every year since 2023, and "erosion of human rights and/or civic freedoms" entering the top ten for the first time in 2025 — both risks the reports link explicitly to AI-enabled information manipulation and surveillance.

## 1.5 Areas of Focus

The legal concerns that motivate this text can be organised around the development and deployment of AI technologies themselves. Four groupings recur throughout, each addressed in dedicated chapters.

**AI inputs** concern the data used by AI technologies — the subjects of that data (human or otherwise), the sources and methods by which it is gathered, and its format (text, image, video, audio, biometric). The legal questions here centre on privacy, consent, and the conditions under which data about people can lawfully be acquired and used. Training data is the new flashpoint: the US decisions of 2025 established that the origin and acquisition method of training data carry legal consequences that extend through the lifetime of the model.

**AI outputs** concern the outcomes AI technologies produce — profiles of individuals, targeted recommendations, pricing decisions, credit assessments, hiring decisions — and the legal obligations that attach to automated decision-making with financial or legal effect. Explainability requirements are central here: under the EU AI Act, Australia's amended *Privacy Act 1988* (Cth), and national laws across multiple jurisdictions, certain automated decisions must be explainable to the people they affect.

**AI incarnations** concern AI that manifests as a person — a synthetic voice, a deepfake video, a virtual agent — and the legal questions of identity, consent, and deception that arise when the human-artificial boundary is deliberately obscured. The EU AI Act's 2026 expansion of prohibitions to cover non-consensual intimate image generation illustrates how rapidly incarnation-specific regulation is developing.

**AI creators** concern the intellectual property landscape in which data scientists operate: both as creators of AI-generated work and as consumers of data whose ownership is contested. The training data cases of 2025 mark the beginning of a sustained period of IP litigation that will continue to reshape what data can be used, how, and at what cost.

## 1.6 Industries and Sectors of Interest

Industry-specific laws create greater obligations in specified circumstances or allow for exceptions from general rules. A credit risk model deployed by a bank operates within financial services regulation in addition to general consumer protection law. A diagnostic AI used in healthcare is subject to medical device regulation as well as professional standards for clinical practice. A hiring algorithm in Australia may engage both the *Privacy Act 1988* (Cth) and anti-discrimination legislation simultaneously. In each case, the technical choices made by data scientists map onto specific legal obligations that sector-specialist lawyers must understand.

Where applicable, industry-specific scenarios are highlighted throughout this text to guide best practice for data scientists working within regulated sectors. The intent is practical: to help practitioners understand not only what the law requires, but why it does so — and how their technical choices create or dissolve the legal risk that lawyers, compliance officers, and regulators must then navigate.

---

## References

### Legislation

*Privacy Act 1988* (Cth)

*Online Safety Act 2021* (Cth)

Regulation (EU) 2024/1689 of the European Parliament and of the Council of 13 June 2024 laying down harmonised rules on artificial intelligence (Artificial Intelligence Act) [2024] OJ L 2024/1689

AB 316, Cal Stats 2025 (effective 1 January 2026)

### Cases

*Thomson Reuters Enterprise Centre GmbH v Ross Intelligence Inc* (D Del, 11 February 2025)

*Bartz v Anthropic PBC* (ND Cal, 23 June 2025)

*Kadrey v Meta Platforms Inc* (ND Cal, 25 June 2025)

### Journal Articles

Edwards, L and Veale, M, 'Slave to the Algorithm? Why a "Right to an Explanation" is Probably Not the Remedy You Are Looking For' (2017) 16 *Duke Law & Technology Review* 18

### Reports and Other Sources

Accenture, *The Age of Co-Intelligence: How Humans, AI Agents and Robots Are Redefining Value* (Accenture, in partnership with The Wharton School, 26 March 2026) <https://www.accenture.com/us-en/insights/strategy/age-of-co-intelligence> accessed 1 July 2026

Australian Government, *National AI Plan 2025* (Department of Industry, Science and Resources, December 2025) <https://www.industry.gov.au/science-research-and-data/artificial-intelligence> accessed 1 July 2026

Bain & Company, *Technology Report 2025* (Bain & Company, 2025) <https://www.bain.com> accessed 1 July 2026

Council of the EU, 'Artificial Intelligence: Council and Parliament Agree to Simplify and Streamline Rules' (Press Release, 7 May 2026) <https://www.consilium.europa.eu/en/press/press-releases/2026/05/07/artificial-intelligence-council-and-parliament-agree-to-simplify-and-streamline-rules/> accessed 1 July 2026

Curry, A and Hodgson, A, 'Seeing in Multiple Horizons: Connecting Futures to Strategy' (2008) 13(1) *Journal of Futures Studies* 1

Deloitte, *Agentic Enterprise 2028: A Blueprint for Growth* (Deloitte, 2025) <https://www.deloitte.com/us/en/what-we-do/capabilities/applied-artificial-intelligence/articles/agentic-ai-enterprise-2028.html> accessed 1 July 2026

European Parliament and Council, Directive (EU) 2024/2853 of the European Parliament and of the Council on liability for defective products [2024] OJ L 2024/2853

International Energy Agency, *Key Questions on Energy and AI* (IEA, 2026) <https://www.iea.org/reports/key-questions-on-energy-and-ai> accessed 1 July 2026

Legal Services Corporation, *Technology Initiative Grants 2025 Annual Report* (LSC, 2025) <https://www.lsc.gov> accessed 1 July 2026

Maslej, N et al., *Artificial Intelligence Index Report 2026* (Stanford University Human-Centered Artificial Intelligence, April 2026) <https://hai.stanford.edu> accessed 1 July 2026

McKinsey & Company, 'The Agentic Organization: Contours of the Next Paradigm for the AI Era' (McKinsey & Company, 26 September 2025) <https://www.mckinsey.com/capabilities/people-and-organizational-performance/our-insights/the-agentic-organization-contours-of-the-next-paradigm-for-the-ai-era> accessed 1 July 2026

McKinsey & Company, 'Building the Foundations for Agentic AI at Scale' (McKinsey & Company, 2 April 2026) <https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/building-the-foundations-for-agentic-ai-at-scale> accessed 1 July 2026

Microsoft WorkLab, 'Agents, Human Agency, and the Opportunity for Every Organization' (2026 Work Trend Index Annual Report, Microsoft, 5 May 2026) <https://www.microsoft.com/en-us/worklab/work-trend-index/agents-human-agency-and-the-opportunity-for-every-organization> accessed 1 July 2026

National Institute of Standards and Technology, *AI Risk Management Framework: Trustworthy AI in Critical Infrastructure — Concept Note* (NIST, April 2026) <https://www.nist.gov/artificial-intelligence> accessed 1 July 2026

National Law Review, '85 Predictions for AI and the Law in 2026' (*National Law Review*, 2026) <https://natlawreview.com/article/85-predictions-ai-and-law-2026> accessed 1 July 2026

Norton Rose Fulbright, 'AI in Litigation Series: An Update on AI Copyright Cases in 2026' (2026) <https://www.nortonrosefulbright.com/en/knowledge/publications/ce8eaa5f/ai-in-litigation-series-an-update-on-ai-copyright-cases-in-2026> accessed 1 July 2026

Prakash, P, 'How to Scan for Trends' (*Medium*, 2021) <https://pujaprakash.medium.com/how-to-scan-for-trends-197a3f3d4e85> accessed 1 July 2026

PwC, '2026 AI Business Predictions' (PwC US, 2026) <https://www.pwc.com/us/en/tech-effect/ai-analytics/ai-predictions.html> accessed 1 July 2026

Ransbotham, S, Kiron, D, Khodabandeh, S, Iyer, S and Das, A, 'The Emerging Agentic Enterprise: How Leaders Must Navigate a New Age of AI' (MIT Sloan Management Review and Boston Consulting Group, November 2025) <https://doi.org/10.63383/jAXE2583> accessed 1 July 2026

World Economic Forum, *The Global Risks Report 2022* (17th edn, World Economic Forum, 2022) <https://www.weforum.org/publications/global-risks-report-2022/> accessed 1 July 2026

World Economic Forum, *The Global Risks Report 2023* (18th edn, World Economic Forum, 2023) <https://www.weforum.org/publications/global-risks-report-2023/> accessed 1 July 2026

World Economic Forum, *The Global Risks Report 2024* (19th edn, World Economic Forum, 2024) <https://www.weforum.org/publications/global-risks-report-2024/> accessed 1 July 2026

World Economic Forum, *The Global Risks Report 2025* (20th edn, World Economic Forum, 2025) <https://www.weforum.org/publications/global-risks-report-2025/> accessed 1 July 2026

World Economic Forum, *The Global Risks Report 2026* (21st edn, World Economic Forum, 2026) <https://www.weforum.org/publications/global-risks-report-2026/> accessed 1 July 2026
