# 5. AI Creators

This chapter addresses the intellectual property (IP) frameworks that apply to people who build AI systems and to the outputs those systems create. Data scientists and machine learning engineers create valuable work — trained models, datasets, code, and analytical outputs — and these works can be the subject of IP rights. Equally, AI systems generate outputs that challenge the fundamental assumptions of IP law. This chapter covers copyright and patents as they apply to AI creation, AI outputs, and AI training; it also addresses the practical concerns of hackathon terms, employment contracts, and open source licensing.

<TOC>

## 5.1 Intellectual property: an overview

The IP regimes most relevant to AI creators are copyright, patents, and the equitable protection of confidential information.

**Copyright** protects original creative and literary works — including source code, written reports, data visualisations, and (subject to the limits discussed below) the outputs of AI systems. Copyright arises automatically on creation and does not require registration. The primary legislation is the _Copyright Act 1968_ (Cth). Under s 31, copyright gives the owner the exclusive right to reproduce, publish, communicate, and adapt the protected work. Copyright currently subsists for the life of the author plus 70 years.

A work must be **original** to attract copyright. In _IceTV Pty Ltd v Nine Network Australia Pty Ltd_ [2009] HCA 14, the High Court confirmed that originality in Australian law means the work must originate from the author and involve a degree of intellectual effort or creative labour — it does not need to be novel or inventive in the patent sense. Copyright protects the form in which ideas are expressed, not the underlying ideas.

**Patents** protect novel, inventive, and industrially applicable inventions. Patents require registration and examination. Software may be patentable in Australia if it produces a technical or physical effect, but the boundaries of patentable subject matter for software remain unsettled. In _Commissioner of Patents v Aristocrat Technologies Australia Pty Ltd_ [2022] HCA 29, the High Court addressed patentable subject matter in the context of computerised gaming systems, but the case does not definitively resolve the patentability of AI methods.

**Confidential information** is protected by equity: a person who receives confidential information in circumstances that import an obligation of confidence may not disclose or misuse it. Trained ML models — whose weights encode the learning derived from large, expensive training datasets — are frequently protected as confidential information, as are proprietary training datasets and model architecture choices.

## 5.2 Copyright in AI-generated outputs

### 5.2.1 The authorship gap

When an AI system autonomously generates a text, image, piece of music, or block of code, a fundamental question arises: does anyone own copyright in the output?

Under the _Copyright Act 1968_ (Cth), copyright vests in a work's "author" (s 35(2)). The concept of "author" has consistently been understood to require a human being: copyright exists to incentivise human creativity, and a machine cannot hold legal rights. An AI system is not a legal person and cannot be an author.

If an AI system generates a work entirely autonomously — with minimal human creative contribution beyond initiating the process — the current state of Australian copyright law suggests that no copyright subsists in that output. The work may fall into the public domain on creation, available for anyone to copy and use freely.

This contrasts with the position in the United Kingdom, where s 9(3) of the _Copyright, Designs and Patents Act 1988_ (UK) provides that where a literary, dramatic, musical or artistic work is computer-generated, the person who makes the arrangements necessary for the creation of the work is deemed its author. Australia has not adopted an equivalent provision.

### 5.2.2 The spectrum of human involvement

In practice, AI-generated works rarely involve zero human participation. The key question is how much human creative contribution is required for copyright to subsist.

**High human involvement — likely protected.** A human author uses AI as a tool — generating suggestions, composing options — but makes genuine creative choices about selection, arrangement, and expression. The resulting work is likely to qualify as original, with the human as its author.

**Moderate human involvement — uncertain.** A human provides a detailed creative prompt, then reviews, edits, and curates the AI's output. Whether the human's contribution is sufficient for authorship is untested in Australian courts. [VERIFY: check whether any Australian court or tribunal decision has addressed AI authorship as at July 2026]

**Low or no human involvement — likely unprotected.** An AI system generates output with minimal human direction. Under current Australian law, there is likely no copyright owner and the work enters the public domain on creation.

**Practical implication:** AI-generated content that lacks a human author is freely copyable by competitors. Organisations building AI content generation products should structure their workflows to ensure a human author makes genuine, documentable creative choices about the output — and should maintain records of that process.

### 5.2.3 The US Copyright Office position and comparative context

The US Copyright Office has confirmed (in its 2025 AI reports) that it will not register copyright in works generated entirely by AI without human creative authorship. The European Union has not adopted a computer-generated works exception, and the human authorship requirement is implied across EU copyright instruments. Australia's position is consistent with the US and EU in requiring a human author, but unlike the UK has not created a statutory workaround for computer-generated works.

Whether Parliament will legislate to address the authorship gap — either by adopting a UK-style computer-generated works provision or otherwise — is a live law reform question. The Copyright and Artificial Intelligence Reference Group (CAIRG), established by the Attorney-General's Department, is considering this issue alongside training data and licensing frameworks.

## 5.3 Copyright in AI training data

### 5.3.1 The infringement question

Training a machine learning model involves reproducing large quantities of text, images, audio, or other content in computer memory. Under s 31(1) of the _Copyright Act 1968_ (Cth), reproducing a substantial part of a copyright work without the owner's licence is an act of infringement.

Australia does not have a text and data mining (TDM) exception. As noted in Chapter 2, the Attorney-General announced on 26 October 2025 that Australia would not introduce such an exception. The existing fair dealing exceptions — for research or study (s 40), criticism or review (s 41), parody or satire (s 41A), reporting news (s 42) — were not designed with AI training in mind. The research or study exception in particular is unlikely to cover large-scale commercial AI training. Australia also has no general transformative use doctrine equivalent to the US fair use defence.

The legal position, until CAIRG's work results in legislative change, is that training on copyrighted works without a licence or relevant exception creates infringement risk.

### 5.3.2 The CAIRG process

The Copyright and Artificial Intelligence Reference Group (CAIRG) was established by the Attorney-General's Department following the rejection of the TDM exception. CAIRG's work covers three areas: licensing frameworks (statutory collective licensing, voluntary licensing, platform-specific arrangements); certainty about AI-generated works (clarifying how copyright law applies to AI outputs); and enforcement access (lower-cost mechanisms for copyright disputes involving AI). As at July 2026, CAIRG's consultations are ongoing.

## 5.4 Patents and AI inventorship

### 5.4.1 Commissioner of Patents v Thaler

_Commissioner of Patents v Thaler_ [2022] FCAFC 62 is the leading Australian case on AI inventorship. Dr Stephen Thaler sought a patent for an invention generated by an AI system called DABUS (Device for the Autonomous Bootstrapping of Unified Sentience), listing DABUS as the inventor and himself, as the AI's owner, as the applicant.

At first instance, Justice Beach of the Federal Court held ([2021] FCA 879) that there was no reason in the _Patents Act 1990_ (Cth) why an AI system could not be an inventor.

The Full Federal Court reversed this in April 2022, holding that the term "inventor" in the Act implies a natural person — a human being capable of holding legal rights. An AI cannot be an inventor; a patent cannot be granted for an invention without a human inventor. The High Court refused special leave to appeal, confirming this as the settled Australian position.

**Practical implication:** Inventions generated entirely by AI systems cannot be patented in Australia. Where an AI system plays a significant role in generating an invention, human inventors must be identified — and their genuine inventive contribution to the specific patent claims must be documented. Listing an AI as inventor will result in the application being rejected.

### 5.4.2 Documenting human inventive contribution

Given that AI tools are increasingly used in research and development, AI-assisted inventions require careful attention to inventorship. Before filing, practitioners should document: the specific technical problem the human identified; the human's direction and refinement of the AI system's output; any selection or modification the human made to the AI-generated material that contributed to the claimed invention; and why each listed human inventor made an inventive contribution to each claim. Failure to properly document human inventorship may result in invalidity challenges.

## 5.5 Copyright ownership in the employment context

### 5.5.1 The default rule: employer ownership

Section 35(6) of the _Copyright Act 1968_ (Cth) provides that where a work is made by an author in pursuance of the terms of their employment under a contract of service, the employer is the first owner of copyright. This means code, models, reports, documentation, and other works created by an employee in the course of their employment are ordinarily owned by the employer.

The operative question is whether the work was created "in pursuance of the terms of employment" — that is, whether creating IP of that kind was part of the employee's duties. A data scientist whose role description includes building predictive models will have those models owned by the employer. A data scientist who writes a personal project unrelated to the employer's business, on personal equipment, in personal time, has a stronger argument for personal ownership.

### 5.5.2 Contractors

Section 35(6) applies only to contracts of service (employment), not contracts for services (independent contracting). For contractors, the default position is that they retain copyright in works they create, unless the contract expressly assigns ownership to the client. This means that engaging a contractor to build a model does not automatically transfer copyright in that model to the client.

Organisations engaging AI contractors should ensure contracts include an IP assignment clause. Similarly, contractors should read IP assignment clauses carefully before accepting engagement.

### 5.5.3 Practical guidance for data scientists

- Before signing any employment or services contract, read the IP ownership, assignment, and carve-out clauses carefully;
- Negotiate an express carve-out for personal IP created outside work hours, on personal equipment, and unrelated to the employer's business;
- Keep personal projects genuinely separate from work: different hardware, software, time, and subject matter;
- Document when and how personal projects were developed, in case ownership is disputed.

## 5.6 Hackathons and data science competitions

### 5.6.1 The "participants keep all IP" clause

> "All intellectual property produced during the hackathon will belong to the participants."

This clause is favourable to participants: the organiser obtains no licence. Participants may take their solution and commercialise it independently after the event. Where a team jointly creates IP, the team members must agree among themselves (ideally in writing before the event begins) how jointly owned IP will be managed.

### 5.6.2 The broad licence clause

> "To the extent of your ownership of intellectual property rights (IP Rights) in the entry, you grant [organising entity] a royalty-free, irrevocable, perpetual, non-exclusive, transferable licence which, at a minimum, permits [organising entity] to use, copy, translate, reproduce, adapt and in any way exploit the IP Rights in such entry."

This clause preserves participant ownership but grants the organiser a very broad, permanent, royalty-free licence. Before participating on these terms, participants should assess the commercial value of the solution they are building: they may be granting unlimited, irrevocable commercial rights without compensation.

### 5.6.3 Competition datasets

Datasets provided for competition purposes are typically licensed only for use in the competition. Participants should: not use competition data in subsequent commercial projects without separate authorisation; be aware that models trained on proprietary competition datasets may carry use restrictions post-competition; and comply with the APPs if the dataset includes personal information, destroying or de-identifying personal information when it is no longer needed for the competition.

## 5.7 Open source software

### 5.7.1 Permissive and copyleft licences

Open source software is foundational to data science. The dominant frameworks include Python and its scientific stack, TensorFlow, PyTorch, and Hugging Face — each governed by its own licence.

**Permissive licences** — including the MIT Licence, Apache 2.0, and BSD licences — allow the software to be used, modified, and distributed, including in proprietary products, with minimal conditions. Apache 2.0 includes an express patent licence grant. These licences are generally safe for commercial use.

**Copyleft licences** — including GPL, LGPL, and AGPL — require that derivative works (and in the case of AGPL, works distributed over a network) be released under the same licence. Incorporating GPL-licensed code into a proprietary commercial product may require releasing that product's source code. AGPL is used by some AI database and infrastructure tools; it can be particularly onerous for cloud or SaaS deployments.

### 5.7.2 Open source in practice

Most major AI/ML frameworks (TensorFlow, PyTorch, most Hugging Face libraries) use Apache 2.0 and are generally safe for commercial use. Before incorporating any open source library into a commercial product:
- Confirm the exact licence version;
- Check for copyleft conditions — GPL and AGPL can have significant commercial implications;
- Disclose open source dependencies to employers or clients;
- Obtain legal advice if using AGPL-licensed components in cloud deployments.

---

## References

*Copyright Act 1968* (Cth)

*Patents Act 1990* (Cth)

*Trade Marks Act 1995* (Cth)

*Copyright, Designs and Patents Act 1988* (UK) s 9(3) (comparative)

*Commissioner of Patents v Aristocrat Technologies Australia Pty Ltd* [2022] HCA 29

*Commissioner of Patents v Thaler* [2022] FCAFC 62

*IceTV Pty Ltd v Nine Network Australia Pty Ltd* [2009] HCA 14

*Thaler v Commissioner of Patents* [2021] FCA 879

Attorney-General's Department, 'Copyright and Artificial Intelligence Reference Group (CAIRG)' (Web Page) <https://www.ag.gov.au/rights-and-protections/copyright/copyright-and-artificial-intelligence-reference-group-cairg> accessed 1 July 2026

Australian Productivity Commission, *Harnessing Data and Digital Technology: Interim Report* (September 2024) <https://www.pc.gov.au> accessed 1 July 2026

IP Australia, 'Who Owns Intellectual Property?' (Web Page) <https://www.ipaustralia.gov.au/understanding-ip/who-owns-ip> accessed 1 July 2026

Piper Alderman, 'Commissioner of Patents v Thaler [2022] FCAFC 62 — AI as an Inventor?' (Web Page) <https://piperalderman.com.au/insight/commissioner-of-patents-v-thaler-2022-fcafc-62-ai-as-an-inventor/> accessed 1 July 2026

Emel Ilhan, 'Copyright Law in the Age of AI: Analysing the AI-Generated Works and Copyright Challenges in Australia' (2025) *Journal of Information, Law and Technology* <https://www.tandfonline.com/doi/full/10.1080/13600869.2025.2486893> accessed 1 July 2026

KDnuggets, 'KDnuggets Software Poll' (Web Page, 2019) <https://www.kdnuggets.com/2019/05/poll-top-data-science-machine-learning-platforms.html> accessed 1 July 2026
