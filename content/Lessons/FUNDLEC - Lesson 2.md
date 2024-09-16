---
draft: false
tags: [FUNDLEC]
title: Basic Solid State Electronics
date: 2024-09-16, 22:02
---

## Sources

1. BASIC SOLID STATE PRINCIPLES (Lecture Slides)
2. Class Lecture

## The Atom’s Structure

- Matter is made up of [[atoms]]
- An atom is made up of three types of charges:
	- Electrons
	- Neutrons
	- Protons
- Protons and Neutrons make up *nucleus*—the atom’s central mass
- Electrons revolve around the nucleus in a fixed orbit
- Electrons distribute themselves in shells
- *Valence electrons* refer to the electrons at the outermost shell
- The total number of electrons in a neutral atom is equivalent to the number of protons in the atom
- *Bohr’s model* is the most popular model for representing an atom
- Charges are denoted using the unit Coulomb ($Q$)
- Protons are bigger than electrons because electrons are **negatively** charged. On the other hand, neutrons share a similar size with protons.
- The charges separate when heated
- The **number of valence electrons** influences the atom’s electrical property.
	- This is because the valence electrons have the highest chances of leaving and finding a pair, generating [[current]]—the movement of charge—as a result.
- An electron becomes a *free electron* once it becomes unbounded to an atom, enabling it to **freely** move and find a pair
- Electrons move away from their current shell when [[voltage]]—the work needed to move a charge—is applied
- 3 electrical states of matter:
	- conductor
	- semiconductor
	- insulator
- An atom is **stable** only when it has eight valence electrons (the maximum number of valence electrons in an atom), except for the atom with only one shell.
	- This is because the force pulling the electrons away from the nucleus counteracts the force pulling the valence electrons towards the nucleus.

## Three Electrical Classifications of Matter

### Conductor

- A [[conductor]] is a material that easily conducts current because of its atoms’ **unstable** outermost shell. In other words, their atoms’ valence electrons are weakly attached to the nucleus.
- Their valence electrons will become free electrons after receiving enough energy; as a result, the free electrons will move randomly from one atom to another.
	- If voltage is applied, the free electrons will move in **one direction** and generates an electric current
	- The free electrons are locating a positive pair
- The energy state determines how good a conductor at conducting current (higher means better)
- has 1 valence electron

> [!TIP]- Finding the Number of Neutrons
> The number of neutrons is equivalent to the difference between the *atomic mass* and the *atomic number* (number of protons)

### Insulator

- Insulators can hardly conduct current because its atoms’ have a **stable** outermost shell.
- Current is rarely produced (even with high amounts of voltage applied) in an insulator because valence electrons from the insulator’s atoms tend to stay in their orbit.
- has 8 valence electrons

### Semiconductor

- Semiconductors have a conductivity **between** the extremes of an inductor and conductor. They are a combination of a conductor and an insulator.
- has 4 valence electrons to form a covalent bond (sharing of electrons)
- their electrons are arranged to form a crystal
- in order to become stable, the atoms of semiconductors **share** their valence electrons with each other. As a result, they neither gain nor lose electrons.

## Types of Semiconductor

### Intrinsic (Pure) Semiconductor

- A silicon crystal is considered an intrinsic semiconductor when there is no other atoms besides silicon atoms present in the material.
	- In the same token, a germanium crystal is considered an intrinsic semiconductor when there is no other atoms besides germanium.
- Although they share electrons, they can still produce free electrons and current when voltage/heat is applied; there, resulting in a conductor. This happens because the heat breaks the bonds formed.
	- Conversely, low temperature will result in an insulator—due to the lack of free electrons to produce current.
	- Separating an electron from its parent atom will leave a *hole* in the valence bond. It is represented as a positive sign because it **behaves like a proton** which attracts electrons from neighboring atoms.
		- At times, an electron merges with the hole and becomes part of the covalent bond. This process is referred to as *recombination*. The amount of time for the electron to become free and then bounded back to an atom is referred to as a *lifetime*.
		- the flow of charges from positive to negative is known as the *hole flow*; however, if it flows from negative to positive, it is known as the *electron flow*.
			- electron flow - movement of free electrons in one direction
			- hole flow - the movement of free electrons to fill a neighboring hole

### Extrinsic Semiconductor

- An extrinsic semiconductor is a semiconductor that was subjected to *doping*—addition of impure elements to pure silicon/germanium crystal—to alter its conductivity.
- Extrinsic semiconductor either results in excess electrons or excess holes; hence, we classify extrinsic semiconductor into two types: n-type and p-type.

#### N-Type (Negative Type) Semiconductor

- This type is formed by adding impure atoms with 5 valence electrons (a.k.a. *donor atoms*)
- There is an **excess electron** donated to the material to contribute to the **conduction**
- The **majority** current carriers are the thermally-generated free electrons.

#### P-Type (Positive Type) Semiconductor

- This type is formed by adding impure atoms with 3 valence electrons (a.k.a. *acceptor atoms*)
- There is an **excess hole** which accepts electron from neighboring atoms to complete a covalent bond
- The **minority** current carriers are the thermally-generated free electrons.

## Energy Level Diagram

- An energy level diagram provides another way for determining electrical characteristic of a material.
	- The energy level diagram of a material indicate the band of energy level associated with each electron of the atom, and the required energy to free the valence electrons.
- valence electrons have a higher energy state than the electrons at the inner shell
- any electrons that have left their parent atom have a higher energy state than those within their parent atom
- three regions of the energy level diagram:
	- **the conduction region -** range of energy values for free electrons
	- **the forbidden region -** the energy gap that separates the valence band and the conduction region. It represents the energy levels required to free the valence electrons
	- **the valence band -** range of energy values for valence electrons
- Energy level diagrams based on the material:
	- for **insulators**, the forbidden region requires 5 $eV$ for valence electrons to move to the conduction region. In other words, its energy gap is 5 $eV$
	- for **conductors**, the valence and conduction band **overlaps**
	- for **semiconductors**, the energy gap for silicon is 1.1 $eV$, while it is 0.67 $eV$ for germanium
