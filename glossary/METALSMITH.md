# Metalsmith

[Metalsmith](http://metalsmith.io/) est une abstraction pour manipuler un répertoire de fichiers. Pour dire les choses simplement, il s'agit d'un générateur de site statique.

Metalsmith, de base, prend les fichiers dans un répertoire source, effectue des opérations sur ces fichiers par l'intermédiaire de plug-ins et écrit ces fichiers dans un répertoire de destination. Les plug-ins peuvent pratiquement tout faire : créer de nouveaux fichiers, filtrer les fichiers, modifier des fichiers basé sur une certaine logique, etc (notez que cela signifie que l'ordre de plug-in fait affaire; les transformations effectuées par un plug-in peuvent être vus et utilisées par les plug-ins suivants, rendant le processus d'un pipeline de construction modulaire). L'ensemble de l'éco-système de plug-ins est ce qui rend Metalsmith si flexible.


