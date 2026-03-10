# Calculadora de Conductividad Térmica

## Archivo principal
- `C:\Users\aulibarri\SCRIPTS\Trabajo\calculadora_conductividad.html`

## Funcionalidades implementadas

### 1. Carga de datos desde Excel
- Lee automáticamente la hoja "registro hora-hora"
- Detecta termopares (Q1, Q2, Q3...) automáticamente
- Detecta mesetas (períodos donde T RAMPA es constante)

### 2. Cálculos
- **ΔT material**: T_aislante_fin - T_aislante_inicio (de cada meseta)
- **ΔT caras**: media(termopar) - media(aislante) (de cada meseta)
- **Tiempo**: (Nº hora final - Nº hora inicial) × 3600 segundos
- **Q = m × Cp × ΔT_material**
- **k = (Q × d) / (A × ΔT_caras × t)**

### 3. Interfaz de usuario
- Pregunta si los termopares están en el mismo hormigón
  - Si Sí: solo 1 bloque de datos para todos
  - Si No: datos independientes por termopar
- Lista de materiales con Cp predefinidos
- Opción "Otro material..." para escribir nombre y Cp manualmente

### 4. Unidades
- Masa: kg
- Cp: kJ/(kg·K) (se convierte a J internally)
- Espesor, Altura, Lado: mm (se convierte a m internamente)

### 5. Materiales disponibles en la lista
- Hormigones densos (0.90)
- Hormigones aislantes (1.00)
- Hormigones AL2O3 60% (0.95)
- Hormigones AL2O3 70% (0.92)
- Hormigones AL2O3 80-90% (0.90)
- Ladrillos refractarios densos (0.90)
- Ladrillos aislantes (0.95)
- Silicato cálcico (0.95)
- Lana mineral / fibra cerámica (0.85)
- Morteros refractarios (0.90)
- Hormigones NO WET (0.88)
- PROMASIL-1000 (1.00)
- INSULFRAX (0.90)
- PROMATON-23 (0.95)

## Archivos relacionados
- `C:\Users\aulibarri\SCRIPTS\Trabajo\xlsx.min.js` - librería para leer Excel
- `C:\Users\aulibarri\SCRIPTS\Trabajo\CURVA SECADO PUERTA ARZYZ.xls` - Excel de prueba
- `C:\Users\aulibarri\SCRIPTS\Trabajo\Puerta secado costellium\CURVA SECADO PUERTA COSTELLUM 1.xls` - Excel con 2 termopares
