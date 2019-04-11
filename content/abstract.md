## Abstract
<!-- Context      -->
Wheelchair users looking for accessible public transport routes,
tourists discovering attractive routes to go around a new city,
or bicycle users trying to avoid highly polluted routes
are some examples where highly individualized route planning is needed.
<!-- Need         -->
Current route planning applications lack flexibility.
The types of queries supported by a route planner
are only determined at design time
and heavily depend on centralized pre-selected data sources.
Integrating a new data source such as another transport mode,
a different road network or wheelchair accessibility is not straightforward
as it generally requires human intervention
to extend the subjacent data model
and route planning algorithm implementation.
<!-- Task         -->
I investigate how relevant data sources available on the Web
can be dynamically reused for answering custom queries,
and thus allow creating more flexible
and personalized route planning applications.
Semantic Web and Linked Data technologies
provide a common framework for data integration.
Yet it remains unclear how relevant data
can be automatically discovered
and reused while remaining independent
from specific route planning algorithm implementations.
<!-- Preliminaries     -->
Preliminary work
(i) tests the feasibility of solving route planning queries
over live and static public transport data sources on the Web,
(ii) explores the trade-offs of different Web APIs
for publishing and consuming live data streams on the Web and
(iii) introduces a Linked Data based approach
for publishing road networks data.