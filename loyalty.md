## Loyalty in GitHub Repositories 

*Jupyter Notebook Link:* <https://nbviewer.jupyter.org/github/harshulvarma/Loyalty-in-GitHub/blob/main/loyalty_in_github.ipynb>

*GitHub Repository Link:* <https://github.com/harshulvarma/Loyalty-in-GitHub>

### Overview

The goal of this project was to find out whether loyalty is manifested in developer behaviour or is a repository trait on GitHub. To do so I find out key differences between loyal or unloyal repositories and predict developer loyalty in repositories on GitHub. The inspiration of the project was to reproduce the analysis and feature engineering in the research paper of Loyalty in Online Communites paper (accessed here: <https://arxiv.org/abs/1703.03386>) where a similiar analysis was conducted on Reddit data.

### Analysis of Loyal repositories and developers

Loyal and Unloyal developers and repositories were firstly found using commiting patterns and operationalizing loyalty by computing their 'loyalty ratio' which was the ratio between loyal and vagrant devs for each repo. A loyal dev was determined as a dev whose 100% of the commits for a given month is towards only one repo with the thought process that commiting to different repos might lead to 'unloyalty' towards one repo. Using loyalty ratio distribution, loyal and unloyal repos were determined based on the top quantile and bottom quantile respecitvely.

For repository level differences were found in average commits per month, average number of devs and also network properties extracted using network graphs representing interaction between devs in a certain repository (show below). Network graphs were constructed if two given devs commited on the same repo at a given month with as they probably interacted with each other or each other's work at some point. For developers average days between commits and the view counts of repositories they choose to commit on were analysed.

<img src="images/loyal.png?raw=true"/>
<img src="images/loyal2.png?raw=true"/>

### Predicting loyal developers on GitHub

Next, I created following features for each developer based on the analysis:
- Number of commits per month for each developer - as seen in section 4.1 is different for loyal and unloyal repositories
- Average repository loyalty ratio - as seen in section 3.0
- Watch count of the repository the developer is committing to - as seen in section 5.1
- Average days between commit for each developer - as seen in section 5.2

And finally using the above features a machine learning pipeline was created using Random Forest to predict whether a given developer is loyal or not with 0.9 AUC.

### Results

Based on overall analysis and the result from the predictions using features created based on commiting patterns of a dev and repository properties it can be determined that *loyalty is indeed manifested in developer behaviour and as well as is a repository trait on GitHub*

For future improvements, the network graph properties can be extracted as an input to the machine learning model. Another improvement can be addition of a time component of change of loyalty ('loyalty rate') for the analysis as well.

### Tools Utilised
- Google BigQuery
- Spark SQL
- PySpark
- NetworkX
- MlLib
