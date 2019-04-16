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
work with heterogeneous data form different sources.
Through the [RDF specification](cite:cites cyganiak2014),
Linked Data is described using a graph-based model, where
each node in the graph represents a concept, object or
literal value in the world and each edge represents
the logical relation between two of them.

In this section I present an overview
of different aspects related to the problem
of dynamically integrating new data sources to enable
more diverse and specific queries in route planning
applications.

### Data Publishing on the Web

When publishing data on the Web,
one of the main goals is to enable its adoption
and foster the creation of new and innovative services.
Tim Berners-Lee introduced a set of principles[^ldprinciples] for
publishing data as Linked Data on the Web.
Extending this principles, the W3C published a document of [best practices
for publishing Linked Data](cite:cites w3c2014).

Traditionally, data is published on the Web following one of two approaches:
(i) as a data dump or (ii) through an API.
In the public transport domain,
[GTFS](cite:cites gtfs), regarded as the de-facto standard
for describing and exchanging transit schedules,
is a common example of data dump publishing.
The European Committee for Standardization released the [NeTEx standard](cite:cites netex)
as a general purpose format for exchanging public transport schedules and related data.
Transport related data is also offered on the Web as route planning APIs.
Navitia.io[^navitia], Plannerstack[^plannerstack], CityMapper
or the open source Open Trip Planner are some examples.
Geo-spatial data is also fundamental for route planning applications.
Different initiatives exist for publishing geo-spatial data on the Web.
For instance, [OpenStreetMap](cite:cites osm)(OSM) stands as a community-driven
rich source of freely available spatial data.
[LinkedGeoData](cite:cites auer2009) publishes a spatial knowledge base
derived from OSM that uses RDF as its data model.
Also [GeoNames](cite:cites geonames) publishes over 25 million geographical names
using stable URIs and a semantic vocabulary[^gnontology].

On the one hand, data dumps offer full flexibility over the data
but are expensive for clients who need to deal
with integration of complete datasets.
On the other hand, APIs offer simpler access to data,
but are expensive for data publishers
and limit query flexibility for clients.
The [Linked Data Fragments (LDF) framework](cite:cites verborgh2014)
explores the different trade-offs in terms of query flexibility
and computational costs of _in between_ Web interfaces
determined by _fragmenting_ datasets and publishing
them on the Web. Based on the concept introduced by LDF,
Colpaert introduces [Linked Connections](cite:cites colpaert2017),
a light-weight data interface for publishing public transit schedules
that allows to perform route planning on the client-side.
Furthermore, in his [PhD dissertation](cite:cites colpaertthesis) Colpaert
presents the Linked Connections Ontology[^lcontology]
and the Linked GTFS vocabulary[^linkedgtfs] used to describe
vehicle departures in public transport networks.

### Data Discovery on the Web


Miel's paper, Hypermedia, Multidimensional Interfaces.

### Route Planning

Route Planning has been extensively studied...

#### Route Planning Queries
Shortest Path, EAT, Profile, Multi-criteria -> SPARQL-Path, LDQL, CypherQL, GraphQL.

#### Route Planning Algorithms
Graph-based (time-expanded, time-dependant), RAPTOR, CSA, Trip-based.

[^ldprinciples]: <a href="https://www.w3.org/DesignIssues/LinkedData.html">https://www.w3.org/DesignIssues/LinkedData.html</a>
[^navitia]: <a href="http://navitia.io/">http://navitia.io/</a>
[^plannerstack]: <a href="http://www.plannerstack.org/">http://www.plannerstack.org/</a>
[^lcontology]: <a href="http://semweb.mmlab.be/ns/linkedconnections#">http://semweb.mmlab.be/ns/linkedconnections#</a>
[^linkedgtfs]: <a href="http://vocab.gtfs.org/gtfs.ttl#">http://vocab.gtfs.org/gtfs.ttl#</a>
[^gnontology]: <a href="http://www.geonames.org/ontology/ontology_v3.1.rdf">http://www.geonames.org/ontology/ontology_v3.1.rdf</a>