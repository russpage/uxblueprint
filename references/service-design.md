# Service design for useful interface work

## Provenance and limits

This is an original application of Scott E. Sampson's *Essentials of Service Design
and Innovation*, fourth edition, supplied by the user as
`ESDI-4E_Chapters_1-6 (1).pdf`. The supplied PDF has 70 pages and ends at printed
page 56. For Arabic printed pages, PDF page = printed page + 14.
References below identify printed pages first, then PDF pages. The source
presents Process Chain Network (PCN) analysis. This file adapts its
concepts to interface work; frontend prescriptions are our extensions.

## Begin with one useful customer task

Identify the user's priority task, the event that starts it, and evidence that it
has succeeded. Include preparation before the UI and necessary work afterward.
Analyze a bounded process segment; subdivide complex journeys. A process with
roughly 10–20 steps is a manageable audit scope, not a required UI step count.
Source: pp. 30–31, 54 / PDF pp. 44–45, 68.

Use the user's judgment for intended success, business ambiguity, and operating
boundaries. Discover mechanical details yourself. Draft the task and assumptions
for correction, then deliver an early useful result appropriate to the request.
Do not turn every small component edit into a research or configuration exercise.

## Map resources, control, and dependencies

Service processes depend on participant resources: effort, information,
belongings, and sometimes the participants themselves. Customers supply inputs
as well as receive outputs. Source: pp. 12–15 / PDF pp. 26–29.
Record who controls each step and who supplies each required resource. Include
operators, partners, and downstream beneficiaries when they affect success.
In B2B work, the immediate customer's customer may matter.
Source: pp. 24–31 / PDF pp. 38–45.

| Step: action + object | Actor/controller | Required input and owner | Prerequisite state | Benefit | Effort/wait | Failure point | Evidence |
|---|---|---|---|---|---|---|---|
| Confirm appointment | Customer; provider validates availability | Selected slot; provider | Slot available; required details accepted | Reserved time | Form completion; response wait | Slot unavailable | Observation or labeled hypothesis |

Adapt this responsibility table to the task. For implementation, add the UI/system
response, handoff recipient, recovery path, and evidence of completion.
An interface transition or submitted request is not proof the next actor completed
their work. Expose pending approvals, external delays, and handoff status.

## Preserve the meaning of PCN

PCN steps use action verbs. Position assigns the actor and region; arrows express
state dependencies, not necessarily transfers of material or information.
A process domain contains steps an entity initiates, leads, or controls.
Source: pp. 18, 21–22, 24 / PDF pp. 32, 35–36, 38.

- Direct interaction: people interact with people across entities.
- Surrogate interaction: an entity acts on another entity's information,
  belongings, or technology without interacting with that person.
- Independent processing: an entity acts on its own controlled resources.

Source: pp. 24–29 / PDF pp. 38–43. Using a provider's website is surrogate
interaction in this framework. A UI/server swimlane diagram or the table above
is an adapted UX map; call it a PCN diagram only if it preserves PCN grammar.

## Separate preparation from realized benefit

Co-production creates value potential through participants' contributions.
Realized benefit occurs when the resulting resource satisfies a need, often
later in the customer's own activities. The source cautions that co-creation
can conflate these moments. Source: pp. 36–37 / PDF pp. 50–51.
In UX work, connected accounts, completed setup, or generated output can be
preparation; do not assume the intended benefit follows. An output can itself
satisfy a need. Define the actionable result or verified improvement that matters.

## Reduce effort while preserving useful control

Assess value for the chosen customer segment. Necessary steps can lack direct
customer value; waiting, uncertainty, confusion, and effort are real costs.
Source: pp. 40–44, 55–56 / PDF pp. 54–58, 69–70.
Remove unnecessary work; explain essential work; simplify, assist, or automate
demanding work. Compare self-service with assistance using required skill,
resources, effort, customization, control, and provider cost. Moving work to
customers can improve provider efficiency while increasing customer burden.
Source: pp. 47–52 / PDF pp. 61–66. Fewer steps alone do not establish better UX.

## Audit with evidence and define recovery

For redesigns, ask customers and operators to describe the process, identify
valued steps, and explain inconvenient, confusing, difficult, or failure-prone
steps. Record branches and waiting; let participants correct the sequence.
Compare perspectives, preserve unresolved differences, label hypotheses, and
repeat the audit after changes. Source: pp. 53–56 / PDF pp. 67–70.
The supplied chapters introduce fail points and error prevention; detailed service
recovery belongs to later chapters not provided. Draft preservation, safe retries,
duplicate prevention, cancellation, rollback, escalation, and recovery copy are
uxblueprint engineering extensions. Specify them when the workflow needs them;
verify recovery behavior rather than claiming the source mandates these mechanisms.
