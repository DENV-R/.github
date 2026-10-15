# DENV-R

**Le cloud souverain qui se dessine.** Une console qui cartographie votre système d'information,
le pilote et le déploie, chez nous ou chez vous. Pensée pour le DSI, le développeur, et celui qui
n'y connaît rien. Hébergée en France, à Nantes.

## Ce que la console fait

- **Stocker** : des espaces de stockage S3 compatibles avec vos outils (Veeam, rclone, Kopia,
  Nextcloud…), avec versions, verrouillage WORM et règles de rétention et de souveraineté.
- **Calculer** : un espace sur notre socle mutualisé en dix minutes, réseau privé, cluster
  Kubernetes de trois nœuds ou machines nues, ports publiés et noms de domaine avec certificats.
- **Composer** : dites ce que vous voulez faire (« sauvegarder mes serveurs », « gérer les mots de
  passe de mon équipe », « un drive pour mon entreprise »…), la console assemble les briques,
  les déploie chez nous ou vous remet le plan `docker-compose` à emporter.
- **Cartographier** : vos stockages chez nous et ailleurs, vos machines, vos clusters, sur une
  seule carte, avec l'état de santé, les coûts et la classification des données.
- **Emporter** : tout ce que votre compte possède s'exporte en Terraform, avec le script
  d'import. Votre SI est à vous, en code.

Une partie de notre infrastructure tourne sur un data center flottant, refroidi par l'eau du
fleuve, sans prélèvement d'eau douce.

## Les outils, ouverts et à parité avec la console

| Outil | Installation | Dépôt / documentation |
|---|---|---|
| Provider Terraform | `source = "denv-r/denvr"` ou `source = "console.denv-r.com/denvr/denvr"` | [terraform-provider-denvr](https://github.com/DENV-R/terraform-provider-denvr) · [registre HashiCorp](https://registry.terraform.io/providers/DENV-R/denvr) |
| Ligne de commande | `pip install denv-r-cli`, commande `denv-r` | [PyPI](https://pypi.org/project/denv-r-cli/) |
| API REST | jeton depuis *Profil → API* | [documentation](https://console.denv-r.com/api/docs/) |
| Télémétrie | `/metrics` au format OpenMetrics | pour Grafana, Zabbix, Prometheus |

```hcl
resource "denvr_espace" "prod" {
  code   = "acme"
  taille = "S"   # réseau privé + cluster Kubernetes de 3 nœuds, prêt en ~10 min
}
```

Ce que nos outils disent franchement : ils demandent, suivent et rendent compte ; aucun d'eux ne
détient de pouvoir de destruction sur le socle, c'est voulu. Chaque refus revient avec sa raison.

## Contact

- Site : [www.denv-r.com](https://www.denv-r.com)
- Console : [console.denv-r.com](https://console.denv-r.com)
- État du service : [console.denv-r.com/etat](https://console.denv-r.com/etat/)
- Support : support@denv-r.com
