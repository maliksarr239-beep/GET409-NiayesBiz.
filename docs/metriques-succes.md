## Métriques de Succès — NiayesBiz

### MVP
Service SMS matinal envoyé avant 6h avec prix de référence (légume · unité · fourchette FCFA · marché source · heure de collecte) à des maraîchers de la zone des Niayes — feature phone uniquement, sans coût sortant pour l'utilisateur.

---

### ⭐ Métrique Nord

**Indicateur :** Taux d'utilisation active en négociation — pourcentage de maraîchers abonnés qui déclarent avoir cité le prix reçu par SMS face à un Bana-Bana au moins une fois dans la semaine écoulée.

**Valeur cible à 30 jours :** 60% des abonnés actifs (soit au minimum 18 maraîchers sur 30) déclarent une utilisation en négociation réelle sur les 7 derniers jours.

**Comment mesurer :** Appel vocal hebdomadaire de 3 minutes par un facilitateur terrain NiayesBiz à chaque abonné, avec une seule question directe : "Est-ce que tu as utilisé le prix du SMS cette semaine pour parler avec un Bana-Bana ?" — réponse oui/non reportée dans un carnet de suivi papier avec date et légume concerné. Consolidation manuelle chaque lundi matin.

---

### 📈 Métriques de Progression

#### Métrique P1
**Indicateur :** Taux de rétention à 30 jours — pourcentage d'abonnés inscrits en J1 qui sont toujours abonnés et n'ont pas demandé à se désinscrire à J30.

**Valeur cible à 30 jours :** 75% de rétention (soit 23 maraîchers sur 30 encore abonnés à J30 sans relance active de NiayesBiz).

**Comment mesurer :** Liste papier des abonnés avec date d'inscription et date de désinscription éventuelle, tenue par le facilitateur terrain ; toute demande de désinscription — qu'elle soit formulée par appel, en face-à-face, ou via un voisin — est enregistrée immédiatement dans le carnet de suivi.

---

#### Métrique P2
**Indicateur :** Fiabilité perçue du prix reçu — pourcentage de SMS dont le prix annoncé est jugé "dans le bon ordre de grandeur" par le maraîcher après sa transaction du jour, c'est-à-dire ni surprenant à la hausse ni trompeur à la baisse de plus de 500 FCFA par rapport au prix réellement obtenu ou négocié.

**Valeur cible à 30 jours :** 80% des SMS évalués jugés fiables par les maraîchers interrogés (mesure sur un échantillon de 10 transactions déclarées par semaine).

**Comment mesurer :** Le facilitateur terrain pose la question le soir de la transaction : "Le prix que tu as reçu ce matin, il était proche de ce que le Bana-Bana a proposé ?" — réponse sur 3 niveaux (proche / un peu différent / très différent) reportée dans le carnet ; écart chiffré noté si le maraîcher se souvient du montant réel.

---

#### Métrique P3
**Indicateur :** Taux de bouche-à-oreille organique — nombre de nouveaux abonnés recrutés par recommandation directe d'un abonné existant, sans démarchage actif de NiayesBiz.

**Valeur cible à 30 jours :** 5 nouveaux abonnés recrutés spontanément par recommandation d'un pair sur les 30 jours du MVP (soit un coefficient de viralité minimal de 0,17 sur la base de 30 abonnés initiaux).

**Comment mesurer :** À l'inscription de chaque nouvel abonné, le facilitateur pose systématiquement la question : "C'est qui qui t'a parlé du service ?" — si le nom cité est celui d'un abonné existant, la source est notée dans le carnet ; aucun outil numérique requis.

---

### 🚨 Métriques d'Alerte

#### Alerte A1
**Signal :** Taux de non-réception du SMS avant 7h — proportion d'abonnés qui, lors du check hebdomadaire, déclarent ne pas avoir reçu le SMS un ou plusieurs matins dans la semaine écoulée.

**Seuil :** Déclenchement si plus de 20% des abonnés signalent une non-réception sur une même semaine, soit 6 abonnés sur 30 affectés — ce seuil indique une défaillance systémique de la chaîne de collecte ou d'envoi, et non un incident isolé.

**Action corrective :** Suspension immédiate de l'envoi du lendemain + audit en 24h de la chaîne complète (présence collecteur terrain confirmée ? SMS envoyé depuis quel numéro ? opérateur Orange ou Free en cause ?) + notification vocale aux abonnés pour expliquer l'interruption et maintenir la confiance avant la reprise.

---

#### Alerte A2
**Signal :** Taux de désinscription hebdomadaire — nombre d'abonnés ayant demandé à se désinscrire dans la même semaine calendaire.

**Seuil :** Déclenchement si 3 désinscriptions ou plus surviennent dans la même semaine (soit 10% du panel initial en 7 jours) — ce rythme, s'il se répète deux semaines consécutives, conduit à un panel non représentatif avant J30 et invalide la Métrique Nord.

**Action corrective :** Appel individuel de compréhension auprès de chaque maraîcher désinscrit dans les 48h ("qu'est-ce qui t'a fait arrêter ?") pour distinguer une cause corrigeable (format illisible, prix trop éloigné, heure d'envoi inadaptée) d'un rejet de fond (service non pertinent pour son activité) — résultat présenté en rétrospective NiayesBiz avant la semaine suivante.

---

### Tableau de Bord S6

À la démo S6, nous présenterons ces 3 chiffres :

1. **Métrique Nord — Taux d'utilisation en négociation :** X% des abonnés actifs ont cité le prix SMS face à un Bana-Bana cette semaine (cible : 60%)
2. **Métrique P1 — Taux de rétention à 30 jours :** X maraîchers sur 30 encore abonnés sans relance (cible : 23/30)
3. **Alerte A1 — Fiabilité de la chaîne d'envoi :** déclenchée / non déclenchée — et si déclenchée, cause identifiée et action corrective appliquée
