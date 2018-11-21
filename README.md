
# NASA JavaScript     ![alt text](https://www.nasa.gov/sites/all/themes/custom/nasatwo/images/nasa-logo.svg)
  Étant donné que la demande en logiciels Web augmente constamment et que des tâches plus critiques sont confiées à JavaScript, appliquons les directives de codage de la NASA aux applications JavaScript / HTML pour des performances, une fiabilité et un monde meilleur.

# Règles
  Ses règles ont été écrite par les ingénieur de la NASA pour des raisons d'efficacité et de bonne écriture de code JavaScript. Ce afin de coder plus safement les plateformes Web 
  ## Régle 1
   Aucune fonction ne doit être plus longue que ce qui peut être imprimé sur une seule feuille de papier
     ![alt text](https://media.makeameme.org/created/papers-papers-everywhere-89ovrp.jpg)
  
  ## Régle 2
  Limitez tout le code à des constructions de flux de contrôle très simples - n'utilisez pas d'instructions goto ni de récursion directe ou indirecte
  * Si vous voulez écrire du code fiable - déposez-en pour en écrire un qui soit cool et qui prévisible à la fois.
  * Définir le standard de codage et le suivre 
  * Utilisez l'analyse statique pour prendre en charge la norme et réduire les risques de défaillance : ESLint + Beaucoup de plugins, Preset
  * Collecter des matrices : [SonaQube](https://www.sonarqube.org/), [Scrutinizer](https://scrutinizer-ci.com/) , [Plato](https://github.com/es-analysis/plato)
  * Analyser les types : Flow / Closure Tools / Types
  
  ## Régle 3 : RESPECT RAM ! 
   GC pourrait devenir votre ennemi
   ### Mesure
   [DevTools]() / Timeline
   ### Comparer
   [DevTools]() / [Profile]() / [Takeheap snapshot]()
  ### Resume 
   * Gérez votre variable avec respect. Déclarez en haut de la portée pour augmenter la visibilité. ESLint vars-on-top. Trier pour la prévisibilité sort-vars
   *  Surveillez les liens mémoire, nettoyez les écouteurs et les variables lorsque vous n'en avez plus besoin .
   * ESLint no-unused-vars
   *  Basculer JavaScript en mode d'allocation de mémoire statique via le regroupement d'objets.
   
   ## Régle 4 : Mise en commun d'objets
   Pas de nouveaux objets au moment de l'exécution    
   ```javaScript
      const pool = createObjectPool(256);
      let object = pool.getObject();
      pool.releaseObject(object);
   ```
   ## Régle 5 : Faire de bons tests || Test Well
   La densité des assertions du code doit être en moyenne d'au moins deux assertions par fonction . 
    * Plus la densité de test est élevée, moins vous obtenez de défauts
    * La quantité minimale de test est 2 par fonctions .
    * Surveillez les anomalies dans l'état du système pendant l'exécution. Générer et gérer des erreurs en cas de pannes critiques.
    * Mesurer la couverture, mais attention, une couverture à 100% ne signifie pas nécessairement que vous avez un code bien testé.
    
  ## Règle 6 : Pas d'état partagé || No shared state ( [ESLint pureness plugin](https://github.com/rom-melnyk/eslint-plugin-pureness))
   L'objet des données doit être déclaré au niveau de portée le plus petit possible
   
  ## Règle 7
   La valeur de retour de la fonction non vide doit être vérifiée par chaque fonction appelante et la validité des paramètres doit être vérifiée à l'intérieur de chaque fonction.
   
  ## Règle 8 
   L'utilisation du pré-processeur doit être limitée à l'inclusion de fichiers d'en-tête. Gardez à l'esprit que le code que vous écrivez n'est pas le code que vous exécutez !  
![alt text](https://media.giphy.com/media/d3mlE7uhX8KFgEmY/giphy.gif)

Bon à savoir lorsque vous utilisez les performances des transpileurs des fonctionnalités de l’ES6 par rapport à celles de l’ES5.
  ## Règle 9 
 L'utilisation de pointeurs doit être spécifiquement restreinte. Un seul niveau de déréférencement est autorisé .   Les pointeurs sur les fonctions ne sont pas autorisés . Tou en sachant que JavaScript fonctionne de base avec les pointeurs.
 * Chaînes d'appel ( Niveau de référence )
 * [LoD](https://en.wikipedia.org/wiki/Level_of_detail) = Loose Compling
      ```javaScript
      Dog.body.legs.run();
            vs
      Dog.run();
   ```
 * Call chains
 ## Règle 10
 
  Tout le code doit être compilé le premier jour de développement, avec tous les avertissements du compilateur activés.  Ne stockez pas les avertissements, ne remettez pas à plus tard les correctifs, gardez le code propre et perfectionniste en vous.
  
  Si le code est au rouge ⚠️
   * Ne panique pas
   * Simplement, prioriser
   * Refactoriser et ajouter des tests pièce par pièce


 ### ...Petit pas pour les développeurs mais ... Grand pas pour que la plate-forme Web soit perçue comme fiable ♻️
 ![alt text](https://img.purch.com/w/660/aHR0cDovL3d3dy5zcGFjZS5jb20vaW1hZ2VzL2kvMDAwLzA3Ny85NDgvb3JpZ2luYWwvbW9vbi1sYW5kaW5nLmpwZw==)
 
 ## Conclusion
  En regardant la conférence je me suis rendu compte du niveau existant de l'automatisation, de la testabilité et d’infrastructure de projets et de code, la quantité de meilleures pratiques établies tirée de langages matures et la masse de connaissances que nous avons déjà sur le développement Web sont étonnantes. Mais quand même… C'est un long chemin à parcourir pour nous et beaucoup de défis à relever.
