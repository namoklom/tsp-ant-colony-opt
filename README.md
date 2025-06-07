# Travelling Salesman Problem (TSP) with Ant Colony Optimization (ACO) Algorithm

## 👤 Author

| Name            | Role              | LinkedIn                                      |
|-----------------|-------------------|-----------------------------------------------|
| Jason Emmanuel  | Data Scientist | [linkedin.com/in/jasoneml](https://www.linkedin.com/in/jasoneml/) |

<img src="https://github.com/user-attachments/assets/332c0635-d00c-47f2-9607-1e43eccc5f61" width="600" />

The project addresses the Travelling Salesman Problem (TSP), which involves determining the most efficient route for visiting a set of cities exactly once before returning to the starting point. The challenge lies in minimizing the total travel distance while covering all destinations. This problem is well-known for its computational complexity, especially as the number of cities increases.

In this particular case, the focus is on twenty major cities in Indonesia, each represented by precise geographic coordinates (latitude and longitude). These coordinates facilitate the calculation of the physical distances between every pair of cities. However, minimizing just the physical distance is often insufficient in practical scenarios, since other factors such as travel costs, tolls, and time also impact the overall efficiency of a route.

To incorporate these considerations, the project applies a multi-objective optimization approach. This means that both geographical distance and route cost are optimized simultaneously, reflecting a balance between the shortest path and the most economical travel. The conflict between these objectives introduces complexity, as a route that is shortest in terms of distance might not be the least costly, and vice versa.

The chosen method to solve this problem is the Ant Colony Optimization (ACO) algorithm, a heuristic inspired by the foraging behavior of real ants. In nature, ants deposit pheromones along paths to food sources, influencing the path choices of other ants and gradually converging on the shortest routes. Similarly, in the algorithm, artificial ants probabilistically build solutions guided by virtual pheromone trails and heuristic information based on distance and cost. Over successive iterations, pheromone levels are updated to favor better routes, allowing the algorithm to adapt and explore promising solutions.

Given the computational demands of simulating many ants over numerous iterations, parallel processing is utilized to enhance efficiency. By distributing tasks across multiple processor cores, the algorithm’s runtime can be significantly reduced, making it feasible to handle complex, multi-objective optimization over a sizable set of cities.

---

## ✨ Features

- 📍 Calculates geographical distance using the **Haversine formula**
- 🐜 Uses Ant Colony Optimization to simulate pheromone-based search
- 🎯 Multi-objective scoring: **distance + cost**
- 🔁 Pheromone evaporation and deposition rules
- 🔍 Local optimization with **2-opt algorithm**
- 📈 Adjustable weights for distance and cost

---

## 🧠 Mathematical Model

### **Haversine Formula (Geographical Distance)**
  
<img width="500" alt="image" src="https://github.com/user-attachments/assets/52eef1af-5401-4275-83f4-9bc88985c460" />

### **Ant Transition Probability**
  
<img width="500" alt="image" src="https://github.com/user-attachments/assets/cee62e56-a4de-422d-bd2a-c179c4d76a7a" />

### **Pheromone Update Rules**
  
<img width="400" alt="image" src="https://github.com/user-attachments/assets/275de9bc-3b5d-445e-b79f-df2a28fefcbd" />

### **2-opt Local Search**
  
<img width="400" alt="image" src="https://github.com/user-attachments/assets/9bd7c868-b965-4db4-9fb3-5314f91865cd" />

### **Multi-objective Score Function**
  
<img width="500" alt="image" src="https://github.com/user-attachments/assets/c5093d7e-6a2a-41aa-80f7-f2db873858e9" />

Detailed formulas are available in the accompanying LaTeX document `mathematical_report.pdf`.

---

## 📊 Result Overview

<img src="https://github.com/user-attachments/assets/25d94f8e-a471-47c8-b15a-b3440158f297" width="600"/>

The graph illustrates the convergence behavior of the Dynamic Multi-Objective Ant Colony Optimization (ACO) algorithm over 100 iterations. The y-axis represents the weighted score, which combines geographical distance and route cost, while the x-axis indicates the number of iterations. Initially, the algorithm rapidly improves the solution, significantly reducing the weighted score within the first 10 iterations. After that, the curve flattens, indicating that the algorithm has reached a plateau and converged to a near-optimal solution. The consistently low score from iteration 12 onward demonstrates stability and convergence of the ACO algorithm in optimizing the multi-objective TSP.

![image](https://github.com/user-attachments/assets/b5e4e9dd-d725-4c78-87d4-e92bef0538dd)

This grid of heatmaps visualizes the pheromone matrix evolution across iterations during the execution of the Ant Colony Optimization (ACO) algorithm. Each subplot shows pheromone intensity between city pairs (indexed along the x and y axes) at specific iterations (e.g., 0, 10, 20, ..., 100). Initially (Iter 0), the pheromone distribution is fairly uniform, indicating equal probability for selecting any city transitions. As iterations progress, the pheromone levels begin to concentrate along specific paths, represented by darker squares. By Iteration 50 and onward, certain routes become significantly more reinforced, showing that the algorithm has identified promising paths for the TSP solution. The persistence of these dark patches through later iterations (e.g., 90–100) suggests convergence and stability of the algorithm toward an optimized tour structure.

![image](https://github.com/user-attachments/assets/73778ce9-a5c0-4bdc-994d-41d90b3ae56d)

The graph shows the progression of the best route found by the Ant Colony Optimization (ACO) algorithm for the Travelling Salesman Problem (TSP) across three stages: iteration 0, 50, and 100. At iteration 0, the route is random and inefficient, indicating exploration without guidance. By iteration 50, the path becomes more geographically coherent as pheromone trails start influencing ant decisions. At iteration 100, the route is significantly optimized, showing a more logical and efficient traversal through Indonesian cities, demonstrating the convergence behavior of ACO over time.

---

## 🧰 Tools & Libraries Used

| Tool / Library              | Description                                                                                                          |
|-----------------------------|----------------------------------------------------------------------------------------------------------------------|
| numpy                     | Core library for matrix operations, random number generation, and numerical computation.                           |
| matplotlib.pyplot         | Visualization library used for plotting the performance of ACO (e.g., tour length vs. iteration).                  |
| seaborn                   | (Optional) Statistical data visualization, useful for heatmaps or route exploration distributions.                  |
| multiprocessing           | Used to parallelize ant simulations for faster performance.                                                         |
| random / numpy.random   | Adds stochastic elements in distance perturbations and probabilistic ant decisions.                                 |
| haversine (custom func)   | Calculates great-circle distance between two latitude-longitude points using the Haversine formula.                 |
| LaTeX    | Used in Markdown to render mathematical equations, such as the pheromone update rule and distance formulas.         |
| Ant Colony Optimization   | Main metaheuristic algorithm inspired by ant foraging behavior.                                                     |
| 2-opt Algorithm           | Local search technique to refine a tour by swapping edges if it leads to a shorter path.                            |
| Dynamic α (alpha) & β (beta)| Adjusts the influence of pheromone vs. heuristic distance information as iterations progress.                       |
| Dynamic Distance Matrix     | Introduces noise or fluctuations in distances to simulate real-world uncertainty.                                   |
