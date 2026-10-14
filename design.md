Practical Exercise 3: Designing a Searching Agent

Repository: PS-Agents

Group Members:
- Member 1: Emmanuel Wandibba 189987
- Member 2: Angela Irungu 191937
- Member 3: Joypraise Kendi 189539

---

 Question 1: Designing the Self-Driving Trailer Agent

 1.1 PEAS Framework

The self-driving trailer agent is an intelligent system designed to transport goods safely and efficiently from one location to another without requiring a human driver to control every movement.

The PEAS framework describes the agent as follows:

Component; Description

1) Performance Measure: Safe transportation of goods, minimum travel distance, reduced fuel consumption, timely delivery, compliance with traffic rules, and prevention of accidents.
2) Environment: Kenyan highways, roads, towns, cities, other vehicles, pedestrians, traffic lights, road signs, weather conditions, roadworks, and delivery destinations.
3) Actuators: Steering system, accelerator, brakes, gear control, indicators, headlights, horn, and communication system.
4) Sensors: Cameras, GPS, radar, LiDAR, speed sensors, proximity sensors, engine sensors, and digital maps. |

 Explanation

- Performance Measure: Determines how well the agent performs its task. A good agent delivers goods safely, follows traffic rules, and minimizes unnecessary travel costs.
- Environment: Includes everything around the trailer that may affect its journey.
- Actuators: Enable the agent to control the trailer's movement and communicate with other road users.
- Sensors: Collect information about the trailer's location, surrounding traffic, road conditions, and obstacles.

The agent uses information from its sensors to make decisions and control its actuators to reach the destination safely and efficiently.

 1.2 The Five Definitions of Agent Environments

The operating environment of the self-driving trailer agent can be classified using the following five definitions.

1. Fully Observable vs Partially Observable

The environment is partially observable because the agent's sensors cannot detect every detail of the road environment at all times. For example, other vehicles may block its view, and road conditions may change unexpectedly.

2. Deterministic vs Stochastic

The environment is stochastic because the results of the agent's actions are not always predictable. For example, another driver may suddenly change lanes, or unexpected rain may affect braking distance.

3. Episodic vs Sequential

The environment is sequential because each decision affects future decisions and the overall journey. For example, choosing a particular highway affects the remaining route, travel time, and fuel consumption.

4. Static vs Dynamic

The environment is dynamic because it changes while the agent is operating. Traffic conditions, pedestrians, weather, and road obstacles may change while the trailer is moving.

5. Discrete vs Continuous

The environment is continuous because the trailer's position, speed, steering angle, and time change continuously. However, some decisions, such as choosing between different roads, may be discrete.

Conclusion: The self-driving trailer operates in a partially observable, stochastic, sequential, dynamic, and continuous environment. These characteristics require the agent to sense its surroundings, make decisions under uncertainty, and continually adapt its driving behavior.

 Question 2: Kenya's Highway Network

2.1 Abstraction

Abstraction is the process of simplifying a real-world problem by representing only the information relevant to solving it.

For the self-driving trailer agent, Kenya's highway network is represented using towns and cities as nodes and roads connecting them as edges. Each road can be assigned a cost based on the distance between the connected towns.

The model focuses on major towns along possible routes from Nairobi to Kisumu, including Naivasha, Nakuru, Kericho, Eldoret, Kakamega, and Kisumu.

The following assumptions are made:

1. Each town or city is represented by a single node.
2. Each highway connecting two towns is represented by an edge.
3. Road distances are used as path costs.
4. Roads are treated as bidirectional where travel is possible in both directions.
5. Traffic lights, buildings, fuel stations, and individual vehicles are excluded from the graph because they are not necessary for the initial route-search model.
6. The search begins at Nairobi and aims to reach Kisumu.

This abstraction allows the agent to compare alternative routes and identify a minimum-distance path without modelling every detail of the real road network.

2.2 Directed Graph

![Directed Graph of Kenya's Highway Network](directed-graph.png)

2.3 Search Tree

![Search Tree from Nairobi to Kisumu](search-tree.png)

Question 3: Optimal Path from Nairobi to Kisumu

3.1 Distance and Path Costs

The path cost function calculates the total road distance between the starting point and the destination. The total cost is obtained by adding the distances of all road segments along a route.

The following two routes are compared:

Route A: Via Naivasha, Nakuru and Kericho

Nairobi to Naivasha: 91 km 
Naivasha to Nakuru: 70.5 km 
Nakuru to Kericho: 107 km
Kericho to Kisumu: 89 km
Total distance:357.5 km

Calculation:

Total cost = 96 + 70.5 + 107 + 89

Total cost = 357.5 km

Route B: Via Nakuru and Eldoret

Nairobi to Nakuru: 161.5 km
Nakuru to Eldoret: 170 km
Eldoret to Kisumu: 123 km
Total distance: 454.5 km

Calculation:

Total cost = 161.5 + 170 + 123

Total cost = 454.5km

3.2 Route Comparison

The two routes are compared based on their total road distances.

Route A: Via Naivasha, Nakuru and Kericho: 357.5 km 
Route B: Via Nakuru and Eldoret: 454.5 km 

The difference between the two route estimates is:

454.5 − 357.5 = 97 km

Based on these preliminary figures, Route A is shorter than Route B.

3.3 Optimal Path

The optimal path is the route with the lowest total path cost, where the cost is measured by road distance.

Based on the preliminary calculations, the selected route is:

Nairobi → Naivasha → Nakuru → Kericho → Kisumu

Its estimated total distance is 357.5 km.

Therefore, Route A is the preferred route in this simplified model because it has a lower estimated distance than Route B. 

 4. Summary

This practical exercise demonstrated how an intelligent searching agent can be designed for a self-driving trailer operating on Kenyan highways. The PEAS framework was used to identify the agent’s performance measures, environment, actuators, and sensors. The environment was classified as partially observable, stochastic, sequential, dynamic, and continuous.

A directed graph was developed to represent selected towns and road connections in Kenya, using towns as nodes and roads as edges. The problem was simplified through abstraction by focusing on road connections and distances rather than unnecessary environmental details.

Finally, road distances were used as path costs to compare possible routes from Nairobi to Kisumu. The route with the lowest total distance was identified as the optimal route among the alternatives considered. This demonstrates how search algorithms can help an autonomous vehicle plan efficient journeys while supporting safe and effective transportation.
