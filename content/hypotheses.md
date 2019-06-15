## Hypotheses
{:#hypotheses}

The first research question is related to the need
of having a declarative and use-case independent mechanism
to express route planning queries, that allows including arbitrary constraints,
while being self-describing about the type of data needed to answer a query.
Existing solutions are usually tightly coupled
to the subjacent data model and algorithm implementation,
limiting the type of queries that can be expressed.
Also, implementation independent approaches
such as regular expression-based syntaxes do not allow
for automated identification of data requirements.
Therefore, I define the following Hypothesis related to Research Question 1:

Hypothesis 1 -
: _A semantic model for expressing route planning queries is at least as expressive as state of the art approaches and allows for complete and automatic identification of query solving data requirements._

The second research question relates to the problem of how data
should be published on the Web to allow for efficient decentralized route planning solutions.
Current Linked Data based approaches for publishing data on the Web
allow for interoperable data integration.
Also, data summarization techniques provide data publishing alternatives
for clients to access just the necessary data to solve a certain query,
accelerating query evaluation times.
Considering this, I define the following Hypothesis related to Research Question 2:

Hypothesis 2 -
: _A data publishing strategy based on data summarization techniques allows for decentralized route planning query evaluation to be as performant as state of the art centralized approaches such as Open Trip Planner._
