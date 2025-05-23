.. index::
	single: FAQ

**************************
Frequently Asked Questions
**************************

This is a list of Frequently Asked Questions about the Data Searches tool. Feel free to suggest new entries!

General questions
=================

**How do I get a copy of the tool?**

	The source code as well as the installer setups can be downloaded from GitHub (`MapInfo <https://github.com/LERCAutomation/DataSearches-MapInfo/releases>`_ or `ArcGIS <https://github.com/LERCAutomation/DataSearches--ArcObjects2/releases>`_ or `ArcGIS Pro <https://github.com/LERCAutomation/DataSearches-ArcPro/releases>`_). Please ensure that you use the correct configuration file, examples copy of which are also included with the releases.

**Can several people use the tool at the same time?**

	Any number of users can use the tool if they have a copy of the tool installed or loaded in their own copy of GIS. Where outputs are written to a central (network) location, it is important to ensure that no two users are saving to the same files at the same time as this can lead to unexpected results.

**Does the tool work with QGIS?**

	Currently only ArcMap Desktop, ArcGIS Pro and MapInfo implementations of the tool exist. However, if funding was available the tool could be adapted to also support QGIS.

Operating the tool
==================

**One of the data layers I want to use isn't showing in the form. How do I get it to show up?**

	This issue can arise in several ways:

	- The layer isn't loaded in your GIS document or workspace. In this case, a :ref:`message will pop up <figlaunchwarning>` before the form is displayed informing you the layer isn't loaded. Add the layer to GIS and reload the profile and the problem should be resolved.
	- The layer isn't listed in the XML configuration document. Please refer to the :doc:`Setting up the tool <../setup/setup>` section and add it as a map layer.
	- The map layer is listed in the configuration document, but the 'LayerName' is spelled incorrectly. Note that the name must follow the exact format of the name of the layer in the active map window (in ArcGIS Pro the name is also case sensitive).

**I ran a data search twice with different radius settings. The combined sites table only has one set of results**

	When the same search reference is used twice, the combined sites table will be overwritten in the second search unless **Append to existing table** is selected in the 'Create Combined Sites Table' option. Please see the :ref:`warning <OverwriteWarning>` in the 'Running the Tool' section for details.

**I ran a data search twice with different radius settings and included the same data layers. There is only one set of results**

	When the same search reference is used twice, the output from any layers that were also included in the first search will be overwritten. If you need to keep two sets of results, for example using different search radii, then move the results from the first search to a different folder before carrying out the second search.


Tool issues
===========

**How do I report a new bug or propose a change in the tool?**

	Please report any issues or propose any new changes to `Andy Foy <mailto:andy@andyfoyconsulting.co.uk>`_. 
