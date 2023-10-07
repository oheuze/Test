# 
Téléchargement
git clone https://github.com/oheuze/CodeJulia

Installation
Décompresser le fichier Lagrange-1D.zip
cd Lagrange-1D
./install.sh
L’installation compile le code et exécute les cas-test :
    • Sod
    • Bizarrium
    • Impact Sn monophase
    • Impact Sn 3 phases (Hybride)
Les résultats sont dans les répertoires Test-Sod, Test-Bizarrium et Test-Impact-Sn .

Julia utilise les packages Dates et EzXML pour la lecture des données, et CSV, Plots et DataFrames pour le post-processing  (import Pkg;Pkg.add(« ## »)).
Lancement des cas
1) Cas simple
Se mettre dans un répertoire Test-*.
	julia
	nom= »acoustic »
	test= »Test-Sod »
	include(« ../Lag-1D.jl »)
	puis
	include(« ../PostProcessing.jl »)

2)Etude paramétrique : voir les fichiers « lanceur »

3) Cas détaillé :
	julia
	nom= »acoustic »
	test= »Test-Sod »
	include(« ../Init-Lag.jl »)
Arrivé à ce niveau (fin de l’initialisation), il est possible d’effectuer le calcul itération par itération, de calculer la solution analytique en Julia, ou d’effectuer des vérifications thermodynamiques :
	Iteration()
	focus()
On peut lancer le calcul jusqu’à la fin à tout moment :
	Run()
