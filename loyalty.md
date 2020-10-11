## Loyalty in GitHub Repositories 

**Jupyter Notebook Link:** https://nbviewer.jupyter.org/github/harshulvarma/Loyalty-in-GitHub/blob/main/loyalty_in_github.ipynb

**GitHub Repository Link:** https://github.com/harshulvarma/Loyalty-in-GitHub

### Overview

The goal of this project was to predict developer loyalty in repositories on GitHub and find out key difference between loyal or unloyal repositories. I wanted to find out whether loyalty is manifested in developer behaviour or is a repository trait. In order to achieve this anlaysis I reproduced the research paper analysis and feature engineering using Loyalty in Online Communites paper (accessible here: https://arxiv.org/abs/1703.03386)

Various analysis was conducted and reproduced from the above paper. Loyal and Unloyal developers and repositories were firstly found using commiting patterns. For repository level key differences were found in average commits per month, average number of devs and also network properties extracted using network graphs representing interaction between devs in a certain repository and are show below. For developers average days between commits and the view counts of repositories they choose to commit on were analysed.

<img src="images/loyal.png?raw=true"/>
<img src="images/loyal2.png?raw=true"/>

Next, I created following features for each developer based on the analysis:
- Number of commits per month for each developer - as seen in section 4.1 is different for loyal and unloyal repositories
- Average repository loyalty ratio - as seen in section 3.0
- Watch count of the repository the developer is committing to - as seen in section 5.1
- Average days between commit for each developer - as seen in section 5.2

And finally using the above features a machine learning pipeline was created using Random Forest to predict whether a given developer is loyal or not with 0.9 AUC.

### Tools Utilised
- Google BigQuery
- Spark SQL
- PySpark
- NetworkX
- MlLib
