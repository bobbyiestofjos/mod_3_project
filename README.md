# Pump It Up: Data Mining the Water Table

This repo contains a machine learning project by Bobby Williams and Dan Hales for Flatiron, DC's Data Science program.

The data used is from this competition: 
https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/page/23/

The dataset contains geographic, mechanical, operational, and financial information on tens of thousands of Water Points (WPs) in Tanzania, as collected by Taarifa for their Waterpoints Dashboard. The goal of the data collection was to improve WP maintenance by classifying all WPs as "functional", "non functional", or "functional needs repair".

The dataset contains a number of inconsistencies and errors, so we reduced the unique values in many columns by creating new, broader categories. For example, we converted "date" into five "phases" of data collection.

We used GridSearchCV to compare different DecisionTreeClassifiers, and chose the model that minimized a metric we referred to as the "overlook rate"––the number of non-functional WPs that were misclassified as functional. We sought to minimize this number because it represents the WPs that do not reliably supply water but would not get fixed. This is a more serious error than, say, sending a crew to fix a functional WP and finding out their work is already done.

Ultimately, we settled on a deep (n=15) tree that did not have drastic overfitting. Both the overlook rate and the overall accuracy score were within 5% for the training and test data.

This repo contains the following files:

- **index.ipynb** our master notebook containing our model, some initial EDA, and visualizations
- **training_values.csv** the training data (as provided by the competition)
- **training_labels.csv** the true values (as provided by the competition)
- **Pump It Up.pdf** the slide deck from our presentation
- **README.md**
