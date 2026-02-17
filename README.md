## IoT Smart Farm – Système de Supervision avec ESP32
#Présentation

Ce projet consiste en la conception et la mise en œuvre d’un prototype de ferme connectée reposant sur des microcontrôleurs ESP32 et des capteurs environnementaux.
L’objectif était de concevoir une architecture IoT complète permettant de :
 - Collecter des données environnementales (humidité)
 - Déclencher des actions locales en fonction de seuils définis
 - Transmettre les données via le protocole MQTT
 - Traiter les informations côté serveur
 - Visualiser les métriques en temps réel
   
Ce projet met en œuvre une chaîne IoT complète, du système embarqué jusqu’à la supervision.

## Architecture du système
Capteurs
   ↓
ESP32 (MicroPython)
   ↓
Broker MQTT (Mosquitto)
   ↓
Node.js / Node-RED
   ↓
Stockage des données
   ↓
Grafana (Dashboards)

## Technologies utilisées
#Systèmes embarqués
 - ESP32
 - MicroPython

#Communication
 - Protocole MQTT
 - Broker Mosquitto

#Backend et traitement
 - Node.js
 - Node-RED

#Visualisation
 - Grafana
   
##Fonctionnement

L’ESP32 lit les données d’humidité via le capteur.
Une condition est évaluée directement sur le microcontrôleur.
Si le taux dépasse un seuil défini :
Un message est affiché sur l’écran intégré à la maquette.
La mesure est publiée sur un topic MQTT dédié. Node.js et/ou Node-RED récupèrent et traitent les données.
Les données sont envoyées vers la couche de stockage.

Grafana affiche les métriques en temps réel via des tableaux de bord.

## Exemple de logique embarquée
if humidity > seuil:
    afficher_message("Humidité élevée détectée")
    publier_mqtt("ferme/humidite", humidity)

##Compétences mises en œuvre

 - Programmation embarquée en MicroPython
 - Intégration de capteurs avec ESP32
 - Implémentation du modèle Publish/Subscribe (MQTT)
 - Configuration d’un broker Mosquitto
 - Traitement de flux temps réel avec Node.js
 - Orchestration de flux via Node-RED
 - Supervision et visualisation de données avec Grafana
 - Conception d’une architecture IoT distribuée
 - Sécurité et bonnes pratiques
 - Structuration des topics MQTT
 - Paramétrage du broker
 - Sensibilisation aux risques d’exposition des objets connectés
 - Compréhension des problématiques d’authentification et de sécurisation des communications

##Auteur
Karadag 
Nissa
De la gestion de flux de données en temps réel

Des outils de supervision

Des enjeux de sécurité liés aux environnements IoT
