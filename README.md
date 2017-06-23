# react-redux-datatable

This is currently still in production.


## Creating a datatable

```
import DataTableWrapper from 'DataTableWrapper.jsx';
let MyTable = DataTableWrapper("someUniqueName");
...js
<MyTable ... />
...
```
`DataTableWrapper` is higher order component(HOC) that will return a component, in this case "MyTable". Therefore, you can then use `<MyTable />` in your component and pass whatever props you need (see below). You can create as many datatables as you need and they will behave independently of each other.


## Props

```columnConfig``` **_(Array of Objects)_**
Provides information about the data stored in each column. Each column is represented by an Object with the following properties:
* className **_(String)_**: The CSS class name to apply to each table cell of this column.
* content **_(String)_**: The content of the column header cell.
* dbField **_(String)_**: The name of the field (in the database) that the column matches to.
* dbSearchField **_(String)_**: If a search field is used with the table to filter the data, this refers to the name of the field (in the database) that the search facility will use.
* sorting **_(Boolean)_**: Enable/disable sorting on the table column.
* style **_(Object)_**: Inline CSS styles to be applied to each cell of this column.

```defaultColumnSorting``` **_(Object)_**
Provides information about how the table should be sorted when it is initially rendered.
* index **_(Interger)_**: A zero-based index of the column number.
* field **_(String)_**: The field (in the database) that represents the data in the column.
* dir **_(String)_**: The direction of the sort (either 'asc' or 'desc').

```dataFetchFunction``` **_(Function)_**
A function that will fetch data to pass to the Data Table. Must return a Promise.

```renderRow``` **_(Function)_**
A function that will process each row of data returned by the `dataFetchFunction`. The `renderRow` function will be supplied with an Object that will represent the row data and should return an Object:
* attr **_(Object)_**: Each property within this object will be applied to the row as an attribute of the `<tr>` element.
* data **_(Array)_**: An array, where each element represents the content of the column within the row.

```tableClass``` **_(String)_**
A CSS class name that will be added to the rendered table.


## Helper Functions
### guid()
Generates a unique id. Can be used to generate a value for the `refetch` prop.
