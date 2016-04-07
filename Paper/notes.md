# Speech Detection Notes

## Regularized Logitistic Regression

- L1 to obtain features than perform L2 on obtained features for better classification accuracy
- Elastic net
- Grouped logistic regression

## Naive Bayes Classifier
- Is this something we can implement? Maybe on the audio data?

## Notes From the Paper
[Paper Link](http://www.cs.columbia.edu/speech/PaperFiles/2015/wmdd_2015_final.pdf)

- Three classification models implemented through [Weka](http://www.cs.waikato.ac.nz/ml/weka/)
	- Random Forests
	- Bagging (bootstrap aggregating)
	- J48: Weka's Iterative Dichotomiser 3
- 10 fold CV used for all models
- 14 acoustic-prosodic features were used for the classification experiment
	- fundamental frequency (physical correlation of pitch)
		- f0 minimum
		- f0 maximum
		- f0 mean
		- f0 median
		- f0 standard deviation
		- f0 mean absolute slope
	- percieved loudness
		- intensity minimum
		- intensity maximum
		- intensity mean
		- intensity standard deviation
	- voice quality
		- jitter
		- shimmer
		- noise to harmonics ratio
	- speaking rate
		- ratio of voiced to total frames
- Different normalization techniques explored on top of raw feature analysis
	- session normalization
		- normalize a given speaker's features using the mean and standard deviation of the speaker’s features throughout both parts of the session.
	- baseline normalization
		- "In the second normalization method, we employed the baseline data collection part of the experiment, in which we collected a 3-4 minute sample of each participant’s (truthful) speech before they had met their partner. To capture the speaker’s deviation from his or her truthful way of speaking, we normalized their speech during the lying game using features extracted from the baseline."
- baseline accuracy (always assuming truth): 59.9%

| Model         | Raw   | Session Norm | Baseline Norm |
|---------------|-------|--------------|---------------|
| J48           | 59.89 | 62.09        | 62.19         |
| Bagging       | 58.65 | 61.19        | 61.01         |
| Random Forest | 61.23 | 63.03        | 62.79         |

- 9 Characterization Features
	- five NEO-FFI scores
	- speaker gender
	- speaker native gender
	- partner gender
	- partner native language
	
| Model         | SessionNorm + NEO, gender, lang |
|---------------|---------------------------------|
| J48           | 64.86                           | 
| Bagging       | 63.9                            | 
| Random Forest | 65.86                           | 

- Best Classifier: Random Forest over SessionNorm + NEO, Gender, Lang features - 65.86
- Proposed next steps
	- add lexical features to analysis
		- lexical feature: *what* is said
	- add more acoustic features
	- as well as analyzing at the IPU level we can analyze at the Turn level
	- different models for different genders

## Outstanding Questions
- What is the difference between prosodic and acoustic features?
- Do we have the 1.0 or new and improved 2.0 IPU segmentation data


