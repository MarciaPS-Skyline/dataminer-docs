---
uid: Web_apps_Main_Release_10.3.0_CU6
---

# DataMiner web apps Main Release 10.3.0 CU6 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!TIP]
> For release notes for this release that are not related to the web applications, see [General Main Release 10.3.0 CU6](xref:General_Main_Release_10.3.0_CU6).

### Enhancements

#### GQI: Enhanced behavior of aggregations applied on empty Elasticsearch tables [ID_36490]

<!-- MR 10.3.0 [CU6] - FR 10.3.8 -->

Up to now, when an aggregation (min, max, average) was applied on an empty Elasticsearch table, the following exception would be thrown:

`Error trapped: Elastic returned unexpected value ''.`

From now on, when an aggregation (min, max, average) is applied on an empty Elasticsearch table, an empty cell will be returned instead.

Because of this change, the behavior of aggregations applied on all types of empty tables becomes more consistent:

| Type | RawValue | DisplayValue |
|------|----------|--------------|
| Avg/Min/Max/Median | null | "Not applicable" |
| (Distinct) Count   | 0    | 0                |
| Std dev/Percentile | null | "Not applicable" |
| Sum                | 0    | 0                |

### Fixes

#### Dashboards app: Black boxes on top of first or last field of selection boxes on small screens [ID_36738]

<!-- MR 10.2.0 [CU18]/10.3.0 [CU6] - FR 10.3.9 -->

When you reduced the screen size to the point at which the navigation pane got hidden, a black box would incorrectly appear on top of the first or last field of a selection box.
