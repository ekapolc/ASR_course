# HW3 Corpus Collection

In lecture 1, we learned about ASR-enabled systems and what to consider when making ASR applications. In homework 1, we learn about measuring errors in ASR, and what kind of errors to expect when applying ASR tasks in the real world. In this assignment, we will start considering the process to actually create such a system, in particular, a personal home assistant such as the [Amazon Echo]( https://www.youtube.com/watch?v=sulDcHJzcB4) or [Google Home]( https://www.youtube.com/watch?v=2KpLHdAURGo ).

Since our machine learning models are data-driven, in this homework we will start the collection of such data. This part of the homework can be done in group of up to 6 people (Create a group in myCourseVille under HW3). Keep in mind that many of the things you consider in this homework might be useful for the project, so you should form the group with the final project in mind. Note that the data you collected in this homework will be shared with everyone in the class (and possibly future classes of ASR). All the recordings should be in .wav format with 16kHz sampling rate and 16 [bit depth](https://en.wikipedia.org/wiki/Audio_bit_depth) .

**Task 1**: In general, a personal assistant can do many tasks, but to keep things simple, you will need to limit the scope to a smaller set. Come up with a good application that is fit to use with ASR technology. For example, let’s make a home assistant that can tell which bus to take.

-- Explain your scope in the writeup

**Task 2**: Record a wake phrase (trigger word, keyword, or hotword depending on the brand). Since these devices are often placed in an open environment, it must have a way to differentiate between a random conversation and an order given to them. These devices are always listening for a particular phrase in order to start processing your speech input. For example, Echo uses “Alexa” while Google uses “Okay Google.” In this class we will use:

“โกวาจี”

Record each person saying “โกวาจี” Name the file <Gender M/F><student ID>_<sentence ID>.wav where sentence ID is 0000. For example, if you are a female with student id 9999999999, name the file

F9999999999_0000.wav
It is recommended to use [Audacity](http://www.audacityteam.org/) for recording  Watch out for clipping in your audio. Clipping occurs when the intensity of the recorded sound exceeds the number representation (overflow). For more details see [here](https://www.uwec.edu/Help/Audacity/track-clip.htm).

Next, record each person saying “โกวาจี” in a sentence that is related to your application name, such as “โกวาจี รถ สาย แปด จะ มา ภาย ใน อีก กี่ นาที” Use sentence ID 0001 for this file.

-- Zip the files, upload the zipped file somewhere, provide a "public link" in the writeup

**Task 3**: Come up with 100 other sentences that users can say to the device for your application. Try to cover as many basic sentence structure as possible. You may use simple templates (Go to X), but do not repeat more than 5 times for each template. Separate each word with space. Label the sentences with ID 0002-0101. Create a text file “transcript.txt” in UTF8 encoding with the sentences. In our bus example:

====transcript.txt====
```
0000 โกวาจี

0001 โกวาจี รถ สาย แปด จะ มา ถาย ใน อีก กี่ นาที

0002 จะ ไป สนามหลวง นั่ง รถ สาย อะไร ดี

0003 สาย ห้า สิบ วิ่ง ถึง ที่ ไหน

0004 สาย ห้า สิบ จาก นี่ ถึง เตาปูน ราคา เท่า ไหร่

0005 ใช้ เวลา กี่ นาที ถ้า จะ ไป สีลม

0006 ใช้ เวลา กี่ นาที ถ้า จะ ไป จุฬา

0007 ใช้ เวลา กี่ นาที ถ้า จะ ไป พารากอน

0008 ใช้ เวลา กี่ นาที ถ้า จะ ไป หมอชิต

0009 ใช้ เวลา กี่ นาที ถ้า จะ ไป เซ็นทรัล ลาดพร้าว

0010 รถ สาย แปด จะ มา ถาย ใน อีก กี่ นาที

0011 รถ สาย แปด จะ มา หรือ ยัง

...

0101 เรา ควร จะ นั่ง สาย แปด ดี ไหม
```
================
-- Upload the text file somewhere and provide a "public link" in the writeup

**Task 4**: Record each person saying each sentences. Name the file according to the sentence ID. A set of speech data used for model training and testing is usually called a speech corpus.

-- Zip the files, upload the zipped file somewhere, provide a "public link" in the writeup

**Task 5**: For each Thai sound covered in class, give one example word from your sentences that contains the sound. If there is none, state so. Ignore tones.
```
p ไป

t ต้นสาย

c จะ

k ก่อน

z อีก

....

ng  <none>
```

-- Write your answer in the writeup

In general, when people design a speech corpus, it is important to cover all the sound patterns in the language in order to properly train the statistical model. A set of sentences that covers the list of sounds presented in the natural language is called a "phonetically balanced set". For this homework, you are not required to do such thing.

**Extra**: Besides creating a speech corpus for ASR, can you think of other case where a phonetically balanced set can be useful?

-- Write your answer in the writeup
