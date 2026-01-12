# Lecture 17: Robot Learning

## From Perception to Action

```
    COMPUTER VISION → ROBOT LEARNING:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   TRADITIONAL CV:              ROBOT LEARNING:                  │
    │                                                                 │
    │   Image ──► Model ──► Label   Sensor ──► Policy ──► Action    │
    │                                                                 │
    │   Passive perception           Active agent in environment     │
    │   Single frame                 Sequential decisions            │
    │   Static evaluation            Dynamic feedback loop           │
    │                                                                 │
    │   ┌─────────────────────────────────────────────────────────┐   │
    │   │                                                         │   │
    │   │              Environment                                │   │
    │   │                 │                                       │   │
    │   │        ┌────────┴────────┐                              │   │
    │   │        │                 │                              │   │
    │   │    observation       reward                             │   │
    │   │        │                 │                              │   │
    │   │        ▼                 ▼                              │   │
    │   │   ┌─────────────────────────┐                           │   │
    │   │   │        Agent           │                           │   │
    │   │   │   (Robot + Policy)     │                           │   │
    │   │   └───────────┬─────────────┘                           │   │
    │   │               │                                         │   │
    │   │            action                                       │   │
    │   │               │                                         │   │
    │   │               └────────────► Environment                │   │
    │   │                                                         │   │
    │   └─────────────────────────────────────────────────────────┘   │
    └─────────────────────────────────────────────────────────────────┘
```

## Learning Paradigms for Robots

```
    THREE MAIN APPROACHES:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   1. REINFORCEMENT LEARNING (RL)                               │
    │      Learn from reward signals through trial and error         │
    │                                                                 │
    │      ┌───────┐     action     ┌───────────┐                    │
    │      │ Agent │ ──────────────►│Environment│                    │
    │      │   π   │◄───────────────│           │                    │
    │      └───────┘  state, reward └───────────┘                    │
    │                                                                 │
    │   2. IMITATION LEARNING (IL)                                   │
    │      Learn from expert demonstrations                          │
    │                                                                 │
    │      Expert demos: [(s₁,a₁), (s₂,a₂), ...]                    │
    │               │                                                │
    │               ▼                                                │
    │      π(a|s) = argmax P(a|s)  (behavior cloning)               │
    │                                                                 │
    │   3. HYBRID APPROACHES                                         │
    │      Combine demonstrations + RL fine-tuning                   │
    │      Pre-train on demos, improve with rewards                 │
    │                                                                 │
    └─────────────────────────────────────────────────────────────────┘
```

## Reinforcement Learning Basics

```
    MARKOV DECISION PROCESS (MDP):

    ┌─────────────────────────────────────────────────────────────────┐
    │   States S: Robot configuration + environment                  │
    │   Actions A: Motor commands, joint angles                      │
    │   Transitions P(s'|s,a): Physics/dynamics                      │
    │   Rewards R(s,a): Task success signal                          │
    │   Policy π(a|s): What action to take                           │
    └─────────────────────────────────────────────────────────────────┘

    OBJECTIVE: Maximize expected cumulative reward

    J(π) = E[Σ γ^t × r_t]    (γ = discount factor)


    VALUE FUNCTIONS:

    ┌─────────────────────────────────────────────────────────────────┐
    │   V(s) = Expected return starting from state s                 │
    │   Q(s,a) = Expected return taking action a in state s         │
    │                                                                 │
    │   Bellman Equation:                                            │
    │   Q(s,a) = r(s,a) + γ × E[V(s')]                              │
    │          = r(s,a) + γ × E[max_a' Q(s',a')]                    │
    └─────────────────────────────────────────────────────────────────┘
```

## Policy Learning Methods

```
    VALUE-BASED (e.g., DQN):

    ┌─────────────────────────────────────────────────────────────────┐
    │   Learn Q-function, derive policy:                             │
    │                                                                 │
    │   State s ──► Neural Net ──► Q(s,a) for all a                 │
    │                                  │                              │
    │                                  ▼                              │
    │                        π(s) = argmax_a Q(s,a)                  │
    │                                                                 │
    │   + Works well for discrete actions                            │
    │   - Hard to scale to continuous control                        │
    └─────────────────────────────────────────────────────────────────┘


    POLICY GRADIENT (e.g., PPO, SAC):

    ┌─────────────────────────────────────────────────────────────────┐
    │   Directly optimize policy parameters θ:                       │
    │                                                                 │
    │   State s ──► π_θ(a|s) ──► Sample action                      │
    │                                                                 │
    │   Gradient: ∇J(θ) = E[∇log π_θ(a|s) × A(s,a)]                 │
    │   where A(s,a) = advantage (how much better than average)     │
    │                                                                 │
    │   + Works for continuous actions                               │
    │   + Can learn stochastic policies                              │
    │   - Sample inefficient                                         │
    └─────────────────────────────────────────────────────────────────┘
```

## Imitation Learning

```
    BEHAVIOR CLONING:

    ┌─────────────────────────────────────────────────────────────────┐
    │   Expert demonstrations: D = {(s_i, a_i)}                      │
    │                                                                 │
    │   Train policy as supervised learning:                         │
    │   L = Σ ||π_θ(s_i) - a_i||²                                   │
    │                                                                 │
    │   ┌──────────────────────────────────────────────┐             │
    │   │  Expert Demos                                 │             │
    │   │  (teleoperation, kinesthetic teaching)       │             │
    │   │  ┌────────────────────────────────────────┐  │             │
    │   │  │ s₁ → a₁, s₂ → a₂, s₃ → a₃, ...       │  │             │
    │   │  └───────────────────┬────────────────────┘  │             │
    │   │                      │                       │             │
    │   │                      ▼                       │             │
    │   │            Supervised Learning               │             │
    │   │                      │                       │             │
    │   │                      ▼                       │             │
    │   │            Policy π_θ(a|s)                   │             │
    │   └──────────────────────────────────────────────┘             │
    │                                                                 │
    │   LIMITATION: Distribution shift!                              │
    │   Robot makes small error → never-seen state → bigger error   │
    └─────────────────────────────────────────────────────────────────┘


    DAGGER (Dataset Aggregation):

    ┌─────────────────────────────────────────────────────────────────┐
    │   1. Train initial policy π₁ from demos                        │
    │   2. Run π₁, expert labels new states                          │
    │   3. Add labeled data to dataset                               │
    │   4. Retrain policy                                            │
    │   5. Repeat                                                     │
    │                                                                 │
    │   Addresses distribution shift by expanding training data     │
    └─────────────────────────────────────────────────────────────────┘
```

## Vision-Based Robot Learning

```
    END-TO-END VISUOMOTOR POLICY:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Camera Image ──► CNN/ViT ──► Features ──► Policy ──► Action │
    │                                                                 │
    │   ┌─────────────┐    ┌─────────────┐    ┌─────────────┐        │
    │   │   RGB       │    │  Encoder    │    │   Policy    │        │
    │   │  (224×224)  │───►│ (ResNet/ViT)│───►│   (MLP)     │───► a  │
    │   │             │    │             │    │             │        │
    │   └─────────────┘    └─────────────┘    └─────────────┘        │
    │                                                                 │
    │   Optionally add:                                              │
    │   - Depth image                                                │
    │   - Proprioception (joint angles, velocities)                  │
    │   - Language instructions                                      │
    └─────────────────────────────────────────────────────────────────┘


    MULTIMODAL ROBOT POLICIES:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Vision ──► Vision Encoder ──┐                                │
    │                               │                                │
    │   Language ──► Text Encoder ──┼──► Transformer ──► Actions    │
    │                               │    Policy                      │
    │   State ──► State Encoder ───┘                                │
    │                                                                 │
    │   Examples: RT-1, RT-2, PaLM-E                                 │
    └─────────────────────────────────────────────────────────────────┘
```

## Simulation to Real (Sim2Real)

```
    TRAIN IN SIMULATION, DEPLOY IN REAL WORLD:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Simulation                      Real World                   │
    │   ┌─────────────────────┐        ┌─────────────────────┐       │
    │   │  Physics Engine     │        │  Actual Robot       │       │
    │   │  (MuJoCo, Isaac)    │        │                     │       │
    │   │                     │        │  ┌───────────────┐  │       │
    │   │  Fast, safe,        │ ──────►│  │   Policy      │  │       │
    │   │  parallelizable     │transfer│  └───────────────┘  │       │
    │   │                     │        │                     │       │
    │   │  Unlimited data     │        │  Slow, risky       │       │
    │   └─────────────────────┘        └─────────────────────┘       │
    │                                                                 │
    └─────────────────────────────────────────────────────────────────┘

    DOMAIN RANDOMIZATION:

    ┌─────────────────────────────────────────────────────────────────┐
    │   Randomize simulation parameters during training:             │
    │   - Physics: friction, mass, damping                           │
    │   - Visuals: lighting, textures, colors                        │
    │   - Dynamics: actuator delays, noise                           │
    │                                                                 │
    │   Policy becomes robust to variation                           │
    │   Real world = just another variation!                         │
    └─────────────────────────────────────────────────────────────────┘
```

## Robot Foundation Models

```
    SCALING ROBOT LEARNING:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   RT-1 / RT-2 (Google):                                        │
    │   - Large-scale robot dataset (130K episodes)                  │
    │   - Transformer policy                                         │
    │   - Generalization across tasks and objects                    │
    │                                                                 │
    │   ┌─────────────────────────────────────────────────────────┐   │
    │   │  "Pick up the apple and put it in the bowl"             │   │
    │   │          │                                               │   │
    │   │          ▼                                               │   │
    │   │  ┌───────────────────────────────────────────────────┐  │   │
    │   │  │              RT-2 (VLM backbone)                   │  │   │
    │   │  │                                                    │  │   │
    │   │  │  Vision ──► PaLI-X ──► Action tokens              │  │   │
    │   │  │             (55B)       (discretized)             │  │   │
    │   │  └────────────────────────────────────────────────────┘  │   │
    │   │          │                                               │   │
    │   │          ▼                                               │   │
    │   │     Robot actions (gripper, arm joints)                 │   │
    │   └─────────────────────────────────────────────────────────┘   │
    │                                                                 │
    │   Key insight: VLM provides semantic understanding,            │
    │   enables generalization to new objects/instructions          │
    └─────────────────────────────────────────────────────────────────┘
```

## Challenges in Robot Learning

```
    ┌─────────────────────────────────────────────────────────────────┐
    │                    OPEN CHALLENGES                              │
    │                                                                 │
    │   1. SAMPLE EFFICIENCY                                          │
    │      Real robot data is expensive to collect                   │
    │      Need: better sim2real, data augmentation                  │
    │                                                                 │
    │   2. GENERALIZATION                                            │
    │      New objects, environments, tasks                          │
    │      Need: foundation models, meta-learning                    │
    │                                                                 │
    │   3. SAFETY                                                     │
    │      Robots can damage themselves or environment               │
    │      Need: safe exploration, constrained RL                    │
    │                                                                 │
    │   4. REAL-TIME CONTROL                                         │
    │      Policies must run at control frequency (100+ Hz)          │
    │      Need: efficient architectures, edge deployment            │
    │                                                                 │
    │   5. LONG-HORIZON TASKS                                        │
    │      Complex tasks require planning + control                  │
    │      Need: hierarchical policies, world models                 │
    └─────────────────────────────────────────────────────────────────┘
```

## Key Takeaways

```
┌────────────────────────────────────────────────────────────────────┐
│ 1. Robot learning: perception → decision → action loop            │
│    Extends CV to embodied AI with real-world interaction          │
│                                                                    │
│ 2. Main paradigms:                                                 │
│    - Reinforcement Learning: learn from rewards                   │
│    - Imitation Learning: learn from demonstrations                │
│    - Hybrid: combine both approaches                              │
│                                                                    │
│ 3. Vision-based policies: image → CNN/ViT → actions               │
│    End-to-end learning from raw pixels                            │
│                                                                    │
│ 4. Sim2Real: train in simulation, deploy in real world            │
│    Domain randomization bridges the reality gap                   │
│                                                                    │
│ 5. Foundation models for robots (RT-1, RT-2):                     │
│    Scale up data and model size for generalization                │
│    Leverage VLM for semantic understanding                        │
│                                                                    │
│ 6. Future: general-purpose robots that can follow any instruction │
│    and adapt to new environments/objects                          │
└────────────────────────────────────────────────────────────────────┘
```
