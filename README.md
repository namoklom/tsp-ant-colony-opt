# Travelling Salesman Problem (TSP) with Ant Colony Optimization (ACO)

This project implements a **multi-objective Ant Colony Optimization (ACO)** algorithm to solve the **Travelling Salesman Problem (TSP)**. It integrates both **geographical distance** and **route cost** as optimization objectives, providing an adaptive and heuristic approach to finding efficient routes.

## ✨ Features

- 📍 Calculates geographical distance using the **Haversine formula**
- 🐜 Uses Ant Colony Optimization to simulate pheromone-based search
- 🎯 Multi-objective scoring: **distance + cost**
- 🔁 Pheromone evaporation and deposition rules
- 🔍 Local optimization with **2-opt algorithm**
- 📈 Adjustable weights for distance and cost

## 🧠 Mathematical Model

- **Haversine Formula (Geographical Distance)**
  
<img width="367" alt="image" src="https://github.com/user-attachments/assets/52eef1af-5401-4275-83f4-9bc88985c460" />

- **Ant Transition Probability**
  
<img width="332" alt="image" src="https://github.com/user-attachments/assets/cee62e56-a4de-422d-bd2a-c179c4d76a7a" />

- **Pheromone Update Rules**
  
<img width="284" alt="image" src="https://github.com/user-attachments/assets/275de9bc-3b5d-445e-b79f-df2a28fefcbd" />

- **2-opt Local Search**
  
<img width="271" alt="image" src="https://github.com/user-attachments/assets/9bd7c868-b965-4db4-9fb3-5314f91865cd" />

- **Multi-objective Score Function**
  
<img width="343" alt="image" src="https://github.com/user-attachments/assets/c5093d7e-6a2a-41aa-80f7-f2db873858e9" />

Detailed formulas are available in the accompanying LaTeX document `mathematical_report.txt`.
