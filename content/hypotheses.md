## Hypotheses
{:#hypotheses}

The first research question is related to the need
of having a declarative and use-case independent mechanism
to express route planning queries that allows for the inclusion of arbitrary constraints,
while being self-describing about the type of data that will be needed to answer the query.
Existing solutions are usually tightly coupled
to the subjacent data model and algorithm implementation,
limiting the type of queries that can be expressed.
Also, implementation independent approaches
such as regular expression-based syntaxes do not allow
for automated identification of data requirements.
Therefore, I define the following Hypothesis related to Research Question 1:

Hypothesis 1 -
: _A semantic model for expressing route planning queries is at least as expressive as state of the art approaches and allows for complete and automatic identification of query solving data requirements._

The second research question relates to the problem of automated relevant data discovery.
Current Linked Data based approaches for publishing data on the Web
allow for interoperable data integration.
Moreover, semantically annotated metadata descriptions
enable relevant data source identification.
However once discovered, dynamically integrating full datasets during query execution
render route planning applications unusable for practical use-cases.
For instance, calculating a route from London to Paris will require discovering
and integrating data from possible transport modes
to travel in the UK and France,
which includes e.g. complete national train networks.
This causes an impractical overhead,
since only a subset of such networks is needed in practice.
Considering this, I define the following Hypothesis related to Research Question 2:

Hypothesis 2 -
: _A data publishing strategy based on data summaries and declarative metadata containing hypermedia controls allows precise automated relevant data discovery able to reach full completeness in a closed-world environment for route planning query solving._

The third research question relates to the performance problem
of route planning algorithms that support arbitrary multi-criteria queries.
The performance of current solutions significantly degrades
with each additional parameter considered for route calculation.
Therefore, I defined the following Hypothesis related to Research Question 3:

Hypothesis 3 -
: _A flexible route planning algorithm that adapts to combine multi-criteria graph and non graph-based approaches performs better in terms of query response time than state of the art arbitrary multi-criteria approaches._