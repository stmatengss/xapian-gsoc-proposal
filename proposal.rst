.. This document is written in reStructuredText, a simple and unobstrusive
.. markup language.  For an introductiont to reStructuredText see:
.. 
.. https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html
.. 
.. Lines like this which start with `.. ` are comments which won't appear
.. in the generated output.
.. 
.. To apply for a GSoC project with Xapian, please fill in the template below.
.. Placeholder text for where you're expected to write something says "FILLME"
.. - search for this in the generated PDF to check you haven't missed anything.
.. 
.. See our GSoC Project Ideas List for some suggested project ideas:
.. https://trac.xapian.org/wiki/GSoCProjectIdeas
..
.. You are also most welcome to propose a project based on your own ideas.
.. 
.. From experience the best proposals are ones that are discussed with us and
.. improved in response to feedback.  You can share draft applications with
.. us by forking the git repository containing this file, filling in where
.. it says "FILLME", committing your changes and pushing them to your fork,
.. then opening a pull request to request us to review your draft proposal.
.. You can do this even before applications officially open.
.. 
.. IMPORTANT: Your application is only valid is you upload a PDF of your
.. proposal to the GSoC website at https://summerofcode.withgoogle.com/ - you
.. can generate a PDF of this proposal using "make pdf".  You can update the
.. PDF proposal right up to the deadline by just uploading a new file, so don't
.. leave it until the last minute to upload a version.  The deadline is
.. strictly enforced by Google, with no exceptions no matter how creative your
.. excuse.
.. 
.. If there is additional information which we haven't explicitly asked for
.. which you think is relevant, feel free to include it. For instance, since
.. work on Xapian often draws on academic research, it's important to cite
.. suitable references both to support any position you take (such as
.. 'algorithm X is considered to perform better than algorithm Y') and to show
.. which ideas underpin your project, and how you've had to develop them
.. further to make them practical for Xapian.
.. 
.. You're welcome to include diagrams or other images if you think they're
.. helpful - for how to do this see:
.. https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html#images
.. 
.. Please take care to address all relevant questions - attention to detail
.. is important when working with computers!
.. 
.. If you have any questions, feel free to come and chat with us on IRC, or
.. send a mail to the mailing lists.  To answer a very common question, it's
.. the mentors who between them decide which proposals to accept - Google just
.. tell us HOW MANY we can accept (and they tell us that AFTER student
.. applications close).
.. 
.. Here are some useful resources if you want some tips on putting together a
.. good application:
.. 
.. "Writing a Proposal" from the GSoC Student Guide:
.. https://google.github.io/gsocguides/student/writing-a-proposal
.. 
.. "How to write a kick-ass proposal for Google Summer of Code":
.. https://teom.wordpress.com/2012/03/01/how-to-write-a-kick-ass-proposal-for-google-summer-of-code/

======================================
Improve Estimated Total Number of Results
======================================

About You
=========

 * Name: Teng Ma

 * E-mail address: stmatengss@gmail.com OR mt16@mails.tsinghua.edu.cn

 * IRC nickname(s): stmatengss

 * Any personal websites, blogs, social media, etc: https://www.linkedin.com/in/teng-ma-69a0a8115/  OR http://stmatengss.github.io

 * github URL: https://github.com/stmatengss

 * Biography:

I was born in China. I received my Bachelor degree in computer science from University of Science and Technology Beijng, China in July 2016. Now I am a third-year PhD student in Department of Computer Science and Technology, Tsinghua University, China. My research advisors are Prof.Yongwei Wu and Prof.Kang Chen. My research interests include distributed database, Remote Direct Memory Access (RDMA), Non-Volatile Memory (NVM), and key-value store systems. I have published two papers in IEEE TPDS and VLDB separately.


Background Information
----------------------

.. The answers to these questions help us understand you better, so that we can
.. help ensure you have an appropriately scoped project and match you up with a
.. suitable mentor or mentors.  So please be honest - it's OK if you don't have
.. much experience, but it's a problem if we aren't aware of that and propose
.. an overly ambitious project.

**Have you taken part in GSoC and/or GCI (https://codein.withgoogle.com/) and/or
similar programmes before?  If so, tell us about how it went, and any areas you
would have liked more help with.**

Unfortunately, no.

**Please tell us about any previous experience you have with Xapian, or other
systems for indexed text search.**

I have good c++ programming skills and a few knowledge about Lucene/Solr. I have used Solr to provide several simple restful APIs about searching stock data. Besides, I have joined a startup search engine company, DingFu Data, as an intern engineer. My works mainly on filtering massive of invalid data before importing documents into the search engine, and design corresponding data schema for web service.

**Tell us about any previous experience with Free Software and Open Source
other than Xapian.**

I have no previous experience.

**What other relevant prior experience do you have (courses taken at college,
hobbies, holiday jobs, etc)?**

1. Distributed System
2. C++ Programming
3. Advanced Data Structure
4. Introduction to System
5. Database System Concept
6. Computer Software Design and Implementation

**What development platforms, tools and methods do you prefer to use?**

I develop softwares in the ubuntu 14.04 platform. Mostly, I use VS Code or Sublime for writing codes. In some cases without a graphical interface, Vim is my primary choice.


**Have you previously worked on a project of a similar scope?  If so, tell us
about it.**

I have worked on a financial search engine project. In this project, user can search stock data, financial report and financial news from website. 
My duty is that filter massive of invalid data before importing documents into the search engine, and design corresponding data schema for web service.

**What timezone will you be in during the coding period?**

UTC+8

**Will your Summer of Code project be the main focus of your time during the
program?**

Yes, this project will be treated as the primary one except some unresistible factors.

**Expected work hours (e.g. Monday–Friday 9am–5pm UTC)**

At least 35 hours and around 5-7 hours for each day. 

**Are you applying for other projects in GSoC this year?  If so, with which
organisation(s)?**

No

.. We understand students sometimes want to apply to more than one org and
.. we don't have a problem with that, but it's helpful if we're aware of it
.. so that we know how many backup choices we might need.


Your Project
============

Motivations
-----------

**Why have you chosen this particular project?**

Recently, I have noticed Xapian is a new emerging project in the search engine software. I have heavy interesting about search engine all the time. Fortunately, I have some experience in using and improving the search engine. Therefore, I think I can learn lots of things from contributing to this project and know how to join in an open source community. By the way, I like the code style in Xapian.

**Who will benefit from your project and in what ways?**

After merging this project to Xapian, the user can get a total number of searching results approximately with lower overhead. Compared with the complete statistic, the speedup is significant. The latency of the search request will be lower than the original and the web service can gain benefit from it.


Project Details
---------------

.. Please go into plenty of detail in this section.

**Describe any existing work and concepts on which your project is based.**

First, I have collected several resources about how to implement and improve the estimation.

### Basic Background

The key purpose is to eliminate the bias between the lower-bound and upper-bound estimation. After that, compared with origin approach (i.e., `round_estimate` in  `roundestimate.h`), this method can return an approximate result to users. This origin approach is a very simple implementation. The final result is produced according to three values: `matches_upper_bound`, `matches_lower_bound` and `matches_estimated`. Those three values are all gained from a sorted index data structure (a.k.a., PostList Tree in Xapian). 

The key challenge is that the estimation of different intersection between terms from an indicated query. As an instance, a query is like <term1, term2>, term1 may have several matched documents (da1, da2 ... dan) and term2 has a set of (db1, db2, ... dbn). Some documents may exist in both term1's set and term2's set. So we need to avoid the repeat count in the final estimation. Inclusion–exclusion principle can meet the requirement to calculate an approximate result.

### Academic

1. (Efficient Search Engine Measurements [WWW'07])[http://wwwconference.org/www2007/papers/paper753.pdf] This paper present two estimators that are able to remedy the skew introduced by approximate degrees. This estimators are based on a careful implementation of an approximate importance sampling procedure.

2. (A Minimal Variance Estimator for the Cardinality of Big Data Set Intersection [SigKDD 17])[https://arxiv.org/pdf/1606.00996.pdf] This paper gives a maximum likelihood method to estimate the Intersection between two sets with a low IO overhead (streaming). We can gain the result through `set1 + set2 - the Intersection of set1 and set2`.

3. (Multilingual Information Retrieval From Research To Practice) In section 2.5, it introduces several useful method for estimating results with a multi-term query.

### Industry

[The collector of Lucene](https://lucene.apache.org/core/7_5_0/core/org/apache/lucene/search/TopDocsCollector.html) has a field `totalHits` to describe the total number of documents that the collector encountered. I try to understand the codes from Lecene.

The conclusions of the implementation details as following:

### Implementation Details

1. Basic implementation: The estimated total number of results will be returned by the `Xapian::MSet::get_matches_estimated()` function. This function belongs to `MSet`. The result is an approximate estimation of both upper bound and lower bound via `round_estimate`. This returned value is based on an evaluation to ensure its upper bound and lower bound. We should assume terms occur independently of one another. The matcher will exploit various short-cuts, and calculate the result from the frequency of occurrence of the terms. The formula is like this `T1 * T2 * T3 * ... * Tn`. 

2. Algorithm: Assume there is a query `term1 term2`, we should get the result of `term1` and `term2` separately from `MSet` as t1 and t2. After that, we can search for the results which contain `term1` from the intersection of `term1` and `term2` as t1 & t2. For searching `term1`, the overhead is acceptable since the size of `term2` is not too large. Finally, we can calculate the final result as `t1 + t2 - t1 & t2`. Similarity, a more complex query can be disaggregated with subterms. These terms will be calculated with the same approach.

3. Challenges: 
    1. Eliminate Bias: We should try to reduce the skew effect we get from assuming independence. On my mind, some of the methods include sampling and parameter tuning are efficient.
    2. Frequency terms: I aim to cache some hot results of the intersection of more than two terms. The cache approach can accelerate the processing of calculating results.

### Evaluation Dataset

1. https://en.wikipedia.org/wiki/AOL_search_data_leak 
This is a intentional release of query logs.

2. We hope to collect more datasets from the internet like a mirror website to provide search service for users.

3. A dump data from wikipedia or other websites to generate a naive workload. 

4. Several non-public research datasets which it's possible to arrange access to. Currently we have access to FIRE, and we're working on access to another one.

**Do you have any preliminary findings or results which suggest that your
approach is possible and likely to succeed?**

The estimation of the total number of search results is well studied in the past 20 years. Especially, these techniques like sampling, random walk, and basic probability calculations make estimation become easy and accuracy. From anther aspect, the sum of result of each term can be obtained from the indexed structure. Thereby, it is not hard for us to estimate the final result of the query since we only need to calculate the intersection of different terms.

**What other approaches to have your considered, and why did you reject those in
favour of your chosen approach?**

1. Using memory cache to buffer several frequent appeared search results. However, this implementation will incur high overhead and heavy storage.
2. Some sampling algorithm will strength the accurary of the results. However, after dicussion with one of the contributor, this approach will increase the complexity of Xapian. 

**Please note any uncertainties or aspects which depend on further research or
investigation.**

1. The computation overhead of calculating the result.
2. How to integrate this function to the whole system without extra changes.
3. Some functions are aggregated with the origin implementation, I need to re-use these APIs to improve its robustness.

**How useful will your results be when not everything works out exactly as
planned?**

I think that my results will be useful, since the project progress is well documented. On the other hand, even if the effect is worse, some of these codes can be re-used in Xapian.

Project Timeline
----------------

Timeline:

Community Bonding Period: May 6-27

Understand the codes of Xapian. Learn how to build up the test environment.

Week 1: 05.27-06.03

Create practical code examples 
Add corresponding API documentation about the total number of search results estimation.

Week 2: 06.03-06.10

Design algorithm and formalize the algorithm, and discuss with mentors to validate its correctness.

Week 3: 06.10-06.17

Implement a beta version according to the algorithm.

Week 4: 06.17-06.24

Add extra APIs in MSet to support estimation. Make changes according to the suggestions from mentors and submit the final pull request.

-- Evaluation Round 1 --

Week 5: 06.24-07.01

Do benchmarks and tests. Conclude the experiment results. 

Week 6: 07.01-07.08

Choose the best approach which will be reserved in Xapian. Discuss with menters to ensure its effect.

Week 7: 07.08-07.15

Integrate them into Xapian and add examples in Xapian accordingly.

Week 8: 07.15-07.22

Make changes according to the suggestions from mentors and submit the final pull request.

-- Evaluation Round 2 --

Week 9: 07.22-07.29

Make Unit tests & issue bugs & Finish uncompleted details

Week 10: 07.29-08.05

Tune algorithms to get a higher performance.

Week 11: 08.05-08.12

Issue bugs and discuss the future works. Document some un-issued problems.

Week 12: 08.12-08.19

Write documents & Final Code Review.

Week 13: 08.19-08.26

Make changes according to the suggestions from mentors and submit the final pull request. After that, submit a final evaluations and documents.

-- Evaluation Round 3 --



Previous Discussion of your Project
-----------------------------------

I notice Google Summer of Code recently. So I haven't discussed with the community yet. However, I will discuss in the IRC or mail list frequently soon. 

.. If you have discussed your project on our mailing lists please provide a
.. link to the discussion in the list archives.  If you've discussed it on
.. IRC, please say so (and the IRC handle you used if not the one given
.. above).

Licensing of your contributions to Xapian
-----------------------------------------

**Do you agree to dual-license all your contributions to Xapian under the GNU
GPL version 2 and all later versions, and the MIT/X licence?**

For the avoidance of doubt this includes all contributions to our wiki, mailing
lists and documentation, including anything you write in your project's wiki
pages.

Yes, I agree with both two license.

.. For more details, including the rationale for this with respect to code,
.. please see the "Licensing of patches" section in the "HACKING" document:
.. https://trac.xapian.org/browser/git/xapian-core/HACKING#L1399

Use of Existing Code
--------------------

**If you already know about existing code you plan to incorporate or libraries
you plan to use, please give details.**

No required

.. Code reuse is often a desirable thing, but we need to have a clear
.. provenance for the code in our repository, and to ensure any dependencies
.. don't have conflicting licenses.  So if you plan to use or end up using code
.. which you didn't write yourself as part of the project, it is very important
.. to clearly identify that code (and keep existing licensing and copyright
.. details intact), and to check with the mentors that it is OK to use.
