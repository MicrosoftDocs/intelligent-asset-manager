---
title: Push Connectors - Table
---
# Universal Inventory Push Connectors

A Push Connector is a piece of code that executes a set of SQL queries to fill tables in the [**Input schema [in]**](Input-Schema.md) schema of the UI data store.

The Inventory Provider that creates the connector decides what form it takes. It can be a script, function, or other add-on module to their solution, or a stand-alone tool. It is up to the Inventory Provider to decide what is the most appropriate format for their customers. The Push Connector is executed independently from the UI application, and pushes data directly into the UI Database.​

The idea is that the actual queries/scripts that extract and upload data are readable/editable.  This way a User can easily customize Connectors in support of his particular setup. For example, the user might update the script that fills tblDatabaseServers to extract an Environment value from the name or distinguished Name of the server. That would be a customer-specific rule.

If at all possible, do not compile your queries into a tool but include them in a readable format.

A Push Connector needs to perform these steps, in order:

1. **Connect to the Data Source and/or target database**  
   ​If the Connector is a query executed on the Data Source, it needs to retrieve the connection of the target UI Database. If the Connector is a stand-alone application or script, it needs to connect to both the Data Source and the target UI Database. The connection string can be asked interactively from the user, or specified as parameter. However, connection strings should be stored and retrieved from permanent configuration after the first run, so execution can be scheduled.

2. **(Optional) Check the UI Database version in table in.__Version**  
   Your queries might not work if the customer is running an older version of the UI database. If the version number found in this table is lower than the version your queries are designed for, you may want to halt execution.
   As from the moment of first release, the UI database will be backward compatible. There is no need to take action if the version found here is higher than what you designed for. (That's not yet the case during this development phase.)

3. **Execute stored procedure in.CleanDataSource, specifying your DataSourceId as a parameter**  
   UI may have many Data Sources. All data from all sources is combined in the Input schema [in] of the database. Before importing new data, all existing data from the same Data Source must be removed from tables in the Input schema, so it is important to distinguish from which Data Source the data originates. Procedure [in].CleanDataSource deletes records with the specified DataSourceId.

   [**Learn more about the UI Data Flow here.​**](Data-Model.md)

   [**Read more about the DataSourceId here.**](Input-Schema.md)

4. **Insert data into the Input schema**
   Execute queries to fill tables in the [in] schema of the UI Database. In their simplest form, these queries look something like:
  
   ​INSERT INTO [in].[tblX]  
   SELECT &lt;columns> FROM &lt;your data source>

5. **Execute stored procedure [in].sp_Import**  
   After all data is uploaded to the Input schema, launch this procedure to import data into the permanent data store [dbo].

6. **(Optional) Check [in].tsysValidationResults and [out].tsysValidation**  

   After sp_import has executed (step #5 above), these tables hold values that allow you to validate results:
   - [in].tsysValidationResults shows issues that may hamper import or produce corrupt data. The corresponding description of the Validation Rules and queries are in [in].tsysValidationRules.
   - [out].tsysValidation shows issues with the result of the import. Column 'Results' shows the number of records that did not meet validation criteria. If validation rules with IDs 1003, 1004, 2003, or 7003 are not met (meaning Results >0), the resulting CIDC file will not contain the minimum quality data standard suggested by Microsoft, therefore users may need to import data from an additional datasource to produce a CIDC that meets the Microsoft standard.

Please keep the following in mind when uploading data:

- ​It is not necessary to fill all tables. Only insert data that is available in your Data Source.

- When unable to determine the correct value, leave the corresponding field empty (NULL). Do not provide default values, such as "0" for integer, or SqlDateTime.MinValue for date/time values. NULL values are not processed, default values are. If you don't have values for mandatory fields, leave the entire table empty.

- Date/time values must be UTC.