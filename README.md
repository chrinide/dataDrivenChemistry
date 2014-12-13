AC 209 Data Science Final project 
===================
<div style="text-align:center">
<img src="http://giant.gfycat.com/AridDarlingGuineapig.gif">
</div>
(Ab initio Molecular Dynamics of Molecules doing the Harlem Shake)

# Under Construction! 
# Contents
- [The Idea](#the-idea) 
- [Data](#data) 
- [Exploration Visualization](#exploration-visualization) 
- [Finding Patterns](#finding-patterns) 
- [Future Directions](#future-directions) 


# The Idea

Quantum chemistry is a branch of theoretical chemistry which applies quantum mechanics  to address problems in chemistry.

In Quantum Chemistry you can calculate a molecule on a computer, simulating and solving the Schrödinger equation to obtain molecular properties.
Chemoinformatics

An open question is: **How can we incorporate quantum effects/information into chemoinformatics?**
Recently in Ramakrishnan et Al. reported in Nature Scientific Data, ["Quantum chemistry structures and properties of 134 kilo molecules"](http://www.nature.com/articles/sdata201422) a data set 134k calculated molecules. 

# Data

Dataset is hosted on http://dx.doi.org/10.6084/m9.figshare.978904, it is a few hundred MB's.
I also have pandas dataframe pickle in my dropbox:
https://www.dropbox.com/sh/6iysi4w0xmmevlt/AABrTLUFZJvrJPDeDCzuhxJYa?dl=0

Results of each calculation has been embeded within a xyz file in a very specific way. The data provided by the article is not very user friendly ( see: http://www.ch.imperial.ac.uk/rzepa/blog/?p=12803), a better format would have been a json or excel database.

They reported computed geometric, energetic, electronic, and thermodynamic properties for 134k stable small organic molecules made up of CHONF atoms.
# Exploration Visualization
The variables to explore were:
* Size: Number of atoms, Molecular Weight, Spatial Extensivity.
* Rotation: Rotational Constants and Clases.
* Energetics: Internal energy, Enthalpy, Gibbs free energy, Zero Point Energy, Atomization Energies.
* Special Properties: Electronic Band Gap, Molar Heat Capacity, Dipole Moment and Polarizability

# Finding Patterns
I did explore matching molecules based on similarity. 
For example taking 1000 random molecules and checking out how similar they were (geometry/structure wise)



This goal, which is the most interesting was not met due to time constraints.
The main idea was:
* Search the most common functional groups, chemical substructures that contain key chemical functionality. For this purpose I wanted to use RDKit, but had problems running it. Tried to think how to formulate this with a Kmeans classifier.
* Create a labeling for each molecule based on a molecule having the substructure or not. This would create a membership of a molecule to within different clusters.
* Reduce dimentionality, maybe with a TruncatedSVD or finding the best features by ranking their importance via a random forest classifier.
* See if membership into a cluster would correspond to general differences in the molecular properties.
* Use SVM/Random Forest to create a classifier of molecular substructure based on molecular properties.


# Future Directions
There is certaintly much more work to be done and many venues to explore with data science and Quantum Chemistry.
For the msot part I stuck to the available dataset, yet I feel there could be more interesting data embedded in the calculations which is not included in the data set.
Examples:
* **Frequencies**, only frequencies were reported but amplitudes were not. Using amplitudes and frequencies together you could devise spectra features such as spectral centroids, brightness o cSpectrum.
* **Coulombic Matrix**, The matrix of electromagnetic interaction between different
molecules.
* **Orbital Occupation Numbers**, Occupation numbers for the electrons within the molecular orbitals.

The main idea would be design and find descriptor that can not be found in a classical way, to demonstrate that a quantum calculation has more conection to reality than a classical one. (at the molecular level).