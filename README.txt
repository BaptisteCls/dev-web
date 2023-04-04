-----------------------------------
Compilation:
Ligne compilation html :pandoc --toc --toc-depth=3 --standalone Cours.md -o Cours.html -c ..\pandoc.css --metadata title="Cours"
Ligne compilation pdf :pandoc --toc --toc-depth=3 --standalone Cours.md -o Cours.pdf --metadata title="Cours"

Explication des options :
--toc = Génere une table des matières en haut du rapport
--toc-depth = Definie la taille de la table des matières
--standalone = Permet le fonctionnemant de certaines options
Rapport.md = Fichier d'entrée
-o sortie = Fichier de sortie
-c css = Css utilisé pour l'html
--metadata title = Titre du rapport

-----------------------------------