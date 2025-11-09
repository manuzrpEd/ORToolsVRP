# Vehicle Routing Problem (VRP) – Capacitated VRP (CVRP)

![VRP Example](https://img.shields.io/badge/VRP-CVRP-blue) ![OR-Tools](https://img.shields.io/badge/Solver-Google%20OR--Tools-green) ![Python](https://img.shields.io/badge/Language-Python%203.9%2B-orange)

This repository implements a **real-world Capacitated Vehicle Routing Problem (CVRP)** solver using **Google OR-Tools** — the same engine powering Google Maps, Uber, and DHL logistics.

We solve the classic question:  
> **What is the optimal set of routes for a fleet of vehicles to deliver goods to customers while minimizing total cost?**

---

### Problem Definition

The **Vehicle Routing Problem (VRP)** generalizes the Traveling Salesman Problem (TSP) to multiple vehicles.  
We focus on the **Capacitated VRP (CVRP)** — the most widely used variant in logistics.

#### Key Elements
| Component       | Description |
|----------------|-------------|
| **Depot**       | Central warehouse — all vehicles start and end here |
| **Customers**   | Delivery locations with known demand (kg, units, pallets) |
| **Vehicles**    | Fleet with fixed capacity (e.g., 30 kg per van) |
| **Distance**    | Haversine (real road-like) or Euclidean |

#### Hard Constraints (CVRP)
- Each customer visited **exactly once**
- Every route **starts and ends** at the depot
- Total demand per route **≤ vehicle capacity**
- All customers served

#### Objective
> **Minimize total distance traveled**  
> (or total cost, time, fuel, CO₂, driver hours)

---

### Features of This Implementation

- **Heterogeneous fleet** (different capacities & cost/km)
- **Real monetary cost optimization** (RM per km)
- **Haversine distance** (Earth curvature-aware)
- **Professional visualization** with customer labels (`C1`, `C2`, ...)
- **Comparison vs naive baselines** (Nearest Neighbor, Random, Worst-case)
- **Production-ready code** (no globals, pure functions, reusable)

---

### Example: Brunei Delivery Optimization

```text
============================================================
TOTAL DISTANCE : 101.51 km
TOTAL COST     : Ringgit Malaysia 121.81
============================================================
Type A   |   43.6 km | Ringgit Malaysia  52.34 | Route: DEPOT → DEPOT → C2 → C5 → C1 → C4 → C3 → DEPOT
Type A   |   57.9 km | Ringgit Malaysia  69.47 | Route: DEPOT → DEPOT → C8 → C9 → C10 → C7 → C6 → DEPOT
Type B   |    0.0 km | Ringgit Malaysia   0.00 | Route: DEPOT → DEPOT → DEPOT
