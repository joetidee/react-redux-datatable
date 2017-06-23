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

```defaultColumnSorting``` **_{Object}_**
Provides information about how the table should be sorted when it is initially rendered.
* index {Interger}: A zero-based index of the column number.
* field {String}: The field (in the database) that represents the data in the column.
* dir {String}: The direction of the sort (either 'asc' or 'desc').


```fetchFunction``` **_{Function}_**
A function that will fetch data to pass to the Data Table. Must return a Promise.


```tableClass``` **_{String}_**
A CSS class name that will be added to the rendered table.

## Helper Functions
### guid()
Generates a unique id. Can be used to generate a value for the `refetch` prop.
