# Assignment13DatabaseComparison

<h1>Load data from the csv file to Neo4j datababase</h1>

USING PERIODIC COMMIT
LOAD CSV FROM 'file:///social_network_nodes.csv' AS line
CREATE (:Artist { id: line[0], name: line[1], job: line[2], birthday:line[3]})


<h1>Load data from the csv file to SQL datababase</h1>

first create schema with name SocialNetwork, then create table named social_network_nodes.

create schema socialNetwork;

CREATE TABLE table_name (
node_id int,
name varchar(45),
job varchar(100),
birthday varchar(100)
);

 
Also put the csv file into the root directory of the docker container.

mysql -u root -p --local-infile socialNetwork

SHOW GLOBAL VARIABLES LIKE 'local_infile';
SET GLOBAL local_infile = 'ON';

load data local infile '/social_network_nodes.csv' into table social_network_nodes;
