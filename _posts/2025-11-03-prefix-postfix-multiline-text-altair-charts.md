---
title: Prefixing, postfixing and multiline text in Vega Altair charts
layout: default
parent: Bytes
permalink: /bytes/prefix-postfix-multiline-text-altair-charts
date: 2025-11-03 00:00:00
tags:
    - Python 
    - Vega-Altair
has_toc: false
---

# Prefixing, postfixing and multiline text in Vega Altair charts

Published on {{ page.date | date_to_long_string: "ordinal" }} under {% for tag in page.tags %}<a href="/tags/{{ tag | downcase }}">{{ tag }}</a>{% unless forloop.last %}, {% endunless %}{% endfor %}
{: .fs-2 .text-grey-dk-000 }

Vega Altair allows to create custom text labels, which can enrich charts with static text-based information. Below is a python example that creates [boxplot][link_to_boxplot] chart with distribution of engine displacement per each cyclinder count groups and adds [text][link_to_text] marks summarizing median and mean values of individual distributions.

```python
import altair as alt
from vega_datasets import data

# take cars dataset
cars = data.cars()

# create chart showing distribution of engine displacement based on cylinders count
chart = (
    alt.Chart(cars)
        .mark_boxplot(extent="min-max", orient="horizontal")
        .encode(
            alt.X("Displacement"),
            alt.Y("Cylinders")
        )
)

# create text labels for each cylinder count group
text = (
    alt.Chart(cars)
        .mark_text(
            # set text alignment for better readibility
            align="left", 
            baseline="middle",
            dx=10,
            dy=-5
        )
        .encode(
            # set starting text position for each distribution
            # text will start at the end of Displacement distribtuion on X-axis
            alt.X("max(Displacement)"),
            # and for each cylinder count on Y-axis
            alt.Y("Cylinders"),
            # define text label
            alt.Text("label:N")
        )
        .transform_joinaggregate(
            # calculate median values
            median = "median(Displacement):Q",
            # calculate mean values
            mean = "mean(Displacement):Q",
            # we want to show the distribution of displacement for each cylinder count group
            groupby = ["Cylinders"]
        )
        .transform_calculate(
            # calculate label values to consist of median and mean data
            # mean value is rounded to 2 decimal places
            label = "['Median: ' + datum.median, 'Mean: ' + round(datum.mean * 100) / 100]"
        )
)

# plot chart and text
chart + text
```

![title][prefix-postfix-multiline-text-01]

[link_to_boxplot]: https://altair-viz.github.io/user_guide/marks/boxplot.html
[link_to_text]: https://altair-viz.github.io/user_guide/marks/text.html
[prefix-postfix-multiline-text-01]: /assets/images/pages/2025-11-03-prefix-postfix-multiline-text-01.png