# deceptive-speech
ML for classifying deceptive speech from audio/text 

## Data
- Original data is labeled transcribed sequences of Deceptive/Not Deceptive speech audio from a (few hundred?) people
- Data is broken into 3 types: Acoustic, Lexical, and Personal
- Acoustic and Lexical are at two granularities: IPU level, and Turn level
  - Acoustic: OpenSMILE (IS13) acoustic/prosodic feature extractor
  - Lexical: DAL lexical sentiment feature extractor
  - Lexical: LIWC lexical sentiment feature extractor
- Personal is collected per person.  
  - These are NEO-FFI personality indicators: Neurotiscism, Extraversion, Openness, Agreeableness, and Conscientiousness
  - Also the persons gender
  - And whether their native language is Mandarin Chinese or American English (1/0?)

## Notes:

### IPUs:

Given train / dev/ test IPU splits:

Split | Num IPUs | % | Num People | %
------|----------|---|------------|---
Train |19390    |35 | 60 | 37
Dev   |12386    |22 | 51 |31
Test  |23766    |43 | 51 |31

** Will combine training and dev and do cross validation to have roughly 60/40 split **

Naive baseline accuracy: 62.12% train, 59.04% test

## TODO:

- [ ] Logistic Regression w/
- [ ] L1 regularization
- [ ] L2 regularization
- [ ] Grouped LASSO -- we should discuss what groupings make sense
- [ ] Random Forest
- [ ] Neural Sequence model
- [ ] Maybe do some simple dimension reduction in preprocessing w/ Chi Square or PCA?
