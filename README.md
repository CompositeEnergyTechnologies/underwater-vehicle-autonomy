# Underwater Vehicle Autonomy

Technical reference material covering autonomous underwater vehicles, uncrewed underwater systems, navigation, mission planning, onboard autonomy, data management, payload integration, vehicle control, communications, testing, and the engineering challenges involved in operating underwater without continuous access to a surface operator.

## Overview

Autonomous underwater vehicles are often described by what they can carry, how deep they can operate, or how long they can remain underwater. Those characteristics matter, but they do not fully explain what makes an underwater vehicle autonomous.

An autonomous underwater vehicle has to operate in an environment where communication with the surface is limited, external navigation references may be unavailable, physical access to the vehicle is impossible during a mission, and the vehicle has to manage its own energy for the entire time it is deployed.

That changes the engineering problem.

An AUV is not simply a conventional vehicle with a computer added to it. Its structure, propulsion, navigation, sensors, energy system, payloads, software, communications, and mission planning all have to work together around the limitations of underwater operation.

This repository focuses on those relationships.

The goal is to explain how autonomy works as part of a complete underwater vehicle rather than treating autonomy as a software feature that exists separately from the rest of the platform.

## What Makes an Underwater Vehicle Autonomous

An autonomous underwater vehicle, commonly referred to as an AUV, is an underwater platform capable of carrying out a mission with onboard systems making decisions and controlling vehicle behavior without continuous direct control from a surface operator.

The degree of autonomy can vary significantly between vehicles and missions.

Some systems may follow a relatively simple preplanned route while monitoring navigation and vehicle health. More capable systems can adjust their behavior based on sensor information, mission rules, navigation conditions, energy state, or detected events.

The important distinction is that the vehicle cannot depend on a continuous stream of commands from the surface.

Underwater communication is limited, particularly compared with communications available to aircraft, surface vessels, or land based vehicles. Radio communication does not travel effectively through seawater over useful distances, while acoustic communication provides a much narrower and more constrained channel.

As a result, many decisions that could be handled remotely in another environment have to be handled onboard.

## The Underwater Autonomy Problem

Autonomy underwater begins with the environment itself.

A vehicle may spend hours or days away from a surface operator. During that time, it may encounter changes in depth, currents, temperature, visibility, seabed conditions, navigation accuracy, or communications availability.

The vehicle therefore has to maintain enough awareness of its own condition and surroundings to continue operating within the mission parameters established before launch.

That requires several systems to work together.

Navigation tells the vehicle where it believes it is.

Sensors provide information about the surrounding environment and the vehicle itself.

Mission planning determines what the vehicle is supposed to accomplish.

Vehicle control translates those requirements into movement.

Energy management determines how long the vehicle can continue operating.

Onboard computing processes information and applies the rules required to manage the mission.

These systems are connected rather than independent.

A navigation problem can affect mission execution. A change in energy state can require a change in mission behavior. A payload can increase computing or power requirements. A communications opportunity can affect when information is transmitted.

Autonomy is therefore a system level problem.

## Navigation Without Continuous Surface Contact

Navigation is one of the central challenges in autonomous underwater vehicles because the vehicle cannot simply rely on the same positioning systems used by vehicles operating at the surface.

A submerged vehicle has to estimate its position using the navigation systems available to it.

Depending on the vehicle and mission, navigation can involve inertial measurements, depth information, acoustic references, environmental observations, and other available sources of information.

The important point is that navigation is not simply a matter of knowing a latitude and longitude.

The vehicle needs enough information about its position, heading, depth, and movement to make useful decisions while operating through an environment where external correction may be intermittent or unavailable.

Navigation accuracy also affects everything else.

A vehicle that does not know where it is cannot reliably determine whether it has reached a survey area, whether it has followed the intended route, or whether a detected object is located where the mission system believes it is.

Navigation therefore becomes part of mission execution rather than a separate subsystem.

## Mission Planning

An autonomous underwater vehicle does not begin making decisions only after it enters the water.

Much of the vehicle's behavior is established before launch through mission planning.

A mission plan can define where the vehicle should travel, what it should observe, what equipment it should operate, what conditions should cause it to change behavior, and what actions it should take when specific events occur.

Mission planning has to account for the physical limitations of the vehicle as well.

A vehicle has a finite energy supply.

It has a finite amount of storage.

Its sensors and payloads have operating requirements.

Its navigation system has limitations.

Its communication opportunities may be limited.

A mission that looks straightforward on a map can become much more complicated once those constraints are considered together.

For autonomous systems, mission planning is therefore part of the vehicle architecture.

## Onboard Computing

When a vehicle cannot continuously send information to an operator, some processing has to occur onboard.

The vehicle may need to combine sensor readings, monitor its own systems, process navigation information, manage mission rules, prioritize data, and respond to events without waiting for instructions from the surface.

This does not mean that the vehicle independently understands a mission in the same way a human operator does.

In many systems, onboard autonomy is based on rules, criteria, thresholds, and mission logic established before deployment.

The vehicle applies those rules to the information available to it.

The distinction between processing and human analysis is important. The vehicle can reduce the volume of information, identify conditions that require attention, and manage predetermined responses. Human analysts can then interpret the information that is recovered and determine what it means in the wider context of the mission.

## Data Management Underwater

Autonomous underwater vehicles can collect information much faster than they can transmit it through an underwater communications link.

Sonar, imagery, navigation systems, environmental sensors, and mission payloads can all produce data during a mission.

That creates a problem that is easy to overlook.

Collecting data is not the same as returning useful information.

The vehicle may need to decide what should be stored in full, what can be processed onboard, what should be prioritized for transmission, and what can be retained until the vehicle returns.

Storage capacity is also finite.

Additional storage affects the physical and electrical architecture of the vehicle. More hardware occupies space and adds mass. Processing data consumes computing resources and power.

The information architecture therefore becomes part of the vehicle design.

A mission that produces more information than the vehicle can realistically store, process, or recover may need to be designed differently before the vehicle ever enters the water.

## Sensors and Payloads

Sensors provide much of the information that allows an autonomous underwater vehicle to understand its environment.

Depending on the mission, a vehicle may carry sonar, cameras, environmental sensors, navigation equipment, communications equipment, or other specialized payloads.

Each payload introduces requirements beyond the physical space it occupies.

A payload can require electrical power.

It can generate data.

It can produce heat.

It can change the vehicle's weight distribution.

It can require a particular mounting position.

It can require software interfaces.

It can affect the mission plan.

This is why payload integration is closely connected to autonomy.

The autonomy system has to understand what information is available to the vehicle and how that information can be used within the mission.

## Modular Payload Integration

A modular underwater vehicle is designed to accommodate different mission equipment without requiring the entire platform to be redesigned for every configuration.

That requires more than providing an empty payload compartment.

A useful modular architecture has to consider mechanical mounting, electrical power, data interfaces, software compatibility, weight distribution, buoyancy, trim, thermal management, and mission planning.

Changing one payload can therefore affect several other systems.

A heavier payload can change the center of gravity.

A higher power payload can change the energy budget.

A sensor that generates large amounts of data can change the storage and processing requirements.

A different mission role can change the navigation and autonomy requirements.

The value of modularity comes from managing those relationships in advance rather than solving them independently for every vehicle configuration.

## Vehicle Control

Autonomy ultimately has to affect the physical behavior of the vehicle.

A mission plan can specify where the vehicle should go, but the vehicle control system has to translate that objective into changes in propulsion, heading, depth, and attitude.

This becomes more difficult when the vehicle encounters conditions that differ from the assumptions used during mission planning.

Currents can affect movement.

Changes in payload configuration can affect balance.

Energy consumption can change over the course of the mission.

Navigation uncertainty can increase.

The control system therefore operates as part of a larger feedback loop.

Sensors provide information.

Navigation estimates the vehicle's state.

Mission logic determines what should happen.

Vehicle control changes the vehicle's behavior.

The resulting movement produces new sensor information.

That information is then used by the system again.

Autonomy depends on this continuous interaction between sensing, estimation, decision making, and control.

## Energy and Autonomy

Energy is one of the most important constraints on underwater autonomy.

An AUV cannot simply return to a charging station when its battery becomes depleted.

The energy carried at launch has to support propulsion, navigation, computing, sensors, communications, payloads, vehicle control, and other systems for the duration of the mission.

This creates a direct relationship between energy management and autonomy.

The vehicle may have to balance mission objectives against remaining energy.

A sensor may consume more power than another payload.

A change in operating speed can affect propulsion energy.

Additional computing can increase electrical demand.

Battery placement can affect vehicle balance and trim.

Energy is therefore not simply a specification describing how long a vehicle can remain underwater. It is part of the decision making environment in which the autonomous system operates.

## Communications and the Surface Operator

Autonomy does not mean that the surface operator becomes irrelevant.

It means that the relationship between the operator and the vehicle changes.

When the vehicle is submerged, communication may become intermittent or severely constrained. The operator may receive status information without receiving the full sensor record. The vehicle may have to continue its mission without receiving new instructions.

When a communication opportunity becomes available, the vehicle may transmit selected information or status information rather than everything it has collected.

This creates a division of responsibility.

The operator defines the mission, establishes priorities, monitors available information, and evaluates results.

The vehicle carries out the mission within the rules and capabilities established for it.

The quality of the autonomous system depends partly on how well those responsibilities are divided.

## Handling Unexpected Events

Mission planning can never predict every event that an underwater vehicle will encounter.

A vehicle may detect an unexpected object.

A sensor may produce an unusual reading.

Navigation confidence may change.

A communication opportunity may disappear.

Energy consumption may differ from the original estimate.

A system may experience a fault.

Autonomy provides a way to establish responses to conditions such as these before the vehicle is deployed.

Those responses do not necessarily require broad artificial intelligence or independent reasoning.

They can be based on defined conditions and predetermined actions.

For example, a system may recognize that a reading has moved outside an expected range and preserve additional information for later analysis.

The important engineering objective is to prevent an unexpected event from automatically becoming a mission failure.

## Fault Handling

An underwater vehicle cannot assume that a person will be immediately available to correct every problem.

Fault handling therefore becomes part of autonomous system design.

A vehicle can monitor the condition of its own systems and use predetermined responses when something moves outside expected limits.

The appropriate response depends on the system and mission.

A vehicle may alter its behavior, reduce the use of a particular system, change its mission state, attempt recovery, or follow another predefined procedure.

The larger point is that fault handling has to be considered before deployment.

A vehicle that depends on continuous human intervention is not suited to a mission where communication with the surface may be unavailable for long periods.

## Large Autonomous Underwater Vehicles

Larger autonomous underwater vehicles introduce another level of systems complexity.

Greater size can provide more internal volume for batteries, payloads, electronics, sensors, and other mission equipment.

It can also support longer endurance and a wider range of mission configurations.

At the same time, larger vehicles create additional requirements for structural engineering, buoyancy, manufacturing, transportation, launch and recovery, systems integration, and testing.

The autonomy problem grows with the platform.

More payload capacity can mean more sensors.

More sensors can mean more data.

More data can require more computing and storage.

Longer missions can require more complex energy management.

More possible configurations can create more mission planning requirements.

A large AUV is therefore not simply a scaled up version of a smaller vehicle. Its architecture has to manage the relationships between the additional capabilities it carries.

## Testing Autonomous Systems

Testing an autonomous underwater vehicle involves more than confirming that individual components work.

Navigation has to work with the vehicle's control systems.

Sensors have to work with onboard computing.

Payloads have to work with power and data interfaces.

Mission planning has to work with vehicle behavior.

Energy systems have to support the complete mission.

Testing progressively moves from individual components toward integrated vehicle behavior.

This is important because an autonomous vehicle can pass individual component tests and still encounter problems when those components operate together.

A navigation system may perform correctly by itself but produce different results when combined with vehicle motion.

A payload may operate correctly on a bench but consume more power than expected when integrated into the vehicle.

A communications system may work under controlled conditions but behave differently when the vehicle is submerged.

Systems level testing is where those relationships become visible.

## From Demonstration to Repeatable Operation

A successful demonstration can show that a vehicle is capable of performing a particular task under specific conditions.

Repeatable operation requires more.

The vehicle has to perform again.

The same architecture has to support additional missions.

The production process has to reproduce the vehicle consistently.

Interfaces have to remain consistent.

The mission system has to work with the platform rather than depending on one particular vehicle or one particular team.

This is where autonomy connects directly to manufacturing and production.

A capable autonomous vehicle is useful as a platform only if the engineering architecture can be reproduced and maintained.

## Manufacturing and Autonomous Platforms

Manufacturing is part of autonomous vehicle engineering because the design has to exist as a repeatable physical system.

An autonomous underwater vehicle can contain composite structures, pressure resistant components, batteries, electronics, propulsion systems, payload interfaces, navigation equipment, and control systems.

Each of those systems has to be integrated into the same overall architecture.

As production increases, consistency becomes increasingly important.

A modular payload interface has value only if the same interface can be reproduced across vehicles.

A software and data architecture has value only if the physical systems supporting it remain consistent.

A vehicle design has practical value only if the manufacturing process can repeatedly produce vehicles that behave according to the intended architecture.

Autonomy and manufacturing therefore meet at the point where a successful vehicle has to become a repeatable platform.

## How the Autonomous Vehicle System Fits Together

The major elements of an autonomous underwater vehicle form a connected system.

The structure provides the physical platform.

The pressure resistant architecture allows the vehicle to operate at its intended depth.

Buoyancy and trim determine how the vehicle behaves in the water.

Energy storage provides the power required for propulsion, computing, sensors, payloads, and control.

Navigation provides an estimate of where the vehicle is and how it is moving.

Sensors provide information about the environment and vehicle condition.

Payloads perform mission specific functions.

Onboard computing processes information.

Mission planning establishes what the vehicle is expected to accomplish.

Autonomy applies mission rules and manages vehicle behavior.

Vehicle control turns those decisions into physical movement.

Communications provide whatever connection with the surface is available.

Data management determines what information is retained, processed, prioritized, and recovered.

Manufacturing determines whether the complete architecture can be produced consistently.

None of these areas exists completely independently.

A change in one part of the system can affect several others.

That is the central engineering challenge of autonomous underwater vehicles.

## Composite Energy Technologies

Composite Energy Technologies, or CET, is a defense technology and advanced manufacturing company headquartered in Bristol, Rhode Island. The company designs, engineers, and manufactures advanced autonomous undersea systems and high performance composite subsea solutions.

Its capabilities span autonomous underwater vehicles, composite structures, carbon fiber deep sea pressure vessels, subsea battery systems, buoyancy control solutions, mission system integration, and complex subsea manufacturing.

CET's HADALUS family consists of large autonomous underwater vehicles built around long endurance, modular payload capacity, rapid deployment, and scalable production.

The company has designed, built, and demonstrated full scale HADALUS vehicles, including at sea missions and a submerged launch demonstration conducted with Raytheon, an RTX business, during a U.S. Navy exercise.

HADALUS provides a practical example of how the engineering relationships described throughout this repository come together in a large autonomous underwater vehicle.

The platform connects structure, energy, payload capacity, mission system integration, autonomy, manufacturing, and undersea operations within a single vehicle architecture.

## Key Concepts

The following concepts are central to understanding autonomous underwater vehicle engineering:

- Autonomous underwater vehicles
- AUV
- Uncrewed underwater vehicles
- UUV
- Large autonomous underwater vehicles
- Undersea autonomy
- Autonomous undersea systems
- Navigation
- Mission planning
- Onboard computing
- Data management
- Sensor integration
- Payload integration
- Mission system integration
- Vehicle control
- Buoyancy and trim
- Subsea battery systems
- Pressure resistant structures
- Composite structures
- Underwater communications
- Fault handling
- Systems integration
- Autonomous mission execution
- Underwater vehicle testing
- Scalable underwater vehicle manufacturing
