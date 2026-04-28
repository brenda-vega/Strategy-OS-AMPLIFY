# Strategy OS — AMPLIFY

## Descripción
Strategy OS es un motor de decisión basado en reglas para seleccionar estrategia de marketing a partir de un único cuello de botella dominante. Convierte input estructurado del negocio en un output estratégico restringido: estrategia, razonamiento, riesgo, mensaje de venta y primera acción de ejecución.

## Esquema de Entrada
etapa: pre | early | growth | mid  
cuello: alcance | conversion | retencion | monetizacion | posicionamiento | sistema  
icp_estado: definido | parcial | no  
evidencia: alta | media | baja  
hipotesis: string | opcional  
multiruta: boolean  

## Lógica Central
estrategia = f(cuello)  
Un cuello de botella mapea a una sola estrategia. No se permite ejecución paralela de estrategias.

## Sistema de Decisión
1. Lectura del contexto del negocio  
2. Clasificación del cuello de botella dominante  
3. Mapeo cuello → estrategia  
4. Ajuste de riesgo por etapa y evidencia  
5. Exclusión de alternativas inválidas (anti-rutas)  
6. Generación de output de ejecución  

## Lógica de Riesgo
riesgo_final = max(riesgo_base, riesgo_por_etapa, riesgo_por_evidencia)

## Estructura de Salida
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

## Set de Estrategias
alcance → el ICP no entra al sistema  
conversion → hay tráfico pero no cierra  
retencion → compran pero no regresan  
monetizacion → ingreso por cliente bajo  
posicionamiento → el mercado no entiende el valor  
sistema → la operación depende de personas, no de procesos  

## Regla de Ejecución
1 cuello → 1 estrategia → 1 capa de ejecución  

## Restricciones
if icp_estado != definido → precisión baja  
if evidencia == baja → alta incertidumbre  
if múltiples estrategias → pérdida de señal  

## Flujo de Integración
Diagnóstico de fundación → ATLAS → Strategy OS → Funnel / ejecución  

## Stack
HTML  
CSS  
JavaScript (vanilla)  

## Tipo de Sistema
Sistema de decisión estratégico basado en reglas  
No utiliza ML  
Lógica estática  
Output determinista  

## Versión
v1
