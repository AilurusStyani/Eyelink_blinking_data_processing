# Eyelink-blinking-data-processing
It is a Matlab function that could recognize and eliminate Eyelink data during blinking and squinting. In the meanwhile, this function can recognize some situations that may influence your results that are listed below:

0. no eye blink detected;
1. small pupil size, the experiments may not operated in a strict darkness room;
2. eye closeing in end;
3. eye closeing in recording begining;
4. sudden increase / decrease;
5. at least one peak within/just before/soon after the eye blink;
6. not firmly closeing in eye blink or just squinting;
7. A long time with eye closing (> 1/5 of totle);
8. have a minimum of pupil size & squinting detected;
9. still have unknow rifts in x and y pixel, that should be caused by not regorous operation or other unknown conditions.
10. Still lots of points outside the screen. It may be caused by no correctly calibration & validation, or may be the subject squinting for too long (>1s).
11. Still have unknown noisy point (sudden decrease to zero for ~1 to 20ms, discontinuously), this maybe caused by Eyelink.

You need global SCREEN.width and SCREEN.height as screen width and height in pixel, 1280x1024 in default.
The function BlinkNoisyPurify.m can purify the data in multiple times unless no more blink points were detected. The function blink_treatment_pupil1.m can only purify once, that continuesly blinking with several times may not be fully purified.

Here are two samples:

![sample_1_before](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample1_before.jpg)

Single purifying (before)

![sample_1_after](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample1_after.jpg)

Single purifying (after)


![multi_before](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample2_1st.jpg)

Multiple puritying (before)

![multi_first_time](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample2_2nd.jpg)

Multiple purifying (first time)

![multi_after](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample2_after.jpg)

Multiple purifying (after)
