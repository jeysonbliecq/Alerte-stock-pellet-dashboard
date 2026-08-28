# Alerte Pellet — Dashboard

Dashboard public du projet **Alerte Pellet** pour le suivi des stocks, prix et réapprovisionnements de granulés de bois.

**Powered by JeyZee**

## Validation UI

### 28 août 2026 — Validation globale du bloc dashboard

Le bloc d'améliorations UI actuellement déployé est validé dans son ensemble :

- logos magasins locaux ;
- compte à rebours réel jusqu'au prochain cycle Debian ;
- photos produits locales optimisées ;
- affichage validé sur le dashboard public.

Ces éléments deviennent la base de référence pour les prochaines évolutions du dashboard.

### 28 août 2026 — Logos magasins validés

Les logos affichés sur les cartes magasins du dashboard sont validés pour :

- Auchan Englos
- Bricorama Loos
- Castorama Englos
- Chronodrive Hallennes-lez-Haubourdin

Les assets locaux utilisés sont stockés dans `assets/store-logos/`.

**Correction Chronodrive validée le 28 août 2026 :** le `C` du logo Chronodrive affiché sur le dashboard utilise désormais le vert Chronodrive, en remplacement de l'ancienne version blanche. Ce rendu devient la référence visuelle officielle pour Chronodrive dans Alerte Pellet.

### 28 août 2026 — Compte à rebours prochaine mise à jour validé

Le dashboard affiche désormais un compte à rebours dynamique jusqu'au prochain cycle réel de surveillance.

L'échéance provient directement du timer systemd du nœud Debian (`alerte-pellet.timer`) et respecte la cadence de production réelle de 10 à 30 minutes après la fin du cycle précédent. Le compteur n'utilise donc aucune durée fixe estimée.

Le post-cycle Debian publie automatiquement la prochaine échéance dans `data/system-state.json`, puis le dashboard est mis à jour et republié.

### 28 août 2026 — Photos produits validées

Les fiches produits du dashboard affichent désormais une photo locale optimisée, chargée en différé (`loading="lazy"`) afin de limiter l'impact sur les performances, notamment sur mobile.

Les photos sont stockées localement dans `assets/product-images/` et ne dépendent pas d'un hotlink externe au moment de l'affichage.

## Règles permanentes d'ajout

À partir de cette validation :

- **chaque nouvelle enseigne ajoutée doit obligatoirement être accompagnée de son logo local** dans `assets/store-logos/` et intégrée au dashboard ;
- **chaque nouveau produit ajouté doit obligatoirement être accompagné de sa photo produit locale** dans `assets/product-images/` et intégrée à sa fiche dashboard ;
- les images doivent rester optimisées et adaptées à un affichage léger sur mobile et ordinateur ;
- toute modification validée du dashboard entraîne une mise à jour de ce README.
