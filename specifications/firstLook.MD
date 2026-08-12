specifications/firstLook.MD

Absolutely. If we're going to build this, I'd aim for something much more ambitious than another co-parenting calendar: a genuinely UK-first, open-source, parent-owned family coordination system.

Cafcass is already pushing the idea of a child-centred “Our Child's Plan”, covering living arrangements, education, healthcare, communication and responsibilities. 
C
Cafcass
+1
 So we can use that philosophy as a foundation, while making the software much more powerful and privacy-preserving.

🇬🇧 Project concept: a parent-owned UK parenting platform

Core principle:

The parents own the data. The child comes first. The software never takes sides.

And importantly, open source means the code can be independently inspected rather than asking parents to blindly trust a company with extremely sensitive family information.

1. Family / children

Each family can have:

Multiple children
Child profile
Date of birth
School/nursery
GP/dentist information
Allergies and important medical information
Emergency contacts
Important people in the child's life
Child's preferences
Important dates
Documents

But we'd deliberately separate child information from adult conflict.

2. Parenting plan

A proper digital version of the things parents actually need to agree:

Living arrangements

Where the child stays
Overnight arrangements
Weekday/weekend patterns
School holidays
Christmas
Birthdays
Bank holidays
Special occasions

Responsibilities

School runs
Clubs
Medical appointments
Homework
Uniform
Equipment
Medication
Childcare

Communication

How parents communicate
Expected response times
Emergency contact procedure
Handover arrangements

This lines up very closely with Cafcass' approach to predictable routines and clear arrangements. 
C
Cafcass

3. Shared calendar

Not just a calendar — a parenting timeline.

Colour-coded:

🟦 Parent A
🟩 Parent B
🟨 School
🟪 Medical
🟥 Important
⚪ Child's own activities

And automatically calculate:

Number of nights with each parent
Percentage of overnight care
Holiday allocation
Missed/changed arrangements
Upcoming handovers

Crucially: the app shouldn't turn this into a competition.

It should say:

“Alex has spent 7 nights with Dad and 6 with Mum.”

rather than:

“Dad has 53.8% custody.”

4. Handover system

This could be one of the killer features.

Each handover can have a simple status:

Leaving Mum's

🟢 Child ready
🟢 Medication packed
🟢 School equipment packed
🟢 Clothing packed

Arriving Dad's

🟢 Arrived
🕐 Running late
🔴 Unable to attend

No arguments. No essays.

Just an objective record.

5. Communication system

I'd avoid building a normal WhatsApp-style chat.

Instead:

Child-related messages only.

Categories:

School
Health
Handover
Activities
Money
Holidays
Emergency
Other

And potentially:

“Rewrite this message neutrally?”

The AI could flag:

⚠️ This message appears emotionally charged. Would you like to make it more child-focused?

But never automatically send anything.

Cafcass itself notes that texts/messages can easily be misinterpreted and recommends keeping communication focused on the child. 
C
Cafcass

6. Evidence / audit trail

This needs careful design.

Every important event could have an immutable-ish history:

12 Aug 2026 — Holiday arrangement proposed
12 Aug 2026 — Parent B responded
13 Aug 2026 — Agreement reached

But the app should never claim that its records are automatically “court evidence.”

Instead:

Export family record

→ PDF
→ CSV
→ JSON
→ ZIP containing original documents

With cryptographic hashes/timestamps so the exported material can demonstrate that the app hasn't silently altered historical records.

That could be extremely useful where parents eventually become involved with the family court—but we'd need to be very careful about legal claims.

7. Money

A proper child-expenses ledger.

For example:

School shoes — £48
Paid by Dad
Split 50/50
Mum owes £24

Or:

Football club — £30/month
Dad pays recurring payment

With receipts attached.

And importantly:

No “debt score”.

It's about transparency, not ammunition.

8. Child's voice ❤️

This is where I'd make it different.

An optional child space appropriate to age.

For example:

“What would make this week easier for you?”

“Anything you want Mum and Dad to know?”

“What are you looking forward to?”

Parents don't automatically get unrestricted access to the child's private thoughts.

There would need to be carefully designed age-appropriate privacy and safeguarding rules.

This fits strongly with Cafcass' emphasis on hearing children's wishes and feelings. 
C
Cafcass

🔐 9. Privacy should be the product

I'd make this one of the biggest differentiators.

Parent-owned architecture

Ideally:

No advertising.
No selling family data.
No behavioural profiling.
No data mining.

And potentially:

Self-hosting

A technically capable parent could run the entire system themselves.

Something like:

Parent's phone
      ↓
Encrypted connection
      ↓
Parent-owned server
      ↓
Encrypted database


Or use a hosted provider if they don't want to manage a server.

That gives us:

Open source + self-hostable + hosted option.

🛡️ 10. Safeguarding mode

This is absolutely essential.

Not every family is a friendly co-parenting situation.

Cafcass explicitly considers domestic abuse, harmful parental conflict and other risks when assessing children's circumstances. 
C
Cafcass

So the app needs a high-conflict/safeguarding mode.

Features could include:

Restricted communication
No location sharing
No automatic address disclosure
Controlled information visibility
Third-party/professional access
Emergency contact arrangements
One-way information sharing where appropriate
Separate accounts and permissions

And never assume both parents are safe to communicate directly.

🧠 11. AI — but with strict boundaries

AI could be extremely useful, but this is sensitive family data.

I'd use AI for:

Good

Summarising a week's events
Turning notes into a neutral message
Finding calendar conflicts
Extracting dates from school letters
Summarising medical/education documents
Translating messages
Helping create parenting-plan proposals

Never

Decide which parent is right
Diagnose a child
Decide custody
Judge parental fitness
Automatically contact social services
Automatically contact the other parent
Secretly analyse someone's behaviour

The AI should essentially be:

“A neutral administrative assistant for the family.”

Not:

“An AI judge.”

🇬🇧 UK-specific from day one

I'd build around UK terminology and services rather than simply taking an American parenting app and changing the currency.

For example:

Cafcass
Family Court
Child Arrangements Orders
Specific Issue Orders
Prohibited Steps Orders
Parental Responsibility
NHS
GP
School/nursery
SEN/SEND
EHCP
UK school holidays
UK bank holidays
UK date/time formats
UK GDPR/data protection
England/Wales initially, with Scotland/Northern Ireland differences explicitly handled

Cafcass distinguishes child-arrangements orders, specific-issue orders and prohibited-steps orders, so the app should understand those concepts without pretending to provide legal advice. 
C
Cafcass

🏗️ And I'd make the whole thing genuinely open source

Something like:

Frontend

React / Next.js
PWA
Eventually native mobile apps

Backend

TypeScript
PostgreSQL
REST/GraphQL API

Authentication

Passkeys
2FA
Recovery mechanisms

Encryption

Encryption in transit
Encryption at rest
Potential end-to-end encryption for sensitive communications

Infrastructure

Docker
Docker Compose
Self-hostable
Automated backups

License
Potentially AGPLv3 so hosted modifications remain open source, though we'd want to discuss the licence carefully.

The really important bit

I'd define the project's philosophy before writing code:

The 10 commandments
The child comes first.
Parents own their data.
The software never takes sides.
Privacy by default.
No advertising.
No selling family data.
No dark patterns.
AI assists; humans decide.
Safeguarding overrides convenience.
Everything important can be exported.

That could genuinely become a serious open-source UK family infrastructure project, rather than just another parenting app.

If you want, we can take this next step and turn it into a proper technical specification — database schema, user roles, permissions, screens, security model, API, MVP scope and a GitHub-ready project structure.

C
Sources
