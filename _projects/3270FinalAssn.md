---
layout: project
title: MAE 3270 (Mechanics of Engineering Materials) Final Project
description: This assignment involves designing an instrumented 3/8-inch drive torque wrench capable of measuring 600 in-lbf of torque using bonded strain gauges. The work begins with analysis of a provided baseline design through both hand calculations and a finite element model in ANSYS, followed by iterative improvements through material selection, dimensional adjustments, and verification of all safety and performance requirements. A CAD model of the optimized wrench is then created and imported into ANSYS for full stress and strain analysis. The project integrates materials selection, stress and deflection analysis, fracture and fatigue safety factors, and FEM validation to demonstrate a complete first-cut mechanical design workflow.
technologies: [Fusion 360, Ansys]
image: /assets/images/randowrench.avif
---

<img src="{{ '/assets/images/CTWCAD.png' | relative_url }}" 
     alt="Torque Wrench CAD"
     width="600">
The material used for this torque wrench design is a quenched and tempered low alloy steel, AISI 4340. The value of poisson’s ratio is between 0.29-0.33; I selected 0.33. The Young’s Modulus is 30.5x10<sup>6</sup> psi and the fracture toughness is 82.5x10<sup>3</sup> psi*√(in). The ultimate tensile strength is 240 ksi and the fatigue strength is 100 ksi. This material was chosen for its high ductility, strength, and toughness. (Q1 and Q2)

<img src="{{ '/assets/images/engdrawingCTW.png' | relative_url }}" 
     alt="Torque Wrench CAD"
     width="600">
Engineering drawing with dimensions of my custom torque wrench from Fusion 360. (Q1)

<img src="{{ '/assets/images/CTW-load-point-deflection-4.4x-scale.png' | relative_url }}" 
     alt="Torque Wrench CAD"
     width="600">
4.4x scale image of the load point deflection. 

<img src="{{ '/assets/images/CTW-load-point-deflection-true-scale.png' | relative_url }}" 
     alt="Torque Wrench CAD"
     width="600">
True scale image of the load point deflection.

<img src="{{ '/assets/images/CTW-max-normal-stress-w-probe.png' | relative_url }}" 
     alt="Torque Wrench CAD"
     width="600">
Maximum normal stress with probe to show the numerical value at the location. (Q6)

<img src="{{ '/assets/images/CTW-max-principal-stress-1.png' | relative_url }}" 
     alt="Torque Wrench CAD"
     width="600">
Maximum principal stress overall. (Q5)

<img src="{{ '/assets/images/CTW-max-principal-stress-2.png' | relative_url }}" 
     alt="Torque Wrench CAD"
     width="600">
Maximum principle stress, close-up view. (Q5)

<img src="{{ '/assets/images/CTW-normal-strain-contours-1.png' | relative_url }}" 
     alt="Torque Wrench CAD"
     width="600">
Normal strain contours. (Q4)

<img src="{{ '/assets/images/CTW-strain-at-gauge.png' | relative_url }}" 
     alt="Torque Wrench CAD"
     width="600">
Strain at the gauge. The gauge is lcoated 1 inch from the center line of the drive. The torque wrench sensitivity is 1.078 mV/V. (Q6 and Q7)

The strain gauge selected for my custom wrench is the single linear general purpose strain gauge from DigiKey electronics. The dimensions are 0.095 in by 0.063 in, and will thus have no problem being secured on the side of my custom wrench whose side face has dimensions 0.4 in by 17 in. (Q8)