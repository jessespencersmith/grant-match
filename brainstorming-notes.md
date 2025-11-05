# Grant Matching Project - Brainstorming Notes

**Date Started:** November 4, 2025
**Last Updated:** November 4, 2025

---

## Project Overview

**Core Goal:** Match Vanderbilt faculty to funding opportunities by analyzing their research profiles and aligning them with RFPs.

**Scale:** 1000+ faculty at Vanderbilt

**Value Proposition:** Not just sending RFPs, but providing contextualized suggestions on why an RFP matches a faculty member's work.

**Context:** Currently everything is manual. ANY automation is improvement. Cost is not the constraint - efficiency and coverage are.

---

## Core Workflow: RFP to Faculty Notification

### When New RFP Arrives:

**Step 1: RFP Intake**
- Grant office receives RFP
- Extract essentials: title, agency, deadline, description, requirements
- Store in system

**Step 2: Matching (The Core Innovation)**
- Input to reasoning model:
  - RFP text (full or essential sections)
  - All faculty research descriptions (1000+ profiles)
- Reasoning model outputs:
  - Suggested faculty (ranked by relevance)
  - Specific rationale for EACH match
  - Alignment points between faculty work and RFP

**Step 3: Faculty Notification Email**
Contains:
1. **The RFP** (link or summary)
2. **Why we're sending it to YOU** (AI-generated, specific rationale)
3. **Your research profile** (what we used to make the match)
4. **Quick feedback options:**
   - ✅ Good match
   - ❌ Bad match
   - ⚠️ My research description is wrong
5. **Easy way to send updated research statement**

**Step 4: Feedback Loop**
- Track all responses
- Learn from feedback
- Update profiles based on corrections
- Improve matching over time

---

## Key Technical Components

### 1. Research Profile System

**ORCID-Based Publication Tracking:**
- Vanderbilt HAS faculty ORCID IDs (huge advantage)
- Query ORCID API for publications
- Much more reliable than name-based matching

**Continuous Updates:**
- Monthly automated ORCID queries for new publications
- AI sanity check flags suspicious attributions only
- Auto-update profiles when new work appears
- Re-generate summaries periodically

**Annual Validation:**
- Once yearly: "Here's your profile - correct if wrong"
- Low response rate is fine
- Faculty can also correct anytime via feedback

**Real-Time Corrections:**
- When faculty receives bad match, can flag profile error
- Can upload corrected statement immediately
- Takes effect for future matches

**Philosophy:** Imperfect data is OK. Quick feedback enables rapid self-correction.

### 2. Matching System

**Single-Stage Reasoning Approach:**
- Run reasoning model on ALL 1000+ faculty per RFP
- No pre-filtering (cost ~$40/RFP is acceptable)
- Rationale quality is the key value-add

**Model Output Requirements:**
- Relevance score (0-100)
- Specific rationale (cite actual publications, not generic)
- Suggested approach or angle
- Key alignment points with RFP sections

**Example of GOOD rationale:**
"Your 2024 paper on neural interfaces (PMID: xxx) directly addresses this RFP's requirement for novel brain-computer interface paradigms (Section 2.3). Your methodology could extend to the multi-modal sensing requirements."

**Example of BAD rationale:**
"Your research in neuroscience aligns with this neuroscience RFP."

### 3. Feedback System

**Email Template:**
```
Subject: Grant Match: [RFP Title]

Dear Dr. [Name],

[RFP Title] - [Agency] - Deadline: [Date]

WHY WE'RE SENDING THIS:
[Specific AI rationale]

Based on your research profile:
[Collapsible section with current profile]

QUICK FEEDBACK:
[Good Match ✓] [Not Relevant ✗] [Profile Wrong ⚠]

[Upload Updated Statement] [View Full RFP]
```

**Feedback Tracking:**
- Log every response type
- Identify patterns (which matches work, which don't)
- Use to improve prompts and thresholds
- Flag systematic profile errors

---

## Cost Analysis

**Per-RFP Matching Cost:**
- 1000 faculty × ~$0.04 per call = **~$40 per RFP**
- Profile updates: ~$600/year
- Infrastructure: ~$1,000/year

**Annual Estimates:**

| RFPs/Year | Total Cost |
|-----------|------------|
| 25        | ~$2,000    |
| 50        | ~$3,000    |
| 100       | ~$5,000    |

**ROI:** One successful grant >> total system cost. This is a no-brainer.

---

## Implementation Phases

### Phase 0: Immediate Actions (This Week)
1. Contact grant office - estimate RFP volume
2. Get faculty ORCID list - assess coverage
3. Analyze scopus-vanderbilt.txt file
4. Get 2-3 recent RFPs as examples

### Phase 1: Proof of Concept (Weeks 1-3)
1. Manually create 20 high-quality faculty profiles
2. Test matching on 2-3 real RFPs
3. Evaluate rationale quality
4. Show to trusted faculty for feedback
5. Iterate on prompts

**Deliverable:** Proof that AI rationales are valuable

### Phase 2: Automation (Weeks 3-6)
1. Build ORCID→publications pipeline
2. Automate profile generation with LLM
3. Test on 50-100 faculty
4. Implement AI sanity check for attributions
5. Set up database

**Deliverable:** Automated profile generation system

### Phase 3: End-to-End System (Weeks 6-10)
1. Build matching pipeline (RFP intake → matching → notification)
2. Design and implement email templates
3. Build feedback tracking system
4. Pilot with 50-100 faculty on 3-5 real RFPs
5. Iterate based on pilot feedback

**Deliverable:** Working system ready for full deployment

### Phase 4: Full Launch (Weeks 10-12)
1. Generate profiles for all 1000+ faculty
2. Train grant office staff
3. Announce to faculty community
4. Begin processing all RFPs
5. Monitor closely and respond to issues

**Deliverable:** Live system

### Phase 5: Continuous Improvement (Ongoing)
1. Monthly feedback analysis
2. Quarterly prompt refinement
3. Annual faculty validation campaign
4. Track success metrics (applications, funding)

---

## Critical Success Factors

1. **Rationale quality:** Must be specific and valuable, not generic
2. **Low friction:** Quick feedback, easy updates
3. **Transparency:** Show your work (profile used)
4. **Rapid iteration:** Fix issues quickly based on feedback
5. **Faculty trust:** Opt-out friendly, respect autonomy

---

## Open Questions

### Need to Answer Soon:
1. What's the actual RFP volume per year?
2. Is ORCID coverage complete?
3. Can we get historical application data for validation?
4. What's appropriate match score threshold?

### Future Considerations:
1. Team formation algorithm (Phase 2 feature)
2. RFP categorization/taxonomy
3. Integration with institutional grant systems
4. Scalability beyond 1000 faculty

---

## Key Insights from Discussion

**"Mouse Not Elephant":** Cost is not the limiting factor. ANY improvement over manual process is valuable.

**"Imperfect Is OK":** With quick feedback, errors self-correct. Don't let perfect be enemy of good.

**"Rationale-First":** The value is explaining WHY, not just matching. This is what faculty will appreciate.

**"ORCID Advantage":** Having faculty ORCID IDs solves the name disambiguation nightmare.

**"No Pre-filtering Needed":** Cost of processing all faculty is low enough that the value of finding non-obvious matches justifies running everyone through the reasoning model.

---

## Next Steps

**Immediate (This Week):**
1. Contact grant office about RFP volume and examples
2. Request faculty ORCID list
3. Analyze existing Scopus data

**Build Proof of Concept (Weeks 1-3):**
1. Create 20 test profiles manually
2. Run matching on real RFPs
3. Validate rationale quality
4. Get faculty feedback

---

## Future Discussion Topics

When we continue brainstorming:
- Team suggestion algorithm design
- RFP categorization approaches
- Learning system architecture details
- Scalability considerations
- Integration with existing systems
