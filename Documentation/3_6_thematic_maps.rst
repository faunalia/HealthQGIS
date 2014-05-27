Thematic maps [3.6]
======================

Thematic maps production is a very simple task to perform with QGIS. Depending on the attribute table related to the layer you can easily create several map types. 
First of all you open the **Properties** menu of the layer you want to create the map by double clicking on it or right clicking and then choosing **Properties**. 
Now move to the **Style** tab: all the layer stylization are linked to this tab. 

Graduated color
-----------------------------


To create a graduated color map, open the **Properties** menu as described above and choose **Graduated** from the drop-down menu: 

.. figure:: img/graduated_1.png
	:align: center
	:scale: 100%

Now you have to choose a numeric field from the attribute table in order to create classes and link them to a specific color. The dropdown menu shown in the next figure shows all the available column of the attribute table. In the following example, the layer has an attribute that describes population of 2009: 

.. figure:: img/graduated_2.png
	:align: center
	:scale: 75%

You can choose a color ramp (or create one) and you can also customize the classification deciding the number of classes and the mode of classification. 
Once done click on **Classify**. 

.. figure:: img/graduated_3.png
	:align: center
	:scale: 75%

|
|

This is the result:

.. figure:: img/graduated_4.png
	:align: center
	:scale: 100%



Unique value
-----------------------------

In QGIS **unique value** classification is known as **Categorized** and you can access it from the dropdown menu as shown in the figure. 
In the following example we have classified Sri Lanka depending on the position of its counties. 

To make this classification, choose **Categorized** from the dropdown menu and then choose the field attribute table you want to perform the categorization (*PROV_Name* for example)

.. figure:: img/categorized_1.png
	:align: center
	:scale: 70%

.. figure:: img/categorized_2.png
	:align: center
	:scale: 75%

Choose the color (many other customization are available) and click on **Classify**. Then close the windows clicking on **OK**.  

.. figure:: img/categorized_3.png
	:align: center
	:scale: 75%

|
|
|
|

The result is:

.. figure:: img/categorized_4.png
	:align: center
	:scale: 90%
