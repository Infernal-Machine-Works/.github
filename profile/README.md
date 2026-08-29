# Infernal Machine Works


> **Building machines that build machines.**
> Open infrastructure for autonomous and AI-assisted engineering — from reasoning to reality.

![](https://raw.githubusercontent.com/Infernal-Machine-Works/.github/refs/heads/master/_images/profile002.png)

**Infernal Machine Works** is a collection of open-source tools for building systems that can design, simulate, validate, manufacture and operate things in the real world.

Modern language models are remarkably capable reasoning engines. They can write software, reason about mechanical designs, plan experiments, analyze data and operate tools. But reasoning alone does not make an autonomous engineer. It needs machinery around it.

It needs persistent projects and artifacts. It needs deterministic tools. It needs simulators that can tell it when an idea does not work. It needs CAD and CAM systems, software tests, hardware interfaces, machine controllers and ways to safely interact with physical equipment.

**Infernal Machine Works builds that machinery.**

## From Reasoning to Reality

The central idea behind Infernal Machine Works is simple:

> **Reasoning proposes. Deterministic systems verify.**

* A language model can propose a mechanical assembly, but geometry software can determine whether its parts actually collide.
* It can generate a machining strategy, but a CAM simulator can determine whether the tool crashes into the workpiece.
* It can write software, but compilers and test suites as well as proof assistants determine whether that software works.
* It can plan the movement of a robot, but kinematic and physical simulation can determine whether that movement is possible.
* And ultimately, sensors and measurements determine whether the physical result agrees with the model.

The goal is therefore not to replace conventional engineering software with language models. Instead, _Infernal Machine Works_ connects reasoning systems with the enormous ecosystem of deterministic engineering tools that already exists - and builds the missing infrastructure required to close the loop between them.

```
                       ┌───────────────┐
                       │    Intent     │
                       │ Human / Agent │
                       └───────┬───────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Reasoning & Planning│
                    │ LLM · Planner · HTN │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
              ┌────►│      Engineering    │────┐
              │     │ CAD · Code · Control│    │
              │     └──────────┬──────────┘    │
              │                │               │
              │                ▼               │
              │     ┌─────────────────────┐    │
              │     │ Simulation & Testing│    │
              │     │ Physics · Geometry  │    │
              │     │ Software · Machines │    │
              │     └──────────┬──────────┘    │
              │                │               │
              │          failure / feedback    │
              └────────────────┘               │
                                               │
                                      validated│
                                               ▼
                                    ┌─────────────────┐
                                    │   Real World    │
                                    │ CNC · Printers  │
                                    │ Robots · Labs   │
                                    └────────┬────────┘
                                             │
                                        measurement
                                             │
                                             └──────► feedback
```

The interesting part is not any individual box. It is the **closed engineering loop**.

## What We Build

Infernal Machine Works contains projects spanning the different layers required for autonomous engineering.

### Engineering Automation

Interfaces and tools that allow software agents to work with conventional engineering environments.

This includes areas such as:

* parametric CAD
* automated assembly design
* CAM and toolpath generation
* manufacturability analysis
* electronics and hardware design
* machine configuration
* engineering artifact management

The objective is not merely to generate files, but to make engineering operations **inspectable, scriptable and verifiable**.

### Simulation & Validation

Generative systems are good at producing plausible solutions. Engineering requires solutions that actually work.

Simulation and validation therefore form a fundamental part of the architecture. Depending on the problem, this may involve:

* geometric and collision analysis
* robot kinematics
* machine simulation
* CAM verification
* physics simulation
* numerical models
* software test suites
* hardware-in-the-loop testing
* measurement and inspection

These systems provide objective feedback that can be fed back into the reasoning process. An agent should not need to *believe* that its design works when it can simply test it.

### Agents & Orchestration

Engineering problems rarely consist of a single prompt followed by a single answer. They involve decomposition, experimentation, implementation, testing, failure, revision and eventually integration. 

_Infernal Machine Works_ explores infrastructure for long-running engineering agents, including:

* task decomposition and planning
* tool orchestration
* hierarchical task networks
* coding and engineering agents
* multi-agent workflows
* persistent execution
* distributed workers
* automated test-and-repair loops

The aim is to move from isolated model invocations toward persistent engineering processes.

### Machines & Robotics

Eventually, engineering leaves the computer. Projects in this area provide interfaces between software agents and physical systems such as:

* robots
* CNC machines
* 3D printers
* laboratory equipment
* sensors
* actuators
* custom automation hardware

Physical execution is treated as another stage of the engineering pipeline rather than as a magical final `run()` call.

Simulation, constraints, validation and feedback remain part of the loop.

### Hardware Interfaces

Sometimes the missing abstraction lives much further down the stack.

Infernal Machine Works may therefore also contain operating-system and hardware infrastructure where existing interfaces make automation unnecessarily difficult.

Examples include:

* userspace hardware drivers
* generic PCIe interfaces
* machine communication protocols
* sensor and actuator interfaces
* embedded controllers
* hardware abstraction layers

The guiding principle is to expose useful hardware capabilities through small, understandable and composable interfaces.

### Infrastructure

Autonomous engineering also requires decidedly unglamorous infrastructure. Fortunately, we like that stuff too.

Projects may include:

* API gateways
* secure networking and VPN infrastructure
* distributed execution
* service discovery
* artifact storage
* versioning and provenance
* authentication and authorization
* monitoring and logging
* project and knowledge infrastructure

These components form the plumbing underneath the more visible engineering systems.

## Engineering Philosophy

Infernal Machine Works is built around a few principles.

### Reasoning proposes. Deterministic systems verify.

Language models are powerful reasoning tools, but plausibility is not verification.

Whenever possible, generated results should be checked by software whose behaviour is constrained by mathematics, physics, formal rules or direct measurement.

### Simulation before actuation.

Trying things is useful. Trying them in a simulator first is usually cheaper.

Any operation capable of damaging a machine, workpiece or environment should have opportunities for deterministic validation before physical execution.

### Validation before fabrication.

A CAD model being syntactically valid does not make it manufacturable. A toolpath existing does not make it safe. A robot trajectory reaching its destination does not make it collision-free.

Each stage should expose validators appropriate to its domain.

### Tests before trust.

Generated software is software. ompile it. Test it. Exercise it. Break it. The same philosophy applies beyond source code.

### Artifacts, not conversations.

Engineering produces persistent objects: source trees, CAD models, simulations, measurements, manufacturing plans, documentation and revisions. These should exist independently of whichever agent happened to create them. Artifacts should be versioned, discoverable and reproducible wherever practical.

### Open interfaces over monoliths.

* A simulator should not have to know which language model is using it.
* A machine interface should not care which planner generated its command.
* A CAD system should expose operations that can be used by humans, scripts or autonomous agents alike.

Small interfaces allow components to be replaced, combined and understood.

### Humans remain part of the system.

Autonomy is a spectrum, not a switch. The same infrastructure should support everything from a human asking an agent to perform one operation to long-running autonomous engineering loops.

Intermediate state should remain inspectable, and humans should be able to intervene where appropriate.

## The Autonomy Ladder

Infernal Machine Works does not assume that engineering suddenly jumps from manual work to complete autonomy.

Instead, increasingly capable systems can be constructed incrementally:

```
        Human engineering
               │
               ▼
      AI-assisted operations
               │
               ▼
       AI-generated designs
               │
               ▼
   Automated validation & repair
               │
               ▼
 Simulation-driven iteration
               │
               ▼
 Automated manufacturing planning
               │
               ▼
      Controlled execution
               │
               ▼
   Measurement and inspection
               │
               ▼
    ┌───────────────────────┐
    │ CLOSED ENGINEERING    │
    │         LOOP          │
    └───────────────────────┘
               │
               └──────────────► iterate
```

Different projects within Infernal Machine Works operate at different points on this ladder. Complete autonomy is not required for the infrastructure to be useful. Every step that turns an informal operation into an explicit, testable interface makes both human and machine-driven engineering easier.

## The Factory Floor

The organization is intentionally broader than a single application or agent framework.

Repositories generally belong to one or more parts of the factory:

* **The Design Office**: CAD, CAM and engineering automation.
* **The Simulation Department**: Physics, geometry, machine simulation and deterministic validators.
* **The Control Room**: Agents, planners, orchestration and execution infrastructure.
* **The Machine Shop**: Robotics, manufacturing and physical automation.
* **The Hardware Department**: Drivers, embedded systems and hardware interfaces.
* **The Infrastructure Basement**: Networking, APIs, distributed execution, storage and all the machinery everyone notices only when it stops working.

Individual projects are intended to remain useful independently wherever possible. One should not need to adopt an entire software stack merely because one particularly strange machine in the basement happens to solve your problem.

## Building Machines That Build Machines

The long-term experiment behind Infernal Machine Works is larger than automating individual engineering programs. We want to find out how far an engineering process can be closed.

* Can an agent turn an objective into a design?
* Can software independently determine whether that design is mechanically valid?
* Can simulation identify its weaknesses?
* Can the agent use those results to improve it?
* Can manufacturing constraints become part of that feedback?
* Can the resulting part be fabricated, measured and compared against its intended properties?
* Can what was learned become part of the next design?

None of these questions requires a magical artificial general engineer. They require reasoning systems surrounded by good tools. And those tools can be built one at a time.

## Status

Infernal Machine Works is an experimental engineering project.

Some repositories contain useful standalone tools. Others contain prototypes, experiments or infrastructure being developed as part of a larger system. Interfaces may change while we learn what autonomous engineering actually requires in practice.

Expect machinery. Expect experiments. Occasionally expect smoke.

<!--
## Contributing

Contributions, experiments and strange machinery are welcome.

Projects should generally favor:

* open and documented interfaces
* reproducible behavior
* deterministic validation where possible
* modular components
* inspectable intermediate state
* interoperability with existing engineering tools
* designs that remain useful without requiring a particular language model or AI provider

The objective is not to build one enormous autonomous-engineering application (yet).

It is to build the pieces from which many such systems can be assembled.
-->

---

<p align="center">
  <strong>INFERNAL MACHINE WORKS</strong><br>
  <em>Building machines that build machines.</em>
</p>

