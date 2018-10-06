# Eyelink-blinking-data-processing
This is a Matlab function that could recognize and eliminate Eyelink data during blinking and squinting based on pupil size. In the meanwhile, this function can recognize some situations that may influence your results which are listed below:

0. Well play! No eye blink detected;
1. The pupil size is a little small, which may because the experiments not operated in a strict darkness room (you can adjest the threshold if you can find where is it :-);
2. Eye closeing in recording ending;
3. Eye closeing at the begining of recording;
4. The pupil size may be sudden increasing / decreasing;
5. At least one peak within/just before/soon after the eye blink;
6. Not firmly closeing in eye blink or just squinting;
7. **Too long time with eye closing (the eliminated data more than 1/5 in total);**
8. **Have a minimum of pupil size & squinting detected (less than 1000 ms);**
9. **Still have unknow rifts in x and y pixel, that could be caused by poor focusing by Eyelink or others like CR or pupil threshold.**
10. **Still lots of points outside the screen. It may be caused by not correctly calibration & validation, or maybe the subject squint for too long (>1s).**
11. Some unknown noisy points are detected (sudden decrease to zero for ~1 to 20ms, discontinuously), not sure why they happened.

You need global SCREEN.width and SCREEN.height as screen width and height in pixel, 1280x1024 in default.
The function BlinkNoisyPurify.m can purify the data in multiple times untill no more junk data are detected. The function blink_treatment_pupil1.m can only purify once, that continuesly blinking in several times may not be fully purified.

For any demand and suggestion, please feel free to comment in [issues](https://github.com/softdrinks/Eyelink-blinking-data-processing/issues). Anyone who wanna more discussion on how to process the data from Eyelink are very welcome!

Here are two samples: 
Blue lines present the pupil size; green lines are for X axis pixel position and red lines for Y axis pixel position. X axis in graphs indicate the time (ms), Y axis indicate pixel unit.

**Sample 1:**
<br>
Single purifying (before)

![sample_1_before](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample1_before.jpg)
<br>
<br>
Single purifying (after)

![sample_1_after](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample1_after.jpg)
<br>
<br>
**Sample 2**
<br>
Multiple puritying (before)

![multi_before](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample2_1st.jpg)
<br>
<br>
Multiple purifying (first time)

![multi_first_time](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample2_2nd.jpg)
<br>
<br>
Multiple purifying (second times)

![multi_after](https://github.com/softdrinks/Eyelink-blinking-data-processing/blob/master/sample/sample2_after.jpg)
