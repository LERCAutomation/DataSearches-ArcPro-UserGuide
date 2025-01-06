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
        <!-- D:\Data Tools\Data Requests\Database\Data Requests - Data.accdb -->

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
            <value>Yes</value>
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
        <GISFolder>
            <value>gis %subref%</value>
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

        <!-- By default, should the log file be opened after running-->
        <DefaultOpenLogFile>
            <value>Yes</value>
        </DefaultOpenLogFile>

        <!-- The default size to use for the buffer -->
        <DefaultBufferSize>
            <value>1</value>
        </DefaultBufferSize>

        <!-- The options for the buffer units. It is not recommended that these are changed -->
        <!-- These are read as: unit to display; unit that ArcGIS uses (American spelling); abbreviated unit -->
        <BufferUnitOptions>
            <value>Centimetres;Centimeters;cm$Metres;Meters;m$Kilometres;Kilometers;km$Feet;Feet;ft$Yards;Yards;yds$Miles;Miles;mi</value>
        </BufferUnitOptions>

        <!-- The default option (position in the list) to use for the buffer units -->
        <DefaultBufferUnit>
            <value>3</value>
        </DefaultBufferUnit>

        <!-- Are we keeping the buffer GIS file? Yes/No -->
        <KeepBufferArea>
            <value>Yes</value>
        </KeepBufferArea>

        <!-- The prefix output name for the buffer GIS file. The size of the buffer will be added automatically. -->
        <BufferPrefix>
            <value>Buffer_%subref%</value>
        </BufferPrefix>

        <!-- The name of the buffer symbology layer file -->
        <BufferLayerFile>
            <value>BufferOutline2.lyrx</value>
        </BufferLayerFile>

        <!-- The base name of the layer to use as the search area -->
        <SearchLayer>
            <value>Enquiry Site</value>
        </SearchLayer>

        <!-- The extension names for point, polygon and line search area layers. 
        Leave blank to just use the SearchLayer name -->
        <SearchLayerExtensions>
            <value>_Point;_Poly;_Line</value>
        </SearchLayerExtensions>

        <!-- The column name in the search area layer used to store the search reference. -->
        <SearchColumn>
            <value>SearchRef</value>
        </SearchColumn>

        <!-- The column name in the search area layer used to store the site name. -->
        <SiteColumn>
            <value>SiteName</value>
        </SiteColumn>

        <!-- The column name in the search area layer used to store the organisation. -->
        <OrgColumn>
            <value>Organisation</value>
        </OrgColumn>

        <!-- The column name in the search area layer used to store the radius. -->
        <RadiusColumn>
            <value>Radius</value>
        </RadiusColumn>

        <!-- Are we keeping the search feature as a layer? Yes/No -->
        <KeepSearchFeature>
            <value>Yes</value>
        </KeepSearchFeature>

        <!-- The name of the search feature output layer -->
        <SearchOutputName>
            <value>SearchArea</value>
        </SearchOutputName>

        <!-- The base name of the search layer symbology file (without the .lyrx). 
        Note the relevant extension (from SearchLayerExtensions) will be added -->
        <SearchSymbologyBase>
            <value>FeatureSymbology</value>
        </SearchSymbologyBase>

        <!-- The buffer aggregate column values. Delimited with semicolons -->
        <AggregateColumns>
            <value>SearchRef;Organisation;SiteName;Radius</value>
        </AggregateColumns>

        <!-- The default option for whether to keep the selected map layers. -->
        <DefaultKeepSelectedLayers>
        	<value>Yes</value>
        </DefaultKeepSelectedLayers>

        <!-- The options for showing the selected tables -->
        <AddSelectedLayersOptions>
            <value>No;Yes - Without labels;Yes - With labels</value><!-- do not change -->
        </AddSelectedLayersOptions>

        <!-- The default option (position in the list) for whether selected map layers should be added to the map window -->
        <DefaultAddSelectedLayers>
            <value>3</value>
        </DefaultAddSelectedLayers>

        <!-- The name of the group layer that will be created in the ArcGIS table of contents -->
        <GroupLayerName>
            <value>%subref%</value>
        </GroupLayerName>

        <!-- The options for overwritting the map labels -->
        <OverwriteLabelOptions>
            <value>No;Yes - Reset Each Layer;Yes - Reset Each Group;Yes - Do Not Reset</value><!-- do not change -->
        </OverwriteLabelOptions>

        <!-- Whether any map label columns should be overwritten (default setting) -->
        <DefaultOverwriteLabels>
            <value>3</value>
        </DefaultOverwriteLabels>

        <!-- The units any area measurements will be done in. Choose from Ha, Km2, m2. Default is Ha. -->
        <AreaMeasurementUnit>
            <value>ha</value>
        </AreaMeasurementUnit>

        <!-- Options for filling out the Combined Sites table dropdown (do not change) -->
        <CombinedSitesTableOptions>
            <value>None;Append to existing table;Overwrite existing table</value>
        </CombinedSitesTableOptions>

        <!-- Whether a combined sites table should be created by default -->
        <DefaultCombinedSitesTable>
            <value>2</value> <!-- 1, 2, 3 -->
        </DefaultCombinedSitesTable>

        <!-- The details of the combined sites table -->
        <CombinedSitesTable>
            <Name>
                <value>%subref%_sites</value> <!-- do not include .txt or .csv -->
            </Name>
            <Columns>
                <value>Site_Type, Site_Ref, Site_Name, Site_Label, Search_Area</value>
            </Columns>
            <Format>
                <value>csv</value>
            </Format>
        </CombinedSitesTable>

        <!-- map layer attributes -->
        <!-- The names, local names, suffixes, SQL clauses and formats of the map tables -->
        <MapLayers>
            <Species_-_Protected>
                <LayerName> <!-- The name of the layer in the display -->
                    <value>Protected_except_Bats_Birds_Poly</value>
                </LayerName>
                <GISOutputName> <!-- The name used for any GIS data extracts -->
                    <value>SppProt_%subref%</value>
                </GISOutputName>
                <TableOutputName> <!-- The name used for any tabular extracts -->
                    <value>%subref%_sppprot</value>
                </TableOutputName>
                <Columns> <!-- The columns to be used in the tabular extracts -->
                    <value>TaxonName, CommonName, TaxonGroup, RecDate, RecYear, GridRef, Grid1k, GRPrec, Easting, Northing, Location, Abundance, AbundCount, SampleType, RoostType, RoostLoc, BasisOfSel, Recorder, Determiner, Comments, Sensitive, Historic, StatusEuro, StatusUK, StatusOth, RecOccKey, SortOrder, GroupOrder, DateStart, DateEnd, DateType, LastUpdate, VersionDt, Radius</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </Columns>
                <GroupColumns> <!-- The columns that should be used for grouping results -->
                    <value>TaxonName, CommonName, TaxonGroup, RecDate, RecYear, GridRef, Grid1k, GRPrec, Easting, Northing, Location, Abundance, AbundCount, SampleType, RoostType, RoostLoc, BasisOfSel, Recorder, Determiner, Comments, Sensitive, Historic, StatusEuro, StatusUK, StatusOth, RecOccKey, SortOrder, GroupOrder, DateStart, DateEnd, DateType, LastUpdate, VersionDt</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </GroupColumns> <!-- The columns that should be used for grouping results -->
                <StatisticsColumns> <!-- If grouping is used, any statistics that should be generated. -->
                    <value></value><!-- example: area_ha;SUM$Status;FIRST -->
                </StatisticsColumns>
                <OrderColumns> <!-- Overrides GroupColumns. Any columns by which the results should be ordered -->
                    <value></value> <!-- Use commas to separate. NOTE case sensitive! -->
                </OrderColumns>
                <Criteria> <!-- Any criteria that should be applied to this layer before extracts are saved -->
                    <value>Historic = 'N'</value><!-- example: Name = 'myName' OR area_ha > 5 -->
                </Criteria>
                <IncludeArea> <!-- Yes / No attribute to define whether an Area field should be included. Ignored for points. -->
                    <value>No</value>
                </IncludeArea>
                <IncludeDistance> <!-- Yes / No attribute to define whether a Distance field should be included -->
                    <value>No</value>
                </IncludeDistance>
                <IncludeRadius> <!-- Yes / No attribute to define whether a Radius field should be included -->
                    <value>Yes</value>
                </IncludeRadius>
                <KeyColumn> <!-- The column in this layer that contains the unique identifier -->
                    <value>TaxonName</value>
                </KeyColumn>
                <Format> <!-- The format that any tabular data will be saved as -->
                    <value>csv</value>
                </Format>
                <KeepLayer> <!-- A Yes/No attribute to define whether a GIS extract should be saved -->
                    <value>No</value>
                </KeepLayer>
                <OutputType> <!-- Whether the layer that is kept should be selected by, clipped to or intersected with the search area -->
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
                </OutputType>
                <LoadWarning>
                    <value>Yes</value>
                </LoadWarning>
                <PreselectLayer>
                    <value>Yes</value>
                </PreselectLayer>
                <DisplayLabels> <!-- switch to decide whether the defined labels should be switched on when displayed. -->
                    <value>No</value>
                </DisplayLabels>
                <LayerFileName> <!-- The name of a layer file (*.lyr) that should be used to symbolise the extract -->
                    <value></value> <!-- Overrides any label settings defined below -->
                </LayerFileName>
                <OverwriteLabels> <!-- A Yes/No attribute to define whether labels may be overwritten -->
                    <value>No</value>
                </OverwriteLabels>
                <LabelColumn> <!-- The name of the label column in this layer (if any) -->
                    <value></value>
                </LabelColumn>
                <LabelClause> <!-- The definition of the labels for this layer (if any) -->
                    <!-- format: Font:Arial$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns> <!-- The columns to be used in the combined sites table. -->
                    <!-- Leave blank if the layer should not be included in the combined sites table -->
                    <!-- Distance may be included as a keyword if IncludeDistance is set to Yes-->
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
            </Species_-_Protected>
            <Statutory_Sites_-_SACs>
                <LayerName>
                    <value>Special Area of Conservation</value>
                </LayerName>
                <GISOutputName>
                    <value>SACs_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sacs</value>
                </TableOutputName>
                <Columns>
                    <value>SAC_NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </Columns>
                <GroupColumns>
                    <value>SAC_NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </GroupColumns>
                <StatisticsColumns>
                    <value></value><!-- example: area_ha;SUM$Status;FIRST -->
                </StatisticsColumns>
                <OrderColumns> <!-- Overrides GroupColumns -->
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value><!-- example: Name = 'myName' OR area_ha > 5 -->
                </Criteria>
                <IncludeArea>
                    <value>No</value><!-- Yes / No -->
                </IncludeArea>
                <IncludeDistance>
                    <value>No</value><!-- Yes / No -->
                </IncludeDistance>
                <IncludeRadius> <!-- Yes / No attribute to define whether a Radius field should be included -->
                    <value>Yes</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>SAC_NAME</value>
                </KeyColumn>
                <Format>
                    <value>txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
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
                    <value>SAC.lyr</value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>Yes</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>Map_Label</value>
                </LabelColumn>
                <LabelClause>
                    <!-- format: Font:Calibri$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
                    <value>Font:Calibri$Size:10$Red:0$Green:0$Blue:0$Type:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <!-- Distance may be included as a keyword if IncludeDistance is set to Yes-->
                    <value>"SAC", " ", SAC_NAME, Map_Label, Radius</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>SAC_NAME, Map_Label</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value> <!-- Overrides CombinedSitesGroupColumns -->
                </CombinedSitesOrderByColumns>
            </Statutory_Sites_-_SACs>
            <Statutory_Sites_-_SPAs>
                <LayerName>
                    <value>Special Protection Area</value>
                </LayerName>
                <GISOutputName>
                    <value>SPAs_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_spas</value>
                </TableOutputName>
                <Columns>
                    <value>SPA_NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </Columns>
                <GroupColumns>
                    <value>SPA_NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </GroupColumns>
                <StatisticsColumns>
                    <value></value><!-- example: area_ha;SUM$Status;FIRST -->
                </StatisticsColumns>
                <OrderColumns> <!-- Overrides GroupColumns -->
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value><!-- example: Name = 'myName' OR area_ha > 5 -->
                </Criteria>
                <IncludeArea>
                    <value>No</value><!-- Yes / No -->
                </IncludeArea>
                <IncludeDistance>
                    <value>No</value><!-- Yes / No -->
                </IncludeDistance>
                <IncludeRadius> <!-- Yes / No attribute to define whether a Radius field should be included -->
                    <value>Yes</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>SPA_NAME</value>
                </KeyColumn>
                <Format>
                    <value>txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
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
                    <value>SPA.lyr</value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>Yes</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>Map_Label</value>
                </LabelColumn>
                <LabelClause>
                    <!-- format: Font:Calibri$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <!-- Distance may be included as a keyword if IncludeDistance is set to Yes-->
                    <value>"SPA", " ", SPA_NAME, Map_Label, Radius</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>SPA_NAME, Map_Label</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value> <!-- Overrides CombinedSitesGroupColumns -->
                </CombinedSitesOrderByColumns>
            </Statutory_Sites_-_SPAs>
            <Statutory_Sites_-_Ramsars>
                <LayerName>
                    <value>Ramsar</value>
                </LayerName>
                <GISOutputName>
                    <value>Ramsars_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_ramsars</value>
                </TableOutputName>
                <Columns>
                    <value>NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </Columns>
                <GroupColumns>
                    <value>NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </GroupColumns>
                <StatisticsColumns>
                    <value></value><!-- example: area_ha;SUM$Status;FIRST -->
                </StatisticsColumns>
                <OrderColumns> <!-- Overrides GroupColumns -->
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value><!-- example: Name = 'myName' OR area_ha > 5 -->
                </Criteria>
                <IncludeArea>
                    <value>No</value><!-- Yes / No -->
                </IncludeArea>
                <IncludeDistance>
                    <value>No</value><!-- Yes / No -->
                </IncludeDistance>
                <IncludeRadius> <!-- Yes / No attribute to define whether a Radius field should be included -->
                    <value>Yes</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>NAME</value>
                </KeyColumn>
                <Format>
                    <value>txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
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
                    <value>Ramsar.lyr</value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>Yes</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>Map_Label</value>
                </LabelColumn>
                <LabelClause>
                    <!-- format: Font:Calibri$Size:10$Red:0$Green:0$Blue:0$TOverlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <!-- Distance may be included as a keyword if IncludeDistance is set to Yes-->
                    <value>"Ramsar", " ", NAME, Map_Label, Radius</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>NAME, Map_Label</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value> <!-- Overrides CombinedSitesGroupColumns -->
                </CombinedSitesOrderByColumns>
            </Statutory_Sites_-_Ramsars>
            <Statutory_Sites_-_SSSIs>
                <LayerName>
                    <value>Site of Special Scientific Interest</value>
                </LayerName>
                <GISOutputName>
                    <value>SSSIs_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_sssis</value>
                </TableOutputName>
                <Columns>
                    <value>SSSI_NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </Columns>
                <GroupColumns>
                    <value>SSSI_NAME</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </GroupColumns>
                <StatisticsColumns>
                    <value></value><!-- example: area_ha;SUM$Status;FIRST -->
                </StatisticsColumns>
                <OrderColumns> <!-- Overrides GroupColumns -->
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value><!-- example: Name = 'myName' OR area_ha > 5 -->
                </Criteria>
                <IncludeArea>
                    <value>No</value><!-- Yes / No -->
                </IncludeArea>
                <IncludeDistance>
                    <value>No</value><!-- Yes / No -->
                </IncludeDistance>
                <IncludeRadius> <!-- Yes / No attribute to define whether a Radius field should be included -->
                    <value>Yes</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>SSSI_NAME</value>
                </KeyColumn>
                <Format>
                    <value>txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
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
                    <value>SSSI.lyr</value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>Yes</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>Map_Label</value>
                </LabelColumn>
                <LabelClause>
                    <!-- format: Font:Calibri$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
                    <value></value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <!-- Distance may be included as a keyword if IncludeDistance is set to Yes-->
                    <!-- "SSSI", SSSI_NAME, SSSI_AREA, Map_Label -->
                    <value>"SSSI", " ", SSSI_NAME, Map_Label, Radius</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>SSSI_NAME, Map_Label</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value> <!-- Must include the remaining columns -->
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value> <!-- Overrides CombinedSitesGroupColumns -->
                </CombinedSitesOrderByColumns>
            </Statutory_Sites_-_SSSIs>
            <Non_Stat_Sites_-_Local_Wildlife_Site>
                <LayerName>
                    <value>Local Wildlife Site</value>
                </LayerName>
                <GISOutputName>
                    <value>LWS_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_lws</value>
                </TableOutputName>
                <Columns>
                    <value>siteid, sitename</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </Columns>
                <GroupColumns>
                    <value>siteid, sitename</value> <!-- Use commas to separate. NOTE case sensitive! -->
                </GroupColumns>
                <StatisticsColumns>
                    <value></value><!-- example: area_ha;SUM$Status;FIRST -->
                </StatisticsColumns>
                <OrderColumns> <!-- Overrides GroupColumns -->
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value><!-- example: Name = 'myName' OR area_ha > 5 -->
                </Criteria>
                <IncludeArea>
                    <value>No</value><!-- Yes / No -->
                </IncludeArea>
                <IncludeDistance>
                    <value>No</value><!-- Yes / No -->
                </IncludeDistance>
                <IncludeRadius> <!-- Yes / No attribute to define whether a Radius field should be included -->
                    <value>Yes</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>siteid</value>
                </KeyColumn>
                <Format>
                    <value>txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
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
                    <value>Yes</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>Map_Label</value>
                </LabelColumn>
                <LabelClause>
                    <!-- format: Font:Calibri$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
                    <value>Font:Calibri$Size:10$Red:255$Green:0$Blue:0$Type:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <!-- Distance may be included as a keyword if IncludeDistance is set to Yes-->
                    <value>"LWS", siteid, sitename, Map_Label, Radius</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>siteid, sitename, Map_Label</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value></value> <!-- Overrides CombinedSitesGroupColumns -->
                </CombinedSitesOrderByColumns>
            </Non_Stat_Sites_-_Local_Wildlife_Site>
            <Management_-_FC>
                <LayerName>
                    <value>Forestry Commission</value>
                </LayerName>
                <GISOutputName>
                    <value>MgmtFC_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_mgmtfc</value>
                </TableOutputName>
                <Columns>
                    <value>COUNT_OBJECTID</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value>OBJECTID;COUNT</value>
                </StatisticsColumns>
                <OrderColumns>
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value><!-- Yes / No -->
                </IncludeArea>
                <IncludeDistance>
                    <value>No</value>
                </IncludeDistance>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>OBJECTID</value>
                </KeyColumn>
                <Format>
                    <value>txt</value>
                </Format>
                <KeepLayer>
                    <value>No</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
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
                    <!-- format: Font:Calibri$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
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
            </Management_-_FC>
            <Management_-_NT_property>
                <LayerName>
                    <value>National Trust property</value>
                </LayerName>
                <GISOutputName>
                    <value>MgmtNT_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_mgmtnt</value>
                </TableOutputName>
                <Columns>
                    <value>COUNT_OBJECTID</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value>OBJECTID;COUNT</value>
                </StatisticsColumns>
                <OrderColumns>
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value><!-- Yes / No -->
                </IncludeArea>
                <IncludeDistance>
                    <value>No</value>
                </IncludeDistance>
                <IncludeRadius>
                    <value>No</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>OBJECTID</value>
                </KeyColumn>
                <Format>
                    <value>txt</value>
                </Format>
                <KeepLayer>
                    <value>No</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
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
                    <!-- format: Font:Calibri$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
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
            </Management_-_NT_property>
            <Management_-_RSPB_reserve>
                <LayerName>
                    <value>RSPB reserve</value>
                </LayerName>
                <GISOutputName>
                    <value>MgmtRSPB_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_mgmtrspb</value>
                </TableOutputName>
                <Columns>
                    <value>COUNT_OBJECTID</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value>OBJECTID;COUNT</value>
                </StatisticsColumns>
                <OrderColumns>
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value><!-- Yes / No -->
                </IncludeArea>
                <IncludeDistance>
                    <value>No</value>
                </IncludeDistance>
                <IncludeRadius>
                    <value>Yes</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>OBJECTID</value>
                </KeyColumn>
                <Format>
                    <value>txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
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
                    <value>RSPBReserve.lyr</value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>Yes</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>Map_Label</value>
                </LabelColumn>
                <LabelClause>
                    <!-- format: Font:Calibri$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
                    <value>Font:Calibri$Size:10$Red:255$Green:0$Blue:0$Type:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value>"RSPB Reserve", " ", Name, Map_Label, Radius</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>Name, Map_Label</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value>Map_Label</value>
                </CombinedSitesOrderByColumns>
            </Management_-_RSPB_reserve>
            <Management_-_WT_site>
                <LayerName>
                    <value>Woodland Trust site</value>
                </LayerName>
                <GISOutputName>
                    <value>MgmtWT_%subref%</value>
                </GISOutputName>
                <TableOutputName>
                    <value>%subref%_mgmtwt</value>
                </TableOutputName>
                <Columns>
                    <value>COUNT_OBJECTID</value>
                </Columns>
                <GroupColumns>
                    <value></value>
                </GroupColumns>
                <StatisticsColumns>
                    <value>OBJECTID;COUNT</value>
                </StatisticsColumns>
                <OrderColumns>
                    <value></value>
                </OrderColumns>
                <Criteria>
                    <value></value>
                </Criteria>
                <IncludeArea>
                    <value>No</value><!-- Yes / No -->
                </IncludeArea>
                <IncludeDistance>
                    <value>No</value>
                </IncludeDistance>
                <IncludeRadius>
                    <value>Yes</value>
                </IncludeRadius>
                <KeyColumn>
                    <value>OBJECTID</value>
                </KeyColumn>
                <Format>
                    <value>txt</value>
                </Format>
                <KeepLayer>
                    <value>Yes</value>
                </KeepLayer>
                <OutputType>
                    <value>Copy</value> <!-- Must be "Copy" (default), "Clip", "Overlay" or "Intersect" -->
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
                    <value>WoodlandTrustSite.lyr</value>
                </LayerFileName>
                <OverwriteLabels>
                    <value>Yes</value>
                </OverwriteLabels>
                <LabelColumn>
                    <value>Map_Label</value>
                </LabelColumn>
                <LabelClause>
                    <!-- format: Font:Calibri$Size:10$Red:0$Green:0$Blue:0$Overlap:Allow -->
                    <!-- Types: Allow / None -->
                    <!-- If no clause is filled in the above settings are applied -->
                    <value>Font:Calibri$Size:10$Red:255$Green:0$Blue:0$Type:Allow</value>
                </LabelClause>
                <MacroName>
                    <value></value>
                </MacroName>
                <CombinedSitesColumns>
                    <value>"Woodland Trust site", " ", SiteName, Map_Label, Radius</value>
                </CombinedSitesColumns>
                <CombinedSitesGroupColumns>
                    <value>SiteName, Map_Label</value>
                </CombinedSitesGroupColumns>
                <CombinedSitesStatisticsColumns>
                    <value></value>
                </CombinedSitesStatisticsColumns>
                <CombinedSitesOrderByColumns>
                    <value>Map_Label</value>
                </CombinedSitesOrderByColumns>
            </Management_-_WT_site>
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

