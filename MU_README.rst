To contribute:

either

1a) fork on github,

or

1b) sync existing fork. You can do
this in the github UI,
as in this video
https://www.youtube.com/watch?v=TsUIRtT80QU
or this
http://stackoverflow.com/questions/20984802/how-can-i-keep-my-fork-in-sync-without-adding-a-separate-remote/21131381#21131381
1. open your fork -- note "this branch is N commits behind ...:master"
2. click New pull request
  now, in comparing changes, there are no changes detected from
  right (your fork) to left (base); however:
3. choose Try 'switching the base' which will switch direction
  (if it doesn't work, you will have to set the respective *.gits manually)
4. click Create pull request (for this comparison)
5. enter name for pull request, e.g 'Update from original'
6. Create pull request
7. Merge pull request
8. Confirm merge



OUTSTANDING
+++++++++++

orig brill trainer
------------------
where did brill_trainer_orig go? It is slower, but has much better memory usage than the fast one. No reason
to throw it out.

documentation
-------------
badly missing

code organization
-----------------
tbl, not brill; and generalized tbl, not tagging (even though nltk 'tagging' is not necessarily pos;
see nltk.tag.api.py


FIXED
+++++

py34 uncovering bug in object.__format__()
------------------------------------------

ref: https://mail.google.com/mail/u/0/#search/kathrindonandt%40yahoo.de/14cb83b1e06dd860

**********************************************************************
File "C:\Python34\Lib\site-packages\nltk-3.0a3-py3.4.egg\nltk\tag\brill_trainer.py", line 143, in __main__.BrillTaggerTrainer.train
Failed example:
    tagger1 = tt.train(training_data, max_rules=10)
Exception raised:
    Traceback (most recent call last):
      File "C:\Python34\lib\site-packages\nltk-3.0a3-py3.4.egg\nltk\tbl\rule.py", line 191, in __hash__
        return self.__hash
    AttributeError: 'Rule' object has no attribute '_Rule__hash'

    During handling of the above exception, another exception occurred:
    (...)


https://github.com/nltk/nltk/issues/769
https://github.com/nltk/nltk/commit/bffbaee2b47cc54d82a6bf4cc5ed58ab6a6a70a9
http://bugs.python.org/issue7994

Main problem fixed (no thanks to me); see also https://github.com/nltk/nltk/pull/1493




TBL on more complex token representations
-----------------------------------------

ref: stackoverflow.com/questions/37960667/training-iob-chunker-using-nltk-tag-brill-trainer-transformation-based-learning/40508641#40508641

Fixed, demo_multifeat_tbl.py




