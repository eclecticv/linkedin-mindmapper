# Adaptive Interview Guide

## Design Principles

1. **Choice-based only**: Every question presents options via AskUserQuestion. Never ask open-ended questions expecting long written answers.
2. **Show progress**: Display a progress bar at the start of each round.
3. **Adaptive**: Use research findings to personalize question options. Skip irrelevant rounds. Go deeper on strong responses.
4. **Gate early**: Round 1 determines which later rounds to include or skip.
5. **One question at a time**: Present one question per AskUserQuestion call. Ask 2-3 questions per round.

## Progress Display Format

At the start of each round, display:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  ROUND X of Y │ [Topic Name]
  ▓▓▓▓▓▓░░░░░░░░░░░░░░
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Use ▓ for completed rounds, ░ for remaining. After Round 1, calculate total active rounds (excluding gated-out rounds) and use that as Y.

---

## Round 1: Company Context

**Purpose**: Establish founder profile and set gates for later rounds. Always ask.

**Question 1.1** — "What best describes your company stage?"
- Pre-revenue — still building
- Early revenue (under $1M ARR)
- Growth ($1M-$10M ARR)
- Scale ($10M+ ARR)

**Question 1.2** — "How big is your team?"
- Just me (solo founder)
- 2-5 people
- 6-20 people
- 20+ people

**Question 1.3** — "How are you funded?"
- Bootstrapped / revenue-funded
- Friends & family / angel
- Seed round
- Series A or later

### Gates Set by Round 1

| Condition | Unlocked | Skipped |
|-----------|----------|---------|
| Solo founder | All solo-relevant content | Round 9 (Team & Culture), all hiring themes |
| Pre-revenue | Vision, building journey themes | Round 8 (GTM), metrics/pricing/churn themes |
| Bootstrapped | Bootstrap philosophy themes | Fundraising rejection stories |
| Team of 6+ | Full team/culture content | — |
| Growth/Scale stage | Full metrics, GTM, leadership | — |

After this round, calculate total active rounds and adjust the progress display.

---

## Round 2: Your Story

**Purpose**: Extract the founding narrative and personal journey. Always ask.

Personalize options using research findings. Reference specific companies, roles, or transitions discovered.

**Question 2.1** — "How would you describe your path to founding [company]?"
- Career insider — saw the problem from inside the industry
- Career pivoter — came from a completely different world
- Repeat founder — done this before
- Accidental founder — didn't plan to start a company
- Technical founder going business-side

**Question 2.2** — "Was there a specific moment that made you start?"
- Yes — a clear aha moment or breaking point
- Gradual realization over time
- Someone else convinced me
- Saw a gap in the market and went for it

**Question 2.3** — If research found a prior company/role, ask: "How much did your time at [prior company/role] shape [company]?"
- Massively — directly inspired what I'm building
- Taught me what NOT to do
- Gave me the network and credibility
- Minimal connection honestly

If no prior company found, skip 2.3.

---

## Round 3: Beliefs & Values

**Purpose**: Surface core convictions — these drive the strongest content. Always ask.

**Question 3.1** — "What do you believe about [their industry] that most people in the space would disagree with?"
- Present 3-4 options based on common debates in their industry (informed by research)
- Plus: "I have a different contrarian take" (ask briefly what it is)

**Question 3.2** — "What hill would you die on about building a company?"
- Speed over perfection
- Quality over speed
- Transparency at all costs
- Opinionated product beats flexible product
- Culture is more important than strategy
- Distribution beats product
- Something else (ask briefly)

**Question 3.3** — "Are you comfortable publicly disagreeing with popular ideas in your space?"
- Yes — I enjoy respectful debate
- Sometimes, depends on the topic
- I prefer to share my view without calling others out
- Not really my style

---

## Round 4: Industry POVs

**Purpose**: Mine contrarian and informed takes. Always ask.

**Question 4.1** — "What's most broken about [their industry] right now?"
- Present 3-4 options based on research into their space
- Plus: "Something else entirely"

**Question 4.2** — "Is there a popular trend in your space that you think is overhyped?"
- [Research-informed trend 1]
- [Research-informed trend 2]
- [Research-informed trend 3]
- Nothing comes to mind
- Actually, there's an UNDERHYPED trend (ask what)

**Question 4.3** — "How do you feel about AI in [their industry]?"
- Transformative — we're leaning in hard
- Useful for specific things but overhyped overall
- Going to disrupt everything and most people aren't ready
- I have a nuanced take different from the mainstream

---

## Round 5: Lessons & Mistakes

**Purpose**: Extract hard-won wisdom — most authentic content material. Always ask.

**Question 5.1** — "What was your most expensive lesson as a founder?"
- A hiring or people mistake
- A product decision that wasted months
- A go-to-market strategy that flopped
- A partnership or deal that went wrong
- Spending too long building before validating
- A technical decision that created massive debt

**Question 5.2** — "If you could go back to day 1, what's the FIRST thing you'd change?"
- How I hired / who I hired first
- What I built first
- How I priced the product
- Who I sold to first
- How I raised money (or didn't)
- My own time management and priorities

**Question 5.3** — "Is there a lesson from BEFORE founding that keeps proving relevant?"
- Yes — from my previous career/industry
- Yes — from a personal experience or hobby
- Yes — from a book or mentor
- Not really — most of my lessons are from founding

---

## Round 6: Mental Models & Decision-Making

**Purpose**: Surface frameworks and thinking tools unique to this founder. Always ask.

**Question 6.1** — "How do you make hard decisions?"
- Data first, always
- Gut feeling informed by experience
- First principles — reason from the ground up
- Consult my network/advisors
- Sleep on it — subconscious does the work
- I have a specific framework (ask briefly)

**Question 6.2** — "Do you have a personal operating principle — a rule you always follow?"
- Yes — something like "always X" or "never Y" (ask what)
- I have a few — depends on the domain
- Not explicitly, but I have strong intuitions
- I'm more reactive than principled

**Question 6.3** — "How do you think about risk?"
- Calculated risk-taker — quantify everything
- Bias toward action — default yes, course-correct later
- Conservative — de-risk obsessively before committing
- Depends entirely on what's at stake

---

## Round 7: Product & Customers

**Purpose**: Extract product thinking and customer insights. Always ask.

**Question 7.1** — "What's your product philosophy?"
- Opinionated — we decide what's best for users
- Customer-driven — build what they ask for
- Vision-led — building for a future most can't see yet
- Simple above all — ruthlessly cut features
- Platform play — building an ecosystem

**Question 7.2** — "Most surprising thing you've learned from customers?"
- They use the product in unexpected ways
- The real pain point wasn't what we thought
- They care about something we thought was trivial
- Price sensitivity was different than expected
- Haven't been surprised — we understood the problem well

**Question 7.3** (gate: has customers) — "Do you have a customer story that would resonate with others?"
- Yes — a dramatic transformation story
- Yes — a "small feature, huge impact" story
- Yes — a "they almost churned but..." story
- Not one I can share publicly
- Too early for this

---

## Round 8: Go-to-Market

**Gate**: Skip entirely if pre-revenue.

**Purpose**: Extract GTM wisdom and growth learnings.

**Question 8.1** — "What's your primary growth channel?"
- Content and inbound
- Outbound (cold email, LinkedIn, calls)
- Product-led growth (freemium, viral)
- Community and word-of-mouth
- Partnerships and integrations
- Still figuring this out

**Question 8.2** — "What GTM approach totally failed for you?"
- Paid advertising
- Hiring salespeople too early
- Building features hoping they'd drive growth
- A specific channel that didn't fit our audience
- Partnership/channel strategy
- Haven't had a major GTM failure yet

**Question 8.3** — "Strong opinion on bootstrap vs. VC?"
- Strong bootstrap advocate
- VC is right in certain situations
- I've changed my mind on this over time
- Depends entirely on the business
- Don't think about this much

---

## Round 9: Team & Culture

**Gate**: Skip entirely if solo founder.

**Purpose**: Extract leadership and culture insights.

**Question 9.1** — "What's your hiring philosophy?"
- Hire slow, fire fast
- Culture and values over skills
- Skills and output over culture fit
- Look for specific traits (ask which)
- Unconventional approach (ask what)

**Question 9.2** — "Something unusual about how your company operates?"
- Async-first / minimal meetings
- Radical transparency (open salaries, metrics)
- Unusual work schedule or structure
- We optimize for one specific value above all
- We're pretty standard honestly

**Question 9.3** — "Tough people decision you'd share lessons from?"
- Yes — the lesson is worth sharing publicly
- Yes — but only in general terms
- Not yet
- Rather not discuss publicly

---

## Round 10: Content Preferences & Comfort Zone

**Purpose**: Calibrate output to match voice and boundaries. Always ask.

**Question 10.1** — "Which content style feels most natural for you?"
- Teaching and educating — breaking things down
- Storytelling — I think in narratives
- Hot takes — I have opinions and I'm not shy
- Behind-the-scenes — showing the real work
- Data and analysis — I'm a numbers person
- A mix of several

**Question 10.2** — "What topics are completely OFF limits for public posting?"
- Specific revenue/financial numbers
- Personal life and family
- Competitor opinions
- Failures and mistakes
- Employee/team issues
- Nothing is off limits — open book
(Allow multiple selections if the tool supports it; otherwise ask "Any others?" after first pick)

**Question 10.3** — "What's your main goal with LinkedIn content?"
- Build personal brand / thought leadership
- Drive leads and pipeline
- Recruit talent
- Build community in my space
- Document the journey
- Multiple of these (ask which are priority)

---

## Post-Interview Synthesis

After completing all active rounds:

1. **Compile the founder profile**: Merge research + all interview responses into a clear picture of who this founder is, what makes them unique, and what content only THEY could create.

2. **Rank pillars by richness**: Prioritize pillars where the founder showed:
   - Strong opinions or emotional responses
   - Specific stories or examples
   - Unique perspectives not widely shared
   - Comfort and enthusiasm

3. **Build skip list**: Remove pillars where:
   - Context requirements aren't met (per content-pillars.md)
   - Founder showed discomfort or disinterest
   - Responses were generic or low-energy
   - Topics explicitly marked off-limits in Round 10

4. **Note voice markers**: From Round 10 and overall interview tone, note preferred style (teaching vs. storytelling vs. hot takes vs. data-driven) and apply to idea generation.
