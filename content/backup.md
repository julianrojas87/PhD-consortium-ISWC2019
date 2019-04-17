I propose
(i) to declaratively model and describe route planning queries
for data requirements identification,
(ii) a Linked Data based publishing strategy
to enable hypermedia-driven automated data discovery, and
(iii) a generic route planning algorithm model
able to automatically adapt.


In the public transport domain,
GTFS is an example of data dump publishing containing data
that describes vehicle schedules for route planning purposes.
This approach allows clients full flexibility over the data
but requires them to deal first with the dataset integration
into their own systems. 
On the other hand, a route planning API


<section id="footnotes">
  <h2>Footnotes</h2>
  <ol>
        <li id="fn:portland">
        <p><a href="https://trimet.org/#/planner">https:/​/​trimet.org/#/planner</a> <a href="#fnref:portland" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:london">
        <p><a href="https://tfl.gov.uk/plan-a-journey/">https:/​/​tfl.gov.uk/plan-a-journey/</a> <a href="#fnref:london" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:antwerp">
        <p><a href="https://www.slimnaarantwerpen.be/en/home">https:/​/​www.slimnaarantwerpen.be/en/home</a> <a href="#fnref:antwerp" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:googlemaps">
        <p><a href="http://maps.google.com/landing/transit/index.html">http:/​/​maps.google.com/landing/transit/index.html</a> <a href="#fnref:googlemaps" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:citymapper">
        <p><a href="https://citymapper.com/">https:/​/​citymapper.com/</a> <a href="#fnref:citymapper" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:moovit">
        <p><a href="https://moovitapp.com/">https:/​/​moovitapp.com/</a> <a href="#fnref:moovit" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:process">
        <p>For a more detailed overview see for example the process to setup Open Trip Planner, a widely used open source route planning application: <a href="https://github.com/opentripplanner/OpenTripPlanner/blob/dev-1.x/docs/Configuration.md">https:/​/​github.com/opentripplanner/OpenTripPlanner/blob/dev-1.x/docs/Configuration.md</a> <a href="#fnref:process" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:airquality">
        <p>Latest measurments from Europe’s air quality monitoring network: <a href="https://www.eea.europa.eu/data-and-maps/explore-interactive-maps/up-to-date-air-quality-data">https:/​/​www.eea.europa.eu/data-and-maps/explore-interactive-maps/up-to-date-air-quality-data</a> <a href="#fnref:airquality" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:ldprinciples">
        <p><a href="https://www.w3.org/DesignIssues/LinkedData.html">https:/​/​www.w3.org/DesignIssues/LinkedData.html</a> <a href="#fnref:ldprinciples" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:navitia">
        <p><a href="http://navitia.io/">http:/​/​navitia.io/</a> <a href="#fnref:navitia" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:plannerstack">
        <p><a href="http://www.plannerstack.org/">http:/​/​www.plannerstack.org/</a> <a href="#fnref:plannerstack" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:gnontology">
        <p><a href="http://www.geonames.org/ontology/ontology_v3.1.rdf">http:/​/​www.geonames.org/ontology/ontology_v3.1.rdf</a> <a href="#fnref:gnontology" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:lcontology">
        <p><a href="http://semweb.mmlab.be/ns/linkedconnections#">http:/​/​semweb.mmlab.be/ns/linkedconnections#</a> <a href="#fnref:lcontology" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:linkedgtfs">
        <p><a href="http://vocab.gtfs.org/gtfs.ttl#">http:/​/​vocab.gtfs.org/gtfs.ttl#</a> <a href="#fnref:linkedgtfs" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:netexquery">
        <p><a href="http://www.netex-cen.eu/model/conceptual/passenger_info/index.htm">http:/​/​www.netex-cen.eu/model/conceptual/passenger_info/index.htm</a> <a href="#fnref:netexquery" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:cypher">
        <p><a href="https://neo4j.com/developer/cypher-query-language/">https:/​/​neo4j.com/developer/cypher-query-language/</a> <a href="#fnref:cypher" class="reversefootnote">&#8617;</a></p>
        </li>
        <li id="fn:graphql">
        <p><a href="https://digitransit.fi/en/developers/apis/1-routing-api/itinerary-planning/">https:/​/​digitransit.fi/en/developers/apis/1-routing-api/itinerary-planning/</a> <a href="#fnref:graphql" class="reversefootnote">&#8617;</a></p>
        </li>
    </ol>
</section>