# Repository Metrics

[![Build Status](https://dev.azure.com/best-practices/computervision/_apis/build/status/repo-metrics?branchName=master)](https://dev.azure.com/best-practices/computervision/_build/latest?definitionId=27&branchName=master)

We developed a script that allows us to track the metrics of the ComputerVisionBestPractices repo. Some of the metrics we can track are listed here:

* Number of stars
* Number of forks
* Number of clones
* Number of views
* Number of lines of code

To see the full list of metrics, see [git_stats.py](scripts/repo_metrics/git_stats.py)

The first step is to set up the credentials, copy the configuration file and fill up the credentials of GitHub and CosmosDB:

    cp scripts/repo_metrics/config_template.py scripts/repo_metrics/config.py

To track the current state of the repository and save it to CosmosDB:

    python scripts/repo_metrics/track_metrics.py --github_repo "https://github.com/Microsoft/ComputerVision" --save_to_database

To track an event related to this repository and save it to CosmosDB:

    python scripts/repo_metrics/track_metrics.py --event "Today we did our first blog of the project" --event_date 2018-12-01 --save_to_database
