# ASR Project

This project should be done by a group of up to 6 people. Create a group under Project.

## What you need to do

**Design an application that uses voice inputs.**

The application should make use of ASR capabilities. We provided tutorials on how to use Kaldi, which you should use as the main ASR engine. The main application can be written in any programming language. There is no requirement for the form of the application (web-based, stand alone app, mobile app, etc.).

Remember that the Acoustic Model is weak, so keep the app simple.

**Design the LM and Lexicon**

Based on the application, design the LM (the sentences you expected to be used), and the lexicon (the words you expected to be used). Use the techniques learned in class to reduce the perplexity.

Tip: List all possible sentences your app should be able to handle (you may write a script to do so). Then, divide the sentences into train, dev, and test set. See the section below for more details.

**Design a dev and test set**

Record 10 sentences/person for the dev set. 10 sentences/person for the test set. This should come from your dev and test set for the LM section (can be just a subset). You will use these recordings to test the ASR performance.

In machine learning, we usually divide our data into training, dev, and test sets. The training set is used to train the model. You have already created the training set in HW3. The dev set is usually used to tune the parameters of the model such as the the language model weight, the word insertion penalty, the size of the model, and the LM parameters (n-gram order, interpolation weight). After the parameters are tuned on the dev set, the parameters are applied to the test set to measure actual performance. This is to mimic the real usage scenario because you do not know what you will get as your test data, so the parameter can only be tuned on your best guess of what the test data will be.

In general, the test set should be collected from the target users in real scenarios. For the project, we do not require that. However, the test set should still reflect the usage as close as possible.

The sentences need not be the same for every person. The test/dev set should be designed to cover the use cases of the app.

One way to approach this is to first design a set of sentences for all possibilities. Then, assign each sentence to different people and test/dev sets. Which same sentences are expected to be spoken by multiple people? Which same sentence should be in both sets?

Measure the performance. If the performance is too bad (more than 30% WER but you should aim for 10-20% WER), you can 1) tweak the LM and Lexicon, 2) simplify the app by removing functionalities, redo the LM, Lexicon, dev set, and test set.

**Build the app**

Follow the tutorials to build the app. The application should be ready for demo on the last day of class

**Presentation**

On May 4th, we will have each team do a 10-15 minutes presentation about their app and design process. The presentation should also included what you tried, what worked, what did not work. It should also include a short demo. The instructors will also be testing your demo.

**Report**

The report will be due around final exam week (exact date still undecided). Read the points distribution to see what is expected in the write-up.

**Tutorials**

[Kaldi](https://github.com/ekapolc/ASR_classproject)

## Points distribution (30 points total + at most 10 extra points)

Presentation and demo (10 points)
Presentation (5 points)
Demo (5 points)
Documentation (20 points)
Scope design (5 points)
- Why would this be a good application for ASR?
- Describe your design process. What kind of sentences are used and why?
- Dev and test set design (5 points)
- Describe the dev and test set. How are the scripts generated and how are they split for different people?
- Does the dev and test set reflects the scope?
- Does the test set represents real usage?
LM implementation (5 points)
- Describe the LM and vocabulary.
- Describe the training set for the LM.
- How did you train the LM? Described what techniques are used, and what effect do they have on the perplexity.
Evaluation of the ASR (5 points)
Report WER on dev and test.
- Report Task completion rate (The percentage of commands that the system responds correctly. The sentence can have errors, but the main content can still be correct.)
Error analysis. What kind of mistakes are common? What words are often mistaken for another word? Does the WER changes by speaker, by gender?
Extra points (At most 10 points)
- 2 points for the group winning the popular vote
- 2 points for the group with the most number of sentence types (number of functions). The group should also maintain the feasibility of the application in terms of performance
- Implement some cool features. At most 5 points per feature. Examples:
- Gowajee continuous listening wake word (instead of a button for push-to-talk)
- Conversation management (Rule-based)
- Good usage of confirmation, or asking for the user to repeat the command
- An application that uses more than one LM and HCLG
Background noise removal (removing the music noise playing in the background for the music app)
