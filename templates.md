# Output templates

Replace bracketed placeholders. Delete sections that don't apply.

---

## 1. Récap (PM / stakeholder)

```markdown
# Bilan semaine — [Nom du projet]
*[Dates : du JJ/MM au JJ/MM]*

[Une phrase : thème de la semaine en langage simple.]

## Ce qui a avancé

- **[Zone produit]** — [Ce que l'utilisateur voit ou peut faire]. *[Statut : Livré | Prêt | En cours].*
- **[Zone produit]** — […]. *[Statut].*
- *(max ~8 bullets ; les 3 premiers = impact le plus fort)*

## Prochaines étapes suggérées

1. [Action compréhensible par un PM]
2. […]
3. *(max 3)*

## À noter

- [Ex. travail non commité, fonctionnalité visible mais inactive, dépendance équipe/back-end]
- *(Omettre cette section si rien d'important)*
```

---

## 2. Standup

```markdown
## Standup — [Projet] — Semaine du [date]

**Fait**
- [Résultat 1]
- [Résultat 2]
- *(max 5)*

**En cours**
- [Item 1]
- *(max 3)*

**Blocages**
- [Blocage] — ou — *Aucun*

**Priorités semaine prochaine**
1. [Priorité PM-friendly]
2. […]
```

---

## 3. Changelog (user-facing)

```markdown
## Changelog — [Projet] — [Période]

### Ajouté
- [Capacité nouvelle, vue utilisateur]

### Modifié
- [Comportement ou écran changé]

### Corrigé
- [Bug que les utilisateurs pouvaient rencontrer]

*(Pas de section "Technique" sauf demande explicite.)*
```

---

## Optional — English variant

Same structure; replace headings:

- Recap → **Weekly summary**
- Ce qui a avancé → **What moved forward**
- Standup sections → **Done / In progress / Blockers / Next priorities**
- Changelog → **Added / Changed / Fixed**
