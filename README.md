Column Chart
============


# Introduction

This small library utilizes D3.js to help visualize numbers as bar-charts. Specifically, for tables with numbers, it can help visualize a certain column of numbers as mini horizontal bar-charts by replacing each number with a horizontal D3 chart.

There are 2 types of charting options in this library:


## 1. Horizontal Bar charts

This is the default option, where it displays numbers in a table column as mini bar charts. Each ```<td>``` element needs to have a set of data-* attrbutes as shown below:

```
data-for-column = "ColumnA"         # name of the column that its part of
data-bar-value = "9"                # size of bar
data-bar-color = "#ff0000"          # red
```

So an example ```<td>``` element would be something as below:
```
<table>
    <tr>
        <td class="barchart"
            data-for-column="ColumnA"
            data-bar-value = "9"
            data-bar-color = "#ff0000">
        </td>

        ...
        ...

    </tr>
</table>
```


## 2. Stacked Horizontal Bar charts.

This is a slightly advanced feature, where each bar-chart is a group of stacks and each stack is a component with its own color. So for example, if you were trying to visualize the ratio of car sales in a dealership by make for a certain month, you could use a stacked-bar chart to represent each month and each stack could be the total sales for a certain make. The data for such a stacked bar-chart needs to be represented as a JSON structure as below:

```
{
    "cols": ["BMW", "Mercedez", .... ],
    "data": [
        { "count": 28, "col": "BMW", "svg_class_id": "bmw" },
        { "count": 44, "col": "Mercedez", "svg_class_id": "mecedez" },
        ...
        ...
    ]
}
```

A legend-control is also added to the top of the table that is decorated with the stacked-bar charts. Two behaviors are supported with the legend control:
* Single-click - Single-clicking a legend hides the corresponding stack for all rows, clicking again reveals the stack again.
* Double-click - Double-clicking a legend hides all other stacks, except the one that was double-clicked.


# Install

Just put the appropriate .js library for debugging (column-chart.js) or production. from the dist/ directory of this project into your project's lib/ directory.

# Build

# Run tests
