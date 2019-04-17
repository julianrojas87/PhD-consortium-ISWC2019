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
Usually a graph-based model.

* Finally, a route planning algorithm tailored
to run over the predefined data model,
is used to calculate available routes[^process].

The route planner service offered by Google Maps for example, follows this approach.
By encouraging public transport operators around the world
to publish their data using the [GTFS](cite:cites gtfs) common format,
Google collects these datasets and integrates them
into their route planning application.
As long as data are homogeneous in terms of structure and format,
i.e. dealing only with public transport data
defined using a common format as GTFS,
integrating new data sources into a route planning application
can be easily automated and the same route planning algorithm implementation
will remain useful without requiring any adaptation.
However, when dealing with other types of data
the data model and the route planning algorithm that operates on top of it,
need to be adapted to support and consider the new data
when calculating possible routes.
Manually adapting implementations of route planning applications
for every new data source that enables to support more diverse queries
does not scale, considering the highly diverse data sources found on the Web.

Problem Statement -
: _Integrating new heterogeneous data sources_
_to extend route planners capabilities requires human intervention_
_to adapt the subjacent data models and route planning algorithm implementations,_
_resulting in ad-hoc and hence not reusable solutions._

A centralized data approach limits the types of queries supported by route planners,
which could serve as an explanation of why route planning applications
such as Google Maps do not allow to query for routes that consider, for example air quality,
even though this type of data can be found published on the Web as Open Data[^airquality].

[^process]: For a more detailed overview see for example the process to setup Open Trip Planner, a widely used open source route planning application: <a href="https://github.com/opentripplanner/OpenTripPlanner/blob/dev-1.x/docs/Configuration.md">https://github.com/opentripplanner/OpenTripPlanner/blob/dev-1.x/docs/Configuration.md</a>

[^airquality]: Latest measurments from Europe's air quality monitoring network: <a href="https://www.eea.europa.eu/data-and-maps/explore-interactive-maps/up-to-date-air-quality-data">https://www.eea.europa.eu/data-and-maps/explore-interactive-maps/up-to-date-air-quality-data</a>