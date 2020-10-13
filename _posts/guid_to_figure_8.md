---
title: "Guidelines to Figure-Eight (CrowdFlower) Platform"
date: "2018-09-11"
collection: posts
permalink: /posts/guid_to_figure_8
tags:
  - Crowdsourcing
  - Crowdflower
  - Figure-Eight
---

How does Figure-Eight works?
======
Figure-Eight is based on the idea of creating millions of simple online tasks to create a distributed computing machine. The business model of Figure-Eight is composed on a customer, a task and a contributor. Figure-Eight provides tools for the customer to upload their data and design their task either by drag and drop or using Crow-Flower Mark up Language (CML). Then, the task became available for the contributors (crowd) to perform. Figure-Eight provides a set of tools to set the desired quality, speed and cost of the task. This section describes the mechanisms provided to achieve the most possible quality in the task.


Contributors
============
Figure-Eight gives the option between “External contributors” and “Internal contributors”. In the external contributors, the job is posted to a global network of contributors. This option is followed by a set of advanced options like the contributor’s level, the country of the contributor and the language of the contributor.  The contributor level specifies the level of experience of the contributor. There are three available levels the higher the level the smaller the number of the contributors who will have access to the task but also the higher the performance quality. The geographical and language options limit the participation to only contributors who are from specific country or speak specific language. The second option is internal contributors, which gives access to the task only to in house work place through a link.


Test questions
==============
igure-Eight requires each task to have a set of test questions which are examples of the data items provided with the right label and the reason of that label. These test questions are used later to test the quality of the contributors’ performance.  By default, there is one test question per page of data items (which means each user can only as many as test questions there are in the task).  If the total number of test questions is more than or equal the number of rows (data items) per page of work, then a Quiz mode is activated. In this quiz mode a contributor must pass the quiz mode, which is composed only of test questions to be able to do the task. If the contributor fails the quiz mode, they are nor paid and permanently disqualified from doing that task.


Quality control
==============
In this section the customer sets certain values to specify the minimum acceptable accuracy on the task. Based on these settings, some contributors are removed from the task if they didn’t achieve the required scores. More these settings have values by default but the customer can edit them.

* Test question minimum accuracy: the customer set that value and contributors must maintain this accuracy throughout the job. If a contributor fails to achieve this score, his work will be removed or labelled untrusted. If the quiz mode is active then this is the minimum score a contributor needs to pass the quiz mode.
* Minimum time per page: The customer sets the minimum time, in seconds, that should a contributor take to compete a page of work.
* Maximum judgments per contributor: This setting limits the number of judgments that any contributor can provide in the job.
* Contributor answer distribution rules: Activating this option helps monitor the distribution of the answers a contributors submit for a task. This setting ensure that a contributor is removed if they tends to favour a specific answer and when they tend to deviate from the answer distribution of the test questions set.
* Dynamic judgment collection: This option allows the platform to automatically collect more judgments on the row (data item) if the contributors disagree on an answer. Judgment here means a contributor’s answer. The more judgments required, the more contributors would do that row of data.
* Row per page: The customer sets the number of data items in one page of work.
* Price per page: The customer sets the price he is willing to pay per page of work.
* Judgments per row: The customer sets the number of judgments to be collected for each row.  The default is 3 judgments per each row of data.

Quality measures
================
Figure-Eight uses two measures to calculate the contributor’s reliability and the quality of each generated row of data:
* Contributor’s trust is the contributor’s accuracy level on the job, determined by the performance on the test questions.
* The confidence score is the level of agreement between contributors to each row of data weighted by the contributor’s trust.

To calculate the confidence score, the following steps are taken:
1. Calculate the sum of the trust scores of the contributors responsible for each response. For example, given three judgments for each tweet. We calculate the sum of  the contributors trust scores for all violent tweets and non violent tweets sum of contributors trust scores (positive label) and sum of contributors trust scores (negative label)
2. Sum the scores for all the responding contributors tweets sum of contributors trust scores (positive + negative)
3. To get the confidence score for each response (positive/negative) divide 1 by 2
4. Finally the response with the highest confidence level is the one chosen for the aggregation report.
---