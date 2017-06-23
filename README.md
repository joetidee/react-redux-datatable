# react-redux-datatable

This is currently still in production.

## Creating a datatable

```
import DataTableWrapper from 'DataTableWrapper.jsx';
let MyTable = DataTableWrapper("someUniqueName");
...
<MyTable ... />
...
```
`DataTableWrapper` is higher order component(HOC) that will return a component, in this case "MyTable". Therefore, you can then use `<MyTable />` in your component and pass whatever props you need (see below);

## Props
```refetch```
Accepts a unique key. The DataTable component will check for this prop and if the value changes it will force a re-fetch of data.

```fetchFunction```
A function that will fetch data to pass to the Data Table. Must return a Promise.

## Helper Functions
### guid()
Generates a unique id. Can be used to generate a value for the `refetch` prop.
