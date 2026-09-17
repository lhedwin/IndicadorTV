# 📊 OceanTradePro - Indicador Técnico Multidimensional para TradingView

![Pine Script](https://img.shields.io/badge/Pine_Script-5.0-blue.svg) ![TradingView](https://img.shields.io/badge/TradingView-Enabled-green.svg) ![License](https://img.shields.io/badge/license-GPLv3-blue.svg) ![Status](https://img.shields.io/badge/status-production--ready-brightgreen.svg)

Indicador técnico avanzado para TradingView desarrollado en Pine Script v5 que combina múltiples estrategias de análisis técnico en una sola herramienta. Proporciona señales de compra/venta mediante cruce de medias móviles, SuperTrend, SSL Channel y EMA Cloud, con opciones personalizables para cada componente.

## 📋 Descripción del Proyecto

OceanTradePro es un indicador técnico integral diseñado para traders que buscan múltiples perspectivas de análisis en un solo gráfico. Combina cinco sistemas de análisis técnico independientes que pueden activarse/desactivarse según las necesidades del usuario:

- **Triple MA Cross**: Sistema de cruce de tres medias móviles (20, 50, 200 periodos)
- **Double HullMA Cross**: Cruce de medias Hull con cálculo matemático avanzado
- **SuperTrend**: Indicador de tendencia con ATR adaptable
- **SSL Channel**: Canal de tendencia dinámico con múltiples tipos de medias
- **EMA Cloud**: Nube de medias exponenciales para identificar tendencias

## 🎯 Características Principales

### 1. Triple MA Cross
- **Medias Móviles**: SMA 20, SMA 50, SMA 200
- **Señales Visuales**: Cruces marcados con cruces grandes de colores
- **Configuración**: Opción para mostrar/ocultar el sistema completo
- **Cruce 20/50**: Indica cambios de tendencia a corto plazo
- **Cruce 50/200**: Identifica cambios de tendencia a largo plazo

### 2. Double HullMA Cross
- **Cálculo HullMA**: Media móvil Hull con periodo configurable (default: 50)
- **Doble Componente**: Dos líneas HullMA que convergen/divergen
- **Señales de Color**: Verde (alcista) / Rojo (bajista)
- **Cruce Detectado**: Marcado con cruz grande del color de la tendencia

### 3. SuperTrend Indicator
- **ATR Period**: Configurable (default: 10)
- **ATR Multiplier**: Ajustable (default: 1.8)
- **Señales de Compra/Venta**: Labels "Buy" y "Sell" en puntos de entrada
- **Highlighter**: Opción para resaltar áreas de tendencia
- **Alertas**: Tres tipos de alertas configurables (Buy, Sell, Cambio de dirección)

### 4. SSL Channel
- **Length**: Configurable (default: 10)
- **Tipos de MA**: SMA, EMA, WMA, VWMA, DEMA, HULL, RMA, TMA1, TMA2, ZLEMA
- **Señales Visuales**: Triángulos en la parte inferior del gráfico
- **Cálculo Dinámico**: Basado en máximos/mínimos de la MA seleccionada
- **Flexibilidad**: 9 tipos diferentes de medias móviles para el cálculo

### 5. EMA Cloud
- **EMAs Principales**: EMA 21, EMA 200, EMA 89/55
- **Tipos de Cloud**: "YellowBlock Cloud" y "Standard Cloud"
- **Visualización**: Nube de color verde (alcista) o rojo (bajista)
- **Línea Central**: EMA 89 (YellowBlock) o EMA 55 (Standard)
- **Relleno Dinámico**: El área entre EMA 21 y EMA 200

## 📁 Estructura del Proyecto

```
IndicadorTV/
├── OceanTradePro.ps          # Indicador principal (Pine Script v5)
├── ATR-SL.ps                 # Indicador ATR con Stop Loss
├── DoubleHullMACross.ps      # Indicador Double Hull MA Cross
├── EMA Cloud Pro.ps          # Indicador EMA Cloud
├── RSI y ATR-SL.ps           # Indicador RSI combinado con ATR
├── SSL-Channel.ps            # Indicador SSL Channel
├── LICENSE                   # Licencia GNU GPL v3
└── README.md                 # Este archivo
```

## 🔧 Requisitos e Instalación

### Requisitos
- **Plataforma**: TradingView (cuenta gratuita o premium)
- **Versión de Pine Script**: v5
- **Timeframes**: Compatible con todos los timeframes
- **Activos**: Funciona con forex, criptomonedas, índices, acciones, etc.

### Instalación en TradingView

1. **Copiar el Código**:
   - Abre el archivo `OceanTradePro.ps`
   - Copia todo el contenido del script

2. **Pine Editor en TradingView**:
   - Ve a [TradingView](https://www.tradingview.com/)
   - Abre el Pine Editor (Panel inferior)
   - Pega el código copiado

3. **Agregar al Gráfico**:
   - Haz clic en "Add to Chart"
   - Configura los parámetros según tus preferencias
   - El indicador se superpondrá al precio (overlay=true)

## 🚀 Configuración y Uso

### Panel de Configuración

El indicador se divide en 5 grupos principales en el panel de configuración:

#### 1. Triple MA Cross
- `Mostrar Triple MA Cross`: Activa/desactiva el sistema
- Las medias se muestran automáticamente cuando está activo

#### 2. Double HullMA Cross
- `Mostrar HullMA Cross`: Activa/desactiva el sistema
- `period`: Ajusta el periodo de la HullMA (default: 50)

#### 3. SuperTrend
- `Mostrar SuperTrend`: Activa/desactiva el sistema
- `ATR Period`: Periodo del ATR (default: 10)
- `ATR Multiplier`: Multiplicador del ATR (default: 1.8)
- `Change ATR Calculation Method?`: Cambia entre ATR estándar y SMA de TR
- `Show Buy/Sell Signals?`: Muestra labels de compra/venta
- `Highlighter On/Off?`: Resalta áreas de tendencia

#### 4. SSL Channel
- `Mostrar SSL Channel`: Activa/desactiva el sistema
- `Length`: Periodo del canal (default: 10)
- `Baseline`: Tipo de media móvil (9 opciones disponibles)

#### 5. EMA Cloud
- `Mostrar EMAs`: Activa/desactiva el sistema
- `Tipo de EMA Cloud`: YellowBlock Cloud o Standard Cloud

### Estrategias Sugeridas

#### Estrategia Multi-Timeframe
1. **Timeframe Diario**: Usa EMA Cloud para tendencia principal
2. **Timeframe 4H**: Usa SuperTrend para entradas
3. **Timeframe 1H**: Usa SSL Channel para confirmación

#### Estrategia de Tendencia
1. Identificar tendencia con EMA Cloud (verde = alcista, rojo = bajista)
2. Esperar cruce de Triple MA en dirección de la tendencia
3. Confirmar con SuperTrend
4. Entrar cuando todos los sistemas alinean

#### Estrategia de Rango
1. Usar SSL Channel para identificar rangos
2. Double HullMA para señales de reversión
3. SuperTrend para confirmación de salida

## 📊 Componentes Técnicos

### Medias Móviles Implementadas
- **SMA**: Simple Moving Average
- **EMA**: Exponential Moving Average
- **WMA**: Weighted Moving Average
- **VWMA**: Volume Weighted Moving Average
- **DEMA**: Double Exponential Moving Average
- **HULL**: Hull Moving Average
- **RMA**: Running Moving Average
- **TMA1/TMA2**: Triangular Moving Average (variantes)
- **ZLEMA**: Zero-Lag Exponential Moving Average

### Cálculos Matemáticos

#### HullMA
```
n2ma = 2 * WMA(close, n/2)
nma = WMA(close, n)
diff = n2ma - nma
sqn = sqrt(n)
HullMA = WMA(diff, sqn)
```

#### SuperTrend
```
ATR = Average True Range
up = src - Multiplier * ATR
dn = src + Multiplier * ATR
trend = close > dn ? 1 : close < up ? -1 : trend[1]
```

#### SSL Channel
```
High = MA(high, len)
Low = MA(low, len)
HLV = close > High ? 1 : close < Low ? -1 : HLV[1]
```

## 🎨 Personalización Avanzada

### Colores y Estilos
- **Triple MA**: Amarillo (20), Naranja (50), Púrpura (200)
- **HullMA**: Verde (alcista) / Rojo (bajista)
- **SuperTrend**: Cyan (tendencia alta) / Naranja (tendencia baja)
- **SSL Channel**: Verde (crossover) / Rojo (crossunder)
- **EMA Cloud**: Verde (nube alcista) / Rojo (nube bajista)

### Alertas Configurables
El indicador genera alertas automáticas para:
- **SuperTrend Buy**: Cuando la tendencia cambia a alcista
- **SuperTrend Sell**: Cuando la tendencia cambia a bajista
- **SuperTrend Direction Change**: Cambio de dirección general

Para configurar alertas:
1. Haz clic en el icono de Alertas en TradingView
2. Selecciona "Condition" → "OceanTrade Indicator PRO"
3. Elige el tipo de alerta deseada
4. Configura notificaciones (email, SMS, push)

## 🐞 Solución de Problemas

### Indicador no aparece en el gráfico
- **Solución**: Verifica que hayas copiado todo el código de `OceanTradePro.ps`
- **Solución**: Asegúrate de estar usando Pine Script v5

### Señales no se muestran
- **Solución**: Verifica que los grupos estén activados en el panel de configuración
- **Solución**: Revisa que `showsignals` esté en `true` para SuperTrend

### Error de compilación
- **Solución**: Verifica que no haya caracteres corruptos al copiar el código
- **Solución**: Asegúrate de estar en una cuenta de TradingView válida

### Rendimiento lento
- **Solución**: Desactiva sistemas que no uses para mejorar rendimiento
- **Solución**: Reduce el timeframe si tienes múltiples indicadores activos

## 📈 Comparación con Otros Indicadores

| Característica | OceanTradePro | Indicadores Individuales |
|---------------|---------------|------------------------|
| **Sistemas Integrados** | 5 en 1 | 1 por indicador |
| **Configuración** | Panel unificado | Múltiples paneles |
| **Señales** | Coordinadas | Desconectadas |
| **Rendimiento** | Optimizado | Variable |
| **Costo** | Gratuito | Variable |

## 🔐 Seguridad y Privacidad

- **Sin Datos Externos**: El indicador funciona completamente localmente en TradingView
- **Sin Conexiones API**: No hace peticiones a servicios externos
- **Código Abierto**: Totalmente auditable y modificable
- **Sin Telemetría**: No recopila datos del usuario

## 🤝 Contribuciones

Para contribuir, abrir issues o pull requests con mejoras:
- Nuevos sistemas de análisis técnico
- Optimizaciones de rendimiento
- Corrección de errores
- Mejoras en la documentación

## 📚 Recursos Adicionales

- [Documentación Pine Script v5](https://www.tradingview.com/pine-script-docs/)
- [Guía de TradingView](https://www.tradingview.com/support/)
- [Foro de Pine Script](https://www.tradingview.com/script/)

## ⚖️ Licencia

Este proyecto está licenciado bajo GNU General Public License v3.0.

## 👨‍💻 Autor

- **Proyecto**: OceanTradePro - Indicador Técnico Multidimensional
- **Autor**: Edwin López (@Lopez_Edwin)
- **Plataforma**: TradingView
- **Última actualización**: Septiembre 2026 (v1.0.0)

---

**Nota**: Este indicador es para fines educativos y de análisis. No constituye asesoramiento financiero. Siempre gestiona tu riesgo adecuadamente y realiza tu propio análisis antes de tomar decisiones de trading.
