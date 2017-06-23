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

```defaultColumnSorting```
{Object} Provides information about how the table should be sorted when it is initially rendered. Options:
* index {Interger}: A zero-based index of the column number.
* field {String}: The field (in the database) that represents the data in the column.
* dir {String}: The direction of the sort (either 'asc' or 'desc').

```fetchFunction```
{Function} A function that will fetch data to pass to the Data Table. Must return a Promise.

```refetch```
Accepts a unique key. The DataTable component will check for this prop and if the value changes it will force a re-fetch of data.

```tableClass```
{String} A CSS class name that will be added to the rendered table.

## Helper Functions
### guid()
Generates a unique id. Can be used to generate a value for the `refetch` prop.
