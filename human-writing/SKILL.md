---
name: human-writing
description: Removes AI writing tells from drafts, replies, docs, commit messages and translations — filler phrases, hype, padding, manufactured balance, fake enthusiasm, fabricated personal experience. Use when writing or rewriting text that should sound like a real person, when editing for tone, or when prose reads as obviously AI-generated.
---

# Human Writing

## Goal

Write like a real person who understands the context, audience, and subject.

The goal is not to make AI writing "more human" by adding casual phrases or imperfections. The goal is to remove the patterns that make writing obviously AI-generated.

**Natural > polished.
Specific > generic.
Useful > complete.**

Do not optimize for sounding impressive. Optimize for sounding like a competent person who simply wanted to communicate something clearly.

---

## 1. Understand the Context First

Before writing, determine:

* Who is speaking?
* Who is reading?
* What is the purpose?
* Where will this be used?
* What tone does the context naturally require?

A GitHub issue, a Reddit reply, a product description, an email, and a technical document should not sound the same.

Do not apply one "professional" writing style everywhere.

---

## 2. Do Not Repeat What the Reader Already Knows

Do not restate the user's question, requirements, or context unless repetition is necessary for clarity.

Avoid openings such as:

* "Great question."
* "This is an interesting topic."
* "Let's take a closer look."
* "There are several important factors to consider."
* "Before we dive in..."

Start with the actual answer or useful information.

---

## 3. Remove Generic AI Language

Avoid phrases that exist mainly to introduce, transition, or summarize information without adding anything.

Examples:

* "It is worth noting that..."
* "It's important to understand that..."
* "In today's rapidly evolving landscape..."
* "At the end of the day..."
* "That being said..."
* "Let's explore..."
* "In conclusion..."
* "This highlights the importance of..."

Use a direct sentence instead.

---

## 4. Prefer Concrete Information

Prefer facts, observations, actions, and results over vague descriptions.

Weak:

> This provides a powerful and flexible solution for modern development workflows.

Better:

> It lets the agent run commands, access project files, and use MCP tools under explicit policies.

If a claim can be made more specific, make it more specific.

---

## 5. Do Not Add Padding

Do not make writing longer just to make it look complete.

Remove:

* unnecessary background
* obvious explanations
* repeated points
* generic summaries
* redundant conclusions
* unnecessary disclaimers
* filler transitions

If two sentences communicate the same thing, keep the stronger one.

A short answer is preferable to a padded answer.

---

## 6. Avoid Unnecessary Hype

Do not automatically turn a technical fact into marketing language.

Avoid words such as:

* revolutionary
* groundbreaking
* powerful
* seamless
* game-changing
* next-generation
* cutting-edge
* incredibly
* unmatched

unless they are genuinely appropriate and supported by context.

Prefer describing what the product actually does.

Instead of:

> A revolutionary AI development experience that transforms the way you build software.

Write:

> An AI coding agent that can edit files, run commands, use MCP tools, and execute tasks remotely.

---

## 7. Do Not Force Balance

Do not artificially structure every topic as:

> On the one hand...
> On the other hand...

Not every subject needs a balanced essay.

If one fact is relevant, state it.
If there is a real trade-off, explain the trade-off.

Do not manufacture opposing viewpoints just to make the writing look thoughtful.

---

## 8. Do Not Overuse Lists

Lists are useful when the information is naturally list-shaped.

Do not turn every paragraph into:

* Point 1
* Point 2
* Point 3
* Point 4
* Conclusion

Normal prose is often more natural.

Use headings and lists when they improve navigation, not because they make the response look organized.

---

## 9. Vary Sentence Structure Naturally

Avoid repetitive sentence patterns.

Do not make every sentence roughly the same length or structure.

Natural writing can contain:

* short sentences
* longer explanations
* fragments when appropriate
* occasional repetition for emphasis
* simple transitions
* uneven paragraph lengths

Do not deliberately add mistakes or awkward wording to "sound human."

---

## 10. Preserve the Author's Voice

When rewriting existing text, improve clarity without replacing the author's personality.

Do not turn:

> This thing is pretty annoying because it keeps locking the whole session.

into:

> This issue significantly impacts the overall user experience by introducing undesirable session-level locking behavior.

The second version may be more formal, but it is not necessarily better.

Preserve directness, informality, technical vocabulary, and personality when they are part of the original voice.

---

## 11. Use Casual Language Only When It Fits

Natural writing can be informal.

Examples:

* "I don't think this is worth adding yet."
* "This works, but the locking is still pretty heavy."
* "I'm not sure this is the right abstraction."
* "The API is simple enough for now."

But do not add slang, contractions, jokes, or casual expressions just to appear human.

**Do not fake casualness.**

---

## 12. Technical Writing

For technical writing, prioritize:

1. correctness
2. clarity
3. precision
4. conciseness
5. natural language

Avoid corporate or promotional language when writing about software.

Prefer:

> The daemon keeps the agent process running on another machine. The desktop client connects to it over RPC.

over:

> Our innovative remote architecture enables a seamless distributed agent experience.

Technical writing should sound like it was written by someone who actually worked on the system.

---

## 13. Product Writing

Product copy should explain what users can actually do.

Prefer:

> Run agents locally or on another machine, with fine-grained policies for files, commands, and tools.

over:

> Unlock a completely new generation of intelligent development workflows.

Do not invent benefits that are not supported by the product.

Do not make every feature sound extraordinary.

---

## 14. Developer Communication

For GitHub issues, pull requests, release notes, discussions, and technical posts:

* be concrete
* state the problem directly
* explain the relevant implementation details
* mention trade-offs when they matter
* avoid corporate language
* avoid unnecessary introductions
* avoid repeating the obvious

Write like a developer talking to other developers.

---

## 15. Do Not Invent Personal Experience

Never fabricate statements such as:

* "I've been using this for months..."
* "In my experience..."
* "I personally found..."
* "When I worked on similar projects..."

unless that experience is actually available in the context.

Do not create a fake personal voice to make the writing more convincing.

---

## 16. Do Not Manufacture Emotion

Do not add artificial enthusiasm, praise, frustration, or confidence.

Avoid:

> This is absolutely fantastic!

> That's a really exciting direction!

> I love this approach!

unless the speaker genuinely intends to express that emotion.

Do not make the writing emotionally stronger than the source or context warrants.

---

## 17. Do Not Explain Obvious Things

Do not explain basic concepts merely to demonstrate knowledge.

If the audience is technically experienced, assume an appropriate level of knowledge.

For example, when discussing Rust:

> `Arc<Mutex<T>>` introduces shared synchronized access.

is enough when the context already assumes familiarity with Rust.

Do not follow it with a textbook explanation unless the user needs one.

---

## 18. Avoid Empty Conclusions

Do not end every response with a generic summary.

Avoid:

> Overall, there are many factors to consider, and the best approach depends on your specific needs.

If the answer has a concrete conclusion, state it.

If there is nothing else to add, stop.

---

## 19. Translation

When translating, preserve the meaning and intent rather than translating sentence by sentence.

Adapt:

* sentence structure
* idioms
* technical terminology
* level of formality
* cultural conventions

The result should read as if it was originally written in the target language.

Do not preserve unnatural wording just because it matches the source sentence structure.

---

## 20. Rewriting

When rewriting existing text:

1. Preserve the original meaning.
2. Preserve important technical details.
3. Preserve the author's voice.
4. Remove unnecessary repetition.
5. Fix awkward phrasing.
6. Improve clarity where needed.
7. Do not add claims that were not present.
8. Do not make the text more formal unless requested.

The goal is **better writing**, not **different writing**.

---

## 21. Final Check

Before returning the text, check:

### AI smell

Does any sentence sound like something an AI assistant would routinely say?

Remove it if it adds no information.

### Information density

Does every sentence contribute something?

If not, remove or shorten it.

### Specificity

Can a vague claim be replaced with a concrete fact, action, example, or result?

Do so.

### Voice

Does the text sound like the intended speaker?

If not, adjust it.

### Simplicity

Can the same thing be said more simply?

Prefer the simpler version.

### Naturalness

Does the text sound like something a real person would actually write in this context?

If it sounds unusually polished, symmetrical, comprehensive, or carefully balanced, simplify it.

---

## Core Principle

Do not make the writing look like **AI trying to imitate a human**.

Make it look like **a normal person who never thought about whether the text sounded like AI in the first place**.