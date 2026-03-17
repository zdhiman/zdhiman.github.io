.. title: Prompt Engineering: How to Write Better Prompts
.. slug: prompt-engineering-writing-better-prompts
.. date: 2026-03-17 10:00:00 UTC+01:00
.. tags: prompt-engineering, generative-ai, artificial-intelligence, productivity
.. category: AI
.. link:
.. description: A practical guide to writing better prompts — the core techniques that turn vague AI outputs into reliable, high-quality results.
.. type: text

.. class:: lead

*A Practical Guide for Getting More from AI*

----

.. contents:: In this article
   :depth: 1
   :local:

----

TL;DR
======

- Prompt engineering is the practice of **writing clearer, more structured inputs** to get reliable, high-quality outputs from language models.
- The single highest-leverage change is being direct: lead with an action verb and specify exactly what you want, in what format, and for whom.
- Adding specific guidelines — desired attributes, step-by-step reasoning instructions, or both — can dramatically improve output quality.
- Structuring your prompts with XML tags or clear delimiters helps models distinguish your instructions from the data they need to process.
- Providing concrete examples of ideal outputs remains one of the most effective techniques, especially for edge cases, complex formats, and nuanced tone.

----

What Prompt Engineering Is
==========================

If you have used an AI assistant for more than five minutes, you have already done prompt engineering — you just may not have done it well. Every time you type a request into a language model, that input is a prompt. Prompt engineering is the deliberate practice of refining those inputs to get outputs that are more accurate, more useful, and more consistent.

The gap between a casual prompt and a well-crafted one is not subtle. A vague request like "write something about our product" will return generic filler. A specific prompt — one that defines the task, the audience, the format, and the constraints — will return something you can actually use. The difference often isn't the model's capability; it's the quality of the instruction.

This matters more than it might seem. As language models are increasingly embedded in professional workflows — drafting communications, synthesizing research, generating code, analyzing data — the ability to communicate precisely with these systems becomes a genuine competitive advantage. It is not a niche technical skill. It is a communication skill, applied to a new kind of collaborator.

Why It Matters Now
==================

The models have gotten dramatically more capable over the past two years, but capability without direction is wasted potential. A model that can draft a nuanced strategy memo will still produce a mediocre one if the prompt gives it nothing to work with.

There is a practical reason this skill is becoming more urgent. As organizations move from experimentation to production — running prompts thousands of times across automated workflows — the quality of each prompt compounds. A prompt that works 70% of the time is a liability at scale. One that works 95% of the time is an asset. The difference between those two is usually a few minutes of thoughtful prompt design.

The techniques that follow are not theoretical. They are the patterns that consistently produce better results across models, tasks, and domains.

Be Clear and Direct
===================

The most impactful improvement you can make to any prompt is also the simplest: say exactly what you want. Lead with an action verb. State the task in the first sentence. Specify the output format, length, and audience if they matter — and they usually do.

Consider the difference between these two prompts:

**Weak:** "I need help with meal planning."

**Strong:** "Generate a one-day meal plan for an athlete who weighs 80kg and is 180cm tall. The plan should meet a 3,000-calorie target, accommodate a gluten-free diet, and include macronutrient breakdowns for each meal."

The first prompt forces the model to guess at nearly everything: who the plan is for, what constraints apply, how detailed the output should be. The second prompt eliminates ambiguity. The model knows the task, the audience, the constraints, and the expected level of detail. In evaluations, this kind of clarity alone can nearly double the quality score of a model's output.

The principle extends to every domain. "Summarize this report" is weaker than "Summarize this report in three bullet points for a VP audience, focusing on budget implications." "Help me with this code" is weaker than "Debug this Python function that is returning a TypeError on line 12 when processing empty lists."

Directness is not rudeness. It is respect for how these systems work — they perform best when they do not have to infer your intent.

Be Specific with Guidelines
============================

Clarity gets you in the right neighbourhood. Specificity gets you to the right address.

There are two forms of specificity that work particularly well in prompts, and they serve different purposes.

The first is **attribute-based guidance**: telling the model what qualities the output should have. This includes things like length, tone, format, structure, reading level, or any other measurable characteristic. If you want a 200-word summary in a professional tone formatted as a numbered list, say so. Models are remarkably good at following these constraints when they are stated explicitly — and remarkably bad at guessing them when they are not.

The second is **step-based guidance**: telling the model how to think through the problem. This is especially valuable for complex tasks where you want the model to consider factors it might otherwise skip. For a meal planning prompt, this might mean instructing the model to first calculate caloric needs, then distribute macronutrients across meals, then check against dietary restrictions, and finally format the result. For a business analysis, it might mean asking the model to consider the problem from multiple stakeholder perspectives before recommending a course of action.

In practice, the strongest prompts combine both forms. You define what the output should look like *and* how the model should arrive at it. This combination of output constraints and reasoning instructions gives you control over both the destination and the route.

Structure Your Prompts
======================

When a prompt involves more than a simple question — when it includes background context, reference data, examples, or multi-part instructions — structure becomes essential.

The most effective structuring technique for language models is the use of **XML tags** to delineate different sections of a prompt. Rather than concatenating instructions, data, and context into a single wall of text, you wrap each component in descriptive tags. Athlete information goes inside ``<athlete_information>`` tags. Code that needs debugging goes inside ``<my_code>`` tags. Reference documentation goes inside ``<docs>`` tags.

This is not ceremonial. Language models process your entire prompt as a sequence of tokens, and they use contextual cues to determine what each section represents. Clear boundaries make it significantly easier for the model to distinguish your instructions from the data it should process, your examples from the actual task, and your constraints from your context.

Tag naming matters. Descriptive, specific names — ``<sales_records>`` rather than ``<data>``, ``<grading_rubric>`` rather than ``<info>`` — give the model additional signal about how to interpret the enclosed content. This is especially important when prompts grow longer or when you are interpolating variable content from external sources.

Even for shorter prompts, wrapping interpolated content in tags is a good habit. It makes the prompt's intent unambiguous and reduces the chance of the model confusing one part of your input for another.

Provide Examples
================

If you could only use one advanced prompting technique, this would be the one to choose.

Providing examples — known as **few-shot prompting** — is the practice of including one or more sample input-output pairs in your prompt to show the model exactly what you expect. One example is "one-shot" prompting. Multiple examples are "multi-shot." Both can dramatically improve output quality, especially for tasks where the desired format, tone, or reasoning style is difficult to describe in words alone.

Examples are particularly powerful in three scenarios. The first is **edge cases and nuance**. If your task involves detecting sarcasm, handling ambiguous inputs, or making judgment calls, showing the model how to handle a tricky case is far more effective than describing the rule abstractly. The second is **complex output formats**. If you need the model to produce structured JSON, a specific table format, or a multi-section report with a particular layout, an example is worth a hundred words of description. The third is **calibrating quality and style**. An example of an ideal response sets a concrete standard that instructions alone cannot match.

The technique is most effective when examples are wrapped in clear XML tags to separate them from the actual task, and when they are accompanied by brief explanations of *why* the example represents an ideal output. This combination — showing what good looks like and explaining what makes it good — gives the model both a target and a rationale.

Ask for Step-by-Step Reasoning
==============================

Some tasks require the model to think before it answers. For problems involving arithmetic, multi-step logic, comparative analysis, or any form of sequential reasoning, explicitly asking the model to show its work can meaningfully improve accuracy.

This technique, often called **chain-of-thought prompting**, was first demonstrated in a 2022 research paper by Wei et al. at Google. The researchers found that prompting models to generate intermediate reasoning steps before arriving at a final answer significantly improved performance on arithmetic, commonsense, and symbolic reasoning tasks. In some cases, the improvement was substantial — the technique helped a large model achieve state-of-the-art results on math benchmarks that it could not solve with standard prompting.

The simplest implementation is to append a phrase like "think through this step by step" or "explain your reasoning before giving the final answer." For more complex tasks, you can provide an example that demonstrates the desired reasoning chain, showing the model the kind of intermediate steps you expect.

A practical nuance worth noting: recent research from Wharton suggests that the value of explicit chain-of-thought prompting has decreased as models have become more capable, since many newer models now perform some form of internal step-by-step reasoning by default. The technique remains most valuable for genuinely complex multi-step problems and for situations where you need transparency into the model's reasoning process — not as a universal default for every prompt.

Iterate and Evaluate
====================

The best prompts are rarely written in a single pass. They are developed through iteration: write a prompt, test it against several inputs, identify where the output falls short, and refine.

This is where prompt engineering most closely resembles traditional engineering. You are not crafting a single message; you are designing an instruction set that needs to perform reliably across a range of inputs. The process looks like this: start with a clear, direct prompt. Run it against a representative set of test cases. Examine the failures — not just the obvious errors, but the subtle ones: outputs that are technically correct but miss the point, or that satisfy the letter of your instructions but not the spirit.

Each failure reveals a gap in your prompt. Maybe the model is ignoring a constraint because it was buried in the middle of a long paragraph. Maybe it is making assumptions you did not anticipate because you left a variable unspecified. Maybe it handles the typical case well but falls apart on edge cases. Each of these observations becomes a targeted improvement.

Over time, you develop an intuition for what makes prompts effective — but that intuition is built on reps, not theory. The practitioners who write the best prompts are the ones who test systematically and refine deliberately.

Putting It All Together
========================

None of these techniques exist in isolation. The most effective prompts typically combine several of them: a clear and direct opening, specific attribute and step-based guidelines, structured XML tags around any interpolated content, one or two well-chosen examples, and an explicit instruction to reason through complex steps.

Here is how these layers might combine for a real task:

A prompt that says "help me with a business analysis" becomes one that says: "Analyse the following quarterly sales data. For each product line, calculate year-over-year growth, identify the top and bottom performers, and flag any anomalies. Present your findings as a three-paragraph executive summary suitable for a board audience. Before writing the summary, reason through the data trends step by step." The sales data itself is wrapped in ``<sales_data>`` tags, and a brief example of an ideal summary is provided in ``<example>`` tags.

The difference in output quality between the casual version and the engineered version is not marginal. It is the difference between getting something you have to rewrite and getting something you can use.

Takeaways
=========

1. **Lead with clarity.** Start every prompt with an action verb and a direct statement of the task. Specify format, length, audience, and constraints upfront.

2. **Add guidelines for both output and reasoning.** Tell the model what the result should look like *and* how to think through the problem.

3. **Use structure.** XML tags, clear section breaks, and descriptive labels help models parse complex prompts accurately.

4. **Show, don't just tell.** Concrete examples of ideal outputs are more powerful than abstract descriptions of what you want.

5. **Iterate deliberately.** Treat prompt development like engineering: test against varied inputs, diagnose failures, and refine based on evidence.

6. **Match technique to task.** Not every prompt needs every technique. Simple questions need simple prompts. Reserve the full toolkit for complex, high-stakes, or repeated tasks where reliability matters.