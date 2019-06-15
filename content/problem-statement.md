## Problem Statement
{:#problem-statement}

Currently available route planning applications
are built following a _centralized data strategy_.
A route planner[^process] calculating routes
using both the bus and metro public transport services in a certain city:

1. Collects datasets of each transport mode,
containing the minimum necessary information for route planning,
i.e. station locations and vehicle schedules.

2. Integrates the data following a predefined (usually graph-based) data model
in a centralized data store.

3. Calculates available routes using a route planning algorithm tailored
to run over the predefined data model.

The route planner service offered by Google Maps for example, follows this approach.
By encouraging public transport operators around the world
to publish their data using the [GTFS](cite:cites gtfs) format,
Google collects these datasets and integrates them
into their route planning application.

However, centralized approaches incur in high costs
in terms of computational infrastructure.
Hosting, integrating and keeping up to date the data
of every transport alternative that wants to be supported,
and effectively processing route planning queries from a scaling number of users,
requires big data storages and powerful processors,
specially if aiming on providing a global route planning solution.
Furthermore, they also limit the types of queries supported
due to the difficulties that are faced
when dealing with heterogeneous data.
As long as data are homogeneous in terms of structure and format,
i.e. dealing only with public transport data using a common format as GTFS,
integrating new data sources into a route planning application
can be easily automated and the same route planning algorithm implementation
will remain useful without requiring many adaptations.
Other types of data make necessary to manually adapt
the data model and the route planning algorithm that runs on top of it.
This could explain why route planning applications
such as Google Maps or Open Trip Planner
do not allow querying for routes that consider, for example air quality,
even though this type of data can be found published on the Web as Open Data[^airquality].

Problem Statement -
: _Integrating new heterogeneous data sources to extend route planners capabilities requires adapting the subjacent data models and route planning algorithm implementations, resulting in ad-hoc and hence not reusable solutions._

[^process]: See Open Trip Planner's case, a widely used open source route planning application: <a href="https://github.com/opentripplanner/OpenTripPlanner/blob/dev-1.x/docs/Configuration.md">https://github.com/opentripplanner/OpenTripPlanner/blob/dev-1.x/docs/Configuration.md</a>

[^airquality]: Latest measurements from Europe's air quality monitoring network: <a href="https://www.eea.europa.eu/data-and-maps/explore-interactive-maps/up-to-date-air-quality-data">https://www.eea.europa.eu/data-and-maps/explore-interactive-maps/up-to-date-air-quality-data</a>