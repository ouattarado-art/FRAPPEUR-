# FRAPPEUR-Cahier des charges – Application client de transport à Bouaké
Version 1.0 – 13 novembre 2026
1. Contexte et objectifs
L'application client permet de commander une course auprès de chauffeurs à Bouaké, avec un accent sur la sécurité, la confiance et l'adaptation au contexte local : paiement Mobile Money, négociation du prix, connectivité parfois limitée.
Objectifs
• Offrir un parcours simple de la commande au paiement.
• Garantir la sécurité des passagers (identité vérifiée, SOS, assistance).
• Fidéliser les clients grâce à un programme de points.
• Rester utilisable avec une connexion instable.
2. Périmètre
Le présent document couvre l'application client (Android en priorité, iOS en phase ultérieure). L'application chauffeur, le back-office d'administration et le moteur de dispatch sont traités à part, mais leurs interfaces avec l'application client sont mentionnées.
3. Utilisateurs cibles
• Client : particulier de Bouaké et environs, smartphone d'entrée ou de milieu de gamme, forfait data limité.
• Contact d'urgence : proche désigné par le client, destinataire des alertes SOS.
4. Exigences fonctionnelles
F1. Écran d'accueil
• Affichage du logo au lancement.
• Message d'accueil vocal en français (autres langues locales possibles ultérieurement).
• Le message vocal est lu à la première ouverture, puis désactivable dans les paramètres.
• Passage automatique à l'inscription ou à la connexion.
F2. Inscription obligatoire
• Saisie de l'identité : nom, prénom, numéro de téléphone (vérifié par code SMS).
• Prise ou import d'une photo de profil.
• Vérification faciale : comparaison entre un selfie en direct et la photo, avec détection de vivacité.
• Recueil du consentement explicite pour le traitement des données biométriques.
• Ajout d'au moins un contact d'urgence.
• Aucune commande de course possible tant que l'inscription n'est pas validée.
• Cas d'échec : nouvelles tentatives limitées, puis revue manuelle par le support.
F3. Sécurité
• Bouton SOS visible en permanence pendant une course, avec confirmation en un geste (appui long) pour éviter les déclenchements accidentels.
• Appel du numéro d'urgence : 112 (à confirmer avec l'opérateur, voir section 8) et envoi de la position GPS en temps réel au contact d'urgence et à l'équipe d'assistance.
• Assistance directe : bouton d'appel ou de chat vers le support, disponible avant, pendant et après la course.
• Communications gratuites : appels et messages entre client et chauffeur via l'application (VoIP et messagerie), sans consommation du crédit téléphonique. Le numéro réel n'est pas affiché.
• Partage du suivi de course avec un proche.
F4. Cartographie et guidage
• Carte détaillée de Bouaké : quartiers, axes principaux, points d'intérêt (marchés, gares, hôpitaux, établissements scolaires).
• Recherche d'adresse et de lieu, avec saisie de repères locaux, fréquents à Bouaké.
• Position du client et du chauffeur en temps réel.
• Guidage et itinéraire jusqu'à la destination, estimation du temps d'arrivée.
• Possibilité d'épingler manuellement un point de prise en charge.
F5. Négociation de prix
• Affichage d'un prix estimé avant la commande.
• Bannière de négociation : le client propose un prix, le chauffeur accepte, refuse ou contre-propose.
• Limites de négociation paramétrables (écart minimum et maximum par rapport au prix estimé).
• Historique de la négociation visible, prix final confirmé par les deux parties avant le départ.
• Délai d'expiration d'une offre (par exemple 60 secondes).
F6. Paiement Mobile Money
• Opérateurs : Orange Money, MTN MoMo, Moov Money, Wave (liste à valider).
• Enregistrement d'un ou plusieurs numéros de paiement.
• Paiement à la fin de la course ou à l'avance, selon le choix du client.
• Reçu numérique et historique des paiements.
• Gestion des échecs : relance, changement de moyen de paiement, signalement au support.
• Option de paiement en espèces à étudier avec le client.
F7. Programme de fidélité
• Gain de points à chaque course terminée et payée.
• Paliers de statut avec avantages : réductions, courses offertes, priorité d'attribution.
• Écran de suivi : solde, historique, prochain palier.
• Règles d'expiration et de plafonnement des points définies par le client.
F8. Mode hors-ligne
• Cartes de Bouaké téléchargeables et mises en cache.
• Consultation de l'historique des courses et des reçus sans connexion.
• Les actions nécessitant le réseau (commande, paiement) sont mises en file d'attente ou refusées avec un message clair.
• Le bouton SOS reste actif : appel par le réseau mobile et SMS de secours avec la dernière position connue.
• Synchronisation automatique au retour de la connexion.
F9. Notation croisée
• À la fin de la course, le client note le chauffeur (1 à 5 étoiles) et peut laisser un commentaire.
• Le chauffeur note aussi le client.
• Les notes sont visibles seulement après que les deux parties ont noté, pour éviter les représailles.
• Signalement d'un comportement abusif depuis l'évaluation.
• Seuils d'alerte : un compte sous un seuil de note moyenne est examiné par le support.
5. Exigences non fonctionnelles
• Performance : écran principal chargé en moins de 3 secondes sur 3G ; application légère (moins de 50 Mo recommandé).
• Compatibilité : Android 8 et supérieur ; iOS 15 et supérieur en phase 3.
• Consommation de données : cartes et visuels optimisés, mode économie de données.
• Disponibilité : service disponible 24 h/24, objectif de 99,5 %.
• Accessibilité : textes lisibles, contrastes suffisants, icônes explicites, accueil vocal.
• Langue : français au lancement.
6. Sécurité et conformité
• Données biométriques : consentement explicite, finalité limitée, chiffrement, durée de conservation définie. Conformité à la réglementation ivoirienne sur la protection des données personnelles (ARTCI).
• Chiffrement des données en transit et au repos.
• Authentification par code SMS, avec protection contre les fraudes.
• Paiement : aucun stockage de code secret Mobile Money ; passage par les API officielles des opérateurs.
• Confidentialité : numéros masqués entre client et chauffeur.
• Journalisation des alertes SOS et des litiges.
7. Parcours principal
1.  Lancement : logo et accueil vocal.
2.  Inscription : identité, photo, vérification faciale, contact d'urgence.
3.  Choix de la destination sur la carte.
4.  Estimation du prix, puis négociation éventuelle.
5.  Attribution du chauffeur, suivi en temps réel.
6.  Course avec SOS, assistance et communication gratuite.
7.  Paiement par Mobile Money.
8.  Notation croisée et attribution des points de fidélité.
8. Points à valider avant développement
Sujet
Question
Numéro d'urgence
Confirmer que le 112 est joignable en Côte d'Ivoire et ajouter si besoin les numéros locaux (police, SAMU, pompiers).
Mobile Money
Opérateurs retenus, conditions d'intégration et frais.
Vérification faciale
Choix du prestataire ou de la solution, seuils d'acceptation, procédure de revue manuelle.
Données cartographiques
Source de la carte de Bouaké et couverture des rues.
Appels gratuits
Solution VoIP retenue et coûts de fonctionnement.
Négociation
Bornes de prix et règles de commission.
Fidélité
Barème de points, paliers et avantages.
Types de véhicules
Taxi, moto-taxi, tricycle : lesquels sont couverts.
9. Planning proposé
• Phase 1 – MVP (environ 3 mois) : accueil, inscription avec vérification, carte et guidage, commande, paiement Mobile Money, SOS.
• Phase 2 (environ 2 mois) : négociation de prix, communications gratuites, notation croisée, assistance directe.
• Phase 3 (environ 2 mois) : programme de fidélité, mode hors-ligne complet, version iOS, optimisations.
Les durées sont indicatives et à ajuster après validation des points de la section 8.
10. Critères d'acceptation
• Un nouvel utilisateur termine l'inscription en moins de 5 minutes.
• Une course peut être commandée, suivie, payée et notée de bout en bout.
• L'appui sur SOS déclenche l'appel d'urgence et l'envoi de la position en moins de 5 secondes.
• Les cartes en cache restent consultables sans connexion.
• Le paiement Mobile Money aboutit pour chaque opérateur retenu.
• Les tests de sécurité et de conformité sont validés avant la mise en production.
