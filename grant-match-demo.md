# Grant Matching Demo - Planning Notes

**Demo Date:** Tomorrow
**Audience:** Research office leadership and staff
**Goal:** Show proof-of-concept for automated grant matching system

---

## Demo Concept

**Core Idea:** Pre-build faculty profiles for School of Engineering, then do LIVE matching against RFPs in real-time during the meeting.

**Why this approach:**
- Shows both components: profile generation + matching
- Real-time demo is impressive and interactive
- They can suggest RFPs to test on the spot
- Demonstrates actual capabilities, not vaporware

---

## Proposed Demo Flow (15-20 minutes)

### Part 1: Problem Statement (2 minutes)
"Vanderbilt has 1000+ grant-eligible faculty and receives dozens to hundreds of RFPs per year. Current matching process is manual, time-consuming, relies on personal networks, and misses interdisciplinary opportunities. We're proposing an AI-powered solution."

### Part 2: Show Pre-Built Profiles (5 minutes)
- Display 3-4 Engineering faculty profile examples
- Explain data sources and generation process
- Emphasize: auto-generated, faculty-validated annually
- Ask: "Does this look accurate? What's missing?"

### Part 3: Live Matching Demo (10 minutes)
- Run matching on 2-3 RFPs in real-time
- Show top 10-15 matches with reasoning
- Display: name, score, explanation, suggestions
- Discuss: "Do these make sense? Anyone missing?"

### Part 4: Discussion & Next Steps (5+ minutes)
- What would make this useful?
- What data do you have available?
- Timeline for pilot?

---

## Preparation Checklist

### TODAY (Priority 1):
- [ ] Check scopus-vanderbilt.txt contents
- [ ] Get Engineering faculty list from website
- [ ] Generate 50+ faculty profiles
- [ ] Find 3-4 engineering-relevant RFPs
- [ ] Test matching code end-to-end

### TONIGHT/EARLY TOMORROW (Priority 2):
- [ ] Review profile quality, fix obvious errors
- [ ] Pre-run matching on test RFPs (backup)
- [ ] Practice demo flow
- [ ] Prepare objection responses
- [ ] Test on demo laptop/network

---

## Key Questions to Ask Them

**About Current Process:**
1. How many RFPs do you distribute per year?
2. Which funding agencies are priorities?
3. How do you identify faculty to notify now?
4. What's the typical response rate?

**About Data:**
5. Do you track who applies to which RFPs?
6. Can we access historical application data?
7. Do you have success rates (applications → funding)?
8. Any existing faculty databases we could leverage?

**About Implementation:**
9. Who would manage this system?
10. What's the approval process for a pilot?
11. Timeline and budget expectations?
12. Integration needs with existing systems?

---

## Objection Responses

**"What about false positives?"**
→ "We provide reasoning with each match so faculty can quickly assess relevance. We'll learn from feedback and tune the system."

**"What if it misses someone?"**
→ "This is a discovery tool to surface opportunities people might miss, especially interdisciplinary ones. It doesn't replace human judgment."

**"How much does this cost?"**
→ "$50-60 per RFP to process all 1000 faculty. At 50 RFPs/year = $3,000 annually. One additional successful grant pays for this many times over."

**"What about privacy?"**
→ "All data from public sources: publications, grants, research statements. Faculty review profiles annually and can opt out."

**"We're too busy to implement this"**
→ "Designed to save you time. You upload RFPs, system matches automatically. We handle setup and maintenance."

---

## Technical Requirements

**Demo Infrastructure:**
- Laptop with API access
- Code that can:
  - Load pre-generated faculty profiles
  - Accept RFP input (paste text or file)
  - Run matching via API call
  - Display results cleanly
- Backup: Pre-run results if live demo fails

**Data Sources for Profiles:**
- Publications: Scopus (check scopus-vanderbilt.txt)
- Grants: NIH Reporter, NSF Awards APIs
- Research statements: Web scraping faculty pages

**Test RFPs from:**
- NSF Engineering directorates
- NIH/NIBIB (biomedical engineering)
- DOE (energy/materials)
- Mix of agencies and topics

---

## Success Criteria

**Minimum Success:**
- They understand what the system does
- They see potential value
- Willing to discuss next steps

**Good Success:**
- They're excited about the concept
- They want to pilot it
- They offer data/resources

**Great Success:**
- Approve pilot on the spot
- Assign point person
- Budget allocated
- Timeline set

**Watch for:**
- Detailed questions = engaged (good)
- Identifying use cases = very interested (great)
- Silent/polite = not engaged (address it)

---

## The Pitch (30 seconds)

"We've built a system that automatically matches Vanderbilt faculty to grant opportunities. AI analyzes research profiles and provides personalized matches with specific reasoning - like 'Dr. Smith is a 92% match because her neural interface work aligns with Section 2.3.' Costs $50 per RFP to process all 1000 faculty - essentially free compared to finding one additional successful grant. Let me show you how it works."

---

## Backup Plans

**If live demo fails technically:**
- Show pre-run results
- "We ran this earlier, here are the results..."

**If results look questionable:**
- Be honest: "This is a prototype, helps us improve"
- Frame as learning opportunity
- Still better than no automation

**If internet fails:**
- Have profiles and results cached locally
- Demo runs offline with pre-loaded data

**If they're not engaged:**
- Ask more questions about their pain points
- Pivot to their suggested RFP
- Focus on specific value propositions

---

## Critical Immediate Next Steps

1. **CHECK scopus-vanderbilt.txt NOW** - What data is actually in there?
2. **Determine realistic prep time** - When exactly is the demo?
3. **Scope appropriately** - 50 profiles or scale down to 30?
4. **Get Engineering faculty list** - From website or other source?
5. **Find test RFPs** - Which ones to use?

---

## Post-Demo Actions

**Immediately after:**
- Send thank-you email with summary
- Share example profiles and results
- Document their feedback and feature requests

**Follow-up materials:**
- Cost analysis spreadsheet
- Proposed pilot timeline
- Data requirements doc
- Success metrics framework

**Decisions needed:**
- Go/no-go on pilot?
- Which school/department for pilot?
- Point of contact assignment?
- Data access agreements?
