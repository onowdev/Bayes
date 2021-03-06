|Python27|_ |Documentation|_ |Pypi|_ |Landscape|_ |Travis|_

.. |Documentation| image:: https://readthedocs.org/projects/bayes/badge/?version=latest
.. _Documentation: http://bayes.readthedocs.io/en/latest/?badge=latest

.. |Pypi| image:: https://badge.fury.io/py/bayes-variants.svg
.. _Pypi: https://badge.fury.io/py/bayes-variants

.. |Landscape| image:: https://landscape.io/github/krzjoa/Bayes/master/landscape.svg?style=flat
.. _Landscape: https://landscape.io/github/krzjoa/Bayes/master

.. |Python27| image:: https://img.shields.io/badge/python-2.7-blue.svg
.. _Python27: https://badge.fury.io/py/bayes-variants

.. |Travis| image:: https://travis-ci.org/krzjoa/Bayes.svg?branch=master
.. _Travis: https://travis-ci.org/krzjoa/Bayes

Bayes
=====

Python implementations of Naive Bayes algorithm variations with sklearn-like API.


Algorithms
----------

* Complement Naive Bayes
* Negation Naive Bayes
* Universal-set Naive Bayes
* Selective Naive Bayes

Installation
------------

You can install this module directly from GitHub repo with command:

::

    pip install git+https://github.com/krzjoa/Bayes.git

or as a PyPI package

::

    pip install bayes-variants


Usage
-----

Bayes classifiers API mimics `Scikit-Learn <http://scikit-learn.org/stable/modules/classes.html>`_ API, so usage is very simple.


.. code-block:: python

    from bayes.classifiers import ComplementNB
    from sklearn.datasets import fetch_20newsgroups
    from sklearn.feature_extraction.text import CountVectorizer
    
    
    vectorizer = CountVectorizer()
    categories = ['alt.atheism', 'talk.religion.misc',
                  'comp.graphics', 'sci.space']
    
    # Train set
    newsgroups_train = fetch_20newsgroups(subset='train',
                                              categories=categories, shuffle=True)
    X_train = vectorizer.fit_transform(newsgroups_train.data)
    y_train = newsgroups_train.target
    
    # Test set
    newsgroups_test = fetch_20newsgroups(subset='test',
                                              categories=categories, shuffle=True)
    X_test = vectorizer.fit_transform(newsgroups_test.data)
    y_test = newsgroups_test.target
    
    # Score 
    cnb = ComplementNB()
    cnb.fit(X_train, y_train).accuracy_score(X_test, y_test)




TODO list
---------
* Weighted Complement Naive Bayes
* Locally Weighted Naive Bayes



