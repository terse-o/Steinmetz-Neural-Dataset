# Steinmetz-Neural-Dataset
**Encoding impact of attention on neuronal modulation and behavior**

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

<p align="center">
<img src="https://github.com/terse-o/Steinmetz-Neural-Dataset/blob/master/Summed%20Spikes.JPG" width="250" height="400" />
</p>
<p align="center">
    <em>Fig 2. Summed Spikes Distribution for Responsive Neurons</em>
</p>

Core statistical methods were used to calculate mean firing rate, variance and variability for each unique neuron across all brain regions through all trials for each mice.


<p align="center">
<img src="https://github.com/terse-o/Steinmetz-Neural-Dataset/blob/master/Neuron_df.JPG" width="250" height="125" />
</p>
<p align="center">
    <em>Fig 3. Mean, Variance, Variability of unique Neurons</em>
</p>

Later a line graph was plotted for each mice for individual neuron activity through 5 epochs. 

<p align="center">
<img src="https://github.com/terse-o/Steinmetz-Neural-Dataset/blob/master/Active.JPG" width="275" height="200" />
<img src="https://github.com/terse-o/Steinmetz-Neural-Dataset/blob/master/Passive.JPG" width="275" height="200" />
</p>
<p align="center">
    <em>Fig 4. Line Graph for Active & Passive Trials</em>
</p>

A scatter plot was created for mean firing rate v/s variance and a regression line was fit through it for both active and passive trials.

<p align="center">
<img src="https://github.com/terse-o/Steinmetz-Neural-Dataset/blob/master/Mean%20vs%20Variance%20-%20Active.JPG" width="275" height="180" />
<img src="https://github.com/terse-o/Steinmetz-Neural-Dataset/blob/master/Mean%20vs%20Variance%20-%20Passive.JPG" width="275" height="180" />
</p>
<p align="center">
    <em>Fig 5. Scatter Plot for Active & Passive Trials</em>
</p>

**Observation:**
As the analysis was done over a short constraint of 2 weeks, it is difficult to make some statements about the observed neural activity with strong confidence. Though across trials there was a clear indication of high variability in visual and motor neurons which could be used as metrics to develop a model for attention. An interesting observation was made in Fig. 4, neurons tend to show a generalized reverse excitation across active (incremental excitation) and passive trials (decreased excitation). A regression line fit across scatter plot suggests a clear linear relationship between mean firing rate and variance, thus, validating our observation. Neurons with High variability showed low intercepts of intersection between mean firing rate and variance.

**Discussion:**
Early analysis gave a clear understanding of model formation, sense of navigating through high-dimensional neural data. For further analysis, all significant neurons can be mapped to appropriate brain regions to understand functionality and connectivity. Small subsets of neurons are being observed in comparission to the actual acumen of neurons in a mice brain. In theory, correlatins in small subsets of data do not imply causation in larger sets of data. Thus, better techniques need to be implemented apart from statistical methods to make sense of interconnectivity and networks of neurons in brain regions. The concept of inhibitory and excitatory neuron could be explored to understand the reverse excitation of neurons among avtive and passive trials.

**Reference:**
Paper published in Nature: "Distributed coding of choice, action and engagement across the mouse brain" (https://www.nature.com/articles/s41586-019-1787-x?proof=t)
