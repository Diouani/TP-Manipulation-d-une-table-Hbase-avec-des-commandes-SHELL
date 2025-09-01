# TP HBase - Manipulation de table avec commandes Shell

## Connexion au shell HBase
```bash
hbase shell
```

## 1. Création de la table
```hbase
create 'users', 'info', 'contact'
```

## 2. Insertion du premier utilisateur (user1)
```hbase
put 'users', 'user1', 'info:prenom', 'ahmed'
put 'users', 'user1', 'info:nom', 'tazi'
put 'users', 'user1', 'contact:email', 'aahmed.tazi@example.com'
put 'users', 'user1', 'contact:phone', '0102030405'
```

## 3. Insertion du second utilisateur (user2)
```hbase
put 'users', 'user2', 'info:prenom', 'asmae'
put 'users', 'user2', 'info:nom', 'karimi'
put 'users', 'user2', 'contact:email', 'asmae.karimi@hotmail.com'
put 'users', 'user2', 'contact:phone', '0607080910'
```

## 4. Récupération d'une ligne
```hbase
get 'users', 'user1'
```

## 5. Scan complet de la table
```hbase
scan 'users'
```

## 6. Mise à jour d'une donnée
```hbase
put 'users', 'user2', 'contact:email', 'asmae.karimi@gmail.com'
```

## 7. Suppression d'une colonne
```hbase
delete 'users', 'user1', 'contact:phone'
```

## 8. Suppression complète d'une ligne
```hbase
deleteall 'users', 'user2'
```

## 9. Ajout d'une nouvelle colonne
```hbase
put 'users', 'user1', 'contact:fax', '0123456789'
```

## 10. Scan avec plage de clés
```hbase
scan 'users', {STARTROW => 'user1', ENDROW => 'user3'}
```

## 11. Comptage des lignes
```hbase
count 'users'
```

## 12. Description de la table
```hbase
describe 'users'
```

## Commandes de nettoyage
```hbase
disable 'users'
drop 'users'
exit
```
