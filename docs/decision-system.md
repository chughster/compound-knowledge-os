# The Decision System

Most people make decisions twice. Once when they make them, and once when they realise they made them wrong. The gap between those two moments is where the learning should happen — but usually doesn't, because there's no record of the original reasoning.

Compound has a built-in decision system. It doesn't just log outcomes. It logs how you thought.

---

## How It Works

### 1. Tag it

When you're facing a real choice, add it to your task list with the `#decision` tag:

```
- [ ] Decide: accept the consulting engagement #decision 📅 2026-07-03
```

This routes the task to the **Decisions tab** in your task dashboard — separated from your normal to-do list, visually distinct, tracked differently.

### 2. Think it through

Say "help me think through [decision]." Claude runs a structured framework before touching any options:

**Classify it first.** Is this actually a hard call? Most decisions are reversible. Treating them as permanent is what causes paralysis. The framework checks: is this consequential *and* irreversible? If not, decide fast and move. Only the decisions at that intersection get full process.

**Find the real problem.** Before generating options, Claude asks: what would have to be true for this problem not to exist? Nine times out of ten, the binary you're evaluating isn't the actual problem — it's one solution to a problem you haven't clearly defined yet.

**Force a third option.** Binary choices are almost always a sign you've accepted someone else's framing. The framework pushes: what would you do if Option A simply didn't exist? This surfaces the alternatives you weren't considering.

**Look both directions in time.** Two projections, run separately:
- *Backcasting (positive):* It's 12 months from now. It worked brilliantly. What happened? Work backwards — this reveals the path.
- *Pre-mortem (negative):* It's 12 months from now. It went badly wrong. What happened? Work backwards — this reveals the risks your optimism was hiding.

**Check your mental state.** Seven situational factors reliably degrade anyone's decision quality: stress, distraction, time pressure, group dynamics, being outside your area of expertise, a strong authority figure in the room, and information overload. If two or more are active when you're making this call, the framework flags it.

**Set tripwires.** Before committing, define the conditions that would trigger a review or change of course. "If metric X drops below Y by date Z, I review the decision." Tripwires make commitments self-enforcing — you don't have to rely on remembering to check.

### 3. Commit and document

Claude writes the decision note to your vault with your reasoning, the options you considered, the outcome you expect, and the tripwires you set. Status: open.

### 4. Review it later

Six months later — at your monthly evolution review, or whenever the outcome is clear — Claude surfaces the note and asks you to fill in what actually happened.

The review has a specific structure. It's not just "did it work?" It asks:

- **What actually happened?**
- **Was the reasoning sound?** *(Separate from whether the outcome was good.)*
- **What would you change about the process?**
- **Verdict:** Correct decision / Wrong decision / Right call, wrong outcome / Wrong call, lucky outcome

That last taxonomy is the point. A good process that produced a bad outcome (bad luck) is different from a bad process that produced a good outcome (dangerous luck). Tracking them separately is how you build actual judgment rather than just outcome-matching.

---

## Example

You're a founder deciding whether to take a 3-month consulting engagement. Good money. But it's 60% of your available hours at a critical product moment.

The framework surfaces:
- The real problem isn't "should I take this?" — it's "what does my runway look like without it, and are there other ways to solve that?"
- The binary is false — there are at least two other options you hadn't considered
- You're deciding under financial stress and time pressure — two degradation factors active
- The path to success requires a written hour cap and IP rights clause in the contract
- The main failure mode is scope creep in weeks 3–4 — you set a tripwire

You take the engagement with those conditions. Three months later you review it. Scope crept slightly. The tripwire fired late. You update the note with a verdict: *Right call, wrong execution on the tripwire.* 

Next time you evaluate a consulting engagement, that note is there. The pattern is documented. The system got smarter because you did.

---

## Why This Matters

Most decision journals die because there's no feedback loop. You write things down but never go back. In Compound, the feedback loop is built in — monthly reviews surface open decisions automatically. You don't have to remember to check. The system does.

Over time, you build something most people never have: a documented record of how you think under uncertainty, not just what happened. That's the compounding asset.
