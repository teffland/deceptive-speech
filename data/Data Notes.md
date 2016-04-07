# Data Notes

- Split into a train and test set 80/20 by person id.  I kept resplitting until they had the right split by turns also (since there are an uneven number of turns per person), so the split is 80/20 for turns as well.

- There are 5 separate feature sets, and a train/test for each. 
They are ‘dal’ (lexical features), ‘is13’ (acoustic features), ‘liwc’ (lexical features), ‘turns’ (acoustic features), and ‘neo’ (personality scores and gender/culture indicator features).

- There is an additional set of train/test called ‘all’, that has all 5 of these merged into one big table with duplicate columns dropped.

- There are an additional 3 feature sets, '*_normed’, which have all of the acoustic features as zscores, normalized computed per person (by person mean and stddev for each column)

For each table there are 3 non-feature columns: ’turn’, ‘person’, and ‘label’ (they are exactly what they sound like).