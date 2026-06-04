## Contraintes MVP — NiayesBiz
### Persona
Abdoulaye Ndiaye · 52 ans · Maraîcher · Sébikhane · Feature phone · Compte Wave

---

### Contraintes Non Négociables

#### Contrainte 1
**Critère :** Le MVP DOIT délivrer chaque SMS entrant en moins de 160 caractères, en français simple ou wolof translittéré, lisible sur écran feature phone sans défilement, avec le format strict : LÉGUME · UNITÉ · FOURCHETTE FCFA · MARCHÉ · HEURE DE COLLECTE.
**Origine :** Chapeau Blanc
**Élimine :** Toute interface web, application mobile, dashboard, notification push, ou message enrichi (HTML, lien URL, image MMS) — aucune de ces formes n'est accessible sur le téléphone d'Abdoulaye.

---

#### Contrainte 2
**Critère :** Le MVP DOIT fonctionner en SMS entrant passif (réception sans action requise de l'utilisateur) OU en USSD pull sur code court (ex : \*346#) — sans jamais exiger qu'Abdoulaye envoie un SMS sortant payant pour recevoir l'information.
**Origine :** Chapeau Noir (risque attrition coût)
**Élimine :** Tout modèle basé sur un SMS sortant initié par l'utilisateur, un abonnement prépayé par SMS, ou un système de requête individuelle à la demande qui consomme le crédit d'Abdoulaye avant qu'il ait perçu la valeur du service.

---

#### Contrainte 3
**Critère :** Le MVP DOIT horodater chaque prix avec l'heure réelle de collecte sur le marché (ex : "collecté 05h45") ET indiquer explicitement le marché source, de sorte qu'Abdoulaye puisse évaluer lui-même la fraîcheur de l'information avant de négocier.
**Origine :** Chapeau Noir (risque données obsolètes)
**Élimine :** Tout système d'envoi de prix sans timestamp, tout prix agrégé sur 24h présenté comme "prix du jour", toute donnée issue d'une seule source non identifiée — une information sans heure et sans source est indéfendable face à un Bana-Bana expérimenté.

---

#### Contrainte 4
**Critère :** Le MVP DOIT couvrir au minimum les 5 légumes les plus vendus dans les Niayes (tomate, oignon, chou, carotte, aubergine) avec l'unité locale dominante pour chacun (cageot, filet, kg), et NE DOIT PAS tenter de couvrir l'intégralité du catalogue maraîcher dès le V1.
**Origine :** Chapeau Blanc (variabilité légume/unité/marché)
**Élimine :** Toute ambition encyclopédique de couverture produit, tout système de paramétrage individuel par maraîcher, toute personnalisation de l'abonnement par type de culture — la complexité de configuration est une barrière d'adoption pour Abdoulaye et un risque de maintenance non maîtrisable pour NiayesBiz.

---

#### Contrainte 5
**Critère :** Le MVP DOIT reposer sur au moins 2 collecteurs humains indépendants présents physiquement sur des marchés de destination différents (ex : Castor + Pikine) avant chaque envoi, et NE DOIT PAS envoyer de SMS si une seule source de données est disponible ce matin-là.
**Origine :** Chapeau Noir (risque fiabilité source unique)
**Élimine :** Tout scraping automatique non vérifié, toute reprise de prix publiés la veille sur un site tiers, tout système de prix calculé algorithmiquement sans validation terrain — la crédibilité du SMS face au Bana-Bana repose entièrement sur la robustesse de la source, pas sur la sophistication technique.

---

#### Contrainte 6
**Critère :** Le MVP NE DOIT PAS inclure de module de formation, de guide de négociation intégré, ou de contenu pédagogique dans la V1 — ces éléments constituent un périmètre distinct qui allonge le délai de mise sur le marché sans valider l'hypothèse centrale (la valeur du prix de référence seul).
**Origine :** Chapeau Noir (risque vulnérabilité face aux Bana-Bana malgré l'information)
**Élimine :** Tout chatbot SMS de conseil, toute fiche technique de négociation envoyée en complément, tout module de literacy financière embarqué — ces fonctionnalités sont légitimes mais appartiennent à la V2, conditionnée à la validation terrain de la V1.

---

### Fonctionnalités Éliminées

- **Application mobile (Android/iOS)** → éliminée parce qu'Abdoulaye possède uniquement un feature phone sans accès internet ; développer une app revient à construire pour un persona inexistant dans les Niayes.
- **Tableau de bord web pour les maraîchers** → éliminé parce que l'accès internet n'est pas disponible sur le terrain et que la consultation d'un dashboard suppose une alphabétisation numérique non validée pour ce profil.
- **Système de prix en temps réel automatisé** → éliminé parce que l'infrastructure de collecte humaine fiable n'existe pas encore ; automatiser sans source vérifiée amplifie le risque de désinformation plutôt que de le réduire.
- **Module de contribution des maraîchers (SMS de prix vendus)** → éliminé en V1 parce que la collecte déclarative non vérifiée introduit un biais de données incontrôlable ; à reconsidérer en V2 avec un protocole de validation croisée.
- **Intégration Wave pour paiement de l'abonnement** → éliminée en V1 parce que monétiser avant la preuve de valeur entraîne l'attrition immédiate décrite dans le Chapeau Noir ; le modèle économique est une question de V2, pas de validation MVP.
- **Couverture de tous les marchés de Dakar** → éliminée parce que la capacité de collecte humaine au lancement est limitée ; deux marchés bien couverts valent mieux que cinq marchés sous-documentés.
- **Personnalisation par maraîcher (choix du légume, fréquence)** → éliminée parce que la configuration individuelle suppose une interface de paramétrage inaccessible sur feature phone et alourdit inutilement la logique opérationnelle de la V1.

---

### Critère de Validation Final

Le MVP est valide si et seulement si : au moins 30 maraîchers des Niayes déclarent, après 4 semaines de réception du SMS matinal, avoir utilisé la fourchette de prix reçue dans au moins une négociation réelle avec un Bana-Bana — et obtenu un prix supérieur ou égal au bas de la fourchette communiquée.
