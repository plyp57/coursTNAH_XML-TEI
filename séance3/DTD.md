# Séance 3 : Spécifications XML 

Les spécifications XML définissent un modèle pour les documents XML qui réglemente l’imbrication des balises, les noms d’éléments autorisés, la façon dont les attributs sont rattachés aux éléments.

Les documents XML qui respectent, en plus de la syntaxe XML, les règles d’un modèle de document sont dits **valides**.

----

## La syntaxe DTD

### Déclaration d’un élément : 
`<!ELEMENT nom_element (contenu)>`
- modèle de contenu :
		- `#PCDATA` : données textuelles
		- `EMPTY`
		- `ANY`
----

### Déclaration d’un sous-élément : 
`<!ELEMENT nom_element (nom_sousElement)>`
- Déclaration d’une séquence de sous-éléments : `<!ELEMENT nom_element (nom_sousElement1, nom_sousElement2)>` *Attention : l’ordre de déclaration des sous-éléments est signifiant.*
	- Nombre d’éléments autorisés :
		* `?` zéro ou un ;
       * `*` zéro ou plusieurs éléments ;
       * `+` un ou plusieurs éléments.

----       
       
### Déclaration des attributs : 
- `<!ATTlist nom_element nom_attribut	type_Données	usage_Attribut>`
	- Les types de données d’attributs :
		* `CDATA` n’importe quelle chaîne de caractère ;
		* `ID` doit contenir une valeur unique dans le document XML. Un seul attribut de ce type par élément est accepté.
		* `IDREF` fait référence à un attribut de type ID d’un élément du document. Les attributs Idref sont généralement utilisés pour établir des relations entre les éléments.
	
    - Les usages d’attributs: 
		* `#IMPLIED` optionnel ;
       * `#REQUIRED` obligatoire ;
       * `#FIXED` à valeur fixe.
----
## Déclarer sa DTD dans son document XML

- DTD interne : `<!DOCTYPE texte [<!ELEMENT nom_element (contenu)>]>`
- DTD externe (à déclarer avant l’élément racine) : 
`<!DOCTYPE texte SYSTEM "nomDTD.dtd">`       