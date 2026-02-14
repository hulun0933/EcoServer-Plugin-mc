# EcoServer
### Adaptive Performance Engine for Minecraft Paper Servers

> EcoServer is not a lag cleaner.  
> It is an adaptive performance control engine built for high-load servers.

[中文文档 / Chinese Version](README.zh-CN.md)

---

## 🚀 Vision

Most optimization plugins react **after** TPS drops.

EcoServer is designed to:

- Predict load trends
- Adapt server behavior dynamically
- Reduce invisible computational waste
- Protect player experience
- Maintain extremely low internal overhead

Instead of brute-force entity wipes, EcoServer introduces a unified adaptive control model.

---

# 🧠 Core Model — LoadScore

LoadScore is the central performance index used by EcoServer.

It aggregates multiple runtime metrics into a single adaptive control value that drives all optimization decisions.

## Conceptual Formula

LoadScore = α(TPS Impact)
+ β(Entity Density)
+ γ(Chunk Activity)
+ δ(Memory Pressure)
+ ε(Player Density)


### Metric Explanation

- **TPS Impact**  
  Deviation from ideal 20 TPS, including moving average trend.

- **Entity Density**  
  Weighted entity count (items, mobs, tile entities).

- **Chunk Activity**  
  Loaded and ticking chunk count.

- **Memory Pressure**  
  Heap usage ratio and GC pause duration.

- **Player Density**  
  Player clustering and hotspot intensity.

Each coefficient (α, β, γ, δ, ε) is configurable.

LoadScore enables multi-factor adaptive control instead of single-threshold reactions.

---

# 🧭 Adaptive State Engine

Based on LoadScore, EcoServer transitions between states:

| State     | Score Range | Behavior |
|-----------|------------|----------|
| NORMAL    | 0–25       | No intervention |
| WATCH     | 25–50      | Light throttling |
| STRESS    | 50–75      | Adaptive entity control |
| CRITICAL  | 75+        | Intelligent cleanup |

Hysteresis is applied to prevent rapid state oscillation.

---

# 🏗 Architecture

EcoServer follows a three-layer structure:

## 1️⃣ Sensor Layer
Collects runtime metrics and calculates LoadScore.

## 2️⃣ Strategy Layer
Interprets LoadScore and determines optimization state.

## 3️⃣ Executor Layer
Applies adaptive optimization strategies dynamically.

---

# 🧊 Planned Features

- TPS moving average monitoring
- Intelligent item cleanup
- Entity sleep system
- Spawner nerf optimization
- JVM GC monitoring (JMX-based)
- Heatmap-based optimization (planned)
- Spark profiling integration (planned)

---

# 🛠 Target Platform

- Paper (Primary)
- Purpur
- Pufferfish

EcoServer is built specifically for optimized server forks.

---

# 📅 Roadmap

## v0.1 – Foundation
- LoadScore implementation
- State controller
- Intelligent item cleanup
- `/eco health` command

## v0.2 – Adaptive
- Entity sleep system
- JVM GC monitoring
- Spawner optimization

## v0.3 – Predictive
- Heatmap system
- World-specific strategies
- Spark integration

## v1.0 – Production Stable
- Large-scale benchmarking
- Public API
- Stability certification

---

# 🔬 Philosophy

EcoServer is not another cleanup plugin.

It aims to become:

> A server-level adaptive performance middleware.

---

# 📄 License

To be decided (MIT recommended).
