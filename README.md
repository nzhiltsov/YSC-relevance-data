YSC Relevance Data
=================

The project contains a combined query set and extended assessment files from the [Yahoo! SemSearch Challenge 2010/11](http://semsearch.yahoo.com) evaluation campaigns. The relevance labels have been acquired after an evaluation campaign on [Amazon Mechanical Turk](http://mturk.com) followed by a thorough quality control analysis (see details in the coming paper).

Current Version
------------
[2.0](https://github.com/nzhiltsov/YSC-relevance-data/archive/2.0.zip)

Notes
------------
There have been made a few changes comparing to the initial YSC files:

* the both query sets from [YSC 2010](http://km.aifb.kit.edu/ws/semsearch10/) and [YSC 2011](http://km.aifb.kit.edu/ws/semsearch10/) campaigns are combined into a single query set
* the query file is formatted as follows: query_num\tquery, e.g. 1\t44 magnum hunting (\t means the tab symbol)
* misspellings in 9 queries were fixed using a feature "Search instead for" of Google Search 
* the relevance labels are standardized according to the three-grade scale: 0 means irrelevance, 1 - fair relevance, 2 - excellent relevance
* 11% initial labels are fixed, the total number of labels has increased by 17%.

We recommend using the following [trec_eval](http://trec.nist.gov/trec_eval/) commands to compute some standard IR evaluation measures:

* NDCG: <i>trec_eval -q -c -m ndcg.0=0,1=1,2=3 assess.txt your_results.txt</i>
* MAP: <i>trec_eval -q -c -l1 -m map assess.txt your_results.txt</i>
* P@10: <i>trec_eval -q -c -l1 -m P.10 assess.txt your_results.txt</i>
    
Citation
----------------------
If you have found these data helpful and used them in your research work, please cite the following paper:

Zhiltsov, N., Agichtein, E. _Improving Entity Search over Linked Data by Modeling Latent Semantics._ Proceedings of the International Conference on Information and Knowledge Management (CIKM 2013). ACM, 2013.
