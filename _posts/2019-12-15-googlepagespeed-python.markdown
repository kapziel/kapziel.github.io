---
layout: post
title:  "pagespeed & python: test your site"
date:   2019-12-15 14:48:52 +0000
categories: python sketching google
---


Originally I wanted to do a quick test to see what was on github already for using pagespeed and python together. After having a bit of a look around I found a basic implementation of the Pagespeed API and python to pull out a url or list or urls and parse using pagespeed. The output was a basic list of metrics, expandng this based on what was needed was fairly trivial, along with added a bit more support for different configurations.

The repo is over [here on github](https://github.com/kapziel/google-pagespeed-api-script).

### Google Pagespeed API - Python
1. This script reads urls from 'pagespeed.txt' file. Load this file with full URLS - make sure to include `https://` parameters (will add in URL validation in future)
2. Queries each url with the google pagespeed api.
3. Filters JSON results to only include desired metrics.
4. Metrics are saved to local .csv spreadsheet for analysis.


#### Current columns are
 - URL
 - First Contentful Paint
 - First Meaningful Paint
 - Speed Index
 - First CPU Idle
 - Time to interactive
 
### Requires

- Requests


### Note

.gitignore hides api token file, this is loaded in via a .txt file. If no files exists `None` is used and script will contine without. To use in production (multiple calls / sec) an api token will be required.
