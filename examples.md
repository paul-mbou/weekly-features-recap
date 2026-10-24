# Examples — technical → PM-friendly

## Example 1 — Events tabs

**Before (too technical)**
```
- Added PublicEventFeedTimeFilter enum (all, upcoming, past)
- event_list_screen switch: 0=upcoming, 1=bookmarked, 2=owned, 3=past
- _OwnedManagedEventsTab uses eventProvider + EventCard
- Added upcomingEvents, pastEvents to app_strings.dart
```

**After (Recap bullet)**
```
- **Liste d'événements** — Quatre onglets clairs : À venir, Enregistrés, Mes événements, Passés. Chaque onglet affiche le bon contenu selon la date et le rôle de l'utilisateur. *Prêt.*
```

---

## Example 2 — Bookmark bug

**Before**
```
- PublicEventBookmarkButton: use _isBookmarked for color, added onBookmarkChanged
- _BookmarkedPublicEventsTab removes item from _events on unbookmark
```

**After**
```
- **Favoris événements** — Quand on retire un événement des enregistrés, il disparaît immédiatement de la liste et l'icône se met à jour. *Corrigé.*
```

---

## Example 3 — Notifications

**Before**
```
- Created task_notification_messages.dart
- scheduleTaskNotifications(eventTitle, languageCode)
- BigTextStyleInformation htmlFormatContentTitle for bold event title
```

**After**
```
- **Rappels de tâches** — Notifications entièrement traduites (FR/EN/ES/AR), avec le nom de l'événement mis en avant et le détail de la tâche en dessous. *Prêt — replanifier en ouvrant la liste des tâches.*
```

---

## Example 4 — Internal refactor (omit from Recap)

**Before**
```
- Refactored public_event_detail_screen: 15 new StatelessWidget classes
- Removed _build* helpers per widget-class-not-functions rule
```

**After (Standup → En cours, one line, or "Travail interne")**
```
- Travail interne : simplification du code écran détail événement (aucun changement visible pour l'utilisateur).
```

---

## Example 5 — Full Recap opening (IDO-style week)

```markdown
# Bilan semaine — IDO

Cette semaine, l'effort s'est concentré sur **les événements**, **les prestataires** et **le polish de l'app** (logo, rappels, navigation).

## Ce qui a avancé

- **Identité visuelle** — Nouveau logo et écran de lancement sur mobile. *Prêt, non publié.*
- **Navigation événements** — Onglets À venir / Enregistrés / Mes événements / Passés avec le bon contenu dans chaque vue. *Prêt.*
- **Favoris** — Retrait d'un événement enregistré reflété instantanément dans la liste. *Corrigé.*
- **Prestataires** — Recherche plus fluide ; bouton « Réserver » sur le profil pour les visiteurs (action à connecter). *Partiel.*
- **Rappels tâches** — Messages de notification dans la langue de l'utilisateur, avec le nom de l'événement en tête. *Prêt.*

## À noter

- Beaucoup de changements sont **locaux** (pas encore commités sur git). Prochaine étape : publier par thème.
```

---

## Example 6 — Quiet week

```markdown
# Bilan semaine — [Projet]

Peu de livraisons visibles cette semaine — surtout de la préparation et des corrections mineures.

- **Correction** — [Une chose concrète si applicable]. *Corrigé.*
- **En préparation** — [Ce qui arrive la semaine prochaine].

Aucun blocage signalé.
```
