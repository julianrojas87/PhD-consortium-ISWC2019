## Problem Statement
{:#problem-statement}

Currently available route planning applications
are built following a centralized data strategy.
For example, a route planner calculating routes
using both the bus and metro public transport services in a certain city:

* First collects the dataset of each transport mode,
containing the minimum necessary information for route planning,
i.e. station locations and vehicle schedules.

* Then integrates the data
following a predefined data model in a centralized data store.

* Finally, a route planning algorithm tailored
to run over the predefined data model,
is used to calculate available routes[^process].

The route planner service offered by Google Maps follows this approach.
By encouraging public transport operators around the world
to publish their data using the [GTFS](cite:cites gtfs) common format,
Google collects these datasets and
integrates them into their route planning application.

Is not a problem if data is homogeneous. i.e. only public transport following using the same standard.
but what happens if other type of data is integrated?

How google cannot calculate a route avoiding zones with high pollution even though the data is openly available.

Problem Statement -
: Integrating new heterogeneous data sources
to extend route planners capabilities requires human intervention
to adapt the subjacent data models and route planning algorithm implementations,
resulting in ad-hoc and hence not reusable solutions.

A centralized data approach limits the types of queries that can be asked to a route planner,
therefore limiting how customizable it can get.
Furthermore,

[^process]: For a more detailed overview see for example the process to setup Open Trip Planner, a widely used open source route planning application: <a href="https://github.com/opentripplanner/OpenTripPlanner/blob/dev-1.x/docs/Configuration.md">https://github.com/opentripplanner/OpenTripPlanner/blob/dev-1.x/docs/Configuration.md</a>