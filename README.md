# Stack Balancing Robot: Hybrid Controller Design – PD + CLF-QP  

This project explores the design and implementation of a **hybrid control system** for balancing a tower of boxes on a hinged plate under external disturbances such as wind. The work was inspired by the *Wii Party – Shifts Gifts* minigame and combines both **linear (PD)** and **nonlinear (CLF-QP)** controllers for stability.  

---

## 🚀 Project Overview  
- A rectangular base plate, hinged at its center about the y-axis, is used to balance **N stacked cube-shaped boxes**.  
- The objective is to maintain the stack upright while counteracting disturbances (e.g., wind).  
- The hybrid controller consists of:  
  - **Feedforward controller**: Applies holding torque to cancel passive dynamics.  
  - **PD controller**: Stabilizes small perturbations within the Region of Attraction (RoA).  
  - **CLF-QP controller**: Stabilizes large perturbations beyond the RoA using Lyapunov-based constraints.  
- The system is simulated in **Unity3D**, leveraging its physics engine for contact force modeling.  

---

## 📖 Features  
- **Mathematical modeling** of environment and robot dynamics using Lagrangian mechanics.  
- **Complementarity conditions** for stick-slip friction dynamics.  
- **Stability analysis** (equilibrium point and Lyapunov-based global asymptotic stability).  
- **Hybrid control architecture** (Feedforward + PD + CLF-QP).  
- **Simulation with wind disturbances**, visualized in Unity3D.  

---

## 📊 Results  
- PD controller maintains stability under small wind perturbations (~40s).  
- CLF-QP controller activates for larger disturbances but struggles under actuator limitations.  
- Simulation showed oscillatory behavior around upright position without convergence due to computational and actuation limits.  

Unity Simulation Environment: https://drive.google.com/file/d/1OzpS5lR1d3bwTLUme0GjN6gg6njCM4c5/view?usp=drive_link

---

## ⚠️ Limitations  
- Unrealistic gain constants due to Unity physics and actuator constraints.  
- Wind modeled only as a planar force.  
- Assumes static gravity torque is always nullified by feedforward control.  
- High computational load limits integration accuracy.  

---

## 🔮 Future Work  
- Adaptive CLF, sliding-mode controllers, or reinforcement learning for realistic tuning.  
- Sim2Real transfer for physical robotic implementation.  
- Adding extra DoFs (e.g., prismatic joints at plate corners) for full 3D wind disturbance handling.  

---

## 📚 References  
1. Nagarajan U, Kantor G, Hollis R. *The Ballbot: An Omnidirectional Balancing Mobile Robot*. IJRR, 2013.  
2. Wang Y, Dehio N, Kheddar A. *On Inverse Inertia Matrix and Contact-Force Model for Robotic Manipulators at Normal Impacts*. IEEE RAL, 2022.  
3. Ames A. D., et al. *Rapidly Exponentially Stabilizing Control Lyapunov Functions and Hybrid Zero Dynamics*. IEEE TAC, 2014.  
4. Ames A. D., et al. *Control Barrier Function Based Quadratic Programs with Application to Adaptive Cruise Control*. IEEE CDC, 2014.  

---
