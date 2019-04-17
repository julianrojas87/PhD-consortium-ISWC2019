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
Therefore, I define the following Hypothesis related to _Research Question 1_:

Hypothesis 1 -
: _A shape-based semantic model for expressing route planning queries is at least as expressive as state of the art approaches and allow for complete and automatic identification for query solving data requirements._


the publication approach
needed to allow automated discovery