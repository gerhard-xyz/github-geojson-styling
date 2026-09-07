# Does github.com render simplestyle in GeoJSON?

[`simplestyle-test.geojson`](simplestyle-test.geojson) holds six features in three pairs. Each pair is one styled feature and one identical control with no styling properties.

| Pair     | Styled feature                                | Control |
| -------- | --------------------------------------------- | ------- |
| Lines    | `stroke: #ff0000`, `stroke-width: 12`         | none    |
| Polygons | `fill: #00ff00`, `stroke: #0000ff`            | none    |
| Points   | `marker-color: #ff00ff`, `marker-size: large` | none    |

The keys are [simplestyle-spec 1.1.0](https://github.com/mapbox/simplestyle-spec/tree/master/1.1.0), on each feature's `properties` object, where the spec and GitHub's documentation both put them.

Open the file and look at the map. If simplestyle is honoured, each pair looks different. If not, all six render the same.

Short version of why: github.com renders GeoJSON with Azure Maps, which doesn't implement simplestyle. Enterprise Server kept the older MapBox renderer, so its [documentation](https://docs.github.com/en/enterprise-server@3.16/repositories/working-with-files/using-files/working-with-non-code-files) still describes the styling properties while the [github.com page](https://docs.github.com/en/repositories/working-with-files/using-files/working-with-non-code-files) doesn't.

Full write-up: [Why GitHub ignores your GeoJSON styling](https://gerhard.xyz/github-geojson-styling).
