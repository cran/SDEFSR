# Changelog

**Version  0.7.2**

* Added *as.data.frame* S3 method for transforming *SDEFSR_Dataset* into a *data.frame*.
* Method *plotRules()* is changed by the default S3 *plot()* method for class *SDEFSR_Rules*.
* Changed *cat()* and *print()* message with *message()* or *warning()* in order to be easily removed.
* Fixed minor errors.

**Version 0.7.1.0**

* Change the name of the *read.keel()* function to *read.dataset()*.
* Added direct support for CSV files on *read.dataset()*.
* Rename *keel* class to *SDEFSR_Dataset* class. 
* Rename *keelFromDataFrame()* to  *SDEFSR_DatasetFromDataFrame()*.
* Added a new object *SDEFSR_Rules* which:
  + Contains all rules generated by an SD algorithm an its associated quality measures.
  + The "[]" operator supports filter rules by quality measure
  + Added S3 method "sort" to sort rules by a given quality measure
* Added new method *plotRules()* which shows a TPR vs FPR plot by using ggplot2 package.
* Fixed error when reading ARFF files with quoted '' variables.
* **Changes of the UI:**
  + Added a new visualization method: Variable vs variable
  + Added functionality to filter numerical variables
  + Added functionality to filter instances by the given numeric or categorical filters
  + On quality measure tab, the functionality to show the plot of *plotRules()* is displayed
  + Changed the server logic to work with the new SDEFSR_Rules object to improve performance on large results.

----

**Version 0.7.0.0**

* Added a new subgroup discovery algorithm: **FuGePSD**.
* New dataset files support: 
    + ARFF files support from *read.keel()* 
    + Conversion from data.frame to *keel* with *keelFromDataFrame()* function.
* Minor optimizations when reading a file.
* Some algorithm optimizations, changed a bit the way of calling the functions **Be aware with this!**
* Fixed problem of the algorithms that returns four files instead of three. Now all the algorithms (except FuGePSD) returns three files.
* Created S3 method to visualize *keel* objects with *print()* and summarize with *summary()*
* **Changes of the UI:**
    + Algorithm selection an parameters now are on the tab panel of the right side of the UI after "Exploratory analysis". We think with this change the user has a better workflow and a better visualisation and organization of the results.
    + Also, the new functionality is available on the GUI, except the conversion from data.frame.
