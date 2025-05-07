## Vortex Backend-end Technical Interview Test

### Parlay Game

This project is a backend system for a fantasy Parlay game focused on NFL and NBA players. It consists of two microservices:

- **entity-service**: Handles player-related data (e.g., name, team, stats).
- **play-service**: Manages user picks and parlay submissions.

## Overview

In a fantasy Parlay game, users select multiple player OR team performance outcomes across different sports (NFL, NBA). If all chosen outcomes are correct, the user wins the parlay.
This system is designed with a microservice architecture to separate responsibilities

## 📦 Microservices

### 1. `entity-service`

**Purpose**: Stores and manages player data.

**Responsibilities**:
- Maintain a database of NFL and NBA players, teams and stats.
- Provide APIs to fetch entity information by entity type and ID. Entities can either be teams or players.

---

### 2. `play-service`

**Purpose**: Handles user picks and parlay submissions.

**Responsibilities**:
- Accept user parlay entries (a combination of picks).
- Validate picks using data from `entity-service`.
- Store parlays and picks in a database.

---

## 🔗 Service Communication

`play-service` communicates with `entity-service` to:
- Validate entity IDs during parlay submission.

This is done via REST API calls (e.g., from `play-service` to `entity-service`

---

## 🧪 Technical Test

# Objective

Update the entity-service to support core features needed by play-service to validate user picks during parlay submissions.

# Tasks

1.  Build logic in `entity-service` to fetch a single entity by `entityType` (`athlete` or `team`) and `entityID`. Entitiy can be either a team or an athlete.
2.  Build logic to fetch multiple entities by `entityType` and a list of `entityIDs`.
3.  Confirm that `play-service` can use `entity-service` to validate all IDs in a submitted parlay.
4.  Save submitted parlay in the database.




