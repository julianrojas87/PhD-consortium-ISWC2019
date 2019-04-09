## Abstract
<!-- Context      -->
Route planning has become a commonly used feature in different contexts.
Commuters checking if their train or bus is on time,
tourists discovering the optimal routes to go around a new city
or ambulances finding the fastest route to attend an emergency
are some examples where route planning is an essential need.
<!-- Need         -->
However,
current route planning applications lack flexibility.
The types of queries supported by a route planner
are only determined at design time
and heavily depend on locally centralized,
pre-selected data sources
(e.g. public transport modes, road networks, wheelchair accessibility, etc).
Integrating a new data source
to support new and more specific queries is not straight forward
as it generally requires modifying the subjacent data model
and route planning algorithm implementation.
<!-- Task         -->
I investigate how relevant data sources available on the Web
can be dynamically reused
for answering specific queries,
and thus allow creating more flexible
and personalized route planning applications.
Semantic and Linked Data technologies
provide a common framework for data integration.
Yet it remains unclear how relevant data
can be automatically discovered
and reused while remaining independent
from specific route planning algorithm implementations.
<!-- Preliminaries     -->
Preliminary work,
(i) test the feasibility of solving route planning queries
over distributed live and static public transport data sources on the Web,
(ii) explore the trade-offs of different Web APIs
for publishing and consuming live data streams on the Web and
(iii) introduce a Linked Data based approach
for publishing road network data.