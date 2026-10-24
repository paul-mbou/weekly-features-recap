# Humanize guide — weekly recaps for non-devs

## Voice

Write like a **product lead briefing a PM over coffee**, not like a commit log.

| Do | Don't |
|----|-------|
| "Les utilisateurs peuvent filtrer leurs événements passés" | "`PublicEventFeedTimeFilter.past` appliqué dans `event_list_screen`" |
| "Les rappels de tâches arrivent en français" | "`task_notification_messages.dart` + `normalizeTaskNotificationLanguageCode`" |
| "Le logo et l'écran de démarrage ont été modernisés" | "Refactor splash + adaptive icons mipmap-anydpi-v26" |

**Tone:** confident, clear, slightly warm. Not corporate fluff, not meme-y.

**Sentence length:** aim for ≤ 20 words. One idea per bullet.

**Verbs:** prefer concrete outcomes — *ajouté, corrigé, amélioré, préparé, simplifié*.

## Glossary — translate or drop

| Dev term | Say instead (FR) |
|----------|------------------|
| refactor | *(omit unless it fixes something visible)* |
| widget / component | écran, bouton, section, carte |
| provider / state | *(omit)* |
| i18n / localization | traduction / multilingue |
| debounce | recherche plus fluide (sans lag à chaque lettre) |
| `@Preview` | aperçu rapide pour l'équipe design |
| hot restart | *(omit)* |
| merge / PR | *(omit unless audience is eng)* |
| API / endpoint | connexion au serveur / back-end *(only if user-facing)* |
| commit | *(omit — say "livré" or "prêt localement")* |

## Structure each bullet

Use: **What changed** → **Who benefits** → *(optional)* **Status**

Examples:
- **Événements enregistrés** — Retirer un favori met à jour la liste tout de suite. *Corrigé.*
- **Onglets événements** — Parcourir À venir, Enregistrés, Mes événements et Passés. *Prêt, en attente de publication.*
- **Profil prestataire** — Les visiteurs voient « Réserver ce prestataire ». *Bouton visible ; action à brancher.*

## Status labels (pick one)

- **Livré** — merged / in production
- **Prêt** — done locally or in branch, not yet released
- **En cours** — partially done
- **Prévu** — discussed, not started

Be explicit when work is **not committed** or **not released**.

## Anti-patterns

1. **Inventory of files** — never list 10+ paths  
2. **Stack of frameworks** — no Riverpod, Flutter, Dart in Recap  
3. **False precision** — "+3944 −5124 lines" means nothing to a PM  
4. **Everything is equally important** — lead with top 3 user impacts  
5. **Passive mush** — "des améliorations ont été apportées" → say what improved  
6. **Duplicate sections** — Recap = story; Standup = sync; Changelog = release notes  

## Recap opening line

Start with one sentence that captures the week's theme:

> Cette semaine, IDO a surtout avancé sur **l'expérience événements** et **la clarté de l'app** (navigation, notifications, identité visuelle).

Then bullets. End with a single **À noter** if uncommitted work exists.

## Standup rules

- **Fait** — past tense, outcomes only, max 5 bullets  
- **En cours** — present, max 3 bullets  
- **Blocages** — honest, max 2; write "Aucun" if true  
- **Priorités** — next week, max 3, actionable for PM (not "fix lint")

## Changelog rules

User-facing categories only:

- **Ajouté** — new capability someone can try  
- **Modifié** — behavior or UI changed  
- **Corrigé** — bug users noticed  

Skip **Removed** unless users lose something they used.

## Length budget

| Section | Target |
|---------|--------|
| Recap | 150–250 words |
| Standup | 80–120 words |
| Changelog | 6–12 bullets total |

If the week was quiet, say so in one line — don't pad.
