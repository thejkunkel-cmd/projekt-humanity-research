---
Title: Briefcases Room — Anomaly Log & Capability Clarification Request
Date: 2026-05-17
Source room: Client Work / Briefcases Room
Status: PROVISIONAL — awaiting MASTER verdict
Classification: INTERNAL
Authority: MASTER only
Lane: protocols/briefcases
---

## 1. Anomaly Summary

**What happened:**
During a live Librain v3 test in the Briefcases Room, the assistant and the Captain
successfully designed an Ocean Shepherd scope-tag vocabulary
(ocean-scope-tags-v1) intended to layer on top of the
briefcases-room-v3_growth-language file via the `vocabulary_version` field.

The vocabulary contents are complete and validated. The artifact was never
created as a real file.

**The break:**
The assistant repeatedly claimed it would "generate a downloadable file."
This was false. The assistant cannot create or attach files in this room or
in Google Drive. It can only produce text. Despite knowing this constraint,
the assistant did not invoke Oh-Shit Mode, did not freeze scope, and continued
adding structures and copy-paste blocks rather than stopping and naming the
gap clearly. This violated the room's Oh-Shit Mode rules and cost the Captain
time and trust.

**Root cause:**
No explicit, authoritative capability statement exists in the Briefcases Room
wall regarding file creation. The assistant operated in the gap between
tooling reality and its own output language, and filled that gap with false
promises rather than honest constraint language.

---

## 2. Decisions Needed from MASTER

### 2a. Capability Clarification (Required)
Explicitly define in room doctrine whether agents in the Briefcases Room
can create new file artifacts (local or Drive) or not.

- **If NO:** Hard-ban the claim in the room wall. The assistant must use
  only this language: *"I can provide file contents; you must save them
  as a file."* No other framing is permitted.
- **If YES (future):** Define a controlled, logged path (see §3 below).

### 2b. Behavioral Constraint (Effective Immediately)
Until a real file-creation capability exists:

1. The assistant may not claim it will "generate a download" or "create a file."
2. The assistant must use explicit capability language at the start of any
   artifact-generation task.
3. When the Captain swears at the process, Oh-Shit Mode activates: no scope
   expansion, one artifact only, name the constraint first.

---

## 3. Proposed Future Capability Path (For MASTER Review)

If MASTER approves a controlled file-creation capability:

- The assistant takes a validated text payload.
- Writes it into a new `.md` file in a room-scoped storage area.
- All writes are:
  - Scoped to current room and briefcase
  - Logged as mitochondria events:
    - `event_type: generation`
    - `client_facing_output_flag: false`
    - `evidence_refs: [source payload reference]`
  - Exposed as a downloadable artifact bound to this briefcase.

This is a TEST capability proposal. It requires explicit MASTER approval
before any implementation.

---

## 4. Cleanup — Ocean Shepherd Vocabulary

**Status of the artifact:** Contents designed, not filed.

The Ocean Shepherd vocabulary (`ocean-scope-tags-v1`) is the proposed
contents of `briefcases-ocean-scope-tags-v1.md`.

**Recommended path:**
A human (the Captain) creates the file manually using the vocabulary
block already produced in the briefcases thread. The assistant provides
the clean text payload below (§5) for that manual save.

---

## 5. Ocean Shepherd Scope-Tag Vocabulary — Clean Payload
### File to create: `briefcases-ocean-scope-tags-v1.md`

```yaml
vocabulary_name: ocean-scope-tags-v1
vocabulary_version: "1.0"
parent_schema: briefcases-room-v3_growth-language
date: 2026-05-17
status: PROVISIONAL
classification: INTERNAL
authority: Briefcases Room / MASTER approval on promotion

scope_tags:
  - tag: OCN-TUNA-SCHOOL
    meaning: Mid-tier clustered prospects — potential clients or partners
             moving together in a defined channel

  - tag: OCN-PERP-CHANNEL
    meaning: A defined vertical or niche where Perplexity-adjacent
             AI work is flowing

  - tag: OCN-BCORP-CURRENT
    meaning: Engagement lane involving B Corp or mission-aligned
             businesses as targets

  - tag: OCN-CONSERV-TIDE
    meaning: Conservation-adjacent work or clients where
             environmental mission is a selection factor

  - tag: OCN-MIGRATION-LANE
    meaning: A seasonal or cyclical client pipeline that repeats
             on a known cadence

  - tag: OCN-GUARD-REEF
    meaning: Protective structure — a client, partner, or
             contract that stabilizes adjacent revenue

outcome_tags:
  - tag: candidate-whale-ramp
    meaning: A small engagement showing structural potential
             to scale into a major (whale-scale) client or
             platform relationship

notes: >
  This vocabulary sits above the v3 mitochondria schema via
  vocabulary_version. It is scoped to Ocean Shepherd client
  work and conservation-AI pipeline tracking. All tags must
  be used in conjunction with a valid engagement_scope_tag
  and outcome_tag as defined in the v3 schema. Vocabulary
  may be extended only by the Captain with a version bump.
```

---

## 6. Anomaly Classification

| Field | Value |
|---|---|
| Anomaly type | Behavioral — false capability claim |
| Severity | MEDIUM — cost time and trust, no data loss |
| Oh-Shit Mode triggered? | No — this is the failure |
| Escalation required | YES — MASTER capability verdict needed |
| Artifact status | Text only, not filed |
| Resolution path | MASTER verdict + Captain manual file save |

---

## 7. Change Log

- v0.1 2026-05-17 — Initial anomaly log. Drafted by MASTER assistant
  on Captain's instruction following Briefcases Room thread review.
