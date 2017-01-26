# Travailler avec nous ?

## ce que vous devez connaitre et appliquer

### ruby

1. rubocop
1. les regles de Sandi Metz.
1. reek
1. coverage élevé unitaire et intégration
1. et bien d'autre ...

### Slim

par défaut

https://github.com/sds/slim-lint/blob/master/lib/slim_lint/linter/README.md

1. Les attriubuttes sont entre parenthèse uniquement (pas de 'curlybrace' ou 'squarebrace').
1. Un attribue par ligne et les '=' sont aligner verticalement 
1. Un fichier ne fait pas plus de 100 lignes (idéalement un partial fait ~58 lignes).

__good__


```slim
.lala(
  att1     = "toto"
  att_no_2 = "tata"
  )
  .lili(
    att_3 = "tutu"
  )
  / la parenthèse fermante peut etre au choix sur le niveau des attributs ou sa balise
 ```
 
 __bad__
 
 ```slim
 .lala{ att2 = "toto" att_no_2="tata"}
   .lili[att_3="tutu"]
 ```
 
 ### CoffeeScript
 
 1. Un fichier ne fait pas plus de 100 ligne
 1. Une fonction fait max 5 ligne
 1. Toute parenthèse qui peut etre optionel ce doit d'etre supprimer.
 1. les variable on un sens explicite (pas d'abréviation, pas de nom de moins de 3 lettre)
 
 ne faisons que peut de coffee mais si ça change on utilisera ça
 http://www.coffeelint.org/
 
 
 
 
 ## Vim/Tmux
 
 avec un nombre concéquent de plugin
 vous devez etre capable de faire du paire programming
 avec chacun des membre de la team.
 
 
