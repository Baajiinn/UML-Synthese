Diagramme de cas d'utilisation
==============================

## Cas d'utilisation

> **Acteur** = entité ui interagit avec le système
> - personne, chose, logiciel
> - Représente un rôle (ou plusieurs possible)
> - Identifié par le nom du rôle
    
> **Cas d'utilisation** = Fonctionnalité visible de l'extérieur
> - action déclenché par système : n'a pas de "propre volonté", se déclenche par un acteur
> - identifié par une action (! VERBE A L'INFINITIF !) (!! ENTOURER !!)


## Diagramme

> **Limite du système** = l'encadré regroupant les cas d'utilisation ( pas les acteurs )
>
> **Nom du système** : en haut à gauche
>
> **Acteur** : représenté par un petit bonhomme
>
> **Association** = Relation entre acteurs et cas d'utilisation
>
> **Héritage**:
> - Flèche : vide intérieur
> - Parent : pointe / Enfant(s) : début
>
> <font color=#00FF00>Eviter plusieurs associations sur le même cas d'utilisation</font>
> <font color=#00FF00>Possibilité d'utiliser l'héritage entre des cas d'utilisations</font>
>
> ### Relation entre cqs d'utilisation
>
> **Extend** = cas d'utilisation pouvant être déclenché ( X est optionnel pour Y)
>> - Flèche : ligne discontinue, pointe noire
>> - X : début / Y : pointe
>> - "extends" marqué à côté de la flèche
>
> **Includes** = scenario de Y declanche par scenarion de X 
>> <font color=#FF0000>Utiliser seulement si scénario commun à plusieurs cas</font>
>> - Flèche : ligne discontinue, pointe noire
>> - X : début / Y : pointe
>> - "includes" marqué à côté de la flèche



Diagramme de séquence
=====================

Représentation graphique de la chronologie des échanges de messages entre acteurs et le système.
Les messages sont représentés horizontalement.

# Type de messages
> **message synchrone** : Emetteur bloqué en attente du retour, exécution bloquée
> **message asynchrone** : Emetteur non bloqué, continue son exécution (processus évoluant en parallèle)


## Diagramme

> <font color=#FF0000>Pour nommer un acteur, ex: {Nom:Client}</font>
> <font color=#FF0000>Pour nommer un système, ex: {:NomSystème}</font>

> Nom des messages lies aux cas d'utilisation (se trouve sur la ligne du message)
> **ligne de vie** : repesente verticalement
> **commentaire** : rectangle avec coin inferieur droit plie, relie avec uniquement pointie
> **message** : ligne continue noire
> **message de retour** : ligne discontinue noire
> **message synchrone** : ligne noire fermée
> **message asynchrone** : fléche ouverte
> **alternative** : encadré partie du système comme un commentaire, {alt}, Condition à l'envoie d'un message
> **boucle** : encadré partie du système comme un commentaire, {loop(variable)}
> **boucle** : encadré partie du système comme un commentaire, {réf}, fait référence à un autre diagramme (pas forcément diagramme de séquence)



Diagramme de classe
===================

Représentation de la structure interne du logiciel

## Diagramme d'objet 

> Représentation de l'état du logiciel 

> Diagramme évoluant avec l'exécution du logiciel
>> - création et suppression d'objets
>> - modification de l'état des objets (valeurs des atributs)
>> - modification des relations entre objets


## Objets et classes

**Objet** = entité concrète ou abstraite qui découle de l'instanciation d'une classe
- identité = adresse mémoire
- état = attributs
- comportement = opérations

**Classe** = Regroupement d'objets de même nature
<font color=#FF0000>Ne pas confondre avec une méthode = implémentation de l'opération</font>


## Hiérarchie de classes

**spécialisation** = raffinement d'une classe en  une sous-clase
**généralisation** = abstraction d'un ensemble de classes en super-classe

**Classe abstraite** = classe sans instance, seulement base pour classes héritées


## Relation

**Aggrégation** = relation composite-composante
- Le composite fait référence à ses composants
- La création ou la destruction du composite est indépendante de la création ou destruction de ses composants
- <font color=#FF0000>Un objet peut faire partie de plusieurs composites à la fois</font>
- Ex: Supprimer la liste de lecture ne supprime pas les morceaux

**Composition** = relation composite-composante
- Le composite contient ses composants
- La création ou destruction du composite entraîne la création ou destruction de ses composants
- <font color=#FF0000>Un objet ne fait partie que d'un composite à la fois</font>




## Diagramme
> **Objets**:
> - {Nom : Class} (Le tout souligné)
> - {attribut = valeur}
> - {méthode(args* : type() )}

> **Classe**:
> - {Nom}
> - {attribut : type() }
> - {méthode(args* : type() )} \ {méthode() : type() }

> **Classe abstraite**:
> - {Nom} (italique ou précédé de "abstract")
> - {attribut : type() }
> - {méthode(args* : type() )} \ {méthode() : type() }

> **Relation**:
> - **Multiplicité** : Contraint le nombre d'objets liés par l'association 
>> - {n} : exactement n
>> - {n,m,p} : exactement n,m,p
>> - {n..m} : entre n et m / ex: {0..1}, Au plus 1 (O ou 1)
>> - {n..*} : au moins n
>> - {*} : plusieurs (0 ou plus)
>
> - **Agrégation** :
>> - losange blanc
>> - composite : losange / composant(s) : ligne
>
> - **Compostition** :
>> - losange noir
>> - composite : losange / composant(s)  : ligne