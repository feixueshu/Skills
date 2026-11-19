# Reusable AI Project Delivery Skills

Two English workflow skills distilled from end-to-end delivery of a working tool, customer presentations, and real-UI software demos.

## Download the complete skills

| Skill | Complete source package | Scope |
|---|---|---|
| Customer Presentation Producer | [customer-presentation-producer.zip](customer-presentation-producer.zip) | Requirements and authoritative inputs, clear workflow diagrams, real screenshots, editable slides, template fidelity, speaker notes, customer/presenter editions, timing, and final QA. |
| Customer Demo Producer | [customer-demo-producer.zip](customer-demo-producer.zip) | Real UI capture, sentence-timed captions, synchronized callouts, optional Japanese narration, targeted revisions, pause/resume records, and final-file QA. |

**These are source packages, not executable installers.** Each ZIP contains one correctly named skill folder with `SKILL.md`, English references, reusable briefs, and the applicable helper scripts/tests. Extract the complete folder; do not copy only `SKILL.md` and discard its references. Preserve that folder structure in the skill location configured for your agent. Follow your agent host's current skill-loading instructions. These packages do not auto-install anything.

## Start with an explicit task

Presentation example:

```text
Use $customer-presentation-producer to create a concise Japanese customer guide
for this tool. Use the attached deck as the actual template. Show one overall
workflow, use real screenshots, keep content editable, and produce a clean
customer edition plus a presenter edition with current notes. Do not record
video until I have approved the guide. Identify anything you could not verify.
```

Demo example:

```text
Use $customer-demo-producer to create a silent-caption walkthrough from the
approved guide and real UI footage. Show the actual changes and the target
result, not only a success message. Time captions sentence by sentence. Preserve
approved sections during revisions. Audition a voice before adding full
narration, if narration is requested. Report completed checks and remaining
human review separately.
```

The demo package is self-contained: its portable capture/timing/voice/QA helpers are included. A separate `japanese-demo-recording` installation is not required. The presentation skill and demo skill can be used independently; their handoff is relevant only when both outputs are requested.

## Tool and runtime boundaries

- Use the presentation workflow, UI control tools, and editor currently available and supported by the host. No proprietary slide package, fixed machine path, browser debugging port, old element ID, or particular capture API is assumed.
- Python helpers use the standard library. Media probing/extraction additionally needs an existing FFprobe/FFmpeg. The callback recorder requires a permitted Node environment and an existing FFmpeg; it never selects or operates a browser itself.
- Optional VOICEVOX/Nemo support calls an already authorized local engine. It does not download/start an engine, bundle a model, or require an unrelated cloud account. Review the actual engine/model terms and attribution for the intended use.
- Example Japanese captions demonstrate the supported language profile; English workflow instructions do not mean that the customer's captions must be English.
- Example plans contain illustrative durations, unconfirmed provenance, and missing footage/audio on purpose. Replace them; they are not ready-made production evidence.

## Included checks

Presentation package: `scripts/audit_pptx.py` reads note bodies and selected package metadata without modifying the deck. It does not render, remove secrets, certify native appearance, or establish complete package equivalence.

Demo package: callback encoder, read-along scheduler, demo-plan checker, final-frame extraction, optional local-voice helper, and 26 offline regression tests. See [VALIDATION.md](VALIDATION.md) for the validation actually performed. Run helper `--help` before use; read-along schedules, demo validation plans, and voice plans are different schemas.

## Reuse the method, not the old project

Keep the objective, authoritative source selection, explicit authorization boundaries, evidence gates, targeted-revision rules, and human final review. Supply your own audience, requirements, files, template, brand, workflow, event budget, environment, and approved voice.

No customer recordings, metadata, logs, credentials, wallet files, brand templates, voice-model binaries, system fonts, or machine-specific configuration are included. A skill is not authorization to push, deploy, delete, spend, publish, or change permissions. A successful automated check is not a human acceptance decision.

Packages were prepared on November 19, 2026. Verify package integrity against [SHA256SUMS](SHA256SUMS). No third-party asset license or future service availability is implied.
