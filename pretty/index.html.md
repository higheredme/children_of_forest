# Format de fichier
Respecter les linters et préconisation de HEM ci-dessous.

## Style guide slim


1. Les parenthèses sont l'unique délimiteur d'attribut
1. Un seul attribut par ligne
1. les = sont alignés
1. tout texte ou code ruby ce doit d'être sur sa propre ligne ou précédé d'une paranthèse fermante
1. la casse est en underscore case pour tout (sauf la partie school à cause de bootstrap, la partie bourbon utilise elle l'underscore case pour tout (nom de fichier, nom de class, nom de variable)
1. L'extention de fichier est .html.slim ( .html.md est une option autorisée )

  ```slim
    / GOOD
    .class_name(
      attribute   = 'val'
      attribute_2 = 'val_2'
    )

    / BAD
    .class-name{attribute = 'val' attribute-2 = 'val-2'}

    / GOOD
    .class_name
      = # ruby code

    / BAD
    .class_name = # ruby code

    / GOOD
    .class_name
      h1
        | text lorem and title

    / GOOD
    .class_name
      p
        |
          text lorem and title
          text lorem and title
          text lorem and title
    / BAD
    .class_name = # ruby code
    .class_name too long mono line blabla.....

   ```
   
   Pour des raisons d'usabilité et de facilitation de la traduction, il est préférable d'utiliser les balises HTML reconnues comme 'em' plutôt que de créer des span et des class css

```slim
    / GOOD
    em emphazie text
    span body tex

    / can be GOOD with class container
    .text_with_emphazie
      em emphazie text
      span body tex


    / BAD
    span.emphazie_class text
    span.body_class text
   
   ```
   
   Deux raisons à ce choix:
   1. l'accesibilité 
   2. les facilités de traduction.
   
   Exemple pour les traductions. Un traducteur peut faire: 
   ```
    "text espagnol<em>espagnol emphazie</em> text"
    ou
    "<em>emphaze française</em> text français"
   ```
   ce qui se traduit au final dans l'app par:
   
   ```slim
    / GOOD after I18n translation process
    .text_with_emphazie
      = t "translation.path.for.text_html"
   ```
   
   à ces fins, nous autorisons et encourageons l'usage de la totalité des 
   [balises inline](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)
   telles que: b, q, em, small, strong et autre


# Intégration à même notre app

1. NDA de protection de notre code et nos process
1. pull request avec git-flow
1. nom des branches en underscore uniquement
1. commit n'excédant pas la quinzaine de fichiers
1. management des assets avec notre architecture

## assets respecter notre archi

1. composition minimale des assets par layout
1. layout et asset students orientés low web


# présentation des style guides
Utiliser et étendre notre style guide.

Pour plus de documentation.
De bons exemples valent mieux que de longs discours
https://blog.hubspot.com/marketing/examples-brand-style-guides#sm.000zwpfsr1019f8trrt2ow59gve6e

http://styleguides.io/examples.html

https://github.com/devnacho/mountain_view

https://github.com/livingstyleguide/livingstyleguide

## Orientation souhaitée

### Approche par composition

[référence atomic-web-design](http://bradfrost.com/blog/post/atomic-web-design/)


tout élément dans le style guide doit:


être référencé comme un atome ou component:
cela inclut couleur, image, typo, ou tout autre type d'asset atomique
avoir un exemple de combinaison *et/ou* intégration dans des pages de démo.

chaque page de démo et visible en stand-alone,

et aussi en galerie mobile (à travers une iframe pointant dans la vu stand-alone)
La structure de fichier pour cela est déjà existante et peut-etre étendue dans le meme esprit.

### Mobile First

Le design de nouveau composant et de page doit être prioritisé dans sa version mobile.
Si un livrable est effectué en version desktop uniquement celui-ci sera rejeté.

#### motivation et lecture

[pro vs cons](https://codemyviews.com/blog/mobilefirst)

[doc](http://www.uxmatters.com/mt/archives/2012/03/mobile-first-what-does-it-mean.php)

[le Mr à l'origine de tout le tralala](http://www.lukew.com/resources/mobile_first.asp)




# mise à jour

Après chaque livrable intermédiaire le code ruby injecté par les dev
ne dois pas être supprimé brutalement :

Toute modification impactant les données et/ou texte de traduction (ajout/suppression)
doit être notifié dans les commentaires de pull request.

Note: cela permet en gestion de projet de demander aux dev/traducteur à leur tour de faire des mise à jours.

## évolution majeur de composant

Au lieu de modifier un composant, dupliquer et faire un nouveau composant voir plusieurs propositions du composant

exemple

```
    components/coponent_x_v2_pr_1.html.slim

    components/coponent_x_v3_pr_1.html.slim
    components/coponent_x_v3_pr_2.html.slim
```

## processus de livraison

1. Chaque livraison se fait par Pull request sur notre Github
1. Chaque Pull request ne peut excéder 15 fichiers
1. Chaque Pull request doit avoir une séance de relecture par au moins un membre de HigherEdME
1. Des demandes de modification (Mise en conformité) peuvent être effectuées par HigherEdMe
1. Une livraison est considérée effectuée lorsqu'il n'y a plus de demande de modification et que la Pull request a été mergé par HigherEdMe
1. HigherEdMe s'autorise jusqu'à 24heures (hors week-end) pour valider ou commenter une Pull Request
1. Plusieurs Pull Requests peuvent être effectuées en parallèle si leur code est suffisement indépendant



