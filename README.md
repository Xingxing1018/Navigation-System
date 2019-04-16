# Assignment 6 report Group: thursday-d-a6
Group members: 
- Nikolaus Parulian, 
- Yogeshwar Kansara, 
- Siti Zhang, 
- Xingxing Zhang, 
- Nihali Jain

Requirements:
- networkx
- pandas
- pygeodesy
- mplleaflet
- matplotlib (if you want to show the network graph)

Assignment analysis and programming ideas:

At first, we choose 9 streets and 22 buildings. As the picture shows, from the north to the south, we choose the block from East Green Street to East Armory Ave. And from the west to the east, we choose the block from S 4th Street to S Wright Street. Next, we create 3 files: buildings.csv, streets.csv and edges.csv. The buildings.csv involves buildings’ name, coordinate and mail code. The streets.csv has the streets’ name. And the edges. csv has the related intersection information. Also, considering the one-way and inactive roads, we create the two additional files: one_direction.csv and inactive_road.csv. Therefore, we finally use 5 files in total. Besides, If we want to add more buildings and streets, we can directly put data into the related csv file.

![alt text](./images/Selected%20Block.PNG "selected block")

In our program, first, we use pandas to read our 5 files. Second, we consider buildings and intersections as graph node. Different nodes will have different attributes. Then, we add edges between building and each street connected to the building. Also we add edges between the street intersections and any intersections. Next, we calculated distance between them as weight of edges. In particular, we use the real coordinate to calculate the distance between the nodes. Then, after the whole graph was built, we are able to use it to compute the shortest path. Meanwhile, the program can finally show the shortest path in a true map. 

Files:
1. buildings.csv: determine the buildings nodes with the geo-location
2. streets.csv: determine the streets covered in our graph
3. edges.csv: define intersections between building and street or street and other street with its geo-location, this file also contains the connection between intersections in N,S,W,E fields
4. one_direction.csv: define the street that has one direction way. Orders matter, in which direction will go through node_a to node_b. The edge from node_b to node_a will be deleted if the street defined in this file
5. inactive_road.csv: optional file to determine if some road segments are closed due to some circumstances. The information of the closed roads will be mentioned in the runtime

Example of running session:

![alt text](./images/travel_string.png "travel path")

The image above show how user can choose travel path from Sherman Hall to Students Arcade Building. As we can see the apps show information that the road between S 5th Street-East Chalmers Street to East Daniel Street-S 5th Street is closed, so the app take reroute to East Chalmers Street instead. This application also can show the image route using mpleaflet library will be shown like below:

![alt text](./images/sherman_to_arcade.png "travel map")

Tasks defined for the assignment are as follows:
1.	Requirement Gathering: All team members
2.	Assigning the task: Nikolaus and Yogeshwar
3.	Data collection: Nikolaus, Yogeshwar and Xingxing
4.	Programming:
  - logic: Nikolaus and Nihali
  - coding: Nikolaus and Nihali
  - OOP: Nikolaus and Yogeshwar
5.	Doctest writing: Siti and Xingxing
6.	Blackbox testing: Siti and Xingxing
7.	Refactoring: Nikolaus
8.	Report writing: Siti and Xingxing
