# EcoServer
### Adaptive Performance Engine for Minecraft Paper Servers

> EcoServer is not a lag cleaner.  
> It is an adaptive performance control engine.

[中文文档 / Chinese Version](README.zh-CN.md)

---

## 🚀 Vision

Most optimization plugins react **after** TPS drops.

EcoServer focuses on:

- Predictive load awareness
- Adaptive server behavior
- Intelligent entity lifecycle control
- Minimal player impact
- Extremely low internal overhead

Instead of brute-force entity wipes, EcoServer introduces
**multi-layer adaptive throttling.**

---

## 🧠 Architecture Overview

EcoServer follows a three-layer control model:

### 1️⃣ Sensor Layer
Collects real-time metrics:

- TPS (moving average)
- Entity distribution
- Chunk activity
- Player density
- JVM memory usage
- GC pause time (planned)

Outputs unified:

