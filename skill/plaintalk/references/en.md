# English track · surface rules

> Read only when the output is English. **Do not port the Chinese rules onto English** —
> the two languages fail differently.

## The failure list

| # | Pattern | Test | Fix |
|---|---|---|---|
| 1 | **Agentless passive** | "X was performed / it was observed that" with no actor | Name the actor: "We ran X". Passive only when the actor is genuinely unknown or irrelevant |
| 2 | **Noun stacking** | ≥3 nouns in a row before the head ("user session token refresh policy error") | Unpack with a preposition: "error in the policy for refreshing session tokens" |
| 3 | **Nominalisation** | "perform an investigation", "make an adjustment", "provides support for" | Use the verb: investigate, adjust, supports |
| 4 | **Significance inflation** | "stands as a testament to", "marks a pivotal moment", "underscores" | Delete; state the fact |
| 5 | **Notability name-dropping** | "featured in numerous publications", "widely regarded as" | Delete unless a specific source is given. **Exception (R12)**: if the draft itself asserts it ("widely adopted in the literature"), it is the *author's* attribution claim — keep it. Deleting an author's own assertion is a fidelity loss, not a fix. |
| 6 | **Superficial -ing analysis** | ", highlighting…", ", underscoring…", ", reflecting…" tacked onto a sentence | Cut the tail; if it carries information make it its own sentence with a subject |
| 7 | **Rule of three** | "seamless, intuitive, and powerful" | Keep at most one, replace the rest with specifics |
| 8 | **Negative parallelism** | "not just X but Y", "it's not about X, it's about Y" | At most once per passage; plain assertion elsewhere |
| 9 | **False range** | "from the dawn of time to the modern era" | Delete unless both endpoints are actually discussed |
| 10 | **Copula avoidance** | "serves as", "stands as", "represents" instead of "is" | Use "is" |
| 11 | **Hedging stack** | "may possibly suggest that it could" | One hedge, max |
| 12 | **Em dash overuse** | more than 1 per 300–500 words, or two in one paragraph | Comma or separate short sentence |
| 13 | **Title Case headings** | "Overview of the System Architecture" | Sentence case, and make it carry content |
| 14 | **Chatbot residue** | "I hope this helps", "Certainly!", "As an AI…" | Delete |
| 15 | **Cutoff disclaimer** | "as of my last update…" | Delete unless the date is load-bearing |

## Tier-1 vocabulary (delete or replace; each has a concrete alternative)

```
delve, leverage (v.), seamless, robust, holistic, paradigm, testament,
underscore, myriad, plethora, elevate, navigate (fig.), unpack (fig.),
foster, cultivate, harness, unlock, game-changer, cutting-edge,
revolutionize, transformative, pivotal, crucial, vital, realm, landscape,
tapestry, journey (fig.), dive in, deep dive, at the end of the day
```

**Do not swap a tier-1 word for a same-family word.** Deleting "delve" and writing
"explore" is fine; deleting "delve" and writing "plumb the depths" is not —
that is substitution, not repair.

## Format and symbols

| # | Pattern | Test | Fix |
|---|---|---|---|
| 16 | **Colon reveal** | noun phrase + colon + lowercase dramatic reveal ("The best part: it learns") | Rewrite as a plain sentence; colons only for lists, labels, quotes; sentence case after the colon |
| 17 | **Abbreviation without expansion** | acronym used before its full form | Expand at first use, then the short form; if the source gives no expansion, list it (S3), do not invent |
| 18 | **Decorative formatting** | skipped heading levels; whole-paragraph bold; emoji in technical text | No skipped levels; bold for key terms and conclusions only; no emoji in docs and reports |

(Source: 16 no-ai-slop; 17–18 project design, same discipline as S3/R11)

## Register and tier

- Decide the reader tier first: specialist / general / novice. Between specialists,
  domain terms stay (see Preserve); do not dumb down peer text.
- General-audience text: prefer high-frequency words; anchor technical terms at first use (S3).
- Short sentences, but complete grammar: keep articles and "that". Telegraph style is not
  plain English — "Ensure file exists before running" → "Make sure that the file exists
  before you run the command." (Source: SimpleEnglish, ASD-STE100 rule 4.2)
- Connect related sentences with connecting words ("Then", "As a result");
  do not leave the reader to infer the link. (Source: STE100 rule 4.4)
- Modal ladder: requirement = **must**; possibility or permission = **can**;
  "should" as recommendation → delete or state as fact ("X is better because Y");
  inverted conditional ("should a failure occur") → "if a failure occurs".
  (Source: STE100 modal ladder)
- Verbs do the work: "made a decision" → "decided"; "has the ability to" → "can".
  (Source: no-ai-slop)

## What good looks like (positive targets, not just removals)

- Sentences average 15–22 words; vary them on purpose rather than uniformly.
- One idea per sentence. A sentence needing a second read gets split.
- Prefer the specific over the general: name the file, the number, the date, the actor.
- Verbs over noun forms: "we checked" not "a check was performed by us".
- Second person is fine in instructions ("click Save"), awkward in explanations.
- If a claim needs evidence, put the evidence in the next sentence, not three down.

## Preserve (anti-false-positive)

- Domain terms between specialists are shared vocabulary; simplifying them is noise.
- A long sentence that carries one idea with a single subordinate clause is fine.
- Legal/contract wording has effect; do not paraphrase, or mark it as unofficial.
- Specs and machine-read formats: precision beats readability.
