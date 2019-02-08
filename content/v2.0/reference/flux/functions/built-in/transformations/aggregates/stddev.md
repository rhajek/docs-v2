---
title: stddev() function
description: The stddev() function computes the standard deviation of non-null records in specified columns.
aliases:
  - /v2.0/reference/flux/functions/transformations/aggregates/stddev
menu:
  v2_0_ref:
    name: stddev
    parent: built-in-aggregates
weight: 501
---

The `stddev()` function computes the standard deviation of non-null records in specified columns.

_**Function type:** Aggregate_  
_**Output data type:** Float_

```js
stddev(columns: ["_value"])
```

## Parameters

### columns
Specifies a list of columns on which to operate.
Defaults to `["_value"]`.

_**Data type:** Array of strings_

## Examples
```js
from(bucket: "telegraf/autogen")
  |> range(start: -5m)
  |> filter(fn: (r) =>
    r._measurement == "cpu" and
    r._field == "usage_system"
  )
  |> stddev()
```

<hr style="margin-top:4rem"/>

##### Related InfluxQL functions and statements:
[STDDEV()](https://docs.influxdata.com/influxdb/latest/query_language/functions/#stddev)  