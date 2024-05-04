# Možnosti
![[myDM/Websites/Graph modeling guidelines - Getting Started ----- 8eb0cb94-0add-44c7-85f5-2ef1ab66e854#^yv5obf]]
+nodes můžou mít štítky
## nodes
- Use nodes to represent entities—that is, the things in our domain that are of interest to us, and which can be labeled and grouped.
Nodes for Things,

Model Facts as Nodes

Represent Complex Value Types as Nodes

Time

> [!nodes.docs]-
> ![[myDM/Websites/Graph modeling guidelines - Getting Started ----- 8eb0cb94-0add-44c7-85f5-2ef1ab66e854#https neo4j com docs getting-started data-modeling guide-data-modeling model-nodes Nodes]]

> [!nodes.blogs]-
> ![[myDM/Websites/Graph Data Modeling Categorical Variables  by David Allen  Neo4j Developer Blog  Medium-----8b1d81d4-0be7-4dc4-a476-1554f60094a5#Separate Node]]

> [!intermediate Nodes.docs]-
> ![[myDM/Websites/Modeling designs - Getting Started ----- d40abf2e-00bd-451d-b820-e097f0bcac42#https neo4j com docs getting-started data-modeling modeling-designs _example_intermediate_nodes Example intermediate nodes]]


![[myDM/Websites/Graph Data Modeling Categorical Variables  by David Allen  Neo4j Developer Blog  Medium-----8b1d81d4-0be7-4dc4-a476-1554f60094a5#^l1r28b]]

Super nodesc

## labels

> [!labels.docs]-
> ![[myDM/Websites/Graph modeling guidelines - Getting Started ----- 8eb0cb94-0add-44c7-85f5-2ef1ab66e854#https neo4j com docs getting-started data-modeling guide-data-modeling add-labels Labels]]

> [!labels.blogs]-
> ![[myDM/Websites/Graph Data Modeling Categorical Variables  by David Allen  Neo4j Developer Blog  Medium-----8b1d81d4-0be7-4dc4-a476-1554f60094a5#Labels]]
>
![[myDM/Websites/Graph Modeling Labels. What are labels for, and how can you…  by David Allen  Neo4j Developer Blog  Medium-----eec9c46c-c8c3-4c4e-8beb-da367f0061e6#^omk907]]

![[myDM/Websites/Graph Data Modeling Categorical Variables  by David Allen  Neo4j Developer Blog  Medium-----8b1d81d4-0be7-4dc4-a476-1554f60094a5#^4j7rzt]]


 
## relations 
Relationships for Structure
- Use relationships both to express the connections between entities and to estab‐ lish semantic context for each entity, thereby structuring the domain.
- Use relationship direction to further clarify relationship semantics. Many rela‐ tionships are asymmetrical, which is why relationships in a property graph are always directed. For bidirectional relationships, we should make our queries ignore direction, rather than using two relationships.

Fine-Grained versus Generic Relationships

> [!relationships.docs]-
> 
> ![[myDM/Websites/Graph modeling guidelines - Getting Started ----- 8eb0cb94-0add-44c7-85f5-2ef1ab66e854#https neo4j com docs getting-started data-modeling guide-data-modeling define-rels Relationships]]
 
> [!.]- nodeXrelation.docs
> ![[myDM/Websites/Modeling designs - Getting Started ----- d40abf2e-00bd-451d-b820-e097f0bcac42#https neo4j com docs getting-started data-modeling modeling-designs property-vs-relationship Property vs relationship fold]]


## properties
- Use node properties to represent entity attributes, plus any necessary entity meta‐ data, such as timestamps, version numbers, etc.
- Use relationship properties to express the strength, weight, or quality of a rela‐ tionship, plus any necessary relationship metadata, such as timestamps, version numbers, etc.

> [!properties.docs]-
> ![[myDM/Websites/Graph modeling guidelines - Getting Started ----- 8eb0cb94-0add-44c7-85f5-2ef1ab66e854#https neo4j com docs getting-started data-modeling guide-data-modeling fillin-properties Properties]]

> [!properties.blogs]-
> ![[myDM/Websites/Graph Data Modeling Categorical Variables  by David Allen  Neo4j Developer Blog  Medium-----8b1d81d4-0be7-4dc4-a476-1554f60094a5#Property Approach]]
> 

![[myDM/Websites/Graph Data Modeling Categorical Variables  by David Allen  Neo4j Developer Blog  Medium-----8b1d81d4-0be7-4dc4-a476-1554f60094a5#^ngw33b]]




# Postup modelování
Iterative and Incremental Development

modeling process can best be summed up as an attempt to create a graph struc‐ ture that expresses the questions we want to ask of our domain. That is, design for queryability:
1. Describe the client or end-user goals that motivate our model. 
2. Rewrite these goals as questions to ask of our domain. 
3. Identify the entities and the relationship that appear in these questions. 
4. Translate these entities and relationships into Cypher path expressions. 
5. Express the questions we want to ask of our domain as graph patterns using path expressions similar to the ones we used to model the domain.



# asi nepotřebuju %% fold %% 
![[myDM/Websites/Modeling relational to graph - Getting Started-----db754def-1808-4936-abd0-63894375d4a4#https neo4j com docs getting-started data-modeling relational-to-graph-modeling model-transformation Data model transformation tips]]

---
![[myDM/Websites/Graph modeling guidelines - Getting Started ----- 8eb0cb94-0add-44c7-85f5-2ef1ab66e854#https neo4j com docs getting-started data-modeling guide-data-modeling describe-domain Describing a domain]] a pak nodes, lables, relations, params

---
blogs

-

