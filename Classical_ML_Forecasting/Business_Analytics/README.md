# Business Analytics for Data Science


---
# How to Breakdown a Business Problem - 4 Stages

1. **Conceptual framing**
   - Before naming any metrics, restate the goal in business terms.
   - Ask what the initiative is meant to change, for whom, and what success would look like to leadership.
   - Then name the challenges early, in **three groups: customer, operational, and risk.**
   - Ask one or two clarifying questions, such as:
     - "Is the primary goal cost reduction or customer experience?" 

2. **Key metrics and evaluation**
- Use a three-tier structure:
  - **North-star / primary metric** -- This is the one number tied to the business goal. Although, this may or may not be possible for all business use cases depending upon the domain. 
  - **Supporting / diagnostic metrics** -- These explain why the primary metric(s) moved.
  - **Guardrail metrics** -- These are things that must not get worse such as:
    - customer satisfaction
    - errors
    - complaints
    - compliance

2b. **How would you evaluate using the key metrics?** 
  - Pilot vs. Control group
  - Before vs. After baseline
  - Time window (e.g. long enough to get past novelty effects + segment cuts)

3. **Data analysis and recommendation**
   - Computations are important here.
   - Compute relevant differences, call out any confounders, and commit to a recommendation.
   - A phased approach works well: expand, iterate, or stop, plus the conditions that would change.

4. **Communicating and adapting**
   - Commonly we will see things such as: "new data shows X — does your recommendation change?"
   - Need to show that updates are not an issue and things can change and iterate.
   - Tailor the message by audience: executives get the answer first and then the business impact, operations gets what changes on the ground, and technical teams get the method and caveats.
  
---
### Domain specific challenges to consider
- **Model risk management:** Fed guidance SR 11-7 requires model validation and documentation.
- **Consumer protection:** UDAAP rules (unfair, deceptive, or abusive practices) mean a wrong answer about fees or rates is a regulatory issue, not just a quality issue.
- **Fair treatment across customer segments**
- **Data handling:** PII and data residency/governance
- **Tracability, Auditability and explainability/interpretation of AI model outputs.**
- **Human-in-the-loop requirements** -- for anything that touches a customer's money or personal data, information and more.


---
### Math and reasoning traps to consider
- **Percent change versus percentage points**: Going from 20% to 25% is a +5 point change and a +25% relative change. Say which one you mean.
- **Is the difference real?** For two proportions, a quick check is a standard error of about √(p(1−p)/n) per group. With 400 customers at 50%, the SE is about 2.5 points, so a 3-point gap is noise. You don't need formulas out loud; "with only 400 customers per group I'd want more data before trusting a 3-point gap" is enough.
- **Averages hiding segments:** A result can be positive overall and negative in a key segment, or flip once you split it (Simpson's paradox). Always ask about segments.
- **Novelty and seasonality:** A first-month lift often fades.
- **Cannibalization and displacement:** Did it create value, or just move volume from one channel to another?
- **ROI and payback:** Payback in months = upfront cost ÷ monthly net benefit. Include run costs, such as LLM inference, vendor fees, and QA headcount.
