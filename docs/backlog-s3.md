## Backlog S3 — NiayesBiz

### HMW Définitif
"Comment pourrions-nous aider les maraîchers des Niayes à recevoir chaque matin, avant 6h, un SMS de prix de référence fiable — légume, unité et marché précisés — issu de données vérifiables, pour qu'ils puissent négocier avec les Bana-Bana depuis une position informée et crédible ?"

---

### User Stories MUST
*(À construire obligatoirement en S3)*

#### US-01
**Story :** En tant que collecteur terrain NiayesBiz, je veux saisir les prix collectés sur le marché (légume · unité · prix bas · prix haut · marché source · heure de collecte) depuis une interface simple sur mon téléphone, afin que les données soient disponibles pour l'envoi SMS avant 5h30.
**Priorité :** MUST
**Outil :** Bolt.new (formulaire web mobile-first, accessible depuis tout navigateur sur smartphone basique)
**Effort :** Faible
**Adresse :** Pain Reliever — Horodatage de collecte terrain dans chaque SMS + Protocole de validation multi-collecteurs défini dès le départ
**Critère d'acceptation :** Un collecteur sans formation technique saisit les 6 champs en moins de 2 minutes depuis son téléphone, la saisie est enregistrée en base avec timestamp automatique, et un second collecteur sur un marché différent peut saisir simultanément sans conflit de données.

---

#### US-02
**Story :** En tant qu'administrateur NiayesBiz, je veux valider et fusionner les saisies des 2 collecteurs en une fourchette de prix consolidée par légume avant 5h45, afin que le SMS envoyé soit basé sur au moins 2 sources indépendantes et non sur une donnée unique non vérifiée.
**Priorité :** MUST
**Outil :** Bolt.new (interface de validation avec vue côte-à-côte des 2 saisies + bouton "Valider & Consolider")
**Effort :** Moyen
**Adresse :** Pain Reliever — Fourchette sourcée et horodatée + Gain Creator — Protocole de validation multi-collecteurs défini dès le départ
**Critère d'acceptation :** L'interface affiche les saisies des 2 collecteurs en parallèle, l'administrateur peut modifier manuellement la fourchette finale, et aucun SMS ne part si une seule source est disponible — le bouton d'envoi reste désactivé tant que 2 saisies ne sont pas confirmées.

---

#### US-03
**Story :** En tant qu'administrateur NiayesBiz, je veux générer automatiquement un SMS de 160 caractères maximum au format strict (LÉGUME · UNITÉ · FOURCHETTE FCFA · MARCHÉ · HH:MM) à partir des données validées, afin que le message soit lisible sur feature phone sans défilement et mémorisable en 30 secondes.
**Priorité :** MUST
**Outil :** Dify (workflow de formatage automatique du message avec contrôle du compteur de caractères + alerte si dépassement 160)
**Effort :** Moyen
**Adresse :** Pain Reliever — Horodatage de collecte terrain + Gain Creator — Format mémorisable en 30 secondes restituable à l'oral 3h après
**Critère d'acceptation :** Le message généré ne dépasse jamais 160 caractères, inclut systématiquement le nom du marché source et l'heure de collecte, couvre les 5 légumes prioritaires (tomate · oignon · chou · carotte · aubergine) avec leur unité locale dominante, et s'affiche correctement sur un écran de feature phone simulé (écran 2 pouces, police système).

---

#### US-04
**Story :** En tant qu'administrateur NiayesBiz, je veux envoyer le SMS consolidé à l'ensemble des numéros abonnés en un seul déclenchement avant 6h, afin qu'Abdoulaye reçoive l'information passivement sur son feature phone sans aucune action ni coût de sa part.
**Priorité :** MUST
**Outil :** SMS API (Orange Sénégal API ou Twilio avec routage local) connectée via Dify ou webhook Bolt.new
**Effort :** Élevé
**Adresse :** Pain Reliever — SMS entrant passif, zéro coût sortant pour Abdoulaye
**Critère d'acceptation :** Le SMS arrive sur au moins 3 numéros de test (feature phones réels, pas smartphones) avant 6h00, le destinataire ne supporte aucun coût de réception, le log d'envoi confirme le statut "délivré" pour chaque numéro, et le système fonctionne sur réseau Orange ET Free Sénégal.

---

#### US-05
**Story :** En tant qu'administrateur NiayesBiz, je veux gérer une liste d'abonnés (ajout · suppression · numéro · nom · localité) depuis une interface simple, afin de contrôler qui reçoit le SMS matinal et de pouvoir ajouter Abdoulaye et ses voisins sans manipulation technique complexe.
**Priorité :** MUST
**Outil :** Bolt.new (CRUD abonnés avec champs : nom · numéro · village · date d'inscription · statut actif/inactif)
**Effort :** Faible
**Adresse :** Gain Creator — Wave comme canal d'incentive sans complexité supplémentaire (prérequis pour le parrainage US-08)
**Critère d'acceptation :** Un abonné peut être ajouté, désactivé ou supprimé en moins de 1 minute, le numéro est au format Sénégal validé automatiquement (+221XXXXXXXXX), la liste est exportable en CSV pour audit, et seuls les abonnés au statut "actif" reçoivent le SMS du lendemain.

---

### User Stories SHOULD
*(À construire si le temps le permet en S3)*

#### US-06
**Story :** En tant que collecteur terrain NiayesBiz, je veux recevoir une alerte automatique à 4h45 si ma saisie du matin n'a pas encore été enregistrée, afin de ne pas bloquer l'envoi du bulletin par oubli ou retard non signalé.
**Priorité :** SHOULD
**Outil :** Dify (workflow de relance automatique par SMS ou appel vocal via API) + Bolt.new (vérification de saisie avant déclenchement)
**Effort :** Moyen
**Adresse :** Pain Reliever — Horodatage et fiabilité de la chaîne d'envoi (mitigation du risque collecteur défaillant identifié dans Alerte A1 des métriques)
**Critère d'acceptation :** Si à 4h45 une des 2 saisies est absente, le collecteur concerné reçoit un SMS de rappel automatique, l'administrateur reçoit une notification parallèle, et le log trace l'incident pour le rapport hebdomadaire.

---

#### US-07
**Story :** En tant qu'administrateur NiayesBiz, je veux consulter un tableau de bord hebdomadaire affichant le taux de livraison des SMS, le nombre d'abonnés actifs et le nombre de saisies collecteurs validées, afin de suivre les 3 métriques de la démo S6 sans outil analytique externe.
**Priorité :** SHOULD
**Outil :** Bolt.new (dashboard avec 3 KPIs affichés en temps réel depuis la base de données)
**Effort :** Moyen
**Adresse :** Gain Creator — Protocole de validation multi-collecteurs + Métrique Nord (taux d'utilisation en négociation) et Métriques de Progression du plan de validation
**Critère d'acceptation :** Le dashboard affiche en temps réel : nombre de SMS envoyés vs livrés (%), nombre d'abonnés actifs vs inactifs, nombre de jours sans défaillance de collecte consécutifs — toutes les données sont issues de la base Bolt.new sans saisie manuelle supplémentaire.

---

### User Stories COULD
*(Roadmap post-MVP — S4 et au-delà)*

#### US-08
**Story :** En tant que maraîcher abonné, je veux parrainer 5 voisins pour recevoir 1 mois de service gratuit crédité directement sur mon compte Wave, afin d'être récompensé de ma contribution à la croissance du réseau sans démarche administrative.
**Priorité :** COULD
**Outil :** Bolt.new (suivi parrainage) + Wave API (crédit automatique) + SMS API (confirmation)
**Effort :** Élevé
**Adresse :** Gain Creator — Wave comme canal d'incentive sans complexité supplémentaire
**Critère d'acceptation :** Lorsque le 5ème filleul s'inscrit avec le code parrain d'Abdoulaye, un crédit d'1 mois est automatiquement envoyé sur son compte Wave avec notification SMS de confirmation — sans intervention manuelle de NiayesBiz.

---

#### US-09
**Story :** En tant que maraîcher abonné, je veux envoyer un SMS court après ma vente pour déclarer le prix réellement obtenu (format : LÉGUME UNITÉ PRIX), afin que mes données enrichissent le bulletin du lendemain et que je devienne acteur de la fiabilité collective du service.
**Priorité :** COULD
**Outil :** Dify (parsing du SMS entrant + validation du format + intégration en base) + SMS API (numéro court dédié)
**Effort :** Élevé
**Adresse :** Gain Creator — Effet réseau naturel dans les Niayes + Produit & Service — Système de prix communautaire déclaré
**Critère d'acceptation :** Un SMS entrant au format "TOM 25KG 4500" est parsé, validé et intégré dans la base de données en moins de 30 secondes, le maraîcher reçoit un accusé de réception SMS automatique, et les données déclarées sont visibles dans l'interface admin avec flag "déclaré" pour les distinguer des prix collecteurs.

---

#### US-10
**Story :** En tant que maraîcher abonné, je veux interroger le service via USSD (\*346#) pour consulter le dernier bulletin de prix disponible à n'importe quelle heure, afin d'accéder à l'information même si j'ai raté le SMS du matin.
**Priorité :** COULD
**Outil :** USSD Gateway (Africa's Talking ou opérateur local) + Dify (logique de requête) + Bolt.new (base de prix)
**Effort :** Élevé
**Adresse :** Pain Reliever — SMS entrant passif (extension du canal d'accès) + Job To Be Done — Communiquer via SMS ou USSD sur feature phone
**Critère d'acceptation :** La composition de \*346# depuis un feature phone Orange ou Free Sénégal affiche en moins de 5 secondes le dernier bulletin validé du jour, sans coût pour l'utilisateur, avec heure de collecte visible sur l'écran du menu USSD.

---

### Sprint S3

**Semaine 1 — Construction du pipeline de données :**
US-01 (formulaire collecteur) + US-02 (interface de validation admin) + US-05 (gestion liste abonnés) — objectif : avoir une base de données alimentable manuellement et une liste d'abonnés test de 10 numéros réels d'ici vendredi.

**Semaine 2 — Construction du pipeline d'envoi :**
US-03 (générateur de SMS 160 caractères via Dify) + US-04 (envoi SMS via API sur réseau Orange/Free Sénégal) — objectif : envoyer un bulletin de test réel à 10 feature phones avant 6h le jeudi de la semaine 2, avec données fictives mais format conforme.

Si avance constatée en fin de semaine 2 : démarrer US-06 (alerte collecteur) ou US-07 (dashboard KPIs).

**Démo S6 — À démontrer obligatoirement :**
US-02 (validation admin en live avec 2 saisies simultanées) + US-03 (génération du SMS 160 caractères en temps réel devant le jury) + US-04 (preuve d'envoi et de réception sur feature phone physique posé sur la table, avant 6h le matin de la démo ou via log de livraison horodaté).
