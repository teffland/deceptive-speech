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
- Data is 

## Notes:

- We should run experiments with nested stratified cross validation (say 5 outer and 3 inner folds)
- The naive baseline is 53%?
- The current baseline is 66%?

## TODO:

- [ ] Logistic Regression w/
- [ ] L1 regularization
- [ ] L2 regularization
- [ ] Grouped LASSO -- we should discuss what groupings make sense
- [ ] Random Forest
- [ ] Neural Sequence model
- [ ] Maybe do some simple dimension reduction in preprocessing w/ Chi Square or PCA?
