# Awesome-Brand-Safety-Ad-Placement-Verifiers

# Top Brand Safety & Ad Placement Verifiers Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Contextual Scraping, Pre-Bid Filtering & Real-Time Brand Protection*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Brand Safety & Ad Placement Verifiers**. These tools scrape contextual pages, classify content, and block unsafe placements before ads display—protecting brand equity while optimizing media spend.

**Examples** include Integral Ad Science (IAS), DoubleVerify, Oracle Moat, HUMAN Security, Zefr, CHEQ, Pixalate, Confiant, GumGum, and Adloox (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, real-time bid stream analysis, and open content classification—ideal for publishers, ad ops teams, and developers seeking transparent, vendor-independent brand safety.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Integral Ad Science (IAS)](https://integralads.com/)**  
  Global media measurement and optimization platform. Provides independent, third-party brand safety and suitability measurement for **ChatGPT Ads**—one of the first media quality partners supporting OpenAI's ad platform . Partnership with **Lyft Media** enables Viewability, Invalid Traffic (IVT), and Brand Safety measurement for in-app inventory—the first media quality measurement partner for Lyft . IAS sits at the intersection of AI, media, and marketing, chosen for ability to see every ad interaction and surrounding context . MRC-accredited across desktop, mobile web, app, and CTV .

- **[DoubleVerify](https://doubleverify.com/)**  
  Digital media measurement and analytics platform verifying ad quality, fraud, and brand safety. **Property-level accreditation** across desktop, mobile web, app, and CTV, with **55 domain and app languages** accredited . Different approach to ChatGPT Ads than IAS—launched **attribution measurement** rather than brand safety to help advertisers understand how ChatGPT Ads contribute to the customer journey . Tag-based measurement reaches players through VAST document; in VAST 4.1+, `AdVerifications` holds one `Verification` element per vendor .

- **[Oracle Moat](https://www.oracle.com/)**  
  Ad verification and measurement platform providing viewability, brand safety, and attention metrics. Widely used across display and video advertising.

- **[HUMAN Security](https://www.humansecurity.com/)**  
  Cybersecurity company protecting digital interactions from bots, fraud, and AI agents. **Human Defense Platform** verifies **20 trillion digital interactions weekly** . Provides high-fidelity decision-making defending against sophisticated threats.

- **[Zefr](https://www.zefr.com/)**  
  Brand suitability and contextual targeting for social platforms (YouTube, TikTok, Meta, Snap, Reddit). **Accredited surfaces** attach content-level labels by URL classification; viewability numbers come through Ads Data Hub—no buyer VAST tag needed . **English only** for YouTube content-level labeling .

- **[CHEQ](https://www.cheq.ai/)**  
  Protects digital assets by identifying and preventing invalid traffic, bots, and automated activities. **CHEQ Essentials** provides real-time detection and mitigation of non-human interactions, reducing fraudulent activity and improving data accuracy .

- **[Pixalate](https://www.pixalate.com/)**  
  Advertising fraud protection and compliance monitoring. Features **Media Ratings Terminal**, **Seller Trust Index**, and **Ad Trust & Safety APIs**. Dual commercialization path: self-serve API tiers (Premium Plus at $5,000/month for 50M hits) and sales-led enterprise packages . MRC-accredited for IVT identification and filtering .

- **[Confiant](https://www.confiant.com/)**  
  Protects digital advertising ecosystems by preventing and monitoring malicious ads and unwanted content in real-time. Detects security risks, enforces compliance controls, and analyzes creative quality. Integrates via APIs/SDKs to block ads carrying malware, scams, or disallowed content .

- **[GumGum](https://gumgum.com/)**  
  Contextual intelligence platform with brand safety verification. Uses computer vision and natural language processing to analyze page content and ensure brand-safe placements.

- **[Adloox](https://www.adloox.com/)**  
  Independent ad verification, brand safety, ad fraud detection, and viewability measurement. **DV360 pre-bid segments** priced at $0.05 CPM for Brand Suitability Exclusion, Viewability Optimization, and Fraud & IVT Filtration; $0.03 CPM for Brand Safety IAB Unsafe Categories Exclusion . Acquired by **Peer39 (June 2026)** —packaging may increasingly sit inside Peer39 constructs .

## Open-Source GitHub Projects

- **[AdVerify](https://github.com/Crynge/AdVerify)**  
  Rust programmatic ad fraud detection & brand safety engine achieving **85,000 requests/second** throughput with **0.012ms p50 latency** . Six detection modules with published accuracy: **Click Injection (98.7%)** — missing IFA, DNT/LMT evasion, impossible screen dimensions; **Impression Laundering (96.2%)** — domain/bundle mismatches, inventory misrepresentation; **Bot Traffic (99.1%)** — known bot UAs, headless browsers, geo-language mismatch; **Ad Stacking (94.5%)** — creative larger than viewport, multi-ad overflow; **Brand Safety (95.8%)** — adult, violent, hate speech, drug, gambling, profanity; **Viewability (93.3%)** — IAB standards, dwell time, visible pixel thresholds . CLI for bid stream log analysis, single URL verification, and brand safety scanning. Full pipeline processes 18,000 req/s at 0.056ms p50 . **The most mature open-source ad verification engine available.**

- **[Gravity SDK](https://pypi.org/project/gravity-sdk/)**  
  Python SDK for contextual ad matching via Gravity API (Async, httpx-only). Integrates with FastAPI, Starlette, Django, Flask. Runs in parallel with LLM calls—**zero added latency** . Sends last 2 conversational messages for contextual ad matching; filters non-conversational roles (tool, function, ipython) . Configurable **relevancy threshold (0.0–1.0, default 0.2)** — lower values serve more ads with weaker contextual matches . Returns structured `AdResult` with ads, status, elapsed time, and error handling. Never raises—returns empty ads on failure . **Ideal for conversational AI ad placement.**

- **[VAST Lint](https://vastlint.org/)**  
  Open-source VAST validator checking structural consistency for **VAST 2.0–4.4** including whether `AdVerifications` is present and correctly structured . Critical for verifying that verification vendor tags survive wrapper hops and SSAI stitching. On open-web and CTV, DoubleVerify's tag-based measurement reaches players through VAST document—a dropped `AdVerifications` node leaves creative playing but verification vendor seeing nothing . **Essential infrastructure for self-hosted verification pipelines.**

- **[Prebid.js C2PA Module (Encypher)](https://github.com/prebid/Prebid.js)**  
  Real-Time Data module merged into Prebid.js (April 2026) emitting **C2PA content provenance signals** in every OpenRTB bid request . Publishers sign at CMS/CDN layer; module detects embedded C2PA markers, verifies server-side, and injects result at `site.ext.data.c2pa` . DSPs receive cryptographic content-integrity signal for brand safety decisioning—**doesn't rely on keyword blocklists or URL classification** . Zero-config for publishers: add module to Prebid build. **First C2PA provenance signal natively in programmatic supply chain.**

### Additional Strong Open-Source Options

- **[OpenRTB Parser Libraries](https://github.com/topics/openrtb)** — Community libraries for parsing OpenRTB bid requests and detecting anomalies in programmatic streams.
- **[IAB Open Measurement SDK (OM SDK)](https://github.com/InteractiveAdvertisingBureau/Open-Measurement-SDK)** — Open-source SDK from IAB Tech Lab enabling single integration supporting multiple verification vendors simultaneously. Eliminates SDK bloat by exposing OMID JavaScript API that DoubleVerify, IAS, Moat access without native code . Expanded to CTV (tvOS, AndroidTV) in 2022 .
- Community **n8n** workflows for brand safety alert routing and pre-bid filtering automation.

**Frameworks for building custom systems**: Combine **AdVerify** for high-throughput bid stream fraud detection with **Gravity SDK** for conversational AI ad placement, **VAST Lint** for verification tag integrity validation, **Prebid.js C2PA Module** for content provenance signals, and **PostgreSQL** for persistence—creating a fully self-hosted, enterprise-grade brand safety platform.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Brand safety systems handling ad placement data must comply with data protection regulations and industry standards (MRC, IAB).
- **Property-level vs. content-level measurement are distinct.** MRC guidelines define **Property-Level Ad Verification** (URL keyword classification) and **Content-Level Brand Safety** (images, video, audio analysis) as separate service lines with separate accreditation . The 2012 IAB Ad Verification Guidelines contain **no reference to "safety"** —property-level reporting without content-level measurement is often mislabeled as "Brand Safety" in the marketplace . **Verify which accreditation a vendor actually holds for the specific environment and language you need.**
- **VAST tag survival is not guaranteed.** A wrapper hop or SSAI stitcher that drops the `AdVerifications` node leaves creative playing and firing impression pixels while verification vendor sees nothing . Always validate resolved InLine XML after every wrapper and stitching step.
- **Open-source coverage gaps exist.** AdVerify covers six detection modules at high accuracy but lacks the platform-specific accreditation letters (YouTube, TikTok, Meta, Snap) that commercial vendors publish . Zefr's English-only YouTube content-level labeling illustrates language coverage limits even among commercial vendors .
- Self-hosted open-source solutions require proper security hardening, OpenRTB parsing infrastructure, and ongoing maintenance. Brand safety decisions affect advertiser spend and publisher revenue—validation against MRC-accredited reference data is essential.

---

**Made for ad ops engineers, brand safety analysts, programmatic traders, and developers building transparent ad verification solutions.**  
Let's make Brand Safety & Ad Placement Verification more open, data-driven, and cryptographically verifiable.
