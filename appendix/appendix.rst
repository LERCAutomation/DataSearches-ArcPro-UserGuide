********
Appendix
********

.. index::
    single: Appendix; Change Log
    single: Appendix
    single: Change Log

.. _change_log:

Change Log
==========

**1.1.2**
(9th May 2025)
    * :guilabel:`New` - Added config variable to convert labels to annotation
    * :guilabel:`Changed` - Move temporary GDB to output folder and use with annotations
    * :guilabel:`Fix` - Bug setting %ref% in layouts

**1.1.1**
(22th Apr 2025)
    * :guilabel:`Improved` - Add %organisation% as variable for output folders, files, etc.

**1.1.0**
(15th Apr 2025)
    * :guilabel:`New` - Added config variables: SearchMapName, MapNames, LayoutNames, SearchRefElement, SiteNameElement, OrganisationElement, RadiusElement, BespokeElements, ZoomRatio and ZoomScales
    * :guilabel:`New` - Added <MapLayers> config variable: MapName
    * :guilabel:`New` - Add buffer and search area to all map windows, if required
    * :guilabel:`New` - Add kept outputs to specified map window name for each layer
    * :guilabel:`New` - Set all preset and bespoke text elements in all layout windows
    * :guilabel:`New` - Zoom to buffer or search area extent at specified zoom ratio in all layout windows
    * :guilabel:`New` - Zoom out to next largest zoom scale in all layout windows, if required
    * :guilabel:`Improved` - Zoom to buffer or search area extent at specified zoom ratio in all map windows
    * :guilabel:`Fix` - Display and set form comboboxes correctly when default values are blank
    * :guilabel:`Removed` - Removed config variables: BufferUnitOptions, AddSelectedLayersOptions, OverwriteLabelOptions, CombinedSitesTableOptions

**1.0.12**
(17th Feb 2025)
    * :guilabel:`Changed` - Added config variable 'GISFolder' to output GIS files to separate sub-folder
    * :guilabel:`Fix` - Ensure search area and buffer are always added to map if kept
    * :guilabel:`Fix` - Possible error when outputting if GIS layers not added to map

**1.0.11**
(14th Jan 2025)

    * :guilabel:`Changed` - Checkboxes styles now match ArcGIS Pro style
    * :guilabel:`Changed` - Standardised shared functions

**1.0.10**
(6th Jan 2025)

    * :guilabel:`Improved` - Extra error handling when updating search layer
    * :guilabel:`Fix` - Ensure XML profiles are not repeated
    * :guilabel:`Fix` - Report errors when adding search area and buffer to map

**1.0.9**
(17th Dec 2024)

    * :guilabel:`Change` - Always open log file after errors

**1.0.8**
(12th Dec 2024)

    * :guilabel:`Change` - Use comma separator for txt output files

**1.0.7**
(5th Dec 2024)

    * :guilabel:`New` - Set label properties and visibility from lyrx file

**1.0.6**
(29th Nov 2024)

    * :guilabel:`Change` - Standardise shared functions
    * :guilabel:`Change` - Adjust progress bar to count only selected layers
    * :guilabel:`New` - Apply symbology even when layer file is specified
    * :guilabel:`Change` - Don't clear/reload form when attribute table is opened/closed

**1.0.5**
(29th Oct 2024)

    * :guilabel:`New` - Button to expand/contract the map layers list
    * :guilabel:`New` - Improve load performance
    * :guilabel:`Change` - Standardise shared functions
    * :guilabel:`Fix` - Bug where map layer names in user interface are truncated

**1.0.4**
(12th Aug 2024)

    * :guilabel:`New` - Improve panel layout
    * :guilabel:`New` - Enable column names to be case insensitive
    * :guilabel:`Change` - Simplify stats column clause syntax
    * :guilabel:`New` - Add units to Area column name when created
    * :guilabel:`Fix` - Bug labelling columns

**1.0.3**
(9th Aug 2024)

    * :guilabel:`New` - Enable order by fields to sort in ascending or descending order
    * :guilabel:`New` - Option to output nearest distance and bearing fields using centroid or boundary
    * :guilabel:`New` - Option to keep selected layers even if not adding to the map
    * :guilabel:`New` - Add step numbers for each layer being processed to the log file
    * :guilabel:`Fix` - Bug when checking output, group by and order by fields exist
    * :guilabel:`Fix` - Bug when columns not found don't result in an error

**1.0.2**
(7th Aug 2024)

    * :guilabel:`New` - Display warning when search ref not found in search layers
    * :guilabel:`New` - Option to pause map during processing
    * :guilabel:`Improved` - Show notifications upon completion
    * :guilabel:`Improved` - Improve method of verifying query
    * :guilabel:`Fix` - Bug not moving output layers to group layer
    * :guilabel:`Fix` - Bug overwriting combined sites table

**1.0.1**
(18th Jul 2024)

    * :guilabel:`New` - Hide site name and organisation fields when not required
    * :guilabel:`New` - Enable process to be cancelled by user

    * :guilabel:`New` - Add new refresh table counts button
    * :guilabel:`Improved` - Adjust list columns width to size of contents

**1.0.0**
(11th Jul 2024)

    * Initial version


.. raw:: latex

   \newpage

.. index::
    single: Appendix; XML files
    single: XML files
    single: XML files; Example Tool XML file

.. _example_xml:

Example tool XML file
=====================

Below is an example of tool XML that must be present for the Data Searches tool in ArcGIS Pro.

::


    <?xml version="1.0" encoding="utf-8"?>

    <!--
    WARNING: This file should be changed carefully and a backup should be
    taken before any changes so that they can be backed out.  Changed lines
    can also be commented out as below.
    -->

    <!--
    This config file contains all the variables used by the DataSearches
    ArcGIS Add-in tool.

    The 'configuration' node is the 'root' node and signifies the start of the
    contents of the configuration file.

    The 'InitialConfig' node contains the nodes relating to the initial setup of the tool.

    Note a detailed XML profile file must also be set up in order for the tool to run.

    -->

    <configuration>
    <InitialConfig>
        <!-- Are we allowing the user to choose their own configuration file? Yes/No -->
        <ChooseXML>
            <value>Yes</value>
        </ChooseXML>

        <!-- What is the default XML file called? If blank, the system looks for DefaultProfile.xml -->
        <DefaultProfile>
            <value>DefaultProfile.xml</value>
        </DefaultProfile>

        <!-- The URL of the online user guide -->
        <HelpURL>
            <value>https://datasearches-userguide.readthedocs.io/en/latest/</value>
        </HelpURL>
    </InitialConfig>
    </configuration>


.. index::
	single: XML files; Example user XML profile

Example user XML profile
========================

Below is an example of an XML profile that might be used to set up the Data Searches tool in ArcGIS Pro.
Note, many of the settings have been included for illustration only and it is up to each user or LERC to
ensure the system is configured to their requirements.

::

    <?xml version="1.0" encoding="utf-8"?>

    <!--
    WARNING: This file should be changed carefully and a backup should be
    taken before any changes so that they can be backed out.  Changed lines
    can also be commented out as below.
    -->

    <!--
    This config file contains all the variables used by the DataSearches
    ArcGIS Pro add-in.

    The 'configuration' node is the 'root' node and signifies the start of the
    contents of the configuration file.

    The 'DataSearches' node contains all of the entries relating to the
    ArcGIS Pro add-in variables.

    Each entry relates to a file, folder, table name, column name or other variable
    used by the ArcGIS Pro add-in to select and export GIS data for each data search.
    -->

    <configuration>
    <DataSearches>

        <!-- The access database where all the data search details are stored. NOT CURRENTLY SUPPORTED.-->
        <DatabasePath>
            <value></value>
        </DatabasePath>

        <!-- The name of the table where the enquiries are stored in the database table. NOT CURRENTLY SUPPORTED. -->
        <DatabaseTable>
            <value>Enquiries</value>
        </DatabaseTable>

        <!-- The column name of the search reference unique value in the database table. NOT CURRENTLY SUPPORTED. -->
        <DatabaseRefColumn>
            <value>EnquiryRef</value>
        </DatabaseRefColumn>

        <!-- The column name of the site name in the database table. NOT CURRENTLY SUPPORTED. -->
        <DatabaseSiteColumn>
            <value>SiteName</value>
        </DatabaseSiteColumn>

        <!-- The column name of the organisation in the database table. NOT CURRENTLY SUPPORTED. -->
        <DatabaseOrgColumn>
            <value>Organisation</value>
        </DatabaseOrgColumn>

        <!-- Is a site name required? Yes/No. -->
        <RequireSiteName>
            <value>Yes</value>
        </RequireSiteName>

        <!-- Is an organisation required? Yes/No. -->
        <RequireOrganisation>
            <value>No</value>
        </RequireOrganisation>

        <!-- Whether the search table should be updated? Yes/No. -->
        <UpdateTable>
            <value>Yes</value>
        </UpdateTable>

        <!-- The character(s) used to replace any special characters in folder names. Space is allowed. -->
        <RepChar>
            <value xml:space="preserve"> </value>
        </RepChar>

        <!-- The folder where the layer files are stored. -->
        <LayerFolder>
            <value>D:\Data Tools\DataSearches\LayerFiles</value>
        </LayerFolder>

        <!-- The file location where all data search folders are stored. -->
        <SaveRootDir>
            <value>D:\Data Tools\DataSearches\Reports</value>
        </SaveRootDir>

        <!-- The folder where the report will be saved. -->
        <SaveFolder>
            <value>%shortref% %sitename%</value>
        </SaveFolder>

        <!-- The sub-folder where all data search extracts will be written to. -->
        <ExtractFolder>
            <value>gis %subref%</value>
        </ExtractFolder>

        <!-- The sub-folder where all data search GIS files will be saved to. -->
        <GISFolder>
            <value>GIS Files</value>
        </GISFolder>

        <!-- The log file name created by the tool to output messages. -->
        <LogFileName>
            <value>DataSearch_%subref%.log</value>
        </LogFileName>

        <!-- Whether the map processing should be paused during processing? -->
        <PauseMap>
            <value>Yes</value>
        </PauseMap>

        <!-- By default, should an existing log file be cleared? -->
        <DefaultClearLogFile>
            <value>No</value>
        </DefaultClearLogFile>

        <!-- By default, should the log file be opened after running. -->
        <DefaultOpenLogFile>
            <value>Yes</value>
        </DefaultOpenLogFile>

        <!-- The default size to use for the buffer. -->
        <DefaultBufferSize>
            <value>1</value>
        </DefaultBufferSize>

        <!-- The default option (position in the list) to use for the buffer units.
        Options are: Centimetres, Metres, Kilometres, Feet, Yards, Miles. -->
        <DefaultBufferUnit>
            <value>3</value>
        </DefaultBufferUnit>

        <!-- Are we keeping the buffer GIS file? Yes/No. -->
        <KeepBufferArea>
            <value>Yes</value>
        </KeepBufferArea>

        <!-- The prefix output name for the buffer GIS file. The size of the buffer will be added automatically. -->
        <BufferPrefix>
            <value>Buffer_%subref%</value>
        </BufferPrefix>

        <!-- The name of the buffer symbology layer file. -->
        <BufferLayerFile>
            <value>BufferOutline.lyrx</value>
        </BufferLayerFile>

        <!-- The base name of the layer to use as the search area. -->
        <SearchLayer>
            <value>Enquiry Site</value>
        </SearchLayer>

        <!-- The extension names for point, polygon and line search area layers. 
        Leave blank to just use the SearchLayer name -->
        <SearchLayerExtensions>
            <value>_point;_region;_polyline</value>
        </SearchLayerExtensions>

        <!-- The column name in the search area layer used to store the search reference. -->
        <SearchColumn>
            <value>EnquiryID</value>
        </SearchColumn>

        <!-- The column name in the search area layer used to store the site name. -->
        <SiteColumn>
            <value>Site_Name</value>
        </SiteColumn>

        <!-- The column name in the search area layer used to store the organisation. -->
        <OrgColumn>
            <value>Organisati</value>
        </OrgColumn>

        <!-- The column name in the search area layer used to store the radius. -->
        <RadiusColumn>
            <value>Radius</value>
        </RadiusColumn>

        <!-- The window names for all maps, loaded from a semi-colon separated string. -->
        <MapNames>
            <value>SINCMap;StatutoryMap;HabitatMap</value>
        </MapNames>

        <!-- The window names for all layouts, loaded from a semi-colon separated string. -->
        <LayoutNames>
            <value>SINCLayout;StatutoryLayout;HabitatLayout</value>
        </LayoutNames>

        <!-- The text element name in each layout used to store the search reference. -->
        <SearchRefElement>
            <value>SearchRef</value>
        </SearchRefElement>

        <!-- The text element name in each layout used to store the site name. -->
        <SiteNameElement>
            <value>SiteName</value>
        </SiteNameElement>

        <!-- The text element name in each layout used to store the organisation. -->
        <OrganisationElement>
            <value></value>
        </OrganisationElement>

        <!-- The text element name in each layout used to store the radius. -->
        <RadiusElement>
            <value>Radius</value>
        </RadiusElement>

        <!-- The text element names and contents in each layout used to store any bespoke text.
        Name and contents must be divided by ';'. Multiple entries must be divided by '$'. -->
        <BespokeElements>
            <value>Bespoke;Land at %sitename% + %radius%</value>
        </BespokeElements>

        <!-- The ratio that map and layout windows will be zoomed out after zooming to a layer extent. -->
        <ZoomRatio>
            <value>1.05</value>
        </ZoomRatio>    

        <!-- The list of zoom scales to use for all layouts, loaded from a semi-colon separated string.
        Note additional scales will be extrapolated from the last two entries. -->
        <ZoomScales>
            <value>2500;5000;7500;10000;12500;15000;20000</value>
        </ZoomScales>    

        <!-- Are we keeping the search feature as a layer? Yes/No -->
        <KeepSearchFeature>
            <value>No</value>
        </KeepSearchFeature>

        <!-- The name of the search feature output layer. -->
        <SearchOutputName>
            <value>SearchArea_%subref%</value>
        </SearchOutputName>

        <!-- The base name of the search layer symbology file (without the .lyrx). 
        Note the relevant extension (from SearchLayerExtensions) will be added. -->
        <SearchSymbologyBase>
            <value>FeatureSymbology</value>
        </SearchSymbologyBase>

        <!-- The buffer aggregate column values. Delimited with semicolons. -->
        <AggregateColumns>
            <value>SearchRef;Organisation;SiteName;Radius</value>
        </AggregateColumns>

        <!-- The default option to keep the selected layers or not. Yes/No (default). Leave blank to hide option in dialog. -->
        <DefaultKeepSelectedLayers>
            <value>Yes</value>
        </DefaultKeepSelectedLayers>

        <!-- The default option for whether selected map layers should be added to the map window. Leave blank to hide option in dialog.
        Options are: No;Yes - Without labels;Yes - With labels.
        Select the position in the list. The default is 1 = No.    -->
        <DefaultAddSelectedLayers>
            <value>3</value>
        </DefaultAddSelectedLayers>

        <!-- The name of the group layer that will be created in the ArcGIS table of contents. -->
        <GroupLayerName>
            <value>%subref%</value>
        </GroupLayerName>

        <!-- Whether any map label columns should be overwritten. Leave blank to hide option in dialog.
        Options are: No;Yes - Reset Each Layer;Yes - Reset Each Group;Yes - Do Not Reset.
        Select the position in the list. The default is 1 = No.    -->
        <DefaultOverwriteLabels>
            <value>1</value>
        </DefaultOverwriteLabels>

	<!-- Should all map labels be converted to annotation? Yes/No -->
	<ConvertLabelsToAnnotation>
		<value>Yes</value>
	</ConvertLabelsToAnnotation>

        <!-- The units any area measurements will be done in. Choose from Ha, Km2, m2. Default is Ha. -->
        <AreaMeasurementUnit>
            <value>Ha</value>
        </AreaMeasurementUnit>

        <!-- Whether a combined sites table should be created. Leave blank to hide option in dialog.
        Option are: None;Append to existing table;Overwrite existing table.
        Select the position in the list. The default is 1 = None.    -->
        <DefaultCombinedSitesTable>
            <value>2</value>
        </DefaultCombinedSitesTable>

        <!-- The details of the combined sites table. -->
        <CombinedSitesTable>
            <Name>
                <value>%subref%_sites</value> <!-- do not include .txt or .csv -->
            </Name>
            <Columns>
                <value>Site_Type, Site_Name, Site_Area</value>
            </Columns>
            <Format>
                <value>csv</value>
            </Format>
        </CombinedSitesTable>

        <!-- The names, local names, suffixes, SQL clauses and formats of the map tables. -->
        <MapLayers>
            <Sites_-_SINC_AoDs>
                <LayerName> <!-- The name of the layer in the display -->
                    <value>GiGL_SINCs_AoD</value>
                </LayerName>
                <MapName> <!-- The name of the map window to add the layer to if it is to be added to the map -->
                    <value>SINCMap</value>
                </MapName>
                <GISOutputName> <!-- The name used for any GIS data extracts -->
                    <value>GiGL_SINCs_AOD_%subref%</value>
                </GISOutputName>
                <TableOutputName> <!-- The name used for any tabular extracts -->
                    <value>%subref%_aods</value>
                </TableOutputName>
                <Columns> <!-- The columns to be used in the tabular extracts -->
                    <value>Ward</value>
                </Columns>
                <GroupColumns> <!-- The columns that should be used for grouping results -->
                    <value>Ward</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </GroupColumns> <!-- The columns that should be used for grouping results -->
                <StatisticsColumns> <!-- If grouping is used, any statistics that should be generated. -->
                    <value></value><!-- example: area_ha;SUM$Status;FIRST -->
                </StatisticsColumns>
                <OrderColumns> <!-- Overrides GroupColumns. Any columns by which the results should be ordered -->
                    <value>Ward</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea> <!-- Yes / No attribute to define whether an Area field should be included. Ignored for points. -->
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields> <!-- Yes / No attribute to define whether a Distance field should be included -->
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius> <!-- Yes / No attribute to define whether a Radius field should be included -->
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn> <!-- The column in this layer that contains the unique identifier -->
                    <value>Ward</value>
                </KeyColumn>
                <Format> <!-- The format that any tabular data will be saved as -->
                    <value>Txt</value>
                </Format>
                <KeepLayer> <!-- A Yes/No attribute to define whether a GIS extract should be saved -->
                    <value>Yes</value>
                </KeepLayer>
                <OutputType> <!-- Whether the layer that is kept should be selected by, clipped to or intersected with the search area -->
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
                </OutputType>
                <LoadWarning> <!-- Whether there will be a warning if this layer is not loaded in the active map. -->
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer> <!-- Whether this layer should be pre-selected in the dialog. -->
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels> <!-- switch to decide whether the defined labels should be switched on when displayed. -->
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName> <!-- The name of a layer file (*.lyr) that should be used to symbolise the extract -->
                    <value>SINCs.lyrx</value> <!-- Overrides any label settings defined below -->
                </LayerFileName>
                <OverwriteLabels> <!-- A Yes/No attribute to define whether labels may be overwritten -->
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn> <!-- The name of the label column in this layer (if any) -->
                    <value>Ward</value>
                </LabelColumn>
                <LabelClause> <!-- The definition of the labels for this layer (if any) -->
                    <!-- format: Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
                    <value></value>
                </LabelClause>
                <MacroName> <!-- The Visual Basic macro script to trigger to post-process the tabular output -->
                    <value></value>
                </MacroName>
                <CombinedSitesColumns> <!-- The columns to be used in the combined sites table. -->
                    <!-- Leave blank if the layer should not be included in the combined sites table -->
                    <!-- Distance may be included as a keyword if IncludeNearFields is set to Yes-->
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns> <!-- Columns that should be used to group data before inclusion in the combined sites table, if any -->
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns> <!-- Statistics columns and their required stats to be used for the combined sites table if CombinedSitesGroupColumns has been specified -->
                    <value></value> <!-- Must include the remaining columns -->
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns> <!-- Columns by which results should be ordered in the Combined Sites table -->
                    <value></value> <!-- Overrides CombinedSitesGroupColumns -->
                </CombinedSitesOrderByColumns>
            </Sites_-_SINC_AoDs>
            <Sites_-_Boroughs>
                <LayerName>
                    <value>LBPolygonsMeridian</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>Borough_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_boroughs</value>
                </TableOutputName>
                <Columns>
                    <value>BoroughCod, BoroughNam</value>
                </Columns>
                <GroupColumns>
                    <value>BoroughCod, BoroughNam</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>BoroughCod</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>Ward</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>No</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>BoroughNam</value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Sites_-_Boroughs>
            <Sites_-_SACs>
                <LayerName>
                    <value>SACLondon</value>
                </LayerName>
                <MapName>
                    <value>StatutoryMap</value>
                </MapName>
                <GISOutputName>
                    <value>SAC_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sacs</value>
                </TableOutputName>
                <Columns>
                    <value>SAC_Name</value>
                </Columns>
                <GroupColumns>
                    <value>SAC_Name</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SAC_Name</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>SAC_Name</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>SAC_Name</value>
                </LabelColumn>
                <LabelClause>
                    <value>Font ("Arial",256,10,16711680,16777215) With SAC_Name Auto On</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value>"SAC", SAC_Name, SAC_Area</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>SAC_Name, SAC_Area</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value>SAC_Name</value>
                </CombinedSitesOrderByColumns>

            </Sites_-_SACs>
            <Sites_-_SPAs>
                <LayerName>
                    <value>SPALondon</value>
                </LayerName>
                <MapName>
                    <value>StatutoryMap</value>
                </MapName>
                <GISOutputName>
                    <value>SPA_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_spas</value>
                </TableOutputName>
                <Columns>
                    <value>SPA_Name</value>
                </Columns>
                <GroupColumns>
                    <value>SPA_Name</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SPA_Name</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>SPA_Name</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>SPA_Name</value>
                </LabelColumn>
                <LabelClause>
                    <value>Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value>"SPA", SPA_Name, SPA_Area</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>SPA_Name, SPA_Area</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value>SPA_Name</value>
                </CombinedSitesOrderByColumns>
            </Sites_-_SPAs>
            <Sites_-_Ramsars>
                <LayerName>
                    <value>RAMSARLondon</value>
                </LayerName>
                <MapName>
                    <value>StatutoryMap</value>
                </MapName>
                <GISOutputName>
                    <value>RAMSAR_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_ramsars</value>
                </TableOutputName>
                <Columns>
                    <value>Ramsar_Name</value>
                </Columns>
                <GroupColumns>
                    <value>Ramsar_Name</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>Ramsar_Name</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>Ramsar_Name</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>Ramsar_Name</value>
                </LabelColumn>
                <LabelClause>
                    <value>Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value>"Ramsar", Ramsar_Name, Ramsar_Area</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>Ramsar_Name, Ramsar_Area</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value>Ramsar_Name</value>
                </CombinedSitesOrderByColumns>
            </Sites_-_Ramsars>
            <Sites_-_SSSIs>
                <LayerName>
                    <value>SSSILondon</value>
                </LayerName>
                <MapName>
                    <value>StatutoryMap</value>
                </MapName>
                <GISOutputName>
                    <value>SSSI_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sssis</value>
                </TableOutputName>
                <Columns>
                    <value>SSSI_Name</value>
                </Columns>
                <GroupColumns>
                    <value>SSSI_Name</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SSSI_Name</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>SSSI_Name</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>SSSI_Name</value>
                </LabelColumn>
                <LabelClause>
                    <value>Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value>"SSSI", SSSI_Name, SSSI_Area</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>SSSI_Name, SSSI_Area</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value>SSSI_Name</value>
                </CombinedSitesOrderByColumns>
            </Sites_-_SSSIs>
            <Sites_-_NNRs>
                <LayerName>
                    <value>NNRLondon</value>
                </LayerName>
                <MapName>
                    <value>StatutoryMap</value>
                </MapName>
                <GISOutputName>
                    <value>NNR_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_nnrs</value>
                </TableOutputName>
                <Columns>
                    <value>NNR_Name</value>
                </Columns>
                <GroupColumns>
                    <value>NNR_Name</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>NNR_Name</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>NNR_Name</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>NNR_Name</value>
                </LabelColumn>
                <LabelClause>
                    <value>Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value>"NNR", NNR_Name, NNR_Area</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>NNR_Name, NNR_Area</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value>NNR_Name</value>
                </CombinedSitesOrderByColumns>
            </Sites_-_NNRs>
            <Sites_-_LNRs>
                <LayerName>
                    <value>LNRLondon</value>
                </LayerName>
                <MapName>
                    <value>StatutoryMap</value>
                </MapName>
                <GISOutputName>
                    <value>LNR_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_lnrs</value>
                </TableOutputName>
                <Columns>
                    <value>LNR_Name</value>
                </Columns>
                <GroupColumns>
                    <value>LNR_Name</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>LNR_Name</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>LNR_Name</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>LNR_Name</value>
                </LabelColumn>
                <LabelClause>
                    <value>Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value>"LNR", LNR_Name, LNR_Area</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>LNR_Name, LNR_Area</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value>LNR_Name</value>
                </CombinedSitesOrderByColumns>
            </Sites_-_LNRs>
            <Sites_-_SINCs>
                <LayerName>
                    <value>GiGL_SINCs</value>
                </LayerName>
                <MapName>
                    <value>SINCMap</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SINCs_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sincs</value>
                </TableOutputName>
                <Columns>
                    <value>SiteRef, SiteName, Grade, AreaHa</value>
                </Columns>
                <GroupColumns>
                    <value>SiteRef, SiteName, Grade, AreaHa</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SiteRef</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>SiteRef</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName>
                    <value>SINCs.lyrx</value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>SiteRef</value>
                </LabelColumn>
                <LabelClause>
                    <value>Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Sites_-_SINCs>
            <Sites_-_pSINCs>
                <LayerName>
                    <value>GiGL_pSINCs</value>
                </LayerName>
                <MapName>
                    <value>SINCMap</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_pSINCs_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_psincs</value>
                </TableOutputName>
                <Columns>
                    <value>SiteRef, SiteName, Grade, AreaHa</value>
                </Columns>
                <GroupColumns>
                    <value>SiteRef, SiteName, Grade, AreaHa</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SiteRef</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>SiteRef</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>SiteRef</value>
                </LabelColumn>
                <LabelClause>
                    <value>Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Sites_-_pSINCs>
            <Sites_-_RIGS>
                <LayerName>
                    <value>GiGL_RIGSandLIGS</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_RIGSandLIGS_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_rigs</value>
                </TableOutputName>
                <Columns>
                    <value>GLA_ID, NAME, DESIGNATIO, AREA_HA</value>
                </Columns>
                <GroupColumns>
                    <value>GLA_ID, NAME, DESIGNATIO, AREA_HA</value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>GLA_ID</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>GLA_ID</value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>Yes</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>GLA_ID</value>
                </LabelColumn>
                <LabelClause>
                    <value>Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Sites_-_RIGS>
            <Species_-_Bat>
                <LayerName>
                    <value>GiGL_DesignatedSpp_Point</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppBat_Point_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppbat</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>Confident = 'N' and TaxonGroup = 'Mammals - Terrestrial (bats)'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>No</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Bat>
            <Species_-_Bat_Polygon>
                <LayerName>
                    <value>GiGL_AllTaxa_Polygon</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppBat_Polygon_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppbatpoly</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>(StatusLeg &lt;&gt; '' OR StatusOth &lt;&gt; '') And Confident = 'N' And TaxonGroup = 'Mammals - Terrestrial (bats)'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Bat_Polygon>
            <Species_-_Birds>
                <LayerName>
                    <value>GiGL_Birds_Point</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppBird_Point_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppbirds</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>GRPrec &lt; 2000 And Confident = 'N'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Birds>
            <Species_-_Plants>
                <LayerName>
                    <value>GiGL_Plants_Point</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppPlant_Point_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppplants</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>GRPrec &lt; 2000 And Confident = 'N'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Plants>
            <Species_-_Other>
                <LayerName>
                    <value>GiGL_OtherTaxa_Point</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppOther_Point_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppother</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>GRPrec &lt; 2000 And Confident = 'N'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Other>
            <Species_-_Historic>
                <LayerName>
                    <value>GiGL_HistoricSpp_Point</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppHistoric_Point_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_spphist</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>GRPrec &lt; 2000 And Confident = 'N'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Historic>
            <Species_-_AllTaxa_Polygon>
                <LayerName>
                    <value>GiGL_AllTaxa_Polygon</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppAll_Polygon_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppalltaxapoly</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>Confident = 'N'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_AllTaxa_Polygon>
            <Species_-_Designated>
                <LayerName>
                    <value>GiGL_DesignatedSpp_Point</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppDesig_Point_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppdesg</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>Confident = 'N'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Designated>
            <Species_-_Designated_Polygon>
                <LayerName>
                    <value>GiGL_AllTaxa_Polygon</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppDesig_Polygon_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppdesgpoly</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>(StatusLeg &lt;&gt; '' OR StatusOth &lt;&gt; '') And Confident = 'N'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Designated_Polygon>
            <Species_-_Confidential>
                <LayerName>
                    <value>GiGL_DesignatedSpp_Point</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppConf_Point_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppconf</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>Confident = 'Y'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Confidential>
            <Species_-_Confidential_Polygon>
                <LayerName>
                    <value>GiGL_AllTaxa_Polygon</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppConf_Poly_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sppconfpoly</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName, Distance</value>
                </OrderColumns>
                <Criteria>
                    <value>(StatusLeg &lt;&gt; '' OR StatusOth &lt;&gt; '') And Confident = 'Y'</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_Confidential_Polygon>
            <Species_-_LISI>
                <LayerName>
                    <value>GiGL_LISISpp_Point</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppLISI_Point_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_spplisi</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_LISI>
            <Species_-_LISI_polygon>
                <LayerName>
                    <value>GiGL_AllTaxa_Polygon</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_SppLISI_Polygon_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_spplisipoly</value>
                </TableOutputName>
                <Columns>
                    <value>TaxonName, CommonName, TaxonRank, TaxonGroup, SortOrder, Abundance, RecDate, RecYear, Recorder, Determiner, GridRef, GRPrec, GRQual, Easting, Northing, Location, BreedStat, StatusLeg, StatusOth, StatusLISI, SurveyName, SurveyBy, Comment, Confident, Sensitive, Verified, RecOccKey, VersionDt, Licence, Distance(CentroidX(Select_Table.obj), CentroidY(Select_Table.obj), CentroidX(Buffer_Area.obj), CentroidY(Buffer_Area.obj), "m")"Distance", CentroidX(Select_Table.obj)"SppX", CentroidY(Select_Table.obj)"SppY", CentroidX(Buffer_Area.obj)"SearchX", CentroidY(Buffer_Area.obj)"SearchY"</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SortOrder, TaxonName</value>
                </OrderColumns>
                <Criteria>
                    <value>StatusLISI &lt;&gt; ''</value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Species_-_LISI_polygon>
            <Habitats_-_Surveys>
                <LayerName>
                    <value>GiGL_habitats</value>
                </LayerName>
                <MapName>
                    <value>HabitatMap</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_habitats_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_habsurvey</value>
                </TableOutputName>
                <Columns>
                    <value>SiteName, PolygonID, GridRef, AreaHa, SurveyDate, HabShort, HabClass</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SiteRef, SurveyDate Desc</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Habitats_-_Surveys>
            <Habitats_-_BAP>
                <LayerName>
                    <value>GiGL_BAP_CA_S</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_BAP_CA_S_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_baphabitat</value>
                </TableOutputName>
                <Columns>
                    <value>SiteName, PolygonID, GridRef, AreaHa, CreatedDt, CondShort, SuitShort</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SiteRef, CreatedDt Desc</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Habitats_-_BAP>
            <Habitats_-_OpenSpaces>
                <LayerName>
                    <value>GiGL_OpenSpace_Sites</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_OpenSpace_Sites_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_openspace</value>
                </TableOutputName>
                <Columns>
                    <value>SiteName, SiteID, GridRef, AreaHa, PPG17, PrimaryUse, OtherUses, StatDes, NonStatDes, LandscDes, Access, Features</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>SiteName, SiteID</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>csv</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Habitats_-_OpenSpaces>
            <Other_-_Notable_Thames_Structures>
                <LayerName>
                    <value>GiGL_JettyRoosts</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_JettyRoosts_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_jettyroosts</value>
                </TableOutputName>
                <Columns>
                    <value>StructureName, AdditionalName, StructureType, Comment, SpeciesComment, SpeciesCommentDate, Easting, Northing</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value>StructureName, StructureType</value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value>Txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Other_-_Notable_Thames_Structures>
            <Other_-_GreenBelt>
                <LayerName>
                    <value>GiGL_GreenBelt</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_GreenBelt_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_greenbelt</value>
                </TableOutputName>
                <Columns>
                    <value>SiteName, SiteID</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value></value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Other_-_GreenBelt>
            <Other_-_MOL>
                <LayerName>
                    <value>GiGL_MOL</value>
                </LayerName>
                <MapName>
                    <value>Layers</value>
                </MapName>
                <GISOutputName>
                    <value>GiGL_MOL_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_mol</value>
                </TableOutputName>
                <Columns>
                    <value>SiteName, SiteID</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value></value>
                </StatisticsColumns>
                <OrderColumns>
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value>
                </IncludeArea>
                <IncludeNearFields>
                    <value>No</value>
                </IncludeNearFields>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value></value>
                </KeyColumn>
                <Format>
                    <value></value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value>
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels>
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName>
                    <value></value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value></value>
                </LabelColumn>
                <LabelClause>
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value></value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value></value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value>
                </CombinedSitesOrderByColumns>
            </Other_-_MOL>
        </MapLayers>

    </DataSearches>
    </configuration>

.. raw:: latex

	\newpage

.. index::
    single: Appendix; Licence
    single: License

.. _licence:

GNU Free Documentation License
==============================

Permission is granted to copy, distribute and/or modify this document under 
the terms of the GNU Free Documentation License, Version 1.3 or any later
version published by the Free Software Foundation; with no Invariant Sections,
no Front-Cover Texts and no Back-Cover Texts.  A copy of the license is
included in the Appendix section.

.. raw:: latex

    The full GNU Free Documentation License can be viewed at `www.gnu.org/licenses/fdl-1.3.en.html <https://www.gnu.org/licenses/fdl-1.3.en.html>`_

.. only:: html

::

                    GNU Free Documentation License
                     Version 1.3, 3 November 2008
    
    
     Copyright (C) 2000, 2001, 2002, 2007, 2008 Free Software Foundation, Inc.
         <http://fsf.org/>
     Everyone is permitted to copy and distribute verbatim copies
     of this license document, but changing it is not allowed.
    
    0. PREAMBLE
    
    The purpose of this License is to make a manual, textbook, or other
    functional and useful document "free" in the sense of freedom: to
    assure everyone the effective freedom to copy and redistribute it,
    with or without modifying it, either commercially or noncommercially.
    Secondarily, this License preserves for the author and publisher a way
    to get credit for their work, while not being considered responsible
    for modifications made by others.
    
    This License is a kind of "copyleft", which means that derivative
    works of the document must themselves be free in the same sense.  It
    complements the GNU General Public License, which is a copyleft
    license designed for free software.
    
    We have designed this License in order to use it for manuals for free
    software, because free software needs free documentation: a free
    program should come with manuals providing the same freedoms that the
    software does.  But this License is not limited to software manuals;
    it can be used for any textual work, regardless of subject matter or
    whether it is published as a printed book.  We recommend this License
    principally for works whose purpose is instruction or reference.
    
    
    1. APPLICABILITY AND DEFINITIONS
    
    This License applies to any manual or other work, in any medium, that
    contains a notice placed by the copyright holder saying it can be
    distributed under the terms of this License.  Such a notice grants a
    world-wide, royalty-free license, unlimited in duration, to use that
    work under the conditions stated herein.  The "Document", below,
    refers to any such manual or work.  Any member of the public is a
    licensee, and is addressed as "you".  You accept the license if you
    copy, modify or distribute the work in a way requiring permission
    under copyright law.
    
    A "Modified Version" of the Document means any work containing the
    Document or a portion of it, either copied verbatim, or with
    modifications and/or translated into another language.
    
    A "Secondary Section" is a named appendix or a front-matter section of
    the Document that deals exclusively with the relationship of the
    publishers or authors of the Document to the Document's overall
    subject (or to related matters) and contains nothing that could fall
    directly within that overall subject.  (Thus, if the Document is in
    part a textbook of mathematics, a Secondary Section may not explain
    any mathematics.)  The relationship could be a matter of historical
    connection with the subject or with related matters, or of legal,
    commercial, philosophical, ethical or political position regarding
    them.
    
    The "Invariant Sections" are certain Secondary Sections whose titles
    are designated, as being those of Invariant Sections, in the notice
    that says that the Document is released under this License.  If a
    section does not fit the above definition of Secondary then it is not
    allowed to be designated as Invariant.  The Document may contain zero
    Invariant Sections.  If the Document does not identify any Invariant
    Sections then there are none.
    
    The "Cover Texts" are certain short passages of text that are listed,
    as Front-Cover Texts or Back-Cover Texts, in the notice that says that
    the Document is released under this License.  A Front-Cover Text may
    be at most 5 words, and a Back-Cover Text may be at most 25 words.
    
    A "Transparent" copy of the Document means a machine-readable copy,
    represented in a format whose specification is available to the
    general public, that is suitable for revising the document
    straightforwardly with generic text editors or (for images composed of
    pixels) generic paint programs or (for drawings) some widely available
    drawing editor, and that is suitable for input to text formatters or
    for automatic translation to a variety of formats suitable for input
    to text formatters.  A copy made in an otherwise Transparent file
    format whose markup, or absence of markup, has been arranged to thwart
    or discourage subsequent modification by readers is not Transparent.
    An image format is not Transparent if used for any substantial amount
    of text.  A copy that is not "Transparent" is called "Opaque".
    
    Examples of suitable formats for Transparent copies include plain
    ASCII without markup, Texinfo input format, LaTeX input format, SGML
    or XML using a publicly available DTD, and standard-conforming simple
    HTML, PostScript or PDF designed for human modification.  Examples of
    transparent image formats include PNG, XCF and JPG.  Opaque formats
    include proprietary formats that can be read and edited only by
    proprietary word processors, SGML or XML for which the DTD and/or
    processing tools are not generally available, and the
    machine-generated HTML, PostScript or PDF produced by some word
    processors for output purposes only.
    
    The "Title Page" means, for a printed book, the title page itself,
    plus such following pages as are needed to hold, legibly, the material
    this License requires to appear in the title page.  For works in
    formats which do not have any title page as such, "Title Page" means
    the text near the most prominent appearance of the work's title,
    preceding the beginning of the body of the text.
    
    The "publisher" means any person or entity that distributes copies of
    the Document to the public.
    
    A section "Entitled XYZ" means a named subunit of the Document whose
    title either is precisely XYZ or contains XYZ in parentheses following
    text that translates XYZ in another language.  (Here XYZ stands for a
    specific section name mentioned below, such as "Acknowledgements",
    "Dedications", "Endorsements", or "History".)  To "Preserve the Title"
    of such a section when you modify the Document means that it remains a
    section "Entitled XYZ" according to this definition.
    
    The Document may include Warranty Disclaimers next to the notice which
    states that this License applies to the Document.  These Warranty
    Disclaimers are considered to be included by reference in this
    License, but only as regards disclaiming warranties: any other
    implication that these Warranty Disclaimers may have is void and has
    no effect on the meaning of this License.
    
    2. VERBATIM COPYING
    
    You may copy and distribute the Document in any medium, either
    commercially or noncommercially, provided that this License, the
    copyright notices, and the license notice saying this License applies
    to the Document are reproduced in all copies, and that you add no
    other conditions whatsoever to those of this License.  You may not use
    technical measures to obstruct or control the reading or further
    copying of the copies you make or distribute.  However, you may accept
    compensation in exchange for copies.  If you distribute a large enough
    number of copies you must also follow the conditions in section 3.
    
    You may also lend copies, under the same conditions stated above, and
    you may publicly display copies.
    
    
    3. COPYING IN QUANTITY
    
    If you publish printed copies (or copies in media that commonly have
    printed covers) of the Document, numbering more than 100, and the
    Document's license notice requires Cover Texts, you must enclose the
    copies in covers that carry, clearly and legibly, all these Cover
    Texts: Front-Cover Texts on the front cover, and Back-Cover Texts on
    the back cover.  Both covers must also clearly and legibly identify
    you as the publisher of these copies.  The front cover must present
    the full title with all words of the title equally prominent and
    visible.  You may add other material on the covers in addition.
    Copying with changes limited to the covers, as long as they preserve
    the title of the Document and satisfy these conditions, can be treated
    as verbatim copying in other respects.
    
    If the required texts for either cover are too voluminous to fit
    legibly, you should put the first ones listed (as many as fit
    reasonably) on the actual cover, and continue the rest onto adjacent
    pages.
    
    If you publish or distribute Opaque copies of the Document numbering
    more than 100, you must either include a machine-readable Transparent
    copy along with each Opaque copy, or state in or with each Opaque copy
    a computer-network location from which the general network-using
    public has access to download using public-standard network protocols
    a complete Transparent copy of the Document, free of added material.
    If you use the latter option, you must take reasonably prudent steps,
    when you begin distribution of Opaque copies in quantity, to ensure
    that this Transparent copy will remain thus accessible at the stated
    location until at least one year after the last time you distribute an
    Opaque copy (directly or through your agents or retailers) of that
    edition to the public.
    
    It is requested, but not required, that you contact the authors of the
    Document well before redistributing any large number of copies, to
    give them a chance to provide you with an updated version of the
    Document.
    
    
    4. MODIFICATIONS
    
    You may copy and distribute a Modified Version of the Document under
    the conditions of sections 2 and 3 above, provided that you release
    the Modified Version under precisely this License, with the Modified
    Version filling the role of the Document, thus licensing distribution
    and modification of the Modified Version to whoever possesses a copy
    of it.  In addition, you must do these things in the Modified Version:
    
    A. Use in the Title Page (and on the covers, if any) a title distinct
       from that of the Document, and from those of previous versions
       (which should, if there were any, be listed in the History section
       of the Document).  You may use the same title as a previous version
       if the original publisher of that version gives permission.
    B. List on the Title Page, as authors, one or more persons or entities
       responsible for authorship of the modifications in the Modified
       Version, together with at least five of the principal authors of the
       Document (all of its principal authors, if it has fewer than five),
       unless they release you from this requirement.
    C. State on the Title page the name of the publisher of the
       Modified Version, as the publisher.
    D. Preserve all the copyright notices of the Document.
    E. Add an appropriate copyright notice for your modifications
       adjacent to the other copyright notices.
    F. Include, immediately after the copyright notices, a license notice
       giving the public permission to use the Modified Version under the
       terms of this License, in the form shown in the Addendum below.
    G. Preserve in that license notice the full lists of Invariant Sections
       and required Cover Texts given in the Document's license notice.
    H. Include an unaltered copy of this License.
    I. Preserve the section Entitled "History", Preserve its Title, and add
       to it an item stating at least the title, year, new authors, and
       publisher of the Modified Version as given on the Title Page.  If
       there is no section Entitled "History" in the Document, create one
       stating the title, year, authors, and publisher of the Document as
       given on its Title Page, then add an item describing the Modified
       Version as stated in the previous sentence.
    J. Preserve the network location, if any, given in the Document for
       public access to a Transparent copy of the Document, and likewise
       the network locations given in the Document for previous versions
       it was based on.  These may be placed in the "History" section.
       You may omit a network location for a work that was published at
       least four years before the Document itself, or if the original
       publisher of the version it refers to gives permission.
    K. For any section Entitled "Acknowledgements" or "Dedications",
       Preserve the Title of the section, and preserve in the section all
       the substance and tone of each of the contributor acknowledgements
       and/or dedications given therein.
    L. Preserve all the Invariant Sections of the Document,
       unaltered in their text and in their titles.  Section numbers
       or the equivalent are not considered part of the section titles.
    M. Delete any section Entitled "Endorsements".  Such a section
       may not be included in the Modified Version.
    N. Do not retitle any existing section to be Entitled "Endorsements"
       or to conflict in title with any Invariant Section.
    O. Preserve any Warranty Disclaimers.
    
    If the Modified Version includes new front-matter sections or
    appendices that qualify as Secondary Sections and contain no material
    copied from the Document, you may at your option designate some or all
    of these sections as invariant.  To do this, add their titles to the
    list of Invariant Sections in the Modified Version's license notice.
    These titles must be distinct from any other section titles.
    
    You may add a section Entitled "Endorsements", provided it contains
    nothing but endorsements of your Modified Version by various
    parties--for example, statements of peer review or that the text has
    been approved by an organization as the authoritative definition of a
    standard.
    
    You may add a passage of up to five words as a Front-Cover Text, and a
    passage of up to 25 words as a Back-Cover Text, to the end of the list
    of Cover Texts in the Modified Version.  Only one passage of
    Front-Cover Text and one of Back-Cover Text may be added by (or
    through arrangements made by) any one entity.  If the Document already
    includes a cover text for the same cover, previously added by you or
    by arrangement made by the same entity you are acting on behalf of,
    you may not add another; but you may replace the old one, on explicit
    permission from the previous publisher that added the old one.
    
    The author(s) and publisher(s) of the Document do not by this License
    give permission to use their names for publicity for or to assert or
    imply endorsement of any Modified Version.
    
    
    5. COMBINING DOCUMENTS
    
    You may combine the Document with other documents released under this
    License, under the terms defined in section 4 above for modified
    versions, provided that you include in the combination all of the
    Invariant Sections of all of the original documents, unmodified, and
    list them all as Invariant Sections of your combined work in its
    license notice, and that you preserve all their Warranty Disclaimers.
    
    The combined work need only contain one copy of this License, and
    multiple identical Invariant Sections may be replaced with a single
    copy.  If there are multiple Invariant Sections with the same name but
    different contents, make the title of each such section unique by
    adding at the end of it, in parentheses, the name of the original
    author or publisher of that section if known, or else a unique number.
    Make the same adjustment to the section titles in the list of
    Invariant Sections in the license notice of the combined work.
    
    In the combination, you must combine any sections Entitled "History"
    in the various original documents, forming one section Entitled
    "History"; likewise combine any sections Entitled "Acknowledgements",
    and any sections Entitled "Dedications".  You must delete all sections
    Entitled "Endorsements".
    
    
    6. COLLECTIONS OF DOCUMENTS
    
    You may make a collection consisting of the Document and other
    documents released under this License, and replace the individual
    copies of this License in the various documents with a single copy
    that is included in the collection, provided that you follow the rules
    of this License for verbatim copying of each of the documents in all
    other respects.
    
    You may extract a single document from such a collection, and
    distribute it individually under this License, provided you insert a
    copy of this License into the extracted document, and follow this
    License in all other respects regarding verbatim copying of that
    document.
    
    
    7. AGGREGATION WITH INDEPENDENT WORKS
    
    A compilation of the Document or its derivatives with other separate
    and independent documents or works, in or on a volume of a storage or
    distribution medium, is called an "aggregate" if the copyright
    resulting from the compilation is not used to limit the legal rights
    of the compilation's users beyond what the individual works permit.
    When the Document is included in an aggregate, this License does not
    apply to the other works in the aggregate which are not themselves
    derivative works of the Document.
    
    If the Cover Text requirement of section 3 is applicable to these
    copies of the Document, then if the Document is less than one half of
    the entire aggregate, the Document's Cover Texts may be placed on
    covers that bracket the Document within the aggregate, or the
    electronic equivalent of covers if the Document is in electronic form.
    Otherwise they must appear on printed covers that bracket the whole
    aggregate.
    
    
    8. TRANSLATION
    
    Translation is considered a kind of modification, so you may
    distribute translations of the Document under the terms of section 4.
    Replacing Invariant Sections with translations requires special
    permission from their copyright holders, but you may include
    translations of some or all Invariant Sections in addition to the
    original versions of these Invariant Sections.  You may include a
    translation of this License, and all the license notices in the
    Document, and any Warranty Disclaimers, provided that you also include
    the original English version of this License and the original versions
    of those notices and disclaimers.  In case of a disagreement between
    the translation and the original version of this License or a notice
    or disclaimer, the original version will prevail.
    
    If a section in the Document is Entitled "Acknowledgements",
    "Dedications", or "History", the requirement (section 4) to Preserve
    its Title (section 1) will typically require changing the actual
    title.
    
    
    9. TERMINATION
    
    You may not copy, modify, sublicense, or distribute the Document
    except as expressly provided under this License.  Any attempt
    otherwise to copy, modify, sublicense, or distribute it is void, and
    will automatically terminate your rights under this License.
    
    However, if you cease all violation of this License, then your license
    from a particular copyright holder is reinstated (a) provisionally,
    unless and until the copyright holder explicitly and finally
    terminates your license, and (b) permanently, if the copyright holder
    fails to notify you of the violation by some reasonable means prior to
    60 days after the cessation.
    
    Moreover, your license from a particular copyright holder is
    reinstated permanently if the copyright holder notifies you of the
    violation by some reasonable means, this is the first time you have
    received notice of violation of this License (for any work) from that
    copyright holder, and you cure the violation prior to 30 days after
    your receipt of the notice.
    
    Termination of your rights under this section does not terminate the
    licenses of parties who have received copies or rights from you under
    this License.  If your rights have been terminated and not permanently
    reinstated, receipt of a copy of some or all of the same material does
    not give you any rights to use it.
    
    
    10. FUTURE REVISIONS OF THIS LICENSE
    
    The Free Software Foundation may publish new, revised versions of the
    GNU Free Documentation License from time to time.  Such new versions
    will be similar in spirit to the present version, but may differ in
    detail to address new problems or concerns.  See
    http://www.gnu.org/copyleft/.
    
    Each version of the License is given a distinguishing version number.
    If the Document specifies that a particular numbered version of this
    License "or any later version" applies to it, you have the option of
    following the terms and conditions either of that specified version or
    of any later version that has been published (not as a draft) by the
    Free Software Foundation.  If the Document does not specify a version
    number of this License, you may choose any version ever published (not
    as a draft) by the Free Software Foundation.  If the Document
    specifies that a proxy can decide which future versions of this
    License can be used, that proxy's public statement of acceptance of a
    version permanently authorizes you to choose that version for the
    Document.
    
    11. RELICENSING
    
    "Massive Multiauthor Collaboration Site" (or "MMC Site") means any
    World Wide Web server that publishes copyrightable works and also
    provides prominent facilities for anybody to edit those works.  A
    public wiki that anybody can edit is an example of such a server.  A
    "Massive Multiauthor Collaboration" (or "MMC") contained in the site
    means any set of copyrightable works thus published on the MMC site.
    
    "CC-BY-SA" means the Creative Commons Attribution-Share Alike 3.0 
    license published by Creative Commons Corporation, a not-for-profit 
    corporation with a principal place of business in San Francisco, 
    California, as well as future copyleft versions of that license 
    published by that same organization.
    
    "Incorporate" means to publish or republish a Document, in whole or in 
    part, as part of another Document.
    
    An MMC is "eligible for relicensing" if it is licensed under this 
    License, and if all works that were first published under this License 
    somewhere other than this MMC, and subsequently incorporated in whole or 
    in part into the MMC, (1) had no cover texts or invariant sections, and 
    (2) were thus incorporated prior to November 1, 2008.
    
    The operator of an MMC Site may republish an MMC contained in the site
    under CC-BY-SA on the same site at any time before August 1, 2009,
    provided the MMC is eligible for relicensing.
    
    
    ADDENDUM: How to use this License for your documents
    
    To use this License in a document you have written, include a copy of
    the License in the document and put the following copyright and
    license notices just after the title page:
    
        Copyright (c)  YEAR  YOUR NAME.
        Permission is granted to copy, distribute and/or modify this document
        under the terms of the GNU Free Documentation License, Version 1.3
        or any later version published by the Free Software Foundation;
        with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.
        A copy of the license is included in the section entitled "GNU
        Free Documentation License".
    
    If you have Invariant Sections, Front-Cover Texts and Back-Cover Texts,
    replace the "with...Texts." line with this:
    
        with the Invariant Sections being LIST THEIR TITLES, with the
        Front-Cover Texts being LIST, and with the Back-Cover Texts being LIST.
    
    If you have Invariant Sections without Cover Texts, or some other
    combination of the three, merge those two alternatives to suit the
    situation.
    
    If your document contains nontrivial examples of program code, we
    recommend releasing these examples in parallel under your choice of
    free software license, such as the GNU General Public License,
    to permit their use in free software.

