Summary Statistics
==================

This chapter explains how to quickly review basic statistics about the
cohorts you use for analyses. 

In summary: after you have made a subset in the Comparison tab, you can go to the Summary Statistics 
tab where you can find a quick overview of your data. You can drag data nodes to this tab which will be 
transformed into boxplots and histograms, including a t-test or chi-squared test. For further advanced 
analysis, you can go to the Advanced Workflow tab.

.. _generating-summary-statistics-label:

Generating Summary Statistics
-----------------------------

Once you have finished defining criteria for the cohorts to compare — the
subsets — then click the **Summary Statistics** button.

.. note::
    As an alternative to generating summary statistics, you can view a breakdown 
    of a particular subset by a selected concept (see `View Subset Breakdown by Concept`_).   

tranSMART displays tables and charts of information that describe the
subsets. The information is displayed in Summary Statistics view in the
following sections:

    A summary of the criteria used to define subsets to compare.

    For example:

    |image500|
	|image501|

    A table showing the number of subjects in each subset that match the subset criteria.

    For example:

    |image502|

    In this example, 56 subjects matched the criteria for Subset 1 and 58 matched the criteria for 
    Subset 2. No (0) subjects matched the criteria for both subsets.
   
    Tables and charts that show how the subjects who match the criteria fit into age and sex 
    demographics.

    This example shows the age portion of the demographics data only:

    |image503|

	The next examples show analysis of concepts for histological type, WHO performance and NGS data

    |image505|

    **Example 1: Histological Type.**: this example shows the analysis of the categorical node 'histological type'

    |image506|

    **Example 2: Tumor diameter.**: This example shows the analysis of the numerical node ‘Tumor diameter'

    |image508|

    **Example 3: NGS data.**: this example shows the analysis of the high dim node ‘Genes’, specified for AURKA expression

Significance Tests
~~~~~~~~~~~~~~~~~~

The analyses include the results of significance testing that Analyze
performs:

|image509|
|image510|

Significance testing is designed to indicate whether the reliability of
the statistics is 95% or greater, based on p-value.

Analyze calculates the significance result using either t-test or
chi-squared statistics to determine the p-value:

-   For continuous variables (for example, subject weight or age), a
    t-test compares the observed values in the two subsets.
    
-   For categorical values (for example, diagnoses), a chi-squared test compares the counts in 
    the two subsets. 

    See `this <https://commons.apache.org/proper/commons-math/javadocs/api-2.2/org/apache/commons/math/stat/inference/TestUtils.html>`__ 
    for the Java methods that calculate the chi-squared and t-test statistic.


If there is not enough data to calculate a test, Analyze displays a
message indicating the insufficient quantity of data. In addition,
significance test results are not displayed in the following
circumstances:

-   If two identical subsets are defined. In this case, the significance
    test results are not meaningful.

-   If all subjects in the first subset have one set of values for the
    categorical value and all subjects in the second subset have other
    categorical values. For example, suppose you set Subset 1 to contain
    only males and Subset 2 to contain only females. If you then try to
    show statistics by gender, tables similar to the following would
    result:

    |image511|

    In this case, the chi-squared function doesn’t return meaningful
    results.


View Subset Breakdown by Concept
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Generating summary statistics provides data for all subsets defined by
study cohorts. You can view data for a particular subset, however, as
following:

#.  Select a cohort from the navigation tree and drag it into a subset; for example:

    |image513|

#.  Click the **Summary Statistics** tab.

#.  Drag and drop a folder from the navigation tree into the empty page;
    for example:

    |image514|

#.  tranSMART calculates the results and displays the data for the given subset and concept:

    |image515|

.. note::
    The Summary Statistics allows you to use high dimensional data as well, see :ref:`hidome-label`.
  

Defining Points of Comparison
-----------------------------

Once you establish the subsets of subjects that you want to compare, you
can apply one or more points of comparison to the subsets. A *point of
comparison* is a concept in the navigation tree.

To apply a point of comparison to the subsets:

#.  You must already have defined the subsets and have generated summary 
    statistics for the subsets, as described in the previous section.

#.  Drag the concept that you want to introduce as the point of
    comparison from the navigation tree and drop it anywhere inside
    the Summary Statistics view.

As soon as you drop the point of comparison into the Summary Statistics
view, tranSMART begins to compare the subsets based on that point of
comparison. When finished, tranSMART displays a side-by-side summary of
how the subjects in each subset match or respond to the point of
comparison.

Results of a Comparison
~~~~~~~~~~~~~~~~~~~~~~~

For example. In a comparison of subjects in an oncology study, suppose Subset 1 contains 
subjects with a so-called MSS tumor characteristic and Subset 2 contains subjects with a so-called
MSI tumor characteristics.

|image525|

After the subsets are defined and summary statistics are generated, an analysis of 
‘Hypermutation’ is dropped into the Summary Statistics view as a point of comparison. As you 
can see, subset 2 (MSI characterized tumors) show a much higher portion of Hypermutated 
tumors, indication a connection between hypermutation and MSI status. Statistical testing claims 
that the results are significant. 

|image526|

.. note::
    when statistical analysis claims the p-value to be 0.0, it indicates the p-value to be very 
    small (<0.01)

.. note::
    To keep the size of the preceding figure within production limits, the demographics 
	(age and gender) portions of the figure are excluded in this screenshot. 

    
Printing the Contents of Summary Statistics View
------------------------------------------------

You can print the contents of Summary Statistics view as shown below.

#.  In Summary Statistics view, click the **Print** button:

    |image518|

    The entire contents of Summary Statistics view appear in a separate browser window.

#.  Click **Print this page**.

.. _viewing-analysis-data-in-grid-view-label:

Viewing Data in Grid View
-------------------------

If you are displaying data in the various tables and charts of Summary Statistics view, and want 
to view the data in a single table, use the **Grid View** option.

Access Grid View as follows:

#.  Click the **Analyze** tool and define your cohorts as described earlier in this chapter.

#.  Click **Summary Statistics**.

#.  Click **Grid View**.

    |image91|

#.  Optionally, you can drag and drop additional points of comparison
    into the grid, and new columns will appear for that data.

#.  You can drag a node from any level of the tree into the grid.

Sample of Grid View for a public study:

|image92|

.. note::
    The ID assigned in the **Subject** column is the internal tranSMART ID that is assigned at the time of data loading. 
    The ID in the **Patient** field contains the original subject ID that was provided in the data.   

    And, also the Grid View allows you to use high dimensional data, see :ref:`hidome-label`.

Grid View Display Options
~~~~~~~~~~~~~~~~~~~~~~~~~

-   **Sort the grid by a specific column.** Click the down-arrow icon
    (|image94|) next to the column heading you want to sort by, then
    select **Sort Ascending** or **Sort Descending**.

-   **Hide or redisplay columns.** Click the down-arrow icon next to any
    column heading, click **Columns** as shown below, then select or
    deselect columns to hide or redisplay:

    |image95|

If a column name does not appear in the menu, you have not included the
associated concept in the analysis. For example, Diagnosis has not been
included in the analysis above.

Visualize High Dimensional data
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Viewing genetic profiling data can be done similarly to described above: find your folder of interest and 
drag it into summary statistics. A pop-up screen will appear in which you can define your search: the 
type of gene symbol you are looking for and the numbers you want to display (log intensity / raw 
intensity / z-scores). 

.. note::
	The Z-score is the signed fractional number of standard deviations by which the value of an 
	observation or data point is above the mean value of what is being observed or measured. Observed 
	values above the mean have positive standard scores, while values below the mean have negative 
	standard scores. In tranSMART Z-scores are calculated during upload using this formula: z = X - μ / σ 
	-- > Z score = value - Average(mean) / Standard deviation

For example, drag ‘Genes’ from the RNA expression/Microarray: Agilent 244k mRNA folder to the Summary Statistics screen:

	|image519|

Next, the following pop-up screen will appear in which you can search for a specific gene (in here: 
AURKA) and what you want to query on (in here: Log Intensity). Next, click ‘OK’. 

	|image520|

After previous actions, the following screen will pop-up. Please note that two subsets are being 
compared. The Log Intensity is being displayed in a Histogram and a Boxplot. 

	|image521|

Visualize High Dimensional data in Grid View
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Similar to the functionality described above,  to visualize genetic data in table format drag the node of 
interest to grid view. Next, define your search (which gene and which type of data, e.g. raw intensity) 
and your values will appear. 

For example, just as in Summary Statistics, drag the ‘Genes’ node from the RNA expression/Microarray: 
Agilent 244k mRNA folder into the Grid view screen. 

	|image522|

Next, define your query by selecting a search term (in here: KRAS) and what you want to Query on (in here: Raw Intensity)

	|image523|

Next, a new row will be added to the grid view screen (see the red arrow). In here the Raw Intensity 
values are being displayed for each patient. 

	|image524|




.. |image76| image:: media/image63.png
   :width: 6.00000in
   :height: 0.80486in
.. |image77| image:: media/image64.png
   :width: 1.68729in
   :height: 0.73949in
.. |image78| image:: media/image65.png
   :width: 6.00000in
   :height: 2.29444in
.. |image79| image:: media/image66.png
   :width: 6.00000in
   :height: 2.35347in
.. |image80| image:: media/image67.png
   :width: 6.00000in
   :height: 5.18819in
.. |image81| image:: media/image68.png
   :width: 5.87106in
   :height: 4.45833in
.. |image82| image:: media/image69.png
   :width: 3.01004in
   :height: 0.77074in
.. |image83| image:: media/image70.png
   :width: 6.00000in
   :height: 1.38264in
.. |image84| image:: media/image71.png
   :width: 6.00000in
   :height: 1.42500in
.. |image85| image:: media/image72.png
   :width: 6.00000in
   :height: 2.34792in
.. |image86| image:: media/image73.png
   :width: 6.00000in
   :height: 4.50764in
.. |image87| image:: media/image74.png
   :width: 6.37851in
   :height: 2.04167in
.. |image90| image:: media/image75.png
   :width: 6.00000in
   :height: 1.42917in
.. |image91| image:: media/image76.png
   :width: 3.98908in
   :height: 0.57285in
.. |image92| image:: media/image77.png
   :width: 6.00000in
   :height: 1.93542in
.. |image94| image:: media/image78.png
   :width: 0.10417in
   :height: 0.17361in
.. |image95| image:: media/image79.png
   :width: 3.17669in
   :height: 3.46832in
.. |image500| image:: media/image500.png
   :width: 8.307in
   :height: 5.28in
.. |image501| image:: media/image501.png
   :width: 8.307in
   :height: 0.88in
.. |image502| image:: media/image502.png
   :width: 2.4in
   :height: 1.05in
.. |image503| image:: media/image503.png
   :width: 8.307in
   :height: 3.07in
.. |image505| image:: media/image505.png
   :width: 8.307in
   :height: 4.333in
 .. |image506| image:: media/image506.png
   :width: 8.253in
   :height: 3.053in
.. |image508| image:: media/image508.png
   :width: 8.32in
   :height: 3.373in
.. |image509| image:: media/image509.png
   :width: 4.68in
   :height: 0.52in
.. |image510| image:: media/image510.png
   :width: 4.413in
   :height: 0.44in
.. |image511| image:: media/image511.png
   :width: 2.84in
   :height: 0.2666in   
.. |image513| image:: media/image513.png
   :width: 8.28in
   :height: 4.586in  
.. |image514| image:: media/image514.png
   :width: 8.32in
   :height: 4.33in  
.. |image515| image:: media/image515.png
   :width: 8.306in
   :height: 3.867in  
.. |image518| image:: media/image518.png
   :width: 8.32in
   :height: 1.253in  
.. |image519| image:: media/image519.png
   :width: 8.307in
   :height: 4.12in  
.. |image520| image:: media/image520.png
   :width: 5.707in
   :height: 3.453in  
.. |image521| image:: media/image521.png
   :width: 8.307in
   :height: 3.467in  
.. |image522| image:: media/image522.png
   :width: 8.307in
   :height: 6.08in  
.. |image523| image:: media/image523.png
   :width: 5.453in
   :height: 2.613in  
.. |image524| image:: media/image524.png
   :width: 8.307in
   :height: 4.733in  
.. |image525| image:: media/image525.png
   :width: 8.33in
   :height: 3.88in  
.. |image526| image:: media/image526.png
   :width: 8.3467in
   :height: 2.853in  
