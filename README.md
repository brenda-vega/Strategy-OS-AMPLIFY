# Strategy OS — AMPLIFY

## Description
Strategy OS is a rule-based decision engine for selecting a marketing strategy based on a single dominant bottleneck. It converts structured business input into a constrained strategic output: strategy, reasoning, risk, sales message, and first execution action.

## Input Schema
etapa: pre | early | growth | mid  
cuello: alcance | conversion | retencion | monetizacion | posicionamiento | sistema  
icp_estado: definido | parcial | no  
evidencia: alta | media | baja  
hipotesis: string | optional  
multiruta: boolean  

## Core Logic
estrategia = f(cuello)  
One bottleneck maps to one strategy. No parallel strategy execution.

## Decision System
1. Read business context  
2. Classify dominant bottleneck  
3. Map bottleneck to strategy  
4. Adjust risk by stage and evidence  
5. Exclude invalid alternatives through anti-routes  
6. Generate execution output  

## Risk Logic
riesgo_final = max(riesgo_base, riesgo_por_etapa, riesgo_por_evidencia)

## Output Structure
{
  estrategia,
  razonamiento,
  riesgo,
  horizonte,
  sales_story[],
  value_bullets[],
  objection: { principal, respuesta },
  accion_1
}

## Strategy Set
alcance → ICP is not entering the system  
conversion → Traffic exists, but does not close  
retencion → Customers buy, but do not return  
monetizacion → Revenue per customer is low  
posicionamiento → Market does not understand the value  
sistema → Operation depends on people, not process  

## Execution Rule
1 bottleneck → 1 strategy → 1 execution layer  

## Constraints
if icp_estado != definido → accuracy = degraded  
if evidencia == baja → uncertainty = high  
if multiple_strategies == true → signal_quality = low  

## Integration Flow
Foundation Diagnosis → ATLAS → Strategy OS → Funnel / Execution  

## Stack
HTML  
CSS  
Vanilla JavaScript  

## System Type
Rule-based strategic decision system  
Non-ML  
Static logic  
Deterministic output  

## Version
v1
