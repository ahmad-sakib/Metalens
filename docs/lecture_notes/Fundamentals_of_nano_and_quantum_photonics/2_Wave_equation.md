# Class Notes: 1.2 Wave Equation


---

## 1. Topic and Motivation

* **What problem are we trying to understand?**  
  In nanophotonics, we frequently study how light behaves in structures with a spatial distribution of permittivities (dielectric properties). The central scientific challenge is determining the electromagnetic response of such structured regions of space. To accomplish this, we must solve Maxwell's equations. This lecture addresses the fundamental method of solving Maxwell's curl equations by combining them into a single, second-order partial differential equation: the **wave equation**.
  
* **Why is this topic physically important?**  
  The wave equation is a foundational pillar of nanophotonics. Understanding its derivation, its underlying physical assumptions, and the physical significance of each term is crucial for describing how light propagates through vacuum, interacts with simple dielectrics, and behaves in complex, direction-dependent (anisotropic) or high-intensity (nonlinear) media.

* **What question does the lecture answer?**  
  The lecture answers: *How do we derive the electromagnetic wave equation from Maxwell's curl equations, how does material polarization modify wave propagation, and how does light propagation mathematically and physically compare to electron behavior?*

---

## 2. Prerequisites

To fully comprehend the material in this lecture, a student should have a solid grasp of:
1. **Vector Calculus**: Proficiency with vector operators, specifically the mathematical and geometric meanings of the **curl** ($\nabla \times$) and **divergence** ($\nabla \cdot$), as well as vector identities.
2. **Maxwell's Curl Equations**: Familiarity with the differential forms of Faraday's Law and Ampère's Law.
3. **Electromagnetic Constitutive Relations**: Understanding how fields relate to material responses:
   * The relationship between magnetic flux density ($\mathbf{B}$), magnetic field ($\mathbf{H}$), and magnetization ($\mathbf{M}$).
   * The relationship between electric displacement ($\mathbf{D}$), electric field ($\mathbf{E}$), and polarization density ($\mathbf{P}$).
4. **Permittivity and Susceptibility**: The concepts of vacuum permittivity ($\epsilon_0$), relative permittivity ($\epsilon_r$), and electric susceptibility ($\chi$).
5. **Basic Wave Mechanics & Quantum Concepts**: The concepts of wave-particle duality and basic electron properties (momentum, wavelength, energy).

---

## 3. Core Concepts

* **Electromagnetic Response**:  
  * *Definition*: The spatial and temporal distribution of electric and magnetic fields that arises when light interacts with a structured environment containing varying permittivities.
  * *Physical Meaning*: It describes how a material alters, reflects, refracts, or guides light.
  * *Intuition*: When an external field is incident, charges in the medium react, creating internal fields that combine with the incident light to form the overall response.
  
* **The Wave Equation**:  
  * *Definition*: A second-order partial differential equation relating the second spatial derivative of a field to its second temporal derivative.
  * *Physical Meaning*: It governs how a localized disturbance in the electromagnetic field propagates through space over time.
  * *Intuition & Connection*: This connects directly to Maxwell's curl equations. Because a changing electric field generates a magnetic field and a changing magnetic field generates an electric field, the two fields mutually regenerate each other, causing a wave to travel through space.

* **Laplacian Operator ($\nabla^2$)**:  
  * *Definition*: In Cartesian coordinates, it is the sum of the second partial spatial derivatives:
    $$\nabla^2 = \frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2} + \frac{\partial^2}{\partial z^2}$$
  * *Physical Meaning*: It represents the spatial curvature or "flux-divergence" of a field at a given point.
  * *Intuition*: It measures how much the value of a field at a point differs from the average value of the field in the immediate neighborhood.

* **Free Space (Vacuum)**:  
  * *Definition*: A region of space containing no free charges ($\rho_f = 0$), no free currents ($\mathbf{J} = 0$), and no polarizable matter ($\mathbf{P} = 0$).
  * *Physical Meaning*: The simplest medium for wave propagation, where fields propagate completely unobstructed.

* **Plane Wave**:  
  * *Definition*: A fundamental, flat-front solution to the wave equation in which the electric and magnetic fields are confined to orthogonal planes and oscillate in time.
  * *Physical Meaning & Intuition*: In a plane wave, $\mathbf{E}$ and $\mathbf{H}$ are mutually perpendicular to each other, and both are simultaneously perpendicular to the direction of propagation (transverse wave). It serves as the basic building block for describing more complex field distributions.

* **Dielectric Medium**:  
  * *Definition*: An insulating material (e.g., glass) where charges are bound and cannot flow as free currents ($\mathbf{J} = 0$), but can displace slightly under an applied field to create polarization ($\mathbf{P} \neq 0$).
  * *Connection to Previous Concept*: Unlike free space (where $\mathbf{P} = 0$), a dielectric medium responds to the wave's electric field, which in turn alters the wave's propagation speed.

* **Refractive Index ($n$)**:  
  * *Definition*: The ratio of the speed of light in a vacuum ($c$) to the phase velocity ($v$) of the wave in a medium:
    $$n = \sqrt{\epsilon_r}$$
  * *Physical Meaning*: A macroscopic measure of how much a medium slows down propagating light.
  * *Intuition*: The higher the refractive index, the more "optically dense" the medium is, and the slower the light travels.

* **Anisotropy**:  
  * *Definition*: A state in which a material's physical response depends on the direction of the applied field.
  * *Physical Meaning*: In an anisotropic medium (like calcite), light polarized along one axis travels at a different speed than light polarized along another axis.
  * *Connection to Previous Concept*: For isotropic dielectrics, the susceptibility $\chi$ is a scalar number. For anisotropic media, $\chi$ becomes a **tensor** (a $3 \times 3$ matrix), making the relation between $\mathbf{P}$ and $\mathbf{E}$ direction-dependent.

* **Linearity vs. Nonlinearity**:  
  * *Linearity*: The polarization $\mathbf{P}$ is directly proportional to the first power of the electric field $\mathbf{E}$ ($\mathbf{P} \propto \mathbf{E}$).
  * *Nonlinearity*: The polarization exhibits dependence on higher powers of the electric field ($\mathbf{E}^2, \mathbf{E}^3$) at high field intensities, introducing second-order ($\chi^{(2)}$) and third-order ($\chi^{(3)}$) susceptibilities.
  * *Intuition*: Under weak fields, atomic charges behave like simple harmonic oscillators (linear). Under extremely intense fields (like lasers), their displacement becomes anharmonic, generating new frequencies (harmonic generation).

* **Dispersion**:  
  * *Definition*: The physical phenomenon where the refractive index of a material varies as a function of the wavelength of the light, i.e., $n(\lambda)$.
  * *Intuition & Connection*: Light of different colors (wavelengths) travels at different speeds through the same dispersive medium, which is why a prism splits white light.

* **Dispersion Relation (Electron vs. Photon)**:  
  * *Definition*: The mathematical relationship between energy ($E$) and momentum ($p$) or frequency ($\omega$) and wavevector ($k$) for a quantum particle or wave.
  * *Physical Meaning*: It determines how the energy of a quantum state scales with its momentum.
  * *Connection*: Electrons display parabolic dispersion ($E = p^2/2m$), whereas photons display linear dispersion ($E \propto p$).

---

## 4. Mathematical Development

This section outlines the step-by-step derivation of the wave equation for the electric field ($\mathbf{E}$) from Maxwell's curl equations.

### Step 1: Establish Maxwell's Curl Equations and Initial Assumptions
We start with Maxwell's curl equations. We assume that the material magnetization is zero ($\mathbf{M} = 0$), so the magnetic flux density is given by:
$$\mathbf{B} = \mu_0 \mathbf{H}$$ (Eq. 4.1)
Where:
* $\mathbf{B}$ is the magnetic flux density.
* $\mathbf{H}$ is the magnetic field.
* $\mu_0$ is the permeability of free space.

Faraday's Law of induction (the first curl equation) is:
$$\nabla \times \mathbf{E} = -\frac{\partial \mathbf{B}}{\partial t} = -\mu_0 \frac{\partial \mathbf{H}}{\partial t}$$ (Eq. 4.2)
Where:
* $\mathbf{E}$ is the electric field.
* $t$ is time.

### Step 2: Take the Curl of Faraday's Law
To decouple the electric and magnetic fields, we take the curl of both sides of Eq. 4.2:
$$\nabla \times (\nabla \times \mathbf{E}) = -\mu_0 \frac{\partial}{\partial t} (\nabla \times \mathbf{H})$$ (Eq. 4.3)
*(Note: Since spatial and temporal derivatives are independent, we swap the curl operator and the time derivative on the right-hand side).*

### Step 3: Substitute Ampère's Law
We express the curl of the magnetic field using the second Maxwell curl equation (Ampère's Law with Maxwell's correction):
$$\nabla \times \mathbf{H} = \mathbf{J} + \frac{\partial \mathbf{D}}{\partial t}$$ (Eq. 4.4)
Where:
* $\mathbf{J}$ is the free current density.
* $\mathbf{D}$ is the electric displacement field.

Substituting Eq. 4.4 into the right-hand side of Eq. 4.3 yields:
$$\nabla \times (\nabla \times \mathbf{E}) = -\mu_0 \frac{\partial}{\partial t} \left( \mathbf{J} + \frac{\partial \mathbf{D}}{\partial t} \right) = -\mu_0 \frac{\partial \mathbf{J}}{\partial t} - \mu_0 \frac{\partial^2 \mathbf{D}}{\partial t^2}$$ (Eq. 4.5)

### Step 4: Substitute the Constitutive Relation for $\mathbf{D}$
We substitute the constitutive relation linking the electric displacement field to the electric field and material polarization:
$$\mathbf{D} = \epsilon_0 \mathbf{E} + \mathbf{P}$$ (Eq. 4.6)
Where:
* $\epsilon_0$ is the permittivity of free space.
* $\mathbf{P}$ is the polarization density.

Substituting Eq. 4.6 into Eq. 4.5:
$$\nabla \times (\nabla \times \mathbf{E}) = -\mu_0 \epsilon_0 \frac{\partial^2 \mathbf{E}}{\partial t^2} - \mu_0 \frac{\partial^2 \mathbf{P}}{\partial t^2} - \mu_0 \frac{\partial \mathbf{J}}{\partial t}$$ (Eq. 4.7)

### Step 5: Simplify the Left-Hand Side (LHS) Using Vector Identity
We invoke the standard vector calculus identity for the curl of a curl of a vector field:
$$\nabla \times (\nabla \times \mathbf{E}) = \nabla (\nabla \cdot \mathbf{E}) - \nabla^2 \mathbf{E}$$ (Eq. 4.8)
Where:
* $\nabla \cdot \mathbf{E}$ is the divergence of the electric field.
* $\nabla^2 \mathbf{E}$ is the Laplacian of the electric field.

To simplify Eq. 4.8, the lecturer introduces two key assumptions:
1. **No free charges**: The region of space contains no free charges ($\rho_f = 0$).
2. **Slowly varying permittivity**: The permittivity $\epsilon$ of the medium does not vary significantly over the scale of the optical wavelength.

Under these conditions, Gauss's Law ($\nabla \cdot \mathbf{D} = \rho_f = 0$) guarantees that:
$$\nabla \cdot \mathbf{E} = 0$$ (Eq. 4.9)
Thus, the term $\nabla (\nabla \cdot \mathbf{E})$ vanishes, leaving:
$$\nabla \times (\nabla \times \mathbf{E}) = -\nabla^2 \mathbf{E}$$ (Eq. 4.10)

### Step 6: Formulate the General Electric Field Wave Equation
Equating the simplified LHS (Eq. 4.10) and the RHS (Eq. 4.7) and multiplying the entire equation by $-1$ results in the general electric wave equation:
$$\nabla^2 \mathbf{E} = \mu_0 \epsilon_0 \frac{\partial^2 \mathbf{E}}{\partial t^2} + \mu_0 \frac{\partial^2 \mathbf{P}}{\partial t^2} + \mu_0 \frac{\partial \mathbf{J}}{\partial t}$$ (Eq. 4.11)
* **Physical Meaning**: This equation shows that spatial variations (Laplacian) of the electric field are driven by three temporal acceleration terms: the vacuum displacement current, the acceleration of bound charges (polarization), and the acceleration of free charges (currents).

### Step 7: Special Case 1 - Propagation in Free Space (Vacuum)
In a vacuum, there is no matter to polarize ($\mathbf{P} = 0$) and there are no free currents ($\mathbf{J} = 0$). Under these conditions, Eq. 4.11 reduces to:
$$\nabla^2 \mathbf{E} = \mu_0 \epsilon_0 \frac{\partial^2 \mathbf{E}}{\partial t^2}$$ (Eq. 4.12)
By comparing Eq. 4.12 to the standard mechanical wave equation ($\nabla^2 \mathbf{E} = \frac{1}{v^2}\frac{\partial^2 \mathbf{E}}{\partial t^2}$), we extract the wave propagation velocity in free space:
$$v = \frac{1}{\sqrt{\mu_0 \epsilon_0}} = c \approx 3 \times 10^8 \text{ m/s}$$ (Eq. 4.13)
* **Physical Meaning**: Electromagnetic waves in a vacuum propagate at a constant speed, $c$ (the speed of light), which is determined entirely by the fundamental constants of nature: permittivity ($\epsilon_0$) and permeability ($\mu_0$) of free space.

### Step 8: Special Case 2 - Propagation in a Lossless, Isotropic Dielectric (e.g., Glass)
When light enters a non-conducting dielectric medium like glass, the following conditions apply:
1. **Insulating medium**: The free current density is zero ($\mathbf{J} = 0$).
2. **Linear, Isotropic response**: The polarization responds linearly and isotropically to the electric field, governed by a scalar susceptibility $\chi$:
   $$\mathbf{P} = \epsilon_0 \chi \mathbf{E}$$ (Eq. 4.14)

Substituting Eq. 4.14 and $\mathbf{J}=0$ into Eq. 4.11 yields:
$$\nabla^2 \mathbf{E} = \mu_0 \epsilon_0 \frac{\partial^2 \mathbf{E}}{\partial t^2} + \mu_0 \epsilon_0 \chi \frac{\partial^2 \mathbf{E}}{\partial t^2}$$ (Eq. 4.15)
Factoring out common terms:
$$\nabla^2 \mathbf{E} = \mu_0 \epsilon_0 (1 + \chi) \frac{\partial^2 \mathbf{E}}{\partial t^2}$$ (Eq. 4.16)

We define the dimensionless relative permittivity (dielectric constant) as:
$$\epsilon_r = 1 + \chi$$ (Eq. 4.17)

Substituting $\epsilon_r$ into Eq. 4.16 gives the wave equation for a simple dielectric:
$$\nabla^2 \mathbf{E} = \mu_0 \epsilon_0 \epsilon_r \frac{\partial^2 \mathbf{E}}{\partial t^2}$$ (Eq. 4.18)

Comparing this to the standard wave equation, the velocity of the wave in the medium ($v$) is:
$$v = \frac{1}{\sqrt{\mu_0 \epsilon_0 \epsilon_r}} = \frac{c}{\sqrt{\epsilon_r}} = \frac{c}{n}$$ (Eq. 4.19)
Where:
* $n = \sqrt{\epsilon_r}$ is the **refractive index** of the medium.
* **Physical Meaning**: In a lossless, simple dielectric, the wave propagates with the exact same spatial and temporal form as in vacuum, but its velocity is reduced by a factor of the refractive index ($n$).

---

## 5. Important Graphs and Physical Interpretation

The lecture discusses a plot of **refractive index ($n$) as a function of wavelength ($\lambda$)** to demonstrate material dispersion.

* **Graph Axes**:
  * **X-axis**: Wavelength ($\lambda$).
  * **Y-axis**: Refractive index ($n$).

* **Physical Meaning of the Curves**:  
  Each curve represents a different material, displaying how its refractive index varies with wavelength. The materials plotted, arranged by their band gap ($E_g$), are:
  1. **Germanium (Ge)**: Blue curve; has a very narrow band gap of $E_g \approx 0.8 \text{ eV}$.
  2. **Gallium Arsenide (GaAs)**: Green curve; has a band gap of $E_g \approx 1.42 \text{ eV}$.
  3. **Gallium Nitride (GaN)**: Has a wider band gap of $E_g \approx 3.4 \text{ eV}$.
  4. **Silicon Dioxide ($\text{SiO}_2$)**: Has a very wide band gap of $E_g \approx 9 \text{ eV}$.

* **Important Observations & Trends**:
  * **Inverse Relationship**: There is a clear inverse relationship between a material's band gap and its refractive index. Materials with smaller band gaps (like Germanium) have significantly higher curves (higher refractive index values across the spectrum), whereas materials with larger band gaps (like Silicon Dioxide) sit much lower on the graph (lower refractive index values).
  * **Dispersion Strength**: The curves show that some materials exhibit rapid variations in refractive index with wavelength (strong dispersion), whereas others remain relatively flat over certain spectral ranges.
  
* **Lecture Gaps and Incompleteness**:  
  * The mathematical equations describing these curves (such as Sellmeier equations or specific resonant models) are not presented.
  * The physical and quantum-mechanical reasons *why* the refractive index is inversely related to the band gap are not detailed; the lecturer notes this is an interesting observation and defers the physical explanation to subsequent lectures.

---

## 6. Limiting Cases

* **The Isotropic Limit (Scalar Susceptibility)**:  
  In a standard symmetric medium, the susceptibility $\chi$ is a scalar quantity. The induced polarization $\mathbf{P}$ is perfectly aligned with the applied electric field $\mathbf{E}$ ($\mathbf{P} = \epsilon_0 \chi \mathbf{E}$). Light propagates with a uniform speed $v = c/n$ regardless of its polarization direction or propagation direction.

* **The Anisotropic Limit (Tensor Susceptibility)**:  
  In asymmetric materials, such as **calcite**, the ease with which charges displace depends on the direction of the applied field.
  * *Mathematical Change*: The scalar susceptibility $\chi$ is replaced by a **susceptibility tensor** (a $3 \times 3$ matrix):
    $$\mathbf{P}_i = \epsilon_0 \sum_{j} \chi_{ij} \mathbf{E}_j$$
  * *Physical Consequence*: The velocity of the electromagnetic wave depends on its direction of propagation and polarization state. This gives rise to double refraction and other complex birefringent phenomena.

* **The Linear Limit (Low-Field Intensity)**:  
  For typical light sources, the electric field is weak relative to the atomic fields holding electrons to nuclei. The material polarization responds in a strictly linear fashion ($\mathbf{P} \propto \mathbf{E}$).

* **The Nonlinear Limit (High-Field Intensity)**:  
  When exposed to highly intense fields (such as focused laser beams), the linear approximation breaks down. The polarization must be expanded as a power series in terms of the electric field:
  $$\mathbf{P} = \epsilon_0 \left( \chi^{(1)} \mathbf{E} + \chi^{(2)} \mathbf{E}^2 + \chi^{(3)} \mathbf{E}^3 + \dots \right)$$
  Where:
  * $\chi^{(1)}$ is the linear susceptibility.
  * $\chi^{(2)}$ is the second-order nonlinear susceptibility, responsible for second-harmonic generation and sum-frequency generation.
  * $\chi^{(3)}$ is the third-order nonlinear susceptibility, responsible for third-harmonic generation and the Kerr effect.
  *(Note: Nonlinear optics is a highly decorated field of physics with multiple Nobel Prizes, but its detailed phenomena are not covered in this course).*

---

## 7. Connections

* **Connection to Preceding Material**:  
  This lecture builds on the definition of the central scientific problem of nanophotonics introduced in Lecture 1.1: solving the electromagnetic response of a system with spatially distributed permittivities. It bridges that problem with practical solution methods by showing how to formulate the wave equation from Maxwell's equations.

* **The Photons-Electrons Analogy**:  
  Optics/photonics and electronics are not isolated domains; they are deeply connected through fundamental physics.
  * **Generation**: Moving electric charges (electrons) generate light (electromagnetic fields). This is classically exemplified by antennas.
  * **Detection**: An incident electric field (light) forces charges to move, translating photons back into electronic signals (currents).

* **Comparison of Wave Properties (Electrons vs. Photons)**:  
  The lecturer highlights key physical parameters to compare electrons and photons under wave-particle duality:

| Parameter | Electrons | Photons |
| :--- | :--- | :--- |
| **Governing Wave Equation** | **Schrödinger Equation** (Second-order in space, **first-order in time**) | **Electromagnetic Wave Equation** (Second-order in **both space and time**) |
| **Dispersion Relation** | **Parabolic Dispersion**: <br> $E = \frac{p^2}{2m}$ (Energy is proportional to the square of momentum) | **Linear Dispersion**: <br> $E \propto p$ (Energy is linearly related to momentum, $E = pc$) |
| **Momentum (Classical)** | $p = m v$ | Not defined classically via mass |
| **Momentum (Quantum)** | $p = \hbar k = \frac{h}{\lambda}$ (De Broglie relation) | $p = \hbar k = \frac{h}{\lambda}$ |
| **Typical Energy Scale** | Can be accelerated to extremely high energies, e.g., up to **$100 \text{ kV}$** in a Scanning Electron Microscope (SEM). | Typically **$1 \text{ to } 3 \text{ eV}$** in the visible spectrum. |
| **Typical Wavelength Scale** | Extremely small (on the picometer scale at high acceleration voltages). | Center of the visible range is **$500 \text{ nm}$**. |

* **Quantum Mechanical Tunneling**:  
  The phenomenon of quantum tunneling (where an electron penetrates a classically forbidden potential barrier) has a direct wave analog in photonics, where electromagnetic waves tunnel through "forbidden regions" (evanescent wave coupling).

---

## 8. Common Misunderstandings

* **Misunderstanding 1: The refractive index of a material is a fixed, single-valued constant.**  
  * *Correction*: Many students assume glass simply has a refractive index of $1.5$. In reality, the refractive index is dispersive and varies with wavelength ($n(\lambda)$). A single number is only a local approximation.
  
* **Misunderstanding 2: The wave equation can only be derived for the electric field.**  
  * *Correction*: There are two parallel forms of the electromagnetic wave equation: one for the electric field $\mathbf{E}$ and another for the magnetic field $\mathbf{H}$. They share a similar mathematical form, and deriving the magnetic wave equation is an excellent exercise for students.

* **Misunderstanding 3: Susceptibility ($\chi$) is always a simple number (scalar).**  
  * *Correction*: This is only true in isotropic media. In anisotropic media (like calcite), susceptibility is a $3 \times 3$ matrix (tensor), meaning the induced polarization is not necessarily parallel to the applied electric field.

* **Misunderstanding 4: The Schrödinger equation and the electromagnetic wave equation have the same mathematical structure because they both describe waves.**  
  * *Correction*: While both are second-order in space (Laplacian), the Schrödinger equation is first-order in time ($\frac{\partial}{\partial t}$), whereas the electromagnetic wave equation is second-order in time ($\frac{\partial^2}{\partial t^2}$).

---

## 9. Key Takeaways

1. **The wave equation** is the essential mathematical tool used to solve for the electromagnetic response of nanophotonic systems.
2. In a **lossless dielectric medium**, the wave propagates with the same form as in vacuum, but is slowed down by the material's **refractive index** ($n = \sqrt{\epsilon_r} = \sqrt{1 + \chi}$).
3. The refractive index exhibits **dispersion** (wavelength dependence) and shows an **inverse relationship with the material's electronic band gap** ($E_g$).
4. **Electrons and photons** share profound wave-like behaviors, including wave equations, de Broglie momentum, and tunneling. However, they differ fundamentally in their dispersion relations (parabolic vs. linear) and the temporal order of their governing wave equations (first-order in time vs. second-order in time).

---

## 10. Exam/Research Perspective

### Crucial Equations to Memorize
* **Free Space Wave Equation**:
  $$\nabla^2 \mathbf{E} = \mu_0 \epsilon_0 \frac{\partial^2 \mathbf{E}}{\partial t^2}$$
* **Speed of Light in Vacuum**:
  $$c = \frac{1}{\sqrt{\mu_0 \epsilon_0}} \approx 3 \times 10^8 \text{ m/s}$$
* **Dielectric Wave Equation**:
  $$\nabla^2 \mathbf{E} = \mu_0 \epsilon_0 \epsilon_r \frac{\partial^2 \mathbf{E}}{\partial t^2}$$
* **Phase Velocity and Refractive Index**:
  $$v = \frac{c}{n}, \quad n = \sqrt{\epsilon_r} = \sqrt{1 + \chi}$$
* **Nonlinear Polarization Expansion**:
  $$\mathbf{P} = \epsilon_0 \left( \chi^{(1)} \mathbf{E} + \chi^{(2)} \mathbf{E}^2 + \chi^{(3)} \mathbf{E}^3 + \dots \right)$$
* **De Broglie Momentum**:
  $$p = \hbar k = \frac{h}{\lambda}$$

### Important Derivations for Exams
1. **Deriving the Electric Field Wave Equation**: Start with Maxwell's curl equations, apply the curl to Faraday's Law, substitute Ampère's Law and constitutive relations, apply the vector double-curl identity, and outline the exact physical assumptions required to set $\nabla \cdot \mathbf{E} = 0$.
2. **Deriving the Magnetic Field Wave Equation**: (Left as a standard student exercise/exam question). Follow the same steps as the electric field derivation, but start by taking the curl of Ampère's Law instead of Faraday's Law.

### Likely Conceptual Exam Questions
1. **Explain the physical conditions required to simplify the vector identity $\nabla \times (\nabla \times \mathbf{E}) = \nabla(\nabla \cdot \mathbf{E}) - \nabla^2 \mathbf{E}$ to $-\nabla^2 \mathbf{E}$ during the derivation of the wave equation.**  
   * *Answer*: You must assume there are no free charges in the medium ($\rho_f = 0$, meaning $\nabla \cdot \mathbf{D} = 0$) and that the permittivity $\epsilon$ does not vary significantly over the scale of the optical wavelength (allowing you to pull $\epsilon$ out of the divergence operator so that $\nabla \cdot \mathbf{E} \approx 0$).
2. **What is an anisotropic medium physically, and how does it modify the mathematical description of the electric susceptibility and polarization?**  
   * *Answer*: An anisotropic medium (such as calcite) is one in which the material response depends on the direction of the applied electric field. Mathematically, the electric susceptibility $\chi$ can no longer be treated as a simple scalar; it must be written as a $3\times3$ tensor (matrix $\chi_{ij}$), which couples different spatial components of the electric field to different spatial components of the induced polarization.
3. **Compare the physical properties of propagating photons in the visible spectrum with electrons in a Scanning Electron Microscope (SEM) across energy, wavelength, and dispersion relations.**  
   * *Answer*: Visible photons have low energies (1 to 3 eV) and relatively large wavelengths (~500 nm), whereas SEM electrons have very high energies (up to 100 kV) and extremely small de Broglie wavelengths. Photons exhibit a linear energy-momentum dispersion relation ($E \propto p$), whereas electrons exhibit a parabolic dispersion relation ($E = p^2/2m$).
4. **Compare the Schrödinger equation and the electromagnetic wave equation. What are their spatial and temporal orders?**  
   * *Answer*: Both equations are second-order in space (they employ the Laplacian operator $\nabla^2$ to describe spatial variation). However, the Schrödinger equation is a first-order partial differential equation with respect to time ($\frac{\partial}{\partial t}$), whereas the electromagnetic wave equation is second-order with respect to time ($\frac{\partial^2}{\partial t^2}$).