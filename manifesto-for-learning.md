---
layout: default
title: A Manifesto for Learning
---
<article class="prose" markdown="1">

It's a trite Chinese idiom that danger = opportunity, but it applies aptly to how the world will change with AI. The super rich are hedging their bets with land in Wyoming and New Zealand. I am in no such position yet, and I don't have anything worth protecting yet, so I do what I can and try to make it work for some people.

One area where I see an opportunity is education. The utopian vision is a $20-a-month tutor for every child: whatever their background, access to the most suitable route to learning whatever they want, with infinite patience. But this is not what is happening right now.

From my own experience it has made me dumber. Not because AI teaches badly, but because an LLM just does what is asked, and our natural inclination is away from effort. We gave every child a tutor and nothing to enforce or encourage discipline. I think there's a lot of value in the answer to: how do we put the discipline back?

Once you solve that, the paradigm of one teacher, thirty children, a calendar, a syllabus paced to the median becomes negotiable. What is useful for a certain child to learn, in what sequence to learn it. I envisage an Aristotelian education for every child in this world.

The benefits compound, we don't want children to just become more efficient students, we want them to be children, free to play, to wonder, to be slow and embodied, to find what is worth learning on their own terms, something that I have found to be a missing part of the foundation of my American "striver elite" colleagues.

School is a place for this, The classroom narrows to what classrooms are uniquely good at — shared inquiry, shared making, the social part of becoming a person, it becomes just that and stops crowding everything else out. 

I propose a workflow, implemented in an example tool that forms the basis for further exploration of these idea. A *repo* per skill, a loop of five verbs, an agent that withholds answers, a few hooks and routines. 

The mechanisms are not new. What is new is that they can finally run — for everyone, not just the children of people who could afford the tutor.

---

## I. Why it makes you dumber

**The shortcut.** Competence is built by effort with feedback; pulling the answer from your own head, getting it wrong, being corrected, pulling again. People avoid that effort when they can (Kool et al., 2010). Offloading works exactly as advertised: let people copy instead of remember and their immediate score rises while what they retain falls, even when they know a memory test is coming (Grinschgl et al., 2021).

**The honeymoon**. From personal experience, early use feels like power, and from the same baseline before exposure, it is. The tool really does extend you: nearly a thousand high-schoolers given GPT-4 for maths practice scored 48% higher with it (Bastani et al., 2025); students writing with ChatGPT improved their essay scores more than students given a human expert (Fan et al., 2025); people solving logic problems with AI beat the norm (Fernandes et al., 2025). That extension is real and worth having — an adult with a skill they already own loses nothing by extending it.

The problem is that it doesn't build on top of our baseline. The feeling is not fake. It is the feeling of being extended, mistaken for the feeling of having learned — and performance while assisted has never been a reliable index of learning (Soderstrom & Bjork, 2015) The same essay-writers did not measurably learn more than any other group. The same logic-solvers overestimated their own score by more than the gain, and the usual gap between the confident and the competent closed: everyone was confident. Experienced programmers believed AI had made them 20% faster; it had made them 19% slower (Becker et al., 2025). 

The feeling fools us into giving up instead of realizing a higher level. After ten minutes of assisted problem-solving, people solve less and give up sooner (Liu, Christian et al., 2026); fifteen minutes after adopting an AI draft, students reasoned worse than students who never had the tool (Liu, Guo et al., 2026); the Bastani students, tested without access, finished 17% below the children who never had it; forty-five days out, a ChatGPT study group remembered 57.5% of the material to the control's 68.5% (Barcauí, 2025). 

Anyone who skipped a week or two of maths will know it compounds: a unit not learned makes the next one harder. The balance to strike is not between using the tool and not using it. It is between what you want extended and what you want to own, for a child, almost everything is still in the second column. What matters is what sits in the rut between the problem and the tool. 

**habit makes it permanent.** Using the shortcut once primes you to use it again: people who Googled the hard questions went on to Google the easy ones they could have answered themselves (Storm, Stone & Benjamin, 2017). Ten years of a maths-practice platform show the creep at scale — after ChatGPT, time spent on the problems it could solve fell quarter after quarter, a cumulative 27% among college students, 31% in high school, 9% in middle school, nothing in fifth grade; and among the college students the divergence vanished entirely under proctoring (Rismanchian et al., 2026). Four weeks of AI prompts in a peer-review task left nothing behind: students relied on the help rather than learning from it, and when it was withdrawn their own strategies only partly filled the gap (Darvishi et al., 2024). 

A habit takes between eighteen days and, by extrapolation, eight months to set (Lally et al., 2010) — the whole of the honeymoon — and once set, across twelve thousand chatbot users' histories, usage habits are "overwhelmingly sticky" (Hicke & Tomlinson, 2026). The pre-AI record has the same shape in experts: endoscopists' detection rate on unaided colonoscopies fell from 28% to 22% within three months of working alongside AI (Budzyń et al., 2025); drivers with more GPS behind them had worse spatial memory and, in a thirteen-person follow-up, the heaviest users declined fastest (Dahmani & Bohbot, 2020); pilots kept their hands but stumbled on the thinking the autopilot had been doing for them (Casner et al., 2014). 

The boundary case is the calculator, which the meta-analyses cleared of harm — except, by one account, in the single grade where the offloaded skill was still being learned (Hembree & Dessart, 1986). Offloading a skill you own costs you slowly. Offloading a skill you are acquiring means you never acquire it. Children are on the wrong side of that line by definition.

**The discipline is the room.** though in the end we must bear responsibility for our destinies, for few children are self-directed; discipline came from the structure and incentives.

It worked because it was mandatory and because shortcuts were harder to access. Today's AI agents lives in the pocket, at the desk at at night, where the structure and incentive doesn't reach. Among the college students, the offloading disappeared when someone was proctoring. Homework was the retrieval practice, it is now an exercise in ctrl-v, or realistically speaking long holding the screen. 

There's been some attempts to move the discipline to the point of use, but it's a pretty new field, I intend to contribute to this. 



---

## II. What the science actually says

This is my understanding of what good learning looks like. 

**Retrieval beats restudy.** Adesope, Trevisan & Sundararajan (2017) meta-analyzed 272 effects across 188 experiments: practicing recall produced g = 0.51 over rereading; g = 0.93 over passive exposure. *Pulling* an answer from your head is the act that consolidates it. Recognition is just a nice feeling but doesn't do much. 

**Spacing beats massing.** Latimier, Peyre & Ramus (2021): g = 0.74 for distributed vs. massed retrieval. The optimal gap between reviews scales with how long you want to remember the thing (Cepeda et al., 2008).

**Self-explanation beats consumption.** Bisra et al. (2018), 69 effect sizes: g = 0.55. Forcing yourself to explain the material in your own words produces durable knowledge that passive reading cannot.

  > Mix similar kinds of problems instead of practising each kind separately. Brunmair & Richter (2019), 59 studies: g = 0.42. Switching between problem types helps you learn to tell them apart and choose the
  > right approach. This works best when the types are easy to confuse; when they are very different, practising each separately can work better.

**Formative feedback beats grading.** Black & Wiliam (1998): d = 0.4–0.7 for frequent low-stakes feedback that the learner uses to adjust strategy. Hattie places formative evaluation at d ≈ 0.9 — among the largest effects in education.

**Interactive beats passive.** Chi & Wylie's ICAP framework (2014): Interactive > Constructive > Active > Passive. Tutoring works not because of what the tutor *says* but because of what the tutor *forces the learner to say*.

**Mastery beats coverage — modestly.** Bloom's 1984 claim of 2 standard deviations from one-on-one tutoring plus mastery learning *does not replicate*. Nickow, Oreopoulos & Quan's 2024 meta-analysis of 96 RCTs put the real tutoring effect at ~0.37 SD. VanLehn (2011) found human tutoring at d = 0.79 and intelligent tutoring systems at d = 0.76 — a fraction of Bloom's headline, but meaningful, and notably *equal* between human and machine when the machine attends to interaction granularity.

The practices work together: recall before checking, return after a gap, explain in your own words, mix similar problem types, use feedback to correct mistakes, exchange questions and explanations, and practise until you can do it reliably. All require you to think and check your understanding. A good tutor makes this happen; a teacher responsible for thirty children has less room to do it for each one. You can build these practices into your own learning, with or without a teacher. Discipline, in this manifesto, means nothing more than running them when the tool would let you skip them
 


---

## III. The loop

How does it look in action?

Five verbs. This is what "discipline" cashes out to. Run them on repeat.

**Calibrate.** Find where you actually are. Write what you can explain unprompted. Record a baseline. Surface the questions you can't answer. You can't progresses from "I don't know what I know."

**Aim.** Pick one thing for the next two weeks. Specific enough to act on. With a "done when" you'd defend. The aim comes from the calibration — from the *edge* of what you currently know, not from someone else's syllabus.

**Practice.** Effort with feedback. Active recall before rereading. Self-explanation before checking. Worked examples while you're a novice; problem-solving as expertise grows (Sweller's expertise reversal — high assistance helps novices and hurts experts; Chen, Kalyuga & Sweller 2017). For embodied skills, the same logic applies off the page: drill the target, capture the attempt, get feedback.

**Reflect.** End every session by writing: one thing that clicked, one still-confused thing, one question to add to the open-questions list. The questions list is the engine. Tomorrow's aim is somewhere in it.

**Measure.** Periodically — weekly, monthly — return to your baseline and test. Not to grade yourself. To see whether the aim is still the right aim. Recalibrate.

---

## IV. The agent

On the scaffold side of the line: Wang et al.'s 2024 Tutor CoPilot RCT (900 tutors, 1,800 K–12 students) found AI-assisted tutors gave fewer answers and asked more guiding questions; their students were 4 points more likely to master a topic, rising to 9 points for students of lower-rated tutors. Kestin et al. (2025) reported roughly double the learning gains of an active-learning classroom from an AI tutor prompted to *scaffold rather than solve* — 194 students, two lessons, no retention measure. De Simone et al. (2025, World Bank, Nigeria) found six weeks of GPT-4 after-school tutoring produced 0.31 SD gains. These are the hopeful studies, and they are as thin as the harmful ones: short, and nobody tested what was left a month later. The direction is consistent. The sizes are not settled.

The pattern is consistent and not subtle:

- **Force constructive engagement** (ICAP). The agent's most important move is the one it withholds.
- **Fade with skill.** Sweller et al.'s 2025 meta-analysis of expertise reversal confirms: high assistance helps novices, hurts experts. A scaffold that never retreats becomes a crutch.
- **Calibrate confidence to competence.** Fernandes et al. (2025) showed people using AI gain output and lose accurate self-assessment; Steyvers & Peters (2025) lay out how far a model's uncertainty signalling diverges from human metacognition; a tool that rarely signals its own uncertainty plausibly feeds the drift. Confidence rises faster than skill. The agent must surface this gap, not paper over it.
- **Prefer hints over answers, questions over explanations** (Lepper & Woolverton's INSPIRE; Graesser's Expectation-Misconception Tailored dialogue; Chi 2009 on tutor-as-constructive-engagement-engine).

The agent is a tutor only when the *learner is doing the work*. Otherwise it is a service. There is a place for services. It is not learning.

---

## V. The artifacts

The workflow has a small physical footprint:

- A folder per skill.
- `goals.md` — the north star.
- `baseline.md` — where you started.
- `focus.md` — your aim this cycle.
- `journal/YYYY-MM-DD.md` — one per session.
- `questions.md` — what you don't yet understand.
- `progress.md` — measurements over time.

These files are not bureaucracy. They are the substrate on which the loop runs. *Reading them back is retrieval. Writing them is self-explanation. Comparing this week's journal to last is formative feedback.* The convention is the mechanism, made tangible.

The agent operates on these files. It can quiz you from `questions.md`, propose the next aim from the gap between `goals.md` and `progress.md`, run a practice session from `focus.md`, and refuse to close a session until you have written a reflection. Daily and weekly automations pull you back when you drift, gently — the system is opportunistic, not coercive. A skipped day is data, not failure.

---

## VI. What becomes negotiable

Solve the discipline and the paradigm loosens. Not before. While the tool in the pocket is a shortcut, the rational move is the one the well-funded schools are already making: take the screens out and keep the room exactly as it was — the deadline, the exam, the adult watching — because the room is the only discipline a child has. The schools that cannot afford that are leaning on the tool harder. So the tutor that was supposed to close the gap between children who could afford one and children who could not is, for now, reopening it: the rich buy the absence of the tool; the poor get the tool without the room.

But the room was never the point. One teacher, thirty children, a calendar, a syllabus paced to the median — that was the price of discipline when discipline had to be delivered in person, in bulk. Every one of those terms is downstream of the constraint. Once the loop runs for each child — an agent that withholds, files that make effort visible, a journal a teacher can read instead of an essay nobody wrote — the constraint is gone and each term comes up for renegotiation. Calibration before curriculum: find where this child actually is, then decide what is worth learning next. Sequence per child, not per cohort. Pace set by the edge of what the child knows, not by the calendar. The classroom keeps what classrooms are uniquely good at — shared inquiry, shared making, the social work of becoming a person — and gives up the part it only ever did because nothing else could. Children are the load-bearing case: if the structure holds for them, it holds.

It holds elsewhere too. **Tutoring** is the natural form: a good tutor's session *is* the loop, and the folder is the shared artifact between tutor and tutee. **Self-directed adult learning** is the default form — what most of us actually spend our lives doing — and the convention plus the agent makes it sustainable for the first time. **Research** is the loop on hard mode: vague goals, faint baselines, ambiguous measurements. The discipline of the workflow does not solve research; it survives it.

This is not a critique of teachers, and it is not a critique of schools. Bloom (1984) measured what the room gave up by being collective, and even with his number deflated it was real: Nickow, Oreopoulos and Quan's 96 trials put one-to-one tutoring near 0.37 standard deviations, and VanLehn found human and machine tutors within a hair of each other once the machine attended to the interaction. We now have the tutor. Aristotle was one child's. His word for what education builds was *hexis* — a settled disposition, laid down by doing the thing repeatedly until it is who you are. That is the whole question of this manifesto in his terms: which disposition is the tool in the pocket laying down — reaching, or retrieving? Answer that for one child and the rest is negotiable.

---

## VII. The promise

If you do this, here is what happens.

You stop confusing time-on-content with progress. You can answer "where am I" with evidence, not vibe. Your questions become better. The thing you are trying to learn becomes a stack of small, falsifiable claims you are working through, not a fog. Months in, you re-read your old journal entries and find someone who didn't know things you now know — and didn't know they didn't know them. That is the only signal that has ever counted.

The agent is not your teacher. It is the patient apprentice your tutor never had time to be — the instrument you play to make the mechanisms real.

And when this runs at scale — for the children who would otherwise lose most of what they were capable of to the gap between the syllabus and themselves, for the adults who would otherwise spend their lives outsourcing self-knowledge to whoever sold them the course — we get a generation back. Not as a metaphor. As the literal claim that a person whose learning runs the mechanisms reaches their actual edge in a fraction of the time, and the difference is theirs to spend on being human.

An Aristotelian education for every child: not the man, the arrangement — one tutor of the first rank, a curriculum of one, and the discipline to make the hours count.

The mechanisms are not negotiable.

The paradigm is.

---

## Appendix: the study that would settle it

Nobody has yet followed the same learners, with the tool taken away at intervals, across months of habitual use. Until someone does, the claim in section I is an argument assembled from pieces. This is the study that would test it, written so the claim can lose.

**The question.** Three stories fit what we know. *Masked cost:* the deficit is there from the first session and stays the same size; the honeymoon is only the assisted score. *Compounding:* the deficit is there from the first session and grows because each unlearned unit makes the next one harder — no habit required. *Habit:* general capacities — learning something new, judging your own accuracy, staying with a hard problem — hold up early and erode only after reaching for the tool becomes automatic. This manifesto bets on the third. The study is built so the data choose one.

**Who.** Fourteen-year-olds in first-year algebra, where the skill is still being acquired — the condition under which, by one account, the calculator studies found their only harm. Randomised by class section, blocked within teacher. Because most students already have an AI habit, everyone is measured for it before the study starts; the habit hypothesis is tested only in students who start with little or none, and the rest are a separate group in which no honeymoon is predicted.

**Four arms, identical platform, one button.** (A) No helper. (B) A new non-AI tool that cannot solve problems — a reference browser — to absorb novelty. (C) An AI that gives answers. (D) The same AI that only hints, behind two gates: write an attempt and a confidence rating before it unlocks, and after any item where you used it, solve the next one alone. Every arm does the same amount of unaided practice and rates confidence on the same items, so D's advantage can't simply be extra practice.

**When.** Fourteen weeks with the tool; a four-week withdrawal mid-semester (not over finals); a retest eight weeks after that. Long enough to pass the novelty dip, which in classroom tools runs from about week four to week ten, and the median time a new habit takes to set.

**What is measured, every two weeks, with phones in a box.**

- *General capacity*, on material that has nothing to do with the course — novel reasoning puzzles, a short lesson on an unfamiliar non-maths topic followed by a quiz — so a student who missed algebra unit 3 isn't penalised for it. Course content is scored separately.
- *Calibration* as discrimination — does confidence track which answers are right — not just "confidence minus score", which falls whenever scores do.
- *Effort tolerance*: time before skipping on several hard items.
- *Habit*, behaviourally: how often the helper is opened before anything is typed, on easy items the student can clearly solve. Reaching for help when you don't need it is the cleanest sign the reach has become automatic. A questionnaire alongside.
- *Cognitive habit off the tool*: a reflection task and a premature-closure task with no AI anywhere near it. If AI installs a shortcut disposition, it should show up here, not only as button-presses.

**How the data decide.** Three models compete — constant deficit, compounding deficit, deficit that starts after each student's own habit sets in — and the preregistered rule picks whichever fits best, so every outcome produces a verdict. Each student's habit date is checked against fake habit dates assigned to students in the no-helper arms; the "decline after habit" has to be bigger in the AI arm than in students who never had one. Habit counts only above a fixed threshold, set in advance. After withdrawal: if the gap closes, it was dependence; if it persists eight weeks later, it was atrophy.

**What would prove this manifesto wrong.** A deficit already present at week two, of the same size at week fourteen, unrelated to when each student's habit formed. Or a deficit that vanishes once you account for unlearned course content. Or arm D no better than arm C. Any of these and section I needs rewriting.

**Size and ethics.** About eighty sections, two thousand students, a year. Minors: parental consent, logging limited to school devices in school hours, results hidden from teachers until the end, help offered on demand throughout, and a monitoring board that stops arm C if its deficit passes the size the study was designed to detect.

**The version one teacher can run.** Not three classes, one per arm — that tests the classes, not the tool. Instead, in one class, each student gets the AI on some units and not others, randomised per student and unit. Weekly ten-minute unaided quizzes with a confidence rating; someone else scores them. It can't settle the question, but it will show whether a habit forms at all, how fast, and whether the gates stop it — and every number the full study needs to be planned honestly.

---

## Footnotes

**Empirical foundations**
- Adesope, O. O., Trevisan, D. A., & Sundararajan, N. (2017). *Rethinking the use of tests: A meta-analysis of practice testing.* Review of Educational Research, 87(3). [link](https://journals.sagepub.com/doi/abs/10.3102/0034654316689306)
- Bisra, K., Liu, Q., Nesbit, J. C., Salimi, F., & Winne, P. H. (2018). *Inducing self-explanation: A meta-analysis.* Educational Psychology Review, 30(3). [link](https://link.springer.com/article/10.1007/s10648-018-9434-x)
- Black, P., & Wiliam, D. (1998). *Inside the Black Box: Raising Standards Through Classroom Assessment.* Phi Delta Kappan. [PDF](http://allianceforlearning.co.uk/wp-content/uploads/2017/03/William-and-Black-Inside-the-Black-Box.pdf)
- Bloom, B. S. (1984). *The 2 Sigma Problem.* Educational Researcher, 13(6). [link](https://journals.sagepub.com/doi/10.3102/0013189X013006004)
- Brunmair, M., & Richter, T. (2019). *Similarity matters: A meta-analysis of interleaved learning.* Psychological Bulletin. [link](https://pubmed.ncbi.nlm.nih.gov/31556629/)
- Cepeda, N. J., Vul, E., Rohrer, D., Wixted, J. T., & Pashler, H. (2008). *Spacing effects in learning.* Psychological Science, 19(11). [PDF](https://laplab.ucsd.edu/articles/Cepeda%20et%20al%202008_psychsci.pdf)
- Chen, O., Kalyuga, S., & Sweller, J. (2017). *The expertise reversal effect as element interactivity.* Educational Psychology Review. [link](https://link.springer.com/article/10.1007/s10648-016-9359-1)
- Chi, M. T. H., & Wylie, R. (2014). *The ICAP framework.* Educational Psychologist. [link](https://onlinelibrary.wiley.com/doi/abs/10.1111/cogs.12626)
- Dunlosky, J., Rawson, K. A., Marsh, E. J., Nathan, M. J., & Willingham, D. T. (2013). *Improving students' learning with effective learning techniques.* Psychological Science in the Public Interest, 14(1). [link](https://journals.sagepub.com/doi/abs/10.1177/1529100612453266)
- Fiorella, L., & Mayer, R. E. (2016). *Eight ways to promote generative learning.* Educational Psychology Review, 28(4). [link](https://link.springer.com/article/10.1007/s10648-015-9348-9)
- Latimier, A., Peyre, H., & Ramus, F. (2021). *A meta-analytic review of the benefit of spacing out retrieval practice.* Educational Psychology Review. [link](https://link.springer.com/article/10.1007/s10648-020-09572-8)
- Macnamara, B. N., Hambrick, D. Z., & Oswald, F. L. (2014). *Deliberate practice and performance: A meta-analysis.* Psychological Science, 25(8). [link](https://pubmed.ncbi.nlm.nih.gov/24986855/)
- Nickow, A., Oreopoulos, P., & Quan, V. (2024). *The impressive effects of tutoring on PreK–12 learning: A meta-analysis.* AERA Open / NBER w27476. [link](https://www.nber.org/papers/w27476)
- Sweller, J. (2023/2025). *Cognitive load theory revisited; expertise reversal meta-analysis.* Educational Psychology Review. [link](https://link.springer.com/article/10.1007/s10648-023-09817-2)
- VanLehn, K. (2011). *The relative effectiveness of human tutoring, intelligent tutoring systems, and other tutoring systems.* Educational Psychologist, 46(4). [link](https://eric.ed.gov/?id=EJ946764)

**AI-assisted learning (2024–2026)**
- Bastani, H., et al. (2025). *Generative AI without guardrails can harm learning.* PNAS. [link](https://www.pnas.org/doi/10.1073/pnas.2422633122)
- De Simone, M., et al. (2025). *Chalkboards to chatbots: Evaluating GPT-4 as a tutor in Nigeria.* World Bank WP 11125. [link](https://eric.ed.gov/?q=source:%22World+Bank%22&id=ED676624)
- Fan, Y., et al. (2025). *Beware of metacognitive laziness: Effects of generative AI on learning.* British Journal of Educational Technology. [link](https://bera-journals.onlinelibrary.wiley.com/doi/abs/10.1111/bjet.13544)
- Kestin, G., et al. (2025). *AI tutoring outperforms active learning.* Scientific Reports. [link](https://www.nature.com/articles/s41598-025-97652-6)
- Lee, H.-P., et al. (2025). *The impact of generative AI on critical thinking.* CHI 2025 / Microsoft Research. [link](https://dl.acm.org/doi/full/10.1145/3706598.3713778)
- Wang, R. E., et al. (2024). *Tutor CoPilot: A human–AI approach for scaling real-time expertise.* Stanford. [arXiv](https://arxiv.org/abs/2410.03017)

**Tutor mechanism**
- Graesser, A. C., et al. (2014). *AutoTutor and family: A 17-year review.* IJAIED. [link](https://link.springer.com/article/10.1007/s40593-014-0029-5)
- Lepper, M. R., & Woolverton, M. (2002). *The wisdom of practice: Lessons learned from the study of highly effective tutors.* In *Improving Academic Achievement.*
**Offloading, habit and the honeymoon**
- Barcauí, A. (2025). *ChatGPT as a cognitive crutch: Evidence from a randomized controlled trial on knowledge retention.* Social Sciences & Humanities Open. [link](https://doi.org/10.1016/j.ssaho.2025.102287)
- Becker, J., Rush, N., Barnes, E., & Rein, D. (2025). *Measuring the impact of early-2025 AI on experienced open-source developer productivity.* METR, arXiv preprint. [link](https://arxiv.org/abs/2507.09089)
- Budzyń, K., et al. (2025). *Endoscopist deskilling risk after exposure to artificial intelligence in colonoscopy.* Lancet Gastroenterology & Hepatology. [link](https://doi.org/10.1016/s2468-1253(25)00133-5)
- Casner, S. M., Geven, R. W., Recker, M. P., & Schooler, J. W. (2014). *The retention of manual flying skills in the automated cockpit.* Human Factors. [link](https://doi.org/10.1177/0018720814535628)
- Dahmani, L., & Bohbot, V. D. (2020). *Habitual use of GPS negatively impacts spatial memory during self-guided navigation.* Scientific Reports. [link](https://doi.org/10.1038/s41598-020-62877-0)
- Darvishi, A., Khosravi, H., Sadiq, S., Gašević, D., & Siemens, G. (2024). *Impact of AI assistance on student agency.* Computers & Education. [link](https://doi.org/10.1016/j.compedu.2023.104967)
- Fan, M., & Chang, P. (2026). *Telling students to evaluate does not make it happen: Task stage, offloading tendency, and error detection in AI-assisted student writing.* Behavioral Sciences. [link](https://doi.org/10.3390/bs16091671)
- Fernandes, D., et al. (2025). *AI makes you smarter but none the wiser: The disconnect between performance and metacognition.* Computers in Human Behavior. [link](https://doi.org/10.1016/j.chb.2025.108779)
- Fischer, M., Rau, H. A., & Rilke, R. M. (2026). *AI tutoring enhances student learning without crowding out reading effort.* IZA DP 18338 / SSRN, working paper. [link](https://doi.org/10.2139/ssrn.5992341)
- Grinschgl, S., Papenmeier, F., & Meyerhoff, H. S. (2021). *Consequences of cognitive offloading: Boosting performance but diminishing memory.* Quarterly Journal of Experimental Psychology. [link](https://doi.org/10.1177/17470218211008060)
- Hembree, R., & Dessart, D. J. (1986). *Effects of hand-held calculators in precollege mathematics education: A meta-analysis.* Journal for Research in Mathematics Education. [link](https://doi.org/10.2307/749255)
- Hicke, R. M. M., & Tomlinson, K. (2026). *Adopt ≠ Adapt: Longitudinal analyses of LLM conversations in the wild.* arXiv preprint. [link](https://arxiv.org/abs/2605.29018)
- Kool, W., McGuire, J. T., Rosen, Z. B., & Botvinick, M. M. (2010). *Decision making and the avoidance of cognitive demand.* Journal of Experimental Psychology: General. [link](https://doi.org/10.1037/a0020198)
- Kosmyna, N., et al. (2025). *Your brain on ChatGPT: Accumulation of cognitive debt when using an AI assistant for essay writing task.* arXiv preprint. [link](https://arxiv.org/abs/2506.08872)
- Lally, P., van Jaarsveld, C. H. M., Potts, H. W. W., & Wardle, J. (2010). *How are habits formed: Modelling habit formation in the real world.* European Journal of Social Psychology. [link](https://doi.org/10.1002/ejsp.674)
- Liu, G., Christian, B., Dumbalska, T., Bakker, M. A., & Dubey, R. (2026). *AI assistance reduces persistence and hurts independent performance.* arXiv preprint. [link](https://arxiv.org/abs/2604.04721)
- Liu, C., Guo, J., Gao, R., Chen, X., Zhu, Q., & Chang, P. (2026). *Borrowed or kept? How self-generation-first and direct-adoption AI workflows shape immediate unaided reasoning.* Frontiers in Psychology. [link](https://doi.org/10.3389/fpsyg.2026.1910545)
- Melanou, C., Beege, M., & Kimmig, M. (2026). *Generative AI and learning dynamics in higher education: A longitudinal empirical study.* Journal of Computer Assisted Learning. [link](https://doi.org/10.1002/jcal.70322)
- Rismanchian, S., Uzun, H., Matayoshi, J., Cosyn, E., & Kurd-Misto, E. (2026). *Faster completion, less learning: Generative AI reduced study time on math problems and the knowledge they build.* arXiv preprint. [link](https://arxiv.org/abs/2605.21629)
- Rodrigues, L., et al. (2022). *Gamification suffers from the novelty effect but benefits from the familiarization effect: Findings from a longitudinal study.* International Journal of Educational Technology in Higher Education. [link](https://doi.org/10.1186/s41239-021-00314-6)
- Soderstrom, N. C., & Bjork, R. A. (2015). *Learning versus performance: An integrative review.* Perspectives on Psychological Science. [link](https://doi.org/10.1177/1745691615569000)
- Steyvers, M., & Peters, M. A. K. (2025). *Metacognition and uncertainty communication in humans and large language models.* arXiv preprint. [link](https://arxiv.org/abs/2504.14045)
- Storm, B. C., Stone, S. M., & Benjamin, A. S. (2017). *Using the Internet to access information inflates future use of the Internet to access other information.* Memory. [link](https://doi.org/10.1080/09658211.2016.1210171)

Appendix 

Honesty about the evidence. Most of what is above comes from single sessions, small samples, or studies that never took the tool away. A semester-long study with a control found neither harm nor help (Melanou et al., 2026). One working-paper trial found unrestricted access beat restricted (Fischer et al., 2026). The EEG study (Kosmyna et al., 2025) rests on eighteen people at the decisive crossover and is not peer-reviewed. The survey literature on both sides measures what people say about their own thinking, which is worth nothing here. No study has yet followed the same learners with unaided tests across months of habitual use; the arc in this section is assembled from pieces, not observed whole. Two things survive the honesty. The mechanism is older than the tool and does not need a trial: remove the effort and you remove what the effort was building. And one moderator shows up in every study that looked for it, including the three that randomised it (Bastani et al., 2025; Fan & Chang, 2026; Liu, Guo et al., 2026): when the student does the thinking — commits an attempt first, or judges the tool's output instead of accepting it — the cost largely disappears. That is the discipline clause, and it is the best-supported sentence in this manifesto. The appendix is the study that would settle the rest.

The labs are working on it. Tutor modes, study modes, models trained to ask rather than tell — some of the harm will attenuate at the model layer, and Bastani's guardrailed "GPT Tutor" shows the shape: it largely removed the harm and, as far as the abstract reports, nothing more. Necessary, not sufficient. A model that withholds the answer is one tab away from one that doesn't, and the child chooses the tab. The discipline cannot live in the model. It has to live in the structure around the child — which is what the rest of this is.
</article>
