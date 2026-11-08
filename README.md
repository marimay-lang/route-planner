# route-planner

![A route-planning example — a Marimay learning project](.github/banner.svg)

> **Personal learning project.** This open-source MIT project is part of
> [Marimay](https://github.com/marimay-lang/marimay), my hobby programming-language project.
> I maintain it in my spare time to learn by building. APIs and tooling may
> change, and progress may be intermittent.

A small delivery-route example written in Marimay. It validates a graph,
finds a shortest route with Dijkstra's algorithm, and prints the stops and
total travel time.

**Status:** Personal learning example for the Marimay 0.1 preview. Its scenario is configured
directly in `scenario.my`; platform-wide compatibility has not been established.

## Run and verify

```sh
mmay check .
mmay run .
mmay test . --engine both
```

Put a compatible `mmay` on your `PATH`. The supplied route visits Depot, Central
Hub, West Hub, East Hub and Customer with a total time of `19.0` minutes.
Edit `locationNames()` and `deliveryNetwork()` in `scenario.my` to try another
graph; every location needs an adjacency-list row.

`planner/api.my` contains graph validation, search and path reconstruction.
Tests cover the expected route, identical endpoints, unreachable destinations
and invalid graph inputs.

## License

[MIT](LICENSE). Existing copyright attribution is retained.
