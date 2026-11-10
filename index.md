---
layout: default
---

**Noah Golder** · [ngolder@ucsd.edu](mailto:ngolder@ucsd.edu)  
Section D33 · Safe Agentic AI: Data-Centric Methods for Auditing, Aligning, and Hardening LLM Agents  
Mentor: Babak Salimi

**What is the most interesting topic covered in your domain this quarter?**

What interests me most is whether we can spot a malicious step while an agent is still working. In LinuxArena, we give an open-weight Qwen model a main task. In attack runs it also gets a side task. We record the model’s internal activations in both settings and train a linear probe on them. An honest run and an attack run might start with the same harmless command, like listing a directory. I want to know what the probe picks up when the visible actions look that similar.

**Describe a potential investigation you would like to pursue for your Quarter 2 Project.**

I’d like to test how early the probe can flag an attack on a main task it hasn’t seen before. I’d pair honest and attack runs for each main task, set aside whole tasks for testing, and mark the first tool call that advances the side task. I’d choose an alert threshold on separate validation runs, then report how often the probe raises an alert before that call and how often it interrupts an honest run. A plot of the scores leading up to the first harmful call would show how much time a reviewer actually has to intervene.

**What is a potential change you’d make to the approach taken in your current Quarter 1 Project?**

I’d give a sample of tool calls their own labels. Knowing that a run had a side task doesn’t tell me whether a particular file read helped carry it out. I’d have two people independently mark which goal each call advances, with room to mark both goals or an unclear case. Then I’d inspect the steps where the probe score and the reviewers disagree. That would help me tell whether a high score follows a specific action or persists throughout an attack run.

**What other techniques would you be interested in using in your project?**

I’d try a text-only baseline that scores the command and its arguments just before execution. I’d test it on the same held-out calls as the activation probe and compare the attacks each catches at the same false-alarm rate. The cases where only the probe raises an alert interest me most. Reading those commands in context could tell me when collecting activations is worth the extra work.
