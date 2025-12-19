---
layout: project
title: Counterflow Plate Heat Exchanger Performance Analysis
description: Thermodynamic Analysis of a Commercial SWEP B10THx20 Heat Exchanger
technologies: [Thermodynamics, Heat Transfer, Experimental Analysis]
image: /assets/images/heat-exchanger-setup.jpg
---

## Overview

For ENGRD 2210 Thermodynamics, I analyzed the performance of a **specific commercial heat exchanger**, the **SWEP B10THx20 brazed plate heat exchanger**, and applied mass, energy, and entropy balances using measured operating data. This project demonstrates how idealized thermodynamic principles translate to real engineering hardware under non ideal conditions.

The SWEP B10THx20 is a compact counterflow plate heat exchanger commonly used in HVAC systems, industrial process cooling, and water to water heat transfer applications. The unit consists of 20 stainless steel plates brazed with copper, providing a total heat transfer area of approximately 0.44 m^2. The manufacturer rated maximum operating temperature is 225 C and the maximum pressure is 30 bar, though the system in this experiment operated well below these limits using liquid water on both sides.

![Labeled experimental setup of the SWEP B10THx20 heat exchanger]({{ "/assets/images/heat-exchanger-setup.jpg" | relative_url }})

## Device operation and qualitative description

Hot water was supplied from an open reservoir heated by a 500 W immersion heater. Cold water was supplied from an insulated reservoir containing ice water. Each fluid stream was driven by a submersible pump delivering approximately 4 L per minute. The hot stream entered the heat exchanger at port 1 and exited at port 2, while the cold stream entered at port 4 and exited at port 3, establishing counterflow operation.

As the fluids passed through alternating corrugated plates, thermal energy transferred from the hot stream to the cold stream through the thin stainless steel walls. The corrugation promotes turbulence, increasing convective heat transfer coefficients and improving overall effectiveness compared to smooth channel designs.

## System diagram and control volume

A control volume was drawn around the entire heat exchanger. The system was modeled as a steady state control volume with two inlet streams and two outlet streams.

Energy interactions included:
- Heat transfer from the hot stream to the cold stream
- Small heat loss to the surroundings
- No shaft work crossing the control volume boundary

Assumptions:
- Steady state operation
- Incompressible liquid water
- Constant specific heat, c_p = 4180 J per kg K
- Negligible kinetic and potential energy changes

![Control volume and energy flow diagram]({{ "/assets/images/heat-exchanger-diagram.jpg" | relative_url }})

## Measured operating conditions

Representative steady state measurements were recorded after temperatures stabilized.

- Hot inlet temperature: 55 C  
- Hot outlet temperature: 42 C  
- Cold inlet temperature: 15 C  
- Cold outlet temperature: 27 C  

Volumetric flow rate on each side: 4 L per minute

Using water density of 1000 kg per m^3, the mass flow rate on each side was:

ṁ = 0.067 kg per s

## Governing equations and analysis

### Mass balance

For each stream at steady state:

ṁ_in = ṁ_out

### Energy balance (hot side)

Q̇_h = ṁ c_p (T_h,in − T_h,out)  

Q̇_h = (0.067)(4180)(55 − 42) ≈ 3640 W

### Energy balance (cold side)

Q̇_c = ṁ c_p (T_c,out − T_c,in)  

Q̇_c = (0.067)(4180)(27 − 15) ≈ 3360 W

The difference between these values is attributed to heat loss to the surroundings and measurement uncertainty, yielding an estimated heat loss of approximately 280 W.

## Effectiveness calculation

The heat capacity rate for each stream was:

C = ṁ c_p ≈ 280 W per K

The maximum possible heat transfer was:

Q̇_max = C_min (T_h,in − T_c,in)  

Q̇_max = 280 (55 − 15) ≈ 11200 W

Using the measured heat transfer:

Effectiveness, ε = Q̇_actual / Q̇_max ≈ 0.30

## Entropy balance and irreversibility

Entropy generation was evaluated using inlet and outlet temperatures in Kelvin:

Ṡ_gen = ṁ c_p ln(T_h,out / T_h,in) + ṁ c_p ln(T_c,out / T_c,in)

The positive entropy generation confirms irreversibility due to heat transfer across finite temperature differences, consistent with the second law of thermodynamics.

## Change in operating condition: parallel flow

To evaluate design sensitivity, I analyzed how performance would change if the same SWEP B10THx20 were reconfigured for parallel flow, where both streams enter at the same end.

Predicted effects:
- Reduced average temperature difference
- Lower cold side outlet temperature
- Reduced heat transfer rate
- Lower effectiveness
- Increased entropy generation for the same heat duty

## Engineering relevance

This project integrates manufacturer specifications, experimental measurements, and thermodynamic governing equations to analyze a real commercial device. The approach mirrors methods used in HVAC system design, thermal diagnostics, and energy efficiency analysis, demonstrating practical application of thermodynamics beyond idealized classroom problems.
