---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "The Effects of Delay on Theremin Pitch Acuity"
subtitle: ""
summary: ""
authors: [suzanne]
tags: [music, science, theremin]
categories: [Papers]
date: 2000-03-15T00:00:00-08:00
lastmod: 2023-02-27T21:42:10-08:00
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

The theremin is an electronic instrument invented early in the 20th century.  What makes the theremin interesting is its interface, which allows you to play the instrument without touching any keys or knobs.  Two antennae on either side of the box, one for pitch and the other for volume control, detect the distance to the performer's hand using capacitance.

Playing a recognizable melody on the theremin requires a combination of muscle memory, visual interpretation of the distance from the hands to the antennae, and aural feedback.  Suzanne noticed that her ability to play the theremin was decreased when she monitored it through an amplifier as opposed to headphones.  Poor room acoustics and heavy processor effects also seemed to negatively affect theremin performance accuracy.

This problem has parallels with other performance situations. While performing in rock bands at clubs, Dave noticed that he had difficulty hearing his guitar clearly over the other instruments. He found it especially troublesome at clubs with poor PA systems or lazy sound men, and also when a lot of  delay or flange was added to his sound; he couldn't tell whether he was in tune or bending strings correctly.

We isolated delay as the experimental factor and formed a hypothesis that a delay in aural feedback would significantly interfere with subjects' performance ability on the theremin.  They would be less accurate in finding the correct pitch with the delay in effect.  Moreover, if they did find the pitch with delay, it would take them longer by an amount greater than the actual time of the delay.

When looking for research papers using the online PsychINFO database, we didn’t find very many experiments that investigated this type of performance problem, or the haptic issues involved.  However, a few of the experiments investigated pitch memory in way that was relevant to our experiment.  The most helpful of these was an experiment conducted by Lois Elliot at the Central Institute for the Deaf, which showed that the presence of an interpolated tone between two other tones interfered with short term pitch memory.  Subjects were asked to determine whether the final tone was higher or lower in pitch than the first one.  Our subjects will produce incorrect tones before they are able to find the correct one, and these tones may also decrease their accuracy.

Perry Cook’s collection of Psychoacoustics essays, _Music, Cognition and Computerized Sound_, contains a good deal of useful information. The idea of an immediate sensory buffer introduced by Daniel Levitin is important, as this seems to be the most likely way that our subjects would store the test tones we play for them.  Mr. Levitin also suggests that muscle memory is both long term, and not very accurate; this would mean that our subjects would be unlikely to develop any useful muscle memory during our short experiment. Brent Gillespie’s chapters on haptics are also relevant to our experiment. His description of the player/instrument  feedback system applies, particularly the section on how a musician might use feedback to help learn an unfamiliar instrument. These haptic issues will be discussed in further detail in the experiment analysis and conclusion.

The experiment we designed to test the delay hypothesis is straightforward.  Each subject answered a few questions concerning their musical background, since we could only get meaningful results from those capable of holding a pitch in memory.  Then they were asked to practice with the theremin, in order to become somewhat acquainted with its pitch range and dynamic feel.  After a few minutes they put on headphones and stood on markings which ensured all subjects were the same distance from the pitch antenna and couldn't use the volume antenna.  When they were ready, the series of trials began.  Each trial started with a random pure tone within the theremin's usable 4.5 octave range.  When the pure tone ended, each subject was expected to try to hit the same pitch in any octave and hold it for as long as the tone had played, guaranteeing that they didn't just pass through it.  A random half of the trials delayed the theremin's signal through the headphones, while the other half left the signal unchanged.  After a certain amount of time the trial ended, either with a hit or a miss, and noise was briefly played before the next trial began.  A computer was programmed to synthesize the tones and noise, as well as analyze and delay the theremin's signal.  Each subject was presented with 20 trials, 1 second of the pure tone, 0.5 seconds of delay if there was any, 14 seconds to match the pitch, and 2 seconds of noise.  We tried to tune these constants to reasonable values and synchronize the volume of the pure tone and the theremin before conducting the experiment.  Subjects usually thought that the experiment was interesting.

The accompanying graphs summarize our subjects' performance.  For the most part, our results supported our hypothesis.  Eight out of nine subjects were correct less often and  took longer to hit the pitch in the delayed trials. Compared to undelayed trials, 1.33 fewer delayed trials were correct, and they took 2.66 more seconds to hit and hold the right pitch .

There seemed to be no improvement in performance over time throughout the trials.  We thought that people might get used to the task and perform better towards the end of their trial, but that turned out not to be the case.  Another way of testing how people might learn to deal with delay would be to run successive tests on the same subject, and see how performance changed.  However, this would have made for either several sessions for each subject, or one long session, which we couldn’t do in this situation.

Without exception, musicians performed better than non musicians.  This isn’t surprising; however, more study would be needed to determine exactly why this is the case.  It could be from the greater pitch acuity, or from greater performance experience.  Examining whether vocal musicians performed as well as those who played an instrument might provide some useful insight to this issue.

The primary problems with the experiment were how to control parameters.  Issues such as whether we should test musicians, non-musicians, or both, whether we should play the test tone continuously or not while the subjects attempted to match the pitch, the range of pitches we should use, and whether to use a pure sine tone, or more musical tones were all difficult to resolve.  There also may have been a few flaws with our procedures.  One such flaw was that we played all tones at the same volume, regardless of pitch, but because of the characteristics of the human ear, the lower tones sounded softer.  Unfortunately, we didn’t have the time to implement any loudness curves in our testing code.  Another possible problem was that we only tested nine people; our results may have been a bit more convincing and given us more useful information if we had tested more subjects.

As we suspected, the presence of delay in auditory feedback causes a significant problem in performance of the theremin.  The fact that our subjects were so often unable to find the correct pitch at all suggest that they are using an inappropriate anticipatory control strategy.  In his chapter on haptic manipulation, Brent Gillespie gives an example of someone picking up an empty cup, and expecting it to be full; this seems fairly similar to the sensation our subjects felt when moving their hand, only to not hear the pitch adjust in a predictable manner.  The fact that musicians dealt with this better may be because they have experience dealing with similar musical situations; they may have to adjust their normal control strategies if they fall out of tune, their band speeds up the tempo, or they are forced to use a different instrument than they normally play.

A lot more could be done with this experiment to yield greater results.  Right now, the only haptic feedback involved is based on body position and motion (kinesthesia).  Letting some subjects use a rubber band wrapped around their hand and the theremin would introduce an element of touch as well.  Any difference in performance between subjects using the rubber band and those who do not would shed light on the role of taction vs. kinesthia in this type of situation.  Another extension would be to examine the actual trials of our subjects, as opposed to the results; one could look for patterns in how subjects attempted to find the right note.  They might use a series of smaller and smaller motions alternating around the right pitch, or they may gradually approach it from one side, or perhaps become erratic when experiencing delay.  An analysis of this type of data may give insight as to how people learn unfamiliar interfaces, as well as how they try to reproduce a pitch in the real world they they only "hear" in their head.  A third extension might be to use different amounts of delay and see how the performance and adaptive measures of our subjects differ.  At 0.1 seconds of delay, they may still be able to use auditory feedback control, while at a full second of delay, they might choose to use only haptic feedback, the visual position of their hand, or some other, unexpected method of compensation.  Finally, the experiment could be conducted with different instruments in order to determine the redundancy of various musical interfaces.  A graph of their relative dependence on aural feedback would probably place the theremin at the top.

Suzanne Aldrich and David Chisholm \
Prof. Jonathan Berger \
Music 151 \
Stanford University \
March 15, 2000