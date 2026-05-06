# AGORA — Plateforme citoyenne pour communes françaises

> Application SaaS multi-tenant de participation citoyenne, conçue pour les communes françaises.

---

## Présentation

AGORA est une plateforme web permettant aux communes de proposer à leurs citoyens un espace numérique de proximité : actualités municipales, agenda, signalements, participation et vie locale.

Chaque commune dispose de son propre espace isolé, accessible via une URL unique :

```
plateforme-agora.fr/app.html?commune=nom-commune-INSEE
```

---

## Architecture

| Composant | Technologie |
|---|---|
| Frontend | HTML / CSS / JS — single file, zéro dépendance |
| Backend | Supabase (PostgreSQL + Auth + Storage) |
| Hébergement | Cloudflare Pages (déploiement manuel) |
| Paiements | Stripe (abonnements annuels) |
| Domaine | plateforme-agora.fr (en cours de propagation) |

---

## Multi-tenant

Une seule application sert toutes les communes. L'isolation des données est garantie par :
- La détection du slug commune dans l'URL (`?commune=slug-insee`)
- Le Row Level Security (RLS) de Supabase
- La vérification de licence active via la table `licences`

---

## URLs

| Page | URL |
|---|---|
| Landing page | `plateforme-agora.fr` |
| App citoyenne | `plateforme-agora.fr/app.html?commune=slug-insee` |
| Back-office | `plateforme-agora.fr/admin.html` |

---

## Structure du repo

```
plateforme-agora/
├── index.html       # Landing page commerciale
├── app.html         # Application AGORA (multi-tenant)
├── admin.html       # Back-office Juicy Solutions
├── _redirects       # Routing Cloudflare Pages
└── README.md        # Ce fichier
```

---

## Tarifs

| Segment | Population | Tarif annuel HT |
|---|---|---|
| Hameau | < 500 hab. | 590 € |
| Village | 500 – 2 000 hab. | 990 € |
| Bourg | 2 000 – 5 000 hab. | 1 790 € |
| Ville | > 5 000 hab. | Sur devis |

TVA non applicable — article 293 B du CGI

---

## Contact

**Juicy Solutions · Léandre Sallé**  
[plateforme-agora.fr](https://plateforme-agora.fr) · juicy.agency.formation@gmail.com
