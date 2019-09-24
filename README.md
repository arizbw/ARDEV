# [Application]- Average Restrain Divider of Evaluation Value (ARDEV)

## Guide

This application is the implementation of Average Restrain Divider of Evaluation Value (ARDEV) which is published in Average Restrain Divider of Evaluation Value (ARDEV) in data stream algorithm for big data prediction, Knowledge-Based Systems, Volume 176, 2019, Pages 29-39, ISSN 0950-7051.

### Base Framework
MOA (Massive Online Analysis) it the base framework that we used for ARDEV.
* [Massive Online Analysis - Home Page](https://moa.cms.waikato.ac.nz/) - Massive Online Analysis - Home Page.
* [Massive Online Analysis - Github Page](https://github.com/Waikato/moa) - Massive Online Analysis - Github Page

### Script to run LearnModel FIMT-DD-ARDEV
```
java -cp moa-ardev.jar moa.DoTask "LearnModelRegression -l trees.FIMTDD -s (ArffFileStream -f (combine-traffic-demand.arff)) -O (ardev-traffic-demand.moa) -m 100000000"
```
### Script to test LearnModel FIMT-DD-ARDEV
```
java -cp moa-ardev.jar moa.DoTask "EvaluateModelRegression -m file:ardev-traffic-demand.moa -s (ArffFileStream -f (combine-traffic-demand.arff)) -i 100000"
```

### Parameters in LearnModelRegression
```
-m : max instance
-s : stream file to learn by the model ( you can change this file as data training forthe model)
-O : save the model
```

### Parameters in EvaluateModelRegression
```
-m : load model file
-s : stream file to learn by the model ( you can change this file to test the model)
-i : amount of instances to be tested
```
