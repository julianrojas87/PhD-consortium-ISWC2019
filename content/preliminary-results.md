## Preliminary Results[^disclaimer]
{:#preliminary-results}

Preliminary work related to Hypotheses 2 and 3,
has tested the feasibility of performing decentralized route planning
over public transport networks including live data.
Based on the non Dijkstra-based algorithm [CSA](cite:cites dibbelt2018)
and a data publishing strategy extended from the proposal given in [](cite:cites colpaert2017),
clients are able to execute the route planning algorithm on the client-side
and use hypermedia controls to discover and integrate the data during
query execution.

Other preliminary work, related to Hypothesis 2,
evaluates computational cost and query performance
for push and pull-based Web interfaces for publishing data streams.
Also introduce a modular architecture for publishing data summaries
based on the concepts introduced in [](cite:cites taelman2016).
Initial results show that push based approaches perform better for
high frequency data streams.

Also related to Hypothesis 2,
a Linked Data based a approach for publishing road networks is introduced.
OSM road network data is published in tiles
allowing clients to dynamically fetch the correct tiles to calculate a route.

[^disclaimer]: To comply with the double-blind review process, references to publications on related preliminary work are not provided.