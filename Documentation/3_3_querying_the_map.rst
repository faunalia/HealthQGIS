.. |mActionLabeling| image:: img/mActionLabeling.png


3.3 Querying the map
=====================

Labeling
-------------

The |mActionLabeling| Labels core application provides smart labeling for vector point, line and polygon layers and only requires a few parameters. 



You can access to the label menu by clicking on the |mActionLabeling| toolbar button:

.. figure:: img/querying_the_map_1.png
	:align: center
	:scale: 70%

or through the **Properties menu** of the layer you want to label (just double click on it) and then select the **labels** tab of the dialog window:

 .. figure:: img/querying_the_map_2.png
	:align: center
	:scale: 70%

First step is to activate the checkbox **Label this layer with** checkbox and select an attribute column from the drop down menu to use for labeling and click **OK**:

 .. figure:: img/querying_the_map_3.png
	:align: center
	:scale: 70%

If you want to perform more fancy labels you have a lot of options in the label dialog windows:

* **Text**: changes the font, the dimension, the color and other features related with the text
* **Formatting**: allows to align the text or choose the decimal places (the label is numeric)
* **Buffer**: draws a buffer around the text
* **Background**: draws a shaped background beyond the label
* **Shadow**: draws a shadow around the text
* **Placement**: manages label placement and the labeling priority
* **Rendering**: defines label and feature options

 .. figure:: img/querying_the_map_4.png
	:align: center
	:scale: 70%

Feature count
--------------------

QGIS has an easy way to count the feature of the polygons. Just click with the right button on the layer you want to count the features of and activate the checkbox **Show Feature Count**. You can now see in square brackets the feature count:

 .. figure:: img/querying_the_map_5.png
	:align: center
	:scale: 70%

Be aware that the feaure count depends directly on the classification of the polygon!


 
