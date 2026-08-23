# Marimay Route Planner

A small, useful application written against the currently executable Marimay
0.1 preview. It computes the fastest delivery route with Dijkstra's algorithm,
prints every stop, and reports the total travel time.

The current Marimay preview does not yet expose program arguments or the accepted
filesystem API to source programs. For now, the application uses an editable
configuration in `scenario.my`. Replace `locationNames()` and
`deliveryNetwork()` to plan another network; every location must have one row
in the adjacency list.

## Run

The commands below assume this project and the Marimay repository are siblings in
`~/Projects/Marimay`:

```sh
../marimay/build/release/mmay check .
../marimay/build/release/mmay run .
../marimay/build/release/mmay test --engine both .
```

Expected output:

```text
Optimal delivery route:
Depot
Central Hub
West Hub
East Hub
Customer
Total travel time in minutes:
19.0
```

## Project layout

- `planner/api.my` contains reusable graph validation, Dijkstra search, and
  path reconstruction.
- `scenario.my` is the editable delivery network.
- `main.my` renders the selected route.
- `planner_test.my` covers the optimal route, start-at-destination,
  unreachable destinations, invalid requests, invalid endpoints, and negative
  travel times.
