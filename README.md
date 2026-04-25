# plateforme-agora.fr
plateforme pour commune et habitants 
# AGORA — Plateforme citoyenne pour communes françaises

> Application SaaS multi-tenant de participation citoyenne, conçue pour les communes françaises.

---

## Présentation

AGORA est une plateforme web permettant aux communes de proposer à leurs citoyens un espace numérique de proximité : actualités municipales, agenda, signalements, participation et vie locale.

Chaque commune dispose de son propre espace isolé, accessible via une URL unique :

```
plateforme-agora.fr?commune=nom-commune-INSEE
```

---

## Architecture

| Composant | Technologie |
|---|---|
| Frontend | HTML / CSS / JS — single file, zéro dépendance |
| Backend | Supabase (PostgreSQL + Auth + Storage) |
| Hébergement | Netlify (CD automatique depuis GitHub) |
| Paiements | Stripe (abonnements annuels) |
| Domaine | plateforme-agora.fr |

---

## Multi-tenant

Une seule application sert toutes les communes. L'isolation des données est garantie par :
- La détection du slug commune dans l'URL
- Le Row Level Security (RLS) de Supabase
- La vérification de licence active via la table `licences`

---

## Déploiement

Tout push sur la branche `main` déclenche un redéploiement automatique via Netlify.
Les mises à jour sont instantanément disponibles pour toutes les communes.

```
git add .
git commit -m "description de la mise à jour"
git push
```

---

## Structure du repo

```
plateforme-agora/
├── index.html       # Application complète
├── _redirects       # Routing Netlify
├── netlify.toml     # Configuration Netlify
└── README.md        # Ce fichier
```

---

## Tarifs

| Segment | Population | Tarif annuel |
|---|---|---|
| Hameau | < 500 hab. | 590 € |
| Village | 500 – 2 000 hab. | 990 € |
| Bourg | 2 000 – 5 000 hab. | 1 790 € |
| Ville | > 5 000 hab. | Sur devis |

---

## Contact

**Juicy Solutions** — [plateforme-agora.fr](https://plateforme-agora.fr)
