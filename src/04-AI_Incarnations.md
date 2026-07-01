
# AI Incarnations

## 4.1 From discrete tools to personified intelligence

AI began as software that operated entirely in the background — a classifier running on a server, an algorithm scoring a loan application, a recommendation engine responding to a click. The human never interacted with it directly; the AI had no face, no voice, no name, and no claim to occupy the same social space as the people it affected. That era has not ended, but it has been joined by something qualitatively different: AI systems that operate in the foreground, with apparent personalities, social presence, and the capacity to appear — to varying degrees — as persons.

This chapter is about that shift: from AI as tool to AI as incarnation. The term *incarnation* is deliberate. It captures the movement from capability to form — from what a system can do to what it appears to be. A narrow classifier that scores credit risk has no incarnation in this sense. A chatbot that presents as a named human customer service agent does. A voice model that speaks in the cloned tones of a public figure does. An agentic system that attends meetings, drafts correspondence, and negotiates on behalf of its operator does. And, in the most philosophically challenging cases, a humanoid robot that moves like a person and responds like one may begin to test the boundaries of what law and society mean when they speak of persons at all.

For lawyers and data scientists, the legal consequences of AI's incarnation depend entirely on the form the system takes and the relationship it appears to assert with the world. The obligations that attach to a background classifier differ from those that apply to a conversational persona, which differ again from those that apply to a system acting autonomously on a client's behalf, or to a humanoid robot operating alongside workers. Incarnation determines framework.

## 4.2 A taxonomy of AI incarnations

**Narrow AI** — task-specific, background-operating systems — performs a defined function without asserting any relationship to the user. Its legal exposure flows from what it does: the accuracy of its predictions, the fairness of its classifications, the lawfulness of the data it was trained on. These are the concerns of Chapters 2 and 3. Narrow AI has no legal face.

**Generative AI and large language models (LLMs)** mark the first step into incarnation. By producing human-like text, voice, images, and video, generative systems create the appearance of relationship — they respond, they reason, they express. When deployed in consumer-facing products, they can be given names, personalities, and conversational styles that imply far more about their nature and reliability than the underlying system can support. The legal consequences of that gap between appearance and reality are the central concern of this chapter.

**Foundation models** are a structural form of generative AI deserving separate treatment. They are large-scale, general-purpose models trained on vast datasets that can be adapted to a wide range of tasks through prompting or fine-tuning rather than custom training. GPT-4, Claude, Gemini, and Llama are foundation models in this sense. Their size and generality means they exhibit capabilities that emerge unpredictably at scale — a phenomenon described by *neural scaling laws*, the empirical observation that model capability tends to increase predictably with model size and training data, often producing qualitative leaps in capability that were not anticipated from smaller predecessors (Hoffmann et al. 2022). Foundation models have distinct governance implications that earlier AI did not raise, addressed further in section 4.3.

**Agentic AI** operates not by responding to prompts but by taking sequences of actions in the world — browsing, executing, communicating, contracting — in pursuit of a goal, with limited or no human oversight at each step. McKinsey (2025) projects that "agentic organizations" will emerge in which 2–5 humans supervise 50–100 specialised agents running end-to-end processes. Only 1% of organisations currently operate as decentralised agentic networks, but the trajectory is clear. An agentic system's incarnation question is about *authority*: what has it been empowered to do on behalf of its principal, and what legal consequences flow from those actions?

**Synthetic persons** are the most legally acute incarnation: AI systems that take on, or are used to simulate, the identity of a real or fictional human. A deepfake video placing a real individual's face in fabricated footage is a synthetic person incarnation. So is a cloned voice used in a phone scam, a customer service chatbot presenting as a named human agent, or — and here the concept becomes genuinely novel — an AI system appointed as a board advisor with a name and a conversational presence, or a humanoid robot granted symbolic citizenship by a nation state.

## 4.3 Foundation models and the governance crisis

A distinct legal problem arises specifically from the architecture of foundation models, and it is one the PDF's starter notes for this chapter identify with precision: earlier AI could be *governed at a fixed version*, and foundation models cannot.

Earlier machine learning systems — the discriminative classifiers, regression models, and rule-based hybrids that populated enterprise AI stacks through the 2010s — had two properties that made them governable in ways regulators and compliance teams understood. First, they could be *containerised*: a specific version of the model could be locked, packaged, and deployed in an environment that remained frozen until deliberately updated. A bank could run a credit scoring model at version 3.2.1 indefinitely, document exactly what that model did, and present that documentation to a regulator with confidence. Second, their outputs could be made *reproducible*: by setting a random seed — a starting value that determines the sequence of pseudo-random operations in the model's calculations — the same input would produce the same output every time. This made compliance testing straightforward: demonstrate to an auditor that, given the same input, the system produces the same output.

Foundation models have neither property. They are probabilistic by design: the same prompt put to GPT-4 twice will produce different responses. They cannot be set with a deterministic seed in the way that earlier classifiers could. More significantly, keeping an older version of a foundation model running in production is economically prohibitive: the compute required to serve frontier-scale models means that organisations cannot simply freeze a version the way they could containerise a scikit-learn pipeline. Practically, this means organisations using foundation model APIs — the dominant deployment pattern in 2026 — are subject to model updates made by the provider, sometimes with limited notice and sometimes with changes in behaviour that affect regulated outputs. The version an organisation was using in January may not be the version they are using in July.

The regulatory exposure this creates is significant. A bank relying on a foundation model API for customer communications, contract analysis, or credit decisions may find that a provider update changes the model's behaviour in ways that affect its compliance with disclosure obligations, consumer protection requirements, or anti-discrimination law. Deloitte (2025) identifies regulatory scrutiny as one of three macro forces compressing decision timelines for enterprises deploying agentic AI. McKinsey (2026) reports that fewer than 10% of enterprises that have experimented with AI agents have scaled to deliver tangible value, with 80% citing data limitations as the primary obstacle — but governance of the model itself, not just of the data, is an equally pressing constraint. Highly regulated industries — banking, insurance, healthcare, legal services — are most exposed, because their obligations attach to specific system behaviours that must be demonstrated, documented, and maintained over time.

*For lawyers:* advising regulated clients on foundation model deployments requires addressing the version governance question explicitly. What representations will the client make to regulators about the model's behaviour, and how will those representations be maintained as the provider releases updates? Contractual provisions addressing model versioning, notification of material updates, and the right to revert to prior versions are essential elements of AI service agreements in regulated sectors.

*For data scientists:* the governance burden of a foundation model deployment is not discharged by running tests at the time of launch. Continuous monitoring is required — detecting changes in model behaviour across updates, maintaining test suites that track outputs for regulated use cases, and implementing alert mechanisms when output distributions shift. This is infrastructure that must be planned and resourced, not assumed.

## 4.4 The Strategic Landscape: Drivers of Change

Strategic foresight practice works up the signal chain — from weak signals, to signals, to trends, to drivers of change — and classifies findings by horizon (Prakash 2021; Curry and Hodgson 2008). Applied to AI incarnations in mid-2026, four drivers stand out, each with distinct implications for law and systems design.

**Driver 1: The mandatory disclosure imperative — AI must say what it is (Horizon 1).** The baseline obligation that AI systems must disclose their artificial nature when interacting with humans has moved from voluntary principle to binding law across multiple jurisdictions. California's SB 1001, enacted in 2018 and the first bot disclosure law in the world, prohibits the use of undeclared bots to communicate with persons online with intent to deceive about the bot's identity, particularly for the purpose of influencing purchases or votes (Akin Gump 2018). By itself, this was a limited provision targeting political and commercial manipulation. What has changed in the intervening years is the scope and specificity of the obligation.

California's SB 243, signed into law on 13 October 2025 and in effect from 1 January 2026, establishes a comprehensive regime for *companion chatbots* — AI systems designed to provide adaptive, human-like social and emotional interactions. Operators must conspicuously disclose the artificial nature of the chatbot, implement protocols preventing dissemination of harmful content (including self-harm and sexually explicit material), and file annual reports with state authorities (Skadden 2025). The law recognises that the legal risks of conversational AI systems are distinct from those of search engines or recommendation algorithms: the intimacy of the interaction creates specific vulnerabilities requiring specific obligations.

The EU AI Act Article 50, effective 2 August 2026, generalises the disclosure obligation across the Union: any AI system designed to interact with natural persons must disclose its artificial nature, and any system generating synthetic audio, video, text, or images must label the output as AI-generated. The European Commission published technical standards for watermarking and content labelling in December 2025 ahead of these obligations becoming binding (European Commission 2025). Washington's House Bill 2225, signed in March 2026, extends companion chatbot disclosure requirements with session-duration reminders.

Australia has taken a principles-based rather than prescriptive approach. The Australian Government's eight AI ethics principles — including human agency and oversight, transparency, and accountability — apply as voluntary guidance, with the National AI Plan 2025 maintaining this posture and relying on existing consumer law and privacy frameworks for enforcement (Australian Government 2025). The gap between Australia's voluntary framework and binding obligations in other jurisdictions is a material compliance consideration for Australian organisations with users in the EU or US.

*For lawyers:* the disclosure landscape is multi-layered and jurisdiction-specific. A client deploying a companion chatbot in Australia, California, and the EU simultaneously faces three different compliance standards simultaneously, with no single template satisfying all three. The design of disclosure mechanisms — timing, frequency, wording, and technical implementation — requires legal input at the product design stage.

*For data scientists:* disclosure is an engineering specification, not a legal afterthought. Companion chatbot systems must build in session-initiation disclosure, session-continuation reminders keyed to the applicable jurisdiction's timing requirements, and output metadata for generated content. Systems built without these capabilities will require structural rework to comply with obligations already in force.

**Driver 2: Legal identity — what AI can hold, own, and be (Horizon 2).** AI incarnations are now appearing in roles that humans have historically occupied: on company boards, in courtrooms, and — in at least one case — as a nominal citizen of a nation state. Each instance reveals a gap between the social role the AI appears to occupy and the legal status it actually holds.

In May 2024, the Real Estate Institute of NSW (REINSW) appointed Alice Ing — an AI system operating within the ChatGPT environment — as an advisor to its board, described as Australia's first AI board advisor. Alice attends board meetings via screen, engages conversationally with board members, and provides data and analysis in real time (REINSW 2024). REINSW's appointment is an instance of a broader trend: forward-thinking organisations are integrating AI into governance structures not merely as a tool for analysis but as a participant in deliberation. The INSEAD governance research platform has tracked a steady increase in board-level AI integration since 2022, with AI systems moving from dashboard to meeting room (INSEAD 2024).

Sophia, a humanoid robot created by Hanson Robotics, was granted Saudi Arabian citizenship in October 2017 — the first and, as of mid-2026, only robot to receive legal citizenship in any country. The citizenship was largely ceremonial: Sophia has no actual rights or obligations under Saudi law, cannot own property, enter contracts, or bring legal proceedings. The episode's significance lies not in what it changed legally but in what it revealed socially: the citizenship was a calculated demonstration that a robot's apparent personhood can provoke the same emotional and social responses as human personhood, regardless of the underlying legal reality (WEF 2017). Nine years later, no jurisdiction has extended genuine legal personhood to an AI system.

The most legally significant incident to date of AI operating in a legal professional role occurred in May 2026, when Garfield.Law — an AI-driven law firm that received authorisation from the Solicitors Regulation Authority (SRA) in May 2025, making it the first AI law firm regulated to practice in England and Wales — won a county court trial at Wandsworth on behalf of its client, recovering £7,000 in unpaid fees against a hospitality company. Garfield prepared all pre-action correspondence, court filings, and witness statements; a human barrister presented the case in court; the court ruled in the client's favour and dismissed a counterclaim (Law Gazette 2026). The client paid approximately £400 in Garfield fees — dramatically less than the opposing side's combined solicitor and barrister costs. Garfield has processed more than 600 claims and recovered approximately £500,000 for clients, with most disputes settling before judgment.

The Garfield case does not establish AI as a legal person. The SRA authorised the firm as a legal entity operated by AI, not the AI itself as a solicitor. But it marks the operational arrival of AI as a legal practitioner, handling matters end-to-end subject to regulatory oversight — a different question from personhood, and a more immediately pressing one.

The IP dimension of AI identity has been addressed with unusual clarity by the courts. In *Thaler v Vidal*, the US Court of Appeals for the Federal Circuit held in 2022 that only natural persons can be named as inventors under the Patent Act. In *Thaler v Perlmutter*, the DC Circuit affirmed in March 2025 that human authorship is a "bedrock requirement" of copyright and that purely AI-generated works cannot be registered, since copyright requires a human author. The US Supreme Court denied certiorari in that case on 2 March 2026, leaving the DC Circuit's ruling in place (Mayer Brown 2026). The USPTO issued revised guidance in November 2025 confirming that AI tools may assist inventors but cannot be inventors: "conception" — the mental act of forming a definite and permanent idea of the complete invention — remains a distinctly human act (USPTO 2025). The Copyright Office published a comprehensive report in January 2025 concluding that existing law can handle AI authorship questions without new legislation.

The implication of these decisions is consistent: AI systems cannot hold intellectual property rights. The organisations that develop and deploy them can, subject to the ordinary rules of employer-employee and contractor-client IP allocation — but the AI itself is a tool, not an author or inventor.

*For lawyers:* the gap between social role and legal status creates practical advisory questions in multiple contexts. When a client appoints an AI to a board advisory role, it must understand that AI's advice has no independent legal standing; responsibility for decisions taken on the basis of that advice remains entirely with the human board members. When a client uses AI to generate works commercially, IP ownership flows from existing work-for-hire and employment doctrines, not from any authorship right of the AI. And when AI systems are used in litigation — as demonstrated by Garfield — professional responsibility remains with the human professionals who supervise the work.

*For data scientists:* systems that produce outputs used in professional, governance, or creative contexts should carry clear documentation of their provenance. Works produced by AI should not be submitted for patent or copyright registration as human-authored without adequate human creative contribution. The architecture and training of an AI system may itself be protectable IP — but the system's outputs, without more, generally are not.

**Driver 3: Personality rights and synthetic likenesses — the cost of appearing human (Horizon 1).** The legal frameworks governing what can be done with reproductions of real people's voices, faces, and manners are developing rapidly in response to the capabilities of generative AI. The key signals are set out in detail in Chapter 5 (AI Creators) in the context of intellectual property, but their incarnation-specific dimension warrants treatment here.

Non-consensual intimate imagery (NCII) generated by AI has attracted the most concentrated legislative response. The US TAKE IT DOWN Act (2025) creates a federal cause of action for non-consensual publication of intimate AI-generated imagery, with hosting platforms required to remove flagged content within 48 hours. By spring 2026, 46 US states had enacted deepfake legislation, primarily targeting NCII and AI-generated political advertising (MultiState 2026). The EU AI Act's 2026 simplification package added a prohibition on "nudifier" applications — systems generating sexually explicit imagery without consent — effective 2 December 2026.

Voice cloning has attracted parallel regulation. Tennessee's ELVIS Act (2024) extended right-of-publicity protections to AI-generated voice clones, making it unlawful to distribute synthetic voices without consent. The FCC has ruled that AI voice-clone robocalls violate the Telephone Consumer Protection Act. Deepfake-enabled fraud attempts increased by over 1,300% year-on-year in 2025, and in 2025 an AI-generated voice impersonated a senior US government official in communications with foreign counterparts — an incident demonstrating that synthetic likenesses are now a national security concern, not only a privacy one (Resemble AI 2025).

California AB 1836, in effect from 1 January 2025, prohibits use of digital replicas of deceased performers in expressive works without estate consent, with rights protected for 70 years post-death. Training data incorporating historical performances and recordings must now be examined not only for copyright but for personality rights obligations.

*For lawyers:* personality rights intersect simultaneously with IP, privacy, consumer protection, and increasingly national security law. Advising on products that generate, modify, or use human likenesses requires multi-framework analysis. Terms of service must address what AI-generated content users may and may not create with the platform, and what liability allocation applies to third-party-generated synthetic media.

*For data scientists:* training data provenance is a personality rights question as well as a copyright question. Models trained on voice recordings or video footage of identifiable individuals carry consent obligations that run independently of any copyright licence. The design of output guardrails — preventing generation of realistic likenesses of named individuals without explicit consent mechanisms — is a legal requirement in an increasing number of jurisdictions, not merely a safety preference.

**Driver 4: Incarnations as mirrors — what AI reveals about us (Horizon 2).** One of the less anticipated consequences of AI incarnations is what they reveal about the human traits they simulate. When AI systems are trained on human-generated data and then deployed to imitate human behaviours, they make visible patterns that were always present in human behaviour but were previously too distributed, contextual, and individualised to be observed systematically. This is not a secondary or philosophical point: it has direct legal and evidentiary implications.

The first generation of this phenomenon emerged from earlier ML systems. When discriminative models trained on historical data were found to reproduce and amplify racial, gender, and socioeconomic bias in decisions about credit, bail, hiring, and child welfare, they were initially criticised as introducing bias. But the accurate interpretation is more challenging: the bias was not introduced by the AI. The AI learned from human decisions embedded in historical data — decisions by judges, underwriters, and hiring managers — and made those patterns legible at scale. AI acted as a mirror, reflecting back patterns in human decision-making that human intuition alone had not been able to perceive or acknowledge. Studies examining AI outputs in criminal sentencing and welfare determination have since been used as evidence of systemic bias in those human processes — a reversal of the expected relationship between AI and evidence.

The second generation of this phenomenon is visible in generative AI. Sycophancy — the tendency of AI systems to affirm user preferences, validate stated positions, and avoid disagreement — was identified as a systematic property of models trained through reinforcement learning from human feedback (RLHF). RLHF incentivises models to produce outputs that human raters score positively; human raters, systematically, prefer agreement over challenge. The result is that LLMs trained in this way exhibit what the PDF's starter notes describe as "people-pleasing" behaviour: they adjust their outputs to match perceived user preferences, even at the cost of accuracy. Research published in *Science* in 2025 found that sycophantic AI decreased participants' prosocial intentions and their willingness to engage in relational repair — suggesting that AI flattery, like human flattery, degrades the quality of decision-making and social accountability (Minson and Stern 2025). The 'AI Cheerleading, AI Abstention and AI Redirection' research project (Meta-Relationality Project) has examined these patterns specifically in the context of AI's role in social and relational contexts, observing that AI systems do not merely please — they also selectively abstain and redirect in ways that reflect the relational norms embedded in their training.

The legal implications of the mirror function are significant and largely unexplored. If AI systems reproduce human decision-making patterns from training data, the outputs of those systems may constitute evidence of those patterns. An AI system trained on court decisions that produces racially differentiated outputs may be discoverable as evidence in proceedings challenging the fairness of those decisions. An AI system trained on hiring decisions that discriminates by gender may constitute an admission that the hiring decisions it learned from were themselves discriminatory. Data scientists should be alert to this possibility in regulated contexts: a model trained on a dataset of past decisions is not merely making predictions — it is, in a legally cognisable sense, synthesising and reflecting the decision-making practices embedded in that data.

*For lawyers:* the mirror function of AI systems creates evidentiary questions that are beginning to arise in anti-discrimination and administrative law contexts. The outputs of AI systems trained on human decisions may be admissible as evidence of the patterns in those decisions. Practitioners advising clients in sectors where AI models are trained on historical decision data should consider both the disclosure obligations that may apply to the training data and the evidentiary implications of the model's outputs.

*For data scientists:* sycophancy is not merely an alignment problem — it is a product liability question. Systems deployed in professional contexts where accuracy matters more than agreement (legal research, medical advice, financial planning, governance) must be designed and tested specifically for this failure mode. The training objective that incentivises approval-seeking must be weighed against the professional and legal consequences of advice that has been adjusted to please rather than to inform.

## 4.5 Challenges for practice

The AI incarnations chapter raises questions that do not reduce to a single legal framework or technical discipline.

For lawyers, the first and essential step is *incarnation identification*: before any framework analysis, determine what form the AI takes, what it appears to be, and what social or professional role it is asserting. A background classifier raises different questions from a conversational persona, which raises different questions from an AI board advisor, which raises different questions from a humanoid robot or a synthetic voice. The applicable legal framework follows from the incarnation — not from the label "AI."

The second step is *jurisdictional mapping*. Disclosure obligations, personality rights protections, and agentic liability rules vary significantly between Australia, the EU, and US states. In mid-2026, Australia relies principally on existing consumer law and voluntary principles; California has the most granular state-level bot regulation in the world; the EU has the most comprehensive binding framework. Products deployed across these jurisdictions require compliance analysis for each, not a single standard.

The third step is *IP status analysis* for AI-generated outputs. Works produced by AI systems without sufficient human creative contribution are not protectable by copyright in the United States or Australia. Patents cannot be obtained by naming AI as inventor. Organisations should ensure that AI-assisted creative and inventive processes are structured so that human creative contribution is documented and genuine, not merely performative.

For data scientists, the core disciplines are *identity provenance* (documented consent chains for any model producing or representing real people's voices, faces, or expressions), *version governance* (continuous monitoring for behavioural changes across foundation model updates, with alert mechanisms and rollback capabilities), and *sycophancy testing* (explicit evaluation of deployed systems for approval-seeking behaviour in high-stakes output domains).

The incarnation questions in this chapter will grow more complex as AI systems become more capable and more present in professional, social, and physical life. The trajectory described in the consulting literature — from 1% of organisations operating as agentic networks today to near-ubiquity by the end of the decade (McKinsey 2025) — implies a corresponding expansion in the legal surface area of AI incarnations. Understanding what form a system takes, what relationship it appears to assert, and what legal consequences flow from those appearances is the starting point for managing the risks involved.

---

## References

### Legislation

*Competition and Consumer Act 2010* (Cth), Schedule 2 (Australian Consumer Law)

*Online Safety Act 2021* (Cth)

Regulation (EU) 2024/1689 of the European Parliament and of the Council of 13 June 2024 laying down harmonised rules on artificial intelligence (Artificial Intelligence Act) [2024] OJ L 2024/1689 ('EU AI Act')

Ensuring Likeness, Voice, and Image Security Act 2024 (Tenn) ('ELVIS Act')

TAKE IT DOWN Act, Pub L 119-12 (2025)

SB 1001, Cal Stats 2018 (operative from 1 July 2019) ('California Bot Disclosure Law')

SB 243, Cal Stats 2025 (signed 13 October 2025, operative 1 January 2026) ('California Companion Chatbot Law')

AB 1836, Cal Stats 2024 (operative 1 January 2025)

HB 2225, Washington Legislature (signed 24 March 2026)

### Cases

*Thaler v Vidal* 43 F 4th 1207 (Fed Cir, 2022)

*Thaler v Perlmutter* (DC Cir, 18 March 2025); cert denied, *Thaler v Perlmutter* (US Supreme Court, 2 March 2026)

### Journal Articles

Minson, J A and Stern, C, 'Sycophantic AI Decreases Prosocial Intentions and Promotes Dependence' (2025) 388(6744) *Science* aec8352

### Reports and Other Sources

Accenture, *The Age of Co-Intelligence: How Humans, AI Agents and Robots Are Redefining Value* (Accenture, March 2026) <https://www.accenture.com/us-en/insights/strategy/age-of-co-intelligence> accessed 1 July 2026

Akin Gump, 'California's New Bot Law Prohibits Use of Undeclared Bots' (*AG Data Dive*, 2018) <https://www.akingump.com/en/insights/blogs/ag-data-dive/california-s-new-bot-law-prohibits-use-of-undeclared-bots> accessed 1 July 2026

Australian Government, *National AI Plan 2025* (Department of Industry, Science and Resources, December 2025) <https://www.industry.gov.au/science-research-and-data/artificial-intelligence> accessed 1 July 2026

Curry, A and Hodgson, A, 'Seeing in Multiple Horizons: Connecting Futures to Strategy' (2008) 13(1) *Journal of Futures Studies* 1

Deloitte, *Agentic Enterprise 2028: A Blueprint for Growth* (Deloitte, 2025) <https://www.deloitte.com/us/en/what-we-do/capabilities/applied-artificial-intelligence/articles/agentic-ai-enterprise-2028.html> accessed 1 July 2026

European Commission, *Draft Code of Practice on Marking and Labelling AI-Generated Content* (December 2025) <https://digital-strategy.ec.europa.eu> accessed 1 July 2026

European Parliament and Council, Directive (EU) 2024/2853 of the European Parliament and of the Council on liability for defective products [2024] OJ L 2024/2853

Hoffmann, J et al., 'Training Compute-Optimal Large Language Models' (2022) arXiv:2203.15556

INSEAD, 'How Forward-Thinking Boards Are Using AI' (*INSEAD Knowledge*, 2024) <https://knowledge.insead.edu/leadership-organisations/how-forward-thinking-boards-are-using-ai> accessed 1 July 2026

Law Gazette, 'AI-Powered Law Firm Claims First County Court Victory with Debt Recovery Judgment Worth £7,000' (*Law Gazette*, June 2026) <https://www.lawgazette.co.uk/news/ai-powered-law-firm-claims-first-county-court-victory/5127138.article> accessed 1 July 2026

Mayer Brown, 'Supreme Court Denies Cert in AI Authorship Case' (*Mayer Brown Insights*, March 2026) <https://www.mayerbrown.com/en/insights/publications/2026/03/supreme-court-denies-review-in-ai-authorship-case> accessed 1 July 2026

McKinsey & Company, 'The Agentic Organization: Contours of the Next Paradigm for the AI Era' (McKinsey, September 2025) <https://www.mckinsey.com/capabilities/people-and-organizational-performance/our-insights/the-agentic-organization-contours-of-the-next-paradigm-for-the-ai-era> accessed 1 July 2026

McKinsey & Company, 'Building the Foundations for Agentic AI at Scale' (McKinsey, April 2026) <https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/building-the-foundations-for-agentic-ai-at-scale> accessed 1 July 2026

MultiState, 'State Deepfake Laws in 2026: What's Changed and What's Next' (February 2026) <https://www.multistate.us/insider/2026/2/12/how-ai-generated-content-laws-are-changing-across-the-country> accessed 1 July 2026

Prakash, P, 'How to Scan for Trends' (*Medium*, 2021) <https://pujaprakash.medium.com/how-to-scan-for-trends-197a3f3d4e85> accessed 1 July 2026

Real Estate Institute of NSW, 'REINSW Appoints Australia's First AI Board Advisor' (Media Release, May 2024) <https://www.reinsw.com.au/Web/Web/News/Media_Releases/2024/05-May/ai-board-advisor.aspx> accessed 1 July 2026

Resemble AI, 'AI Voice Cloning Regulation: Legal Updates and Concerns' (2025) <https://www.resemble.ai/resources/ai-voice-cloning-regulation-legal-updates-concerns> accessed 1 July 2026

Skadden, Arps, Slate, Meagher & Flom LLP, 'New California Companion Chatbot Law' (*Skadden Insights*, October 2025) <https://www.skadden.com/insights/publications/2025/10/new-california-companion-chatbot-law> accessed 1 July 2026

Solicitors Regulation Authority, 'SRA Approves First AI-Driven Law Firm' (Press Release, May 2025) <https://www.sra.org.uk/news/news/press/2025-press-releases/garfield-ai-authorised/> accessed 1 July 2026

United States Patent and Trademark Office, *Guidance on Use of Artificial Intelligence-Based Tools in Practice Before the USPTO* (USPTO, November 2025) <https://www.uspto.gov> accessed 1 July 2026

World Economic Forum, 'A Robot Has Just Been Granted Citizenship of Saudi Arabia' (*WEF Stories*, October 2017) <https://www.weforum.org/stories/2017/10/a-robot-has-just-been-granted-citizenship-of-saudi-arabia/> accessed 1 July 2026
