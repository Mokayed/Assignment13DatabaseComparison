# Assignment13DatabaseComparison

<p>Load data from the csv file to Neo4j datababase</p>


USING PERIODIC COMMIT
LOAD CSV FROM 'file:///social_network_nodes.csv' AS line
CREATE (:Artist { id: line[0], name: line[1], job: line[2], birthday:line[3]})
