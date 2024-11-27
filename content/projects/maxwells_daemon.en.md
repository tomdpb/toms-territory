---
slug: maxwells_daemon
title: "Maxwell's Daemon"
language: en
author: Tom
Date: 2023-08-26
---

- Status: Complete
- [GitHub project link](https://github.com/tomdpb/maxwells-daemon-cbpm-project)
- Language: Python with Jupyter Notebook

## About

This was a project I had to do for the subject Computer Based Physical Modelling at the University of Leipzig. It consists of a simulation of Maxwell's Daemon.

Maxwell's Daemon is a thought experiment created to test the validity of the Second Law of Thermodynamics. In a nutshell, there is an isolated system with two boxes. These boxes are connected by a gate, and start off with particles of different velocities. Although all the particles are moving and bouncing around each other, the goal is to have all the hot/fast particles in one box, and all the cold/slow particles in the other box.
In order to have all the particles sorted, a daemon sits at the gate and instantly opens and closes it in such a way where all hot/fast particles become trapped in one box and all cold/slow particles become trapped in the other side. By doing this, the initially chaotic system with becomes ordered, and the direct result is one box becoming warmer while the other becomes colder.

The ordering of a system means entropy is decreased. A curious problem occurs in this thought experiment: despite it being an isolated system, we have somehow decreased entropy without adding energy, which a direct violation of the Second Law of Thermodynamics. The Second Law of Thermodynamics states that heat should flow from hot to cold until it reaches thermodynamic equilibrium. Or, to use a cooler sounding quote: in an isolated system, entropy can only increase.

## Functionality

This project is made using a Jupyter Notebook running Python. Running the Notebook will show a simulation of particles bouncing around and slowly becoming ordered.

## Behind the Scenes

Behind the scenes, a particle class is created to manage the behaviour of all the particles. The container coordinates are passed to the particle class, and there are some external helper functions for finding velocities and calculating temperature and kinetic energies that are compiled with numba in order to speed things up slightly.

This is then all drawn and simulated with ipycanvas. Finally, the system updates every frame, and the user is shown its status.
