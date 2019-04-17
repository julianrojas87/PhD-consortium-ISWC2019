## Related Work
{:#related-work}

Including new data sources to allow more diverse
and specific queries in route planning applications
can be generalized as a data integration problem.
The [Semantic Web](cite:cites bernerslee2001)
and [Linked Data](cite:cites heath2011) technologies
provide a common environment where data
is given a well-defined meaning,
better allowing machines to comprehend and
work with heterogeneous data from different sources.
Through the [RDF specification](cite:cites cyganiak2014),
Linked Data is described using a graph-based model, where
each node in the graph represents a concept, object or
literal value in the world, and each edge represents
the logical relation between two of them.
This graph can be queried upon using the [SPARQL](cite:cites sparql) query language,
which is the W3C recommendation to query RDF.  

In this section I present an overview
of different aspects related to the problem
of dynamically integrating new data sources to enable
more diverse and specific queries in route planning
applications.

### Data Publishing on the Web

Millions of datasets are published on the Web [](cite:cites noy2019).
Following the right strategy when publishing data
is key to increase the interoperability and reusability of data,
and foster the creation of new and innovative services.
In this direction, Tim Berners-Lee introduced a set of principles[^ldprinciples] for
publishing data as Linked Data on the Web.
Extending this principles, the W3C published a document of [best practices
for publishing Linked Data](cite:cites w3c2014), which provides a set of guidelines
and design principles aimed at data publishers.

Traditionally, data is published on the Web following one of two approaches:
(i) as a data dump or (ii) through an API.
In the public transport domain,
[GTFS](cite:cites gtfs), which is regarded as the de-facto standard
for describing and exchanging transit schedules,
is a common example of data dump publishing.
The European Committee for Standardization released the [NeTEx standard](cite:cites netex)
as a general purpose format for exchanging public transport schedules and related data.
Transport related data is also offered on the Web as route planning APIs.
Navitia.io[^navitia], Plannerstack[^plannerstack], CityMapper
or the open source Open Trip Planner are some examples.
Geospatial data is also fundamental for route planning applications.
Different initiatives exist for publishing geospatial data on the Web.
For instance, [OpenStreetMap](cite:cites osm)(OSM) stands as a community-driven
rich source of freely available spatial data.
[LinkedGeoData](cite:cites auer2009) publishes a spatial knowledge base
derived from OSM that uses RDF as its data model.
Also [GeoNames](cite:cites geonames) publishes over 25 million geographical names
using stable URIs and a semantically annotated vocabulary[^gnontology].

On the one hand, data dumps offer full flexibility over the data
but are expensive for clients who need to deal
with integration of complete datasets.
On the other hand, APIs offer simpler access to data,
but are expensive for data publishers
and limit query flexibility for clients.
The [Linked Data Fragments (LDF) framework](cite:cites verborgh2014)
explores the different trade-offs in terms of query flexibility
and computational costs of _in between_ Web interfaces
determined by _fragmenting_ datasets and publishing them on the Web.
Based on the LDF concept,
the [Linked Connections specification](cite:cites colpaert2017) was introduced.
Defined as a light-weight data interface for publishing public transit schedules
that allows to perform route planning on the client-side,
it uses the Linked Connections Ontology[^lcontology]
and the Linked GTFS vocabulary[^linkedgtfs] to describe
vehicle departures in public transport networks [](cite:cites colpaertthesis).

### Data Discovery on the Web

To dynamically integrate data sources available on the Web
into route planning applications,
discovering which data sources are relevant for resolving a certain query
is a necessary previous step.
One approach to enable automated discovery of datasets
is using data catalogs descriptions.
For instance, the [DCAT vocabulary](cite:cites dcat)
is used to describe high-level metadata (keywords,
location, data format, etc.) of datasets,
enabling clients to discover what kind of data
is contained on a certain dataset and how to access it.
Given the graph-based nature of Linked Data on the Web,
active approaches such as link traversal can be used
to discover data during query execution.
In [](cite:cites hartig2016) several link traversal approaches
are studied showing significant improvements in query response time
compared to a naive approach.

Hypermedia-based approaches are also considered in the literature
for enabling automated discovery of data.
The approach presented in [](cite:cites vandersande2016) describes
how to perform data source selection based on hypermedia links and controls.
Hypermedia is also used to semantically describe responses
of Web APIs in [](cite:cites taelman2017). A shape-based approach
using [SHACL](cite:cites shacl), is used by the authors
to declare a parameterized structure of API responses.

The use of data summaries as a strategy to enable
more precise data discovery to improve query response times
is explored in [](cite:cites saleem2014).
In the same direction, [Multidimensional Interfaces](cite:cites taelman2016) are
defined to semantically describe ordinal ranges within datasets,
e.g. time-based or geospatial-based ranges,
which are inherent to the nature
of commonly used route planning related datasets,
such as public transport network topologies (geospatial range)
and their schedules (time range).

### Route Planning

Route Planning has been extensively studied throughout the years.
Multiple algorithms have been proposed to calculate routes
over different types of networks (e.g. road, public transport, multimodal, etc),
and using different criteria (e.g. shortest path, travel time, number of transfers, etc).
The authors in [](cite:cites bast2015) and [](cite:cites pajorthesis) present
a comparative analysis of multiple route planning algorithms
for road, public transit and multimodal networks.
Most algorithms use subjacent graph-based data models
to represent the different transportation networks over which they operate,
and are defined as extensions of [Dijkstra's algorithm](cite:cites dijkstra1959).
In recent years, different approaches
that disregard Dijkstra-like graph algorithms,
have been introduced for public transport and multimodal networks.
[RAPTOR](cite:cites raptor2019), [CSA](cite:cites dibbelt2018), [Transfer Patters](cite:cites bast2016),
[Trip-based routing](cite:cites witt2016) are among the approaches
that exploit the basic elements of public transport networks
to calculate routes directly on the timetables.

There is no consensus about the criteria
that route planning algorithms should support.
The parameters supported by route planning algorithms
change from one approach to another depending on the data model,
the algorithm implementation and the use-case.
In [](cite:cites kelly2011) a list of data requirements
for _ideal multimodal route planners_ is introduced.
It identifies 22 different parameters from traditional data sources such as GTFS feeds and OSM.
The NeTEx standard defines also a _Trip Plan Query Model_[^netexquery]
that considers among others, accessibility, via and trip fares parameters.
A extensive analysis of formal languages using regular expressions
to define constrained shortest path queries is presented in [](cite:cites barret2000).
Furthermore, the Web of Data opens the door for new possibilities
and use-cases that need to be supported by route planning algorithms.
For instance, the Multi-Criteria RAPTOR algorithm supports
route calculation with an arbitrary number of input parameters.
However, additional criteria has a significant impact on the algorithm performance,
causing it to become too slow for practical use [](cite:cites raptor2019).

Given that Linked Data is also described using a graph-based model,
the problem of finding routes between nodes have been previously studied.
SPARQL 1.1 introduced the Property Paths (PP) syntax
that allow query engines to test for path existence between nodes.
In [](cite:cites savenkov2017) an extension for PP syntax is proposed
to compute the top-k shortest paths of a given path expression between two nodes.
An extension of the query semantics of PP is presented in [](cite:cites hartig2015)
to support navigation of PP over the Web of Data instead of over single RDF graphs.
A more expressive alternative is later introduced as the [Linked Data Query Language (LDQL)](cite:cites ldql)
that allows expressing query graph patterns and navigation paths independently.
Another approach is introduced in [](cite:cites rutgers2016) as an extension of the property graph query language
CypherQL[^cypher], which allows for top-k shortest paths queries,
calculated path weights and filtering on path edges and nodes.
Lastly, multimodal route plans are calculated using a GraphQL interface
published by the Finish Transit Agency[^graphql].

[^ldprinciples]: <a href="https://www.w3.org/DesignIssues/LinkedData.html">https://www.w3.org/DesignIssues/LinkedData.html</a>
[^navitia]: <a href="http://navitia.io/">http://navitia.io/</a>
[^plannerstack]: <a href="http://www.plannerstack.org/">http://www.plannerstack.org/</a>
[^lcontology]: <a href="http://semweb.mmlab.be/ns/linkedconnections#">http://semweb.mmlab.be/ns/linkedconnections#</a>
[^linkedgtfs]: <a href="http://vocab.gtfs.org/gtfs.ttl#">http://vocab.gtfs.org/gtfs.ttl#</a>
[^gnontology]: <a href="http://www.geonames.org/ontology/ontology_v3.1.rdf">http://www.geonames.org/ontology/ontology_v3.1.rdf</a>
[^netexquery]: <a href="http://www.netex-cen.eu/model/conceptual/passenger_info/index.htm">http://www.netex-cen.eu/model/conceptual/passenger_info/index.htm</a>
[^cypher]: <a href="https://neo4j.com/developer/cypher-query-language/">https://neo4j.com/developer/cypher-query-language/</a>
[^graphql]: <a href="https://digitransit.fi/en/developers/apis/1-routing-api/itinerary-planning/">https://digitransit.fi/en/developers/apis/1-routing-api/itinerary-planning/</a>