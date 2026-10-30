# Refactoring the ROI of Software

**Lessons from the Frontlines of OpenRewrite Adoption**  
DaShaun Carter · 90-minute session

A public presentation about making software modernization a continuous workflow with OpenRewrite, AI-assisted recipes, and N-0 patching.

## View the presentation

Open [docs/index.html](docs/index.html) in a browser. Scripts, styles, fonts, images, and captured results are bundled locally. No build, API keys, or network connection is required to view the slides. External reading links and the separate live demo require their own access.

Use the arrow keys or Space to navigate, Esc for the overview, and F for fullscreen. Slides are grouped vertically by topic; use Down to continue within a topic and Right to move to the next topic.

To serve locally with a JDK that includes `jwebserver`:

```sh
jwebserver -b 127.0.0.1 -p 8123 -d docs
```

Then open <http://localhost:8123/>. To print or save a PDF, open <http://localhost:8123/?print-pdf> in Chrome or Edge and print with landscape orientation and background graphics enabled.

## Topics and session format

The session includes 60 minutes of content and discussion, 15 minutes for breaks, and 15 minutes for Q&A.

| Topic | Minutes |
| --- | ---: |
| Modernization and the CI/CD workflow | 8 |
| Live demo: analyze, upgrade, patch | 18 |
| Why not just use AI? (includes a 3-minute discussion) | 15 |
| N-0 and adoption across repositories | 8 |
| Upgrade evidence and review decisions | 8 |
| Takeaways | 3 |
| Breaks, spread through the session | 15 |
| Q&A | 15 |

The presentation covers reusable, versioned transformations; the cost of inference, review, verification, and rework; AI-assisted recipe creation; and Good, Better, Best approaches to adoption across repositories. N-0 describes the goal of staying on the latest patch of the software you ship.

The AI section adapts themes from [Spring Boot 4.1: Sweet & Sour](https://dashaun.com/spring-boot-4-1-sweet-and-sour/#/), including recipe versioning, verification, and a pilot-to-rollout workflow.

## Live demo

The Analyze → Upgrade → Patch walkthrough uses the separate [public demo repository](https://github.com/dashaun-tanzu/saa-patch-2-6-trivy-exec). Follow that repository's README for setup, tool requirements, and execution. Demo infrastructure is not bundled here. The slides' “Open the running live demo” link expects that app to be running locally at <http://localhost:4173/>.

The slides describe a Spring Boot 2.6 / Java 8 baseline and a configured Boot 4.1 / Java 27 demo target. This differs from the captured Boot 2.7 / Java 8 to Boot 4.x / Java 25 comparison later in the presentation. These versions describe the presented workflows, rather than a claim about the latest available releases.

The demo examines the migration plan, dependency changes, application health, CycloneDX SBOM, and Trivy findings. A health response does not establish behavioral correctness. Scan findings depend on the vulnerability database and scanned components; zero findings does not establish the absence of vulnerabilities. Startup and memory observations are not controlled benchmarks.

## Reading the captured results

The comparison and appendix contain historical upgrade observations verified on October 29, 2026. The tables compare Spring Application Advisor, Codex, and Claude on the same baseline and task. Models, workflow settings, and release channels differ, so the results are not a controlled vendor speed ranking.

Repeated runs compare tracked patches from two runs per tool. Agent repeats were captured on October 29; Advisor repeats were captured on October 25 and 26. These observations do not establish a consistency rate. Upgrade time excludes verification. Token accounting differs by CLI, and zero reported tokens does not mean zero total cost.

The review-cost discussion assumes 400 pull requests at 30 minutes each, totaling 200 review-hours. This is an illustrative workload, not measured savings. Every recipe-generated change still requires testing and review.

Advisor is Spring Application Advisor, a Broadcom product built on OpenRewrite. DaShaun works at Broadcom.

## Static distribution

- `docs/index.html`: slides, presentation styles, and captured results.
- `docs/images/`: presentation artwork.
- `docs/reveal.js/`: bundled presentation runtime and plugins.
- `THIRD_PARTY_NOTICES.md`: third-party license information.

This distribution contains no speaker notes or live-demo infrastructure. The `docs/` directory is the complete static site and can be served by any static host. For GitHub Pages, select the branch containing this distribution and the `/docs` folder. No build step is needed.

## Credits

Presentation runtime: [reveal.js](https://revealjs.com), distributed under the MIT license. See [third-party notices](THIRD_PARTY_NOTICES.md) for the bundled runtime, plugins, and font licenses.

[dashaun.com](https://dashaun.com) · [OpenRewrite](https://github.com/openrewrite)
