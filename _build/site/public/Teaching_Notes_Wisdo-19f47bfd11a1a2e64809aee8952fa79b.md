# Teaching Notes: "Wisdom in Optimization"

## Facilitation Guide & Discussion Strategies

---

## Framing the Assignment (First Class)

### Hook: The Question Students Should Ask Themselves

Start with this core question:

> **"Am I designing and deploying these systems as a steward of God's creation, or am I complicit in extraction, exploitation, or disorder?"**

This isn't a soft question. It's the kind of question that should make a computer scientist pause and think carefully about their work. Use it to open the conversation:

**In Class:**

- Write the question on the board.
- Don't explain it yet. Ask students: "When you build a system, what does this question make you wonder about?"
- Let them respond. You'll likely hear answers related to: Who uses it? How much energy does it use? Is it for profit or purpose? Does it help people or manipulate them?
- Then say: "Today we're going to ground this question in a specific technical practice: optimization. And we're going to connect it to Christian theology about creation and stewardship."

### Why This Matters

Many students see computer science as "neutral" or "technical"—separate from ethics and theology. This assignment challenges that assumption head-on. Key points:

1. **Every design choice reflects values.** There are no neutral systems. When you choose an inefficient algorithm, you're saying something about your values. You're saying: "These wasted resources don't matter to me," or "Speed-to-market matters more than impact," or "I didn't think about it."

2. **Stewardship is not optional for believers.** If students claim Christian faith, they can't compartmentalize their work into "secular" and "sacred" categories. Their technical practice is a form of discipleship.

3. **This isn't just about the environment.** Stewardship applies to all resources, including computational resources. When a system wastes energy, it has real impacts: higher costs for users, larger carbon footprints, devices that become obsolete faster, and exclusion of people with limited bandwidth.

---

## Suggested In-Class Walkthrough (30-45 minutes)

Use this to introduce the assignment:

### Step 1: Warm-Up Analysis (10 min)

Use **bubble sort** as an example (familiar to all students).

**Show the code:**

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr
```

**Ask:**

- "What is this algorithm doing?"
- "How many comparisons and swaps does it make in the worst case for an array of size n?" (n²)
- "Where is it doing unnecessary work?"

**Point out the inefficiency:** Even if the array is already sorted after the first pass, bubble sort keeps comparing. It doesn't recognize the pattern that the data is ordered.

### Step 2: Introduce the Theological Frame (8 min)

Say something like:

> "From a Christian perspective, we believe God created the universe with wisdom and order. God's designs are elegant—they don't waste effort or resources. Think about photosynthesis, water cycles, or how your body processes oxygen. These are all remarkably efficient.
>
> When we design algorithms, we're participating in a kind of discovery. We're asking: 'What is the structure of this problem? What pattern can I align my solution with?' An efficient algorithm respects that structure. An inefficient algorithm fights against it, doing unnecessary work.
>
> More than that, we're called to be stewards. Stewardship isn't just about trees and soil—it's about all resources. When we waste computational resources through inefficient design, we're not being good stewards. We're being exploitative."

Pause. Let this sink in.

### Step 3: Make It Concrete (12 min)

**Ask students to calculate:**

If bubble sort runs on:
- A moderately sized dataset (n=1,000): ~1 million comparisons
- A larger dataset (n=1 million): ~1 trillion comparisons

**Each comparison uses energy.** Not much per comparison, but at scale?

- Cloud data centers use enormous amounts of electricity.
- If a company uses an inefficient sorting algorithm for a service that processes millions of queries per day, the waste adds up.
- That waste = higher operating costs passed to customers, more carbon emissions, faster device obsolescence.

**Now personalize it:** 
"If you were designing the sorting function for a payment processing system that processes 100 million transactions per day, would you use bubble sort or merge sort? Why?"

Students will say: "Merge sort, because it's faster."

**Follow-up:** "Right. And one reason is stewardship. It's about respecting the resources you're using and not wasting them."

### Step 4: Introduce the Assignment (5 min)

Walk through the three parts:
1. **Analyze an inefficient algorithm** - show how detailed the analysis should be
2. **Design an optimized version** - emphasize the "discovery" of pattern/structure
3. **Reflect theologically** - these are the hard questions; they require honesty

---

## Common Student Responses & How to Address Them

### Response 1: "Optimization Isn't My Job—The Hardware Is Fast Enough"

**What students mean:** "Why should I worry about efficiency when computers are so powerful? This feels like premature optimization."

**How to address it:**

**In the moment:** "That's actually a really common view, especially after the 'Premature optimization is the root of all evil' aphorism became popular. But here's the thing: optimizing an algorithm often isn't about doing extra work. It's about *recognizing structure* and avoiding unnecessary work in the first place."

**Deeper response:** "Also, think about scale. Yes, your laptop is fast. But if your algorithm runs on a data center serving millions of users, or on mobile devices with limited batteries, or in an embedded system where power consumption matters, then efficiency isn't optional—it's responsible design."

**Theological angle:** "From a creation perspective, we don't get to assume resources are infinite just because they're abundant. Abundance is a gift, but a gift doesn't authorize us to waste. A gardener doesn't assume water is unlimited just because rain falls."

### Response 2: "In the Real World, We Don't Have Time for This. We Ship First, Optimize Later"

**What students mean:** "Time-to-market matters more than perfection. This is idealistic."

**How to address it:**

**Acknowledge the tension:** "You're right that there's real pressure in industry to move fast. And sometimes good-enough is actually good enough. But that's different from never thinking about it."

**Reframe:** "Here's what I think you should develop as a habit: When you're designing a solution, spend *just a little bit* of time asking: 'Is there a structure to this problem I'm not seeing? Is there a smarter way?' Often, the optimized solution is just as easy to implement as the naive one—you just have to think about it first."

**Real-world example:** "Netflix engineers optimize their systems meticulously because they understand: if our system uses 10% less energy per query, across 200 million users, that's millions of dollars saved and thousands of tons of CO₂ not emitted. That's not just virtue—it's business sense."

**Theological angle:** "And more importantly, you're a steward. That doesn't mean perfectionism paralysis, but it does mean *intentionality*. When you make a choice to ship an inefficient system, you should be doing that consciously, not just because you didn't think about it."

### Response 3: "This Is Mixing Religion and Computer Science. They're Separate Domains"

**What students mean:** "I don't like theology bleeding into tech. They have nothing to do with each other."

**How to address it:**

**Calmly:** "I understand the impulse to keep domains separate. But here's the thing: You can't keep them separate. Every system you design embodies values and assumptions about the world. The question isn't whether theology influences technology—it's whether it influences it *consciously* or *unconsciously*."

**Examples:**
- "If you design a social media algorithm to maximize engagement, you're making a theological claim: that human flourishing is achieved through more engagement. Is that true? Worth asking."
- "If you extract as much data as possible from users to train a model, you're making a claim about who owns that data and what matters. Is it?"
- "If you optimize for speed at the expense of privacy, you're choosing speed over human dignity. That's a values choice."

**Non-preachy angle:** "Look, you don't have to agree with Christian theology to see this. Secular ethicists are asking the same questions: What are we building? For whom? What values does it reflect? This assignment is just *one* framework for asking those questions. It's the Christian framework because this is a Christian university, but the underlying point—that you should think about values in design—is pretty universal."

### Response 4: "I Optimized My Algorithm, but the Reflection Questions Are Too Vague"

**What students mean:** "I don't know what theological answer you're looking for. What's the 'right' answer?"

**How to address it:**

**This is actually good.** It means they're being thoughtful. Encourage it:

"Great question. And it's important: I'm *not* looking for a particular theological conclusion. I'm looking for *honest engagement* with the questions. Here's what matters:

1. You've actually read and thought about the theology provided
2. You're connecting those ideas specifically to your algorithm—not speaking in generalities
3. You're thinking critically about the tensions (e.g., 'optimization is good, but what if it requires less readable code?')
4. You're being honest about your own choices and assumptions

An A-level reflection might say: 'I didn't think about stewardship when I chose my first algorithm. Now I see how I can design more responsibly. But I also realize that in industry, I might have to make trade-offs. Here's how I'd think about those trade-offs...'

A lower-level reflection would be: 'Optimization is important because resources are finite and stewardship is important and that's good.'"

---

## Discussion Prompts to Deepen Engagement

Use these before, during, or after the assignment:

### Before (To Set Up the Question)

**"Think about a system you use regularly (Instagram, Google, your university's email). Do you think the engineers who built it were thinking about stewardship? How can you tell?"**

Expected answers: Some mention privacy concerns, speed, tracking, etc. The point is to make students realize: *Design choices are visible. They reveal what the designer valued.*

**"If you were redesigning that system with stewardship in mind, what would you change?"**

This helps them see that stewardship isn't abstract—it leads to concrete design changes.

### During (To Deepen the Reflection)

**"You optimized this algorithm, and it's now faster. But the optimized version is harder to read. Should you keep it? What factors matter in deciding?"**

This is the real question. Optimize for *what*, exactly? Execution speed? Readability? Energy efficiency? Deployment ease? These are value questions.

**"What if you discovered that the inefficient algorithm was written by someone who was under intense time pressure and just wanted to ship something that worked? Does that change how you think about it?"**

This is about judgment and grace. Stewardship doesn't mean harsh condemnation of everyone who didn't optimize. But it does mean awareness and intention going forward.

**"Many AI/ML systems are extraordinarily compute-intensive. Some researchers argue that's worth it because the benefits (better medicine, better translation, etc.) outweigh the cost. Do you agree? How would you decide?"**

This introduces genuine moral complexity. Not everything is a simple "optimize!" or "don't optimize!" decision.

### After (To Connect to Professional Identity)

**"How will this assignment change how you think about your work as a computer scientist or engineer?"**

Listen for: Increased awareness, intention, a sense of responsibility. These are signs the assignment worked.

**"When you're in industry, what would need to be true for you to push back against shipping an inefficient system?"**

This is about virtue formation—helping students imagine themselves as people of integrity in their future work.

---

## How to Grade Fairly While Maintaining Rigor

### The Challenge

You want to:
- Evaluate *technical* skill fairly (Part 1 & 2)
- Encourage *honest theological reflection* without requiring a particular belief (Part 3)
- Not punish students who are new to thinking theologically

### The Solution

**For Parts 1 & 2 (Technical):** Grade these like any rigorous CS assignment. The rubric is clear: Is the analysis correct? Is the optimization real? Does the code work?

**For Part 3 (Reflection):** Grade based on:
- **Engagement:** Does the student seriously engage with the texts and concepts, not blow them off?
- **Connection:** Do the theological ideas connect specifically to *their* algorithm, or are they generic?
- **Honesty:** Is there evidence of real thinking, or just "right answers"?
- **Depth:** Do they acknowledge complexity, trade-offs, questions they don't have answers to?

**What NOT to grade on:**
- Whether the student agrees with Christian theology
- Whether they reached a "correct" conclusion about stewardship
- Whether they write beautifully (though clarity helps)

**Example:** A student writes: "I realized I never thought about whether an algorithm was efficient. I just wanted it to work. Now I see stewardship means I should think about resources. But I also wonder—if I'm working for a company that doesn't care about this, what's my responsibility? I don't know." 

**Grade:** This is A-level reflection. It's honest, it engages the theology, it acknowledges complexity. You want more of this.

---

## Ways to Extend the Assignment

### For Advanced Students

**Option 1: Historical Investigation**
"Choose a real-world system (Google's search algorithm, Facebook's news feed, Uber's dispatch system) that is known to have efficiency issues or to have prioritized something other than computational efficiency. Research: Why did the engineers make the choices they did? What pressures were they under? What would a stewardship-informed redesign look like?"

**Option 2: Ethics Case Study**
"Some argue that making systems *too* efficient can harm workers (e.g., warehouse robots that replace humans, automated systems that eliminate jobs). Research and reflect: Can efficiency and justice ever be in tension? How would you balance them?"

**Option 3: System Design from Scratch**
"Design a new system (a data structure, a caching strategy, a database schema) from first principles with stewardship in mind. What would change about how you design it if resource conservation was a primary goal from the start, not an afterthought?"

### For Struggling Students

**Option 1: Simplified Reflection**
Provide a scaffolded reflection template:
- "I discovered that [inefficiency] by [method]"
- "This matters because [resource impact]"
- "From a stewardship perspective, this means [principle]"
- "I will [action] going forward"

**Option 2: Discussion-Based Reflection**
Instead of writing 2-3 pages, have a one-on-one or small-group discussion about the assignment. Let them think out loud.

**Option 3: Paired Work**
Let students work in pairs: one writes the technical part, one leads the reflection (though both contribute).

---

## Connecting to Future Assignments

Once you've done this assignment, reference it throughout the course:

**In Databases:** "Remember the stewardship question? When you're writing SQL queries for the assignment, ask: Is this query efficient? If it scans the whole table, what resources are we wasting?"

**In Computational Modeling:** "When you're building your model, think about the trade-off between accuracy and computational complexity. Sometimes a simpler model is better stewardship."

**In any code review:** "Let's look at this section. Is it clear *why* we made this choice? Is it efficient? Does it reflect our values?"

---

## A Note on Tone

This assignment asks serious questions. But it shouldn't feel heavy-handed or judgmental. Your tone should be:

- **Curious:** "I wonder what you'll discover when you optimize this..."
- **Invitational:** "I'm asking you to think about something you might not have considered before..."
- **Honest:** "I don't claim to have all the answers to stewardship questions. But I think they're worth asking."
- **Affirming:** "Your technical work matters. The systems you build affect real people and creation. That's worth taking seriously."

Avoid:
- Moral superiority ("People who don't optimize are irresponsible")
- Oversimplification ("Just always optimize everything")
- Preachiness ("God wants you to be efficient")

---

## Faculty Reflection

Before teaching this, consider:

1. **Your own practice:** Do you optimize your code? When? When not? Why? Be honest with students about the tensions you navigate.

2. **Your institution:** How does your university value efficiency in its own systems? Sometimes there's irony in teaching stewardship in an environment that prioritizes other values. Name that.

3. **Your faith (or lack thereof):** If you're not a Christian believer teaching in a Christian context, how do you approach this? Some options:
   - "I'm an atheist, but I think the stewardship framework is useful regardless"
   - "I'm teaching from my institution's tradition; you're invited to engage with it even if you disagree"
   - Talk to your department chair about how to frame it authentically

4. **Student composition:** How many of your students are Christian? How many are exploring faith? How many are skeptical? Tailor your language and framing accordingly, while maintaining rigor.

---

## Troubleshooting

**"Students are just going through the motions on the reflection"**

Try: In the next class, spend 10 minutes discussing one student's reflection (anonymously, with permission). Ask the class: "What makes this reflection honest vs. generic?" The example will help all students understand the standard.

**"The theological content feels disconnected from the algorithm stuff"**

Try: When students bring their work to office hours, ask: "Show me exactly where in your optimization process stewardship mattered. What would you have done differently without thinking about stewardship?" Make the connection concrete and specific.

**"Some students are really uncomfortable with the theology"**

Try: Acknowledge it in class. "I know this might feel unfamiliar. You don't have to agree with it to engage with it. Just give it serious thought." Consider offering an alternative reflection that uses secular ethical frameworks (utilitarianism, virtue ethics, etc.) instead.

**"Students are writing longer reflections, not better ones"**

Try: Explicitly say that length doesn't correlate with quality. Have an example of a short, excellent reflection alongside a longer, mediocre one. Show the difference.

---

## One More Thing

Remember: The goal isn't for students to leave this course as theologians. It's for them to leave asking better questions about their work. If a student says, "I'd never thought of my code as an ethical choice before. Now I do," that's success. That's vocational formation happening.

