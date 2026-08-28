# Alerte Pellet — Dashboard

Dashboard public du projet **Alerte Pellet** pour le suivi des stocks, prix et réapprovisionnements de granulés de bois.

**Powered by JeyZee**

## Validation UI

### 28 août 2026 — Logos magasins validés

Les logos affichés sur les cartes magasins du dashboard sont validés pour :

- Auchan Englos
- Bricorama Loos
- Castorama Englos
- Chronodrive Hallennes-lez-Haubourdin

Les assets locaux utilisés sont stockés dans `assets/store-logos/`.

### 28 août 2026 — Compte à rebours prochaine mise à jour validé

Le dashboard affiche désormais un compte à rebours dynamique jusqu'au prochain cycle réel de surveillance.

L'échéance provient directement du timer systemd du nœud Debian (`alerte-pellet.timer`) et respecte la cadence de production réelle de 10 à 30 minutes après la fin du cycle précédent. Le compteur n'utilise donc aucune durée fixe estimée.

Le post-cycle Debian publie automatiquement la prochaine échéance dans `data/system-state.json`, puis le dashboard est mis à jour et republié.
