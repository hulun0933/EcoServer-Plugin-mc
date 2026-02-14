# EcoServer
### Adaptive Performance Engine for Minecraft Paper Servers

> EcoServer is not a lag cleaner.  
> It is an adaptive performance control engine designed for high-load servers.

[中文文档 / Chinese Version](README.zh-CN.md)

---

## 🚀 Vision

Most optimization plugins react only after TPS drops.

EcoServer focuses on predictive load modeling and adaptive control.  
Instead of brute-force entity wipes, it dynamically adjusts server behavior
based on real-time performance conditions.

The goal is simple:

- Prevent performance collapse
- Minimize invisible computational waste
- Protect player experience
- Maintain extremely low internal overhead

---

# 🧠 Core Model — LoadScore

LoadScore is the central performance index of EcoServer.

All optimization decisions are derived from this unified load evaluation model.

Rather than relying on single thresholds (e.g., entity count > X),
EcoServer aggregates multiple runtime factors into one adaptive score.

## Conceptual Formula



LoadScore = α(TPS Impact)
+ β(Entity Density)
+ γ(Chunk Activity)
+ δ(Memory Pressure)
+ ε(Player Density)


## Metric Breakdown

**TPS Impact**  
Deviation from ideal 20 TPS, including moving average trend analysis.

**Entity Density**  
Weighted count of entities (items, mobs, tile entities).

**Chunk Activity**  
Number of loaded and ticking chunks.

**Memory Pressure**  
Heap usage ratio combined with GC pause duration.

**Player Density**  
Clustering intensity and hotspot distribution.

Each coefficient (α β γ δ ε) is configurable,
allowing fine-tuning for different server environments.

LoadScore becomes the single driving signal of the entire adaptive engine.

---

# 🧭 Adaptive State Engine

Based on LoadScore, EcoServer transitions between performance states:

| State     | Score Range | Behavior |
|-----------|------------|----------|
| NORMAL    | 0–25       | No intervention |
| WATCH     | 25–50      | Light throttling |
| STRESS    | 50–75      | Adaptive entity control |
| CRITICAL  | 75+        | Intelligent cleanup |

Hysteresis control is applied to prevent rapid oscillation between states.

---

# 🏗 System Architecture

EcoServer follows a three-layer control architecture.

## 1️⃣ Sensor Layer
Collects runtime metrics and computes LoadScore.

## 2️⃣ Strategy Layer
Interprets LoadScore and determines system state.

## 3️⃣ Executor Layer
Applies adaptive optimization strategies dynamically, including:

- Intelligent item cleanup
- Entity sleep management
- Spawner optimization
- Adaptive view-distance control (experimental)

---

# 🧊 Planned Capabilities

- TPS moving average monitoring
- Intelligent value-aware item cleanup
- Entity lifecycle throttling
- JVM GC monitoring via JMX
- Player heatmap-based optimization
- Spark profiling integration

---

# 🛠 Target Platform

- Paper (Primary)
- Purpur
- Pufferfish

EcoServer is designed specifically for optimized server forks.

---

# 📅 Development Roadmap

## v0.1 – Foundation
- LoadScore implementation
- State controller
- Intelligent cleanup
- `/eco health` command

## v0.2 – Adaptive
- Entity sleep system
- GC monitoring
- Spawner optimization

## v0.3 – Predictive
- Heatmap engine
- World-specific rules
- Spark integration

## v1.0 – Production Stable
- Large-scale benchmarking
- Public API exposure
- Stability validation

---

# 🔬 Philosophy

EcoServer is not another cleanup plugin.

It aims to become:

> A server-level adaptive performance middleware.

---

# 📄 License

MIT License
