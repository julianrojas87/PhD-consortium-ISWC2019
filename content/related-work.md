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
Moreover, the Web offers a common platform for data sharing
where different data publishing strategies
may facilitate and influence a decentralized
approach for route planning applications.

In this section I present an overview
of different aspects related to the problem
of dynamically integrating new data sources to enable
more diverse and specific queries in route planning
applications, such as data publishing
and route planning algorithms.

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

Traditionally, data is often published on the Web
either as a data dump or through an API.
In the public transport domain,
[GTFS](cite:cites gtfs), which is regarded as the de-facto standard
for describing and exchanging transit schedules,
is a common example of data dump publishing.
The European Committee for Standardization
released the [NeTEx standard](cite:cites netex)
as a general purpose format for exchanging public transport schedules and related data.
NeTEx is the standard selected by the European Union,
under the Directive 2010/40/EU[^eudirective],
for the provision of an EU-wide multimodal travel information service,
where every member state will publish their public transport-related datasets
through a National Access Point.

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

On the one hand, data dumps offer full query flexibility over the data
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
the [Linked Connections specification](cite:cites colpaert2017) was introduced
as a light-weight data interface for publishing public transit schedules
that allows to perform route planning on the client-side.
It uses the Linked Connections Ontology[^lcontology]
and the Linked GTFS vocabulary[^linkedgtfs] to describe
vehicle departures in public transport networks [](cite:cites colpaertthesis).

Data summarization techniques are also used when publishing data on the Web
to facilitate its access and speed up querying processes.
Taelman et al. introduced [Multidimensional Interfaces](cite:cites taelman2016)
as mechanism to semantically describe ordinal ranges within datasets,
e.g. time-based or geospatial-based ranges,
which are inherent to the nature
of commonly used route planning related datasets,
such as public transport network topologies (geospatial range)
and their schedules (time range).
Graph-based summarization techniques such as [Contraction Hierarchies](cite:cites geisberger2012),
[K-means](cite:cites hartigan1979) or [connectivity-based clustering](cite:cites flinsenberg2004)
are also commonly used in the route planning domain
to reduce the amount of data that needs to be processed
when solving route planning queries.

_Hypermedia_ plays also an important role when publishing data on the Web.
Providing declarative descriptions about how data can be consumed,
helps clients to understand the means of accessing data sources
and increases their interoperability.
The Hydra vocabulary[^hydra] aims on providing a common terminology for describing
hypermedia-driven Web APIs to create generic API clients.
Hypermedia is also used to semantically describe responses
of Web APIs in Tealman et al. [](cite:cites taelman2017).
A shape-based approach using [SHACL](cite:cites shacl),
is used to define a parameterized structure of API responses.

### Route Planning

Route Planning has been extensively studied throughout the years.
Multiple algorithms were proposed to calculate routes
over different types of networks (e.g. road, public transport, multimodal, etc),
and using different criteria (e.g. shortest path, travel time, number of transfers, etc).
Bast et al. [](cite:cites bast2015) and Pajor [](cite:cites pajorthesis) present
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

Different solutions that use some of the aforementioned
route planning algorithms are available.
For instance Open Trip Planner[^otp] provides an open source implementation
of Dijkstra-based and RAPTOR algorithms
for planning routes over public transport and road networks.
OsmAnd[^osmand] is also an open source route planner for road networks
that implements a Dijkstra-based algorithm on top of OSM data.
Being open source allows these solutions to be extended
to include new different types of data sources for route planning.
However, extending them requires substantial effort to adapt the
algorithms and the data models over which they operate.

There is no consensus about the criteria
that route planning algorithms should support.
The parameters supported by route planning algorithms
change from one approach to another depending on the data model,
the algorithm implementation and use-case.
Kelly et al. [](cite:cites kelly2011) presents a list of data requirements
for _ideal multimodal route planners_.
It identifies 22 different parameters from traditional data sources such as GTFS feeds and OSM.
The NeTEx standard defines also a _Trip Plan Query Model_[^netexquery]
that considers among others, accessibility, via and trip fares parameters.
A extensive analysis of formal languages using regular expressions
to define constrained shortest path queries is presented in Barret et al. [](cite:cites barret2000).
Furthermore, the Web of Data opens the door for new possibilities
and use-cases that need to be supported by route planning algorithms.
For instance, the Multi-Criteria RAPTOR algorithm supports
route calculation with an arbitrary number of input parameters.
However, additional criteria has a significant impact on the algorithm performance,
causing it to become too slow for practical use [](cite:cites raptor2019).

Given that Linked Data is also described using a graph-based model,
the problem of finding routes between nodes have been previously studied.
SPARQL 1.1 introduced the Property Paths (PP) syntax
that allows query engines to test for path existence between nodes.
Savenkov et al. [](cite:cites savenkov2017) propose an extension for PP syntax
to compute the top-k shortest paths of a given path expression between two nodes.
An extension of the query semantics of PP is also presented in Hartig et al. [](cite:cites hartig2015)
to support navigation of PP over the Web of Data instead of over single RDF graphs.
A more expressive alternative is later introduced as the [Linked Data Query Language (LDQL)](cite:cites ldql)
that allows expressing query graph patterns and navigation paths independently.
Another approach is introduced in Rutgers et al. [](cite:cites rutgers2016)
as an extension of the property graph query language
CypherQL[^cypher], which allows for top-k shortest paths queries,
calculated path weights and filtering on path edges and nodes.
Lastly, multimodal route plans are calculated using a GraphQL interfaces
published by the Finish[^fn-graphql] and Norwegian[^nw-graphql] Transit Agencies.

[^ldprinciples]: <a href="https://www.w3.org/DesignIssues/LinkedData.html">https://www.w3.org/DesignIssues/LinkedData.html</a>
[^eudirective]: <a href="http://data.europa.eu/eli/dir/2010/40/oj">http://data.europa.eu/eli/dir/2010/40/oj</a>
[^navitia]: <a href="http://navitia.io/">http://navitia.io/</a>
[^plannerstack]: <a href="http://www.plannerstack.org/">http://www.plannerstack.org/</a>
[^lcontology]: <a href="http://semweb.mmlab.be/ns/linkedconnections#">http://semweb.mmlab.be/ns/linkedconnections#</a>
[^linkedgtfs]: <a href="http://vocab.gtfs.org/gtfs.ttl#">http://vocab.gtfs.org/gtfs.ttl#</a>
[^hydra]: <a href="https://www.hydra-cg.com/spec/latest/core/">https://www.hydra-cg.com/spec/latest/core/</a>
[^gnontology]: <a href="http://www.geonames.org/ontology/ontology_v3.1.rdf">http://www.geonames.org/ontology/ontology_v3.1.rdf</a>
[^otp]: <a href="https://github.com/opentripplanner/OpenTripPlanner">https://github.com/opentripplanner/OpenTripPlanner</a>
[^osmand]: <a href="https://github.com/osmandapp/Osmand">https://github.com/osmandapp/Osmand</a>
[^netexquery]: <a href="http://www.netex-cen.eu/model/conceptual/passenger_info/index.htm">http://www.netex-cen.eu/model/conceptual/passenger_info/index.htm</a>
[^cypher]: <a href="https://neo4j.com/developer/cypher-query-language/">https://neo4j.com/developer/cypher-query-language/</a>
[^fn-graphql]: <a href="https://digitransit.fi/en/developers/apis/1-routing-api/itinerary-planning/">https://digitransit.fi/en/developers/apis/1-routing-api/itinerary-planning/</a>
[^nw-graphql]: <a href="https://api.entur.io/journey-planner/v2/ide/">https://api.entur.io/journey-planner/v2/ide/</a>