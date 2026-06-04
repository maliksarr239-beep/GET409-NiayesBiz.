## Hypothèses de Validation — NiayesBiz

### HMW Définitif
"Comment pourrions-nous aider les maraîchers des Niayes à recevoir chaque matin, avant 6h, un SMS de prix de référence fiable — légume, unité et marché précisés — issu de données vérifiables, pour qu'ils puissent négocier avec les Bana-Bana depuis une position informée et crédible ?"

---

### Hypothèses CRITIQUES

#### Hypothèse C1 — Fiabilité et utilité réelle du prix de référence

**Affirmation :** Nous croyons qu'un maraîcher des Niayes qui reçoit une fourchette de prix horodatée (légume · unité · marché · heure de collecte) avant 6h est en mesure de l'utiliser comme levier de négociation face à un Bana-Bana ce même matin — et qu'un prix collecté à 5h30 reste suffisamment fiable jusqu'à 9h pour ne pas induire une négociation perdante.

**Indicateur :** Nous le saurons si au moins 7 maraîchers sur 10 interrogés après une transaction déclarent que la fourchette reçue était "dans le bon ordre de grandeur" par rapport au prix finalement obtenu ou proposé, ET si aucun ne rapporte avoir négocié à la baisse à cause d'un prix SMS erroné.

**Méthode :** Simulation manuelle en Wizard of Oz : un membre de NiayesBiz se rend à Castor ou Pikine à 5h30 pendant 5 jours consécutifs, collecte les prix à la main, envoie un SMS manuel à 10 maraîchers de Sébikhane avant 6h, puis les rappelle ou les visite le soir pour un debriefing de 5 minutes sur leur transaction du matin.

**Qui valide :** 1 collecteur terrain NiayesBiz (présence physique marché) + Abdoulaye Ndiaye et 9 maraîchers recrutés via le groupement local.

**Délai S3 :** 5 jours de collecte + 2 jours d'analyse = résultat disponible en fin de semaine 1 du sprint S3.

---

#### Hypothèse C2 — Continuité et robustesse de la collecte humaine

**Affirmation :** Nous croyons qu'il est possible de recruter et de maintenir au moins 2 collecteurs humains fiables sur des marchés différents (Castor + Pikine) capables de relever les prix des 5 légumes prioritaires avant 5h30 chaque matin ouvrable, moyennant une incitation financière ou non-financière acceptable pour NiayesBiz sur la durée d'un MVP.

**Indicateur :** Nous le saurons si 2 collecteurs recrutés assurent une présence effective ≥ 9 matins sur 10 pendant 2 semaines consécutives sans défaillance non anticipée, ET si le coût total de leur incitation est inférieur à 15 000 FCFA par semaine pour les deux.

**Méthode :** Recrutement express en 48h de 2 profils existants sur les marchés (porteurs, revendeurs secondaires, agents ANSD locaux) via réseau de terrain ; test de collecte en conditions réelles sur 10 jours avec check-in quotidien par appel vocal à 6h pour confirmer l'envoi ; remplacement simulé d'un collecteur à J7 pour tester la résilience du dispositif.

**Qui valide :** Coordinateur terrain NiayesBiz (recrutement + suivi) + comptabilité quotidienne du taux de présence réelle.

**Délai S3 :** Recrutement J1–J2, test opérationnel J3–J12, analyse résilience J13–J14 — résultat complet à mi-sprint S3.

---

### Hypothèses IMPORTANTES

#### Hypothèse I1 — Réponse adaptative des Bana-Bana

**Affirmation :** Nous croyons que les Bana-Bana, confrontés à un maraîcher citant un prix SMS, adopteront un contre-discours standardisé ("mon prix intègre le transport, le risque, l'invendu") qui neutralise partiellement l'avantage informationnel d'Abdoulaye — et que ce contre-discours est suffisamment prévisible pour être anticipé dans un guide de réponse simple.

**Indicateur :** Nous le saurons si, lors d'entretiens avec 3 à 5 Bana-Bana actifs dans les Niayes, au moins 3 arguments récurrents de dévaluation du prix de référence émergent spontanément — et si ces arguments sont formulables en réfutations courtes mémorisables par Abdoulaye.

**Méthode :** Entretiens semi-directifs de 20 minutes avec 4 Bana-Bana (recrutés via maraîchers partenaires, sans révéler le projet GreenSprint) en jouant le rôle d'un acheteur curieux des pratiques de prix ; cartographie des arguments récurrents ; test de réfutations orales auprès de 5 maraîchers pour évaluer leur confiance à les utiliser.

**Qui valide :** 1 membre NiayesBiz formé à l'entretien non directif + 5 maraîchers testeurs de réfutations.

**Délai S3 :** Entretiens Bana-Bana en semaine 1 (3 jours), synthèse + test réfutations en semaine 2 (2 jours) — résultat avant la fin de S3.

---

#### Hypothèse I2 — Acceptabilité du modèle sans coût sortant pour le maraîcher

**Affirmation :** Nous croyons qu'un maraîcher comme Abdoulaye acceptera de s'inscrire à un service de SMS entrant gratuit (push) ou d'utiliser un code USSD court sans frais, sans exiger de contrepartie financière immédiate — à condition que la valeur du premier SMS reçu soit perceptible dès la première semaine.

**Indicateur :** Nous le saurons si 8 maraîchers sur 10 contactés acceptent de donner leur numéro pour recevoir le SMS test sans rémunération, ET si au moins 6 sur 10 déclarent vouloir continuer après réception de 3 SMS consécutifs.

**Méthode :** Recrutement direct au champ ou au groupement avec pitch oral de 2 minutes ("tu reçois chaque matin le prix de la tomate à Castor, gratuitement, sur ton téléphone — tu veux essayer ?") sans support écrit ; suivi de l'opt-in réel + micro-sondage à J+3 et J+7 par appel vocal.

**Qui valide :** 1 facilitateur terrain NiayesBiz natif wolofophone + données d'opt-in/opt-out sur 10 jours.

**Délai S3 :** Recrutement J1–J3, suivi J4–J10, résultat J11 — parallélisable avec C1 et C2.

---

### Hypothèses SECONDAIRES

#### Hypothèse S1 — Lisibilité et mémorisation du format SMS sur feature phone

**Affirmation :** Nous croyons qu'Abdoulaye est capable de lire, comprendre et mémoriser oralement le contenu d'un SMS de 160 caractères au format structuré (LÉGUME · UNITÉ · FOURCHETTE · MARCHÉ · HEURE) sur son feature phone, sans assistance, et de restituer l'information correctement lors d'une négociation orale 2 à 3 heures plus tard.

**Indicateur :** Nous le saurons si 8 maraîchers sur 10 testés peuvent citer spontanément le légume, l'unité et la fourchette de prix d'un SMS reçu 2 heures plus tôt, sans relire le téléphone, lors d'un jeu de rôle de négociation simulée.

**Méthode :** Test de lisibilité en 3 formats SMS distincts (structure, langue, niveau de détail) sur 10 maraîchers ; simulation de négociation 2h après réception avec un membre NiayesBiz jouant le Bana-Bana ; score de mémorisation et de compréhension sur grille simple.

**Qui valide :** 1 facilitateur terrain + grille d'évaluation de mémorisation à 5 critères.

**Délai S3 :** Test réalisable en 1 journée terrain + 1 journée d'analyse — à planifier en fin de S3 une fois le format C1 stabilisé.

---

#### Hypothèse S2 — Pertinence des 5 légumes prioritaires comme périmètre V1

**Affirmation :** Nous croyons que tomate, oignon, chou, carotte et aubergine représentent au moins 70% du volume de vente hebdomadaire d'un maraîcher type des Niayes à Sébikhane, et que couvrir ces 5 légumes suffit à rendre le service immédiatement utile sans extension de périmètre.

**Indicateur :** Nous le saurons si l'analyse des carnets de vente ou les déclarations de 10 maraîchers confirment que ces 5 légumes représentent ≥ 70% de leurs transactions avec les Bana-Bana sur les 4 dernières semaines.

**Méthode :** Revue de 10 carnets de vente informels (ou reconstitution mémorielle guidée avec grille) lors de visites terrain de 30 minutes par maraîcher ; croisement avec les données disponibles de la FENAGIE Maraîchage ou de l'ANSD si accessibles.

**Qui valide :** 1 membre NiayesBiz + données déclaratives maraîchers + sources secondaires disponibles.

**Délai S3 :** 2 jours terrain + 1 jour analyse — parallélisable avec les autres hypothèses dès J1 de S3.

---

### Priorité de Validation S3

La première chose à tester en S3 : envoyer manuellement pendant 5 matins consécutifs un SMS de prix collecté à 5h30 sur le marché de Castor à 10 maraîchers de Sébikhane, puis les interviewer le soir même pour déterminer si la fourchette reçue était fiable, utilisable et a effectivement modifié leur posture de négociation face aux Bana-Bana.
