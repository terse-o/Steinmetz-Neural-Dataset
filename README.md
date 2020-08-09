# Steinmetz-Neural-Dataset
Encoding impact of attention on neuronal modulation and behavior

This project was my introduction to neuroscience through the Neuromatch Academy summer school. In this project we worked with the Steinmetz dataset. It was an experiment conducted with 10 different mices. A total of 39 sessions. Each session containing varying number of trials for each mice.

<p align="center">
<img src="https://github.com/terse-o/Steinmetz-Neural-Dataset/blob/master/Task.JPG?raw=true" width="400" height="250" />
</p>
<p align="center">
    <em>Fig 1. 2-FAC Task</em>
</p>

**Task:**
The mice was trained to perform a *2 Alternative Forced Choice Task*, wherein it was head-fixed in front of a screen with a wheel in front of it. The mice was presented with stimulus of varying contrasts on either or both sides of the screen. The wheel was synched to move the stimulus. The mice was rewarded for moving high contrast stimulus to center of the screen. For every wrond response the mice was punished with a noise signal. The responses were categorized in 3 groups: *Go, No-Go, Miss trials* depending on its response to different stimuli. There were 2 sets of trials: *Active* (where the mice got a feedback for its response) and *Passive* (where mice only had to observe the stimuli without any response).

**Question:**
We decided to explore the impact that attention has on neural activities through all brain regions on unique neuron level. Attention is not a distinct binary process (Paying attention or not paying attention), rather is continuous (We are always paying attention to something). We hypothesized, in order to observe the impact of attention we need to develop an encoding model for varying stimuli and trials:

**Hypothesis 1:** Explore change in neural spiking activity through all brain regions for different combinations of stimulus. Further hypothesizing *harder to differentiate stimuli (For example, 0.75 - right & 0.5 - left or same contrasts on both sides) would require more attention*.

**Hypothesis 2:** Explore change in neural spiking activity through all brain regions for active and passive trials. Suggesting, *active trials (more engagement with wheel movement) would require more attenion as compared to passive trials (mere observation)*.

**Analysis:**
Exploratory data analysis was done to make sense of high-dimensional data. A 2-way ANOVA was performed to identify the significance of activity in each neuron for varying stimulus contrasts. The entire 250 bin trial was broken down into 5 epochs representing various steps of trial (like visual stimulus onset, analysis window, go cue, reponse, feedback).
Core statistical methods were used to calculate mean firing rate, variance and variability for each unique neuron across all brain regions through all trials for each mice. Later a line graph was plotted for each mice for individual neuron activity through 5 epochs. A scatter plot was created for mean firing rate v/s variance and a regression line was fit through it to observe a linear relationship for both active and passive trials.
