# Mise en place d'un système SIEM (Wazuh) pour la détection et la gestion des incidents de sécurité

Projet pluridisciplinaire - 4e année Ingénierie Réseaux
Université Mouloud Mammeri de Tizi-Ouzou (UMMTO) - Département Informatique - 2025/2026

**Réalisé par :** LOUNIS Tassadit, MAMERI Louiza, HOCINE Zahia, KADI Massilva
**Encadrante :** Mme OUBABAS Sarah

## Description

Ce projet étudie et déploie une solution SIEM open source, **Wazuh**, dans un
laboratoire virtualisé qui simule l'infrastructure d'Algérie Télécom. L'objectif
est de centraliser les journaux de sécurité, de les analyser et de détecter des
attaques simulées.

## Architecture du laboratoire

Réseau interne : 192.168.1.0/24

| VM  | Rôle                                         | Système        | Adresse IP    |
|-----|----------------------------------------------|----------------|---------------|
| VM1 | Contrôleur de domaine Active Directory       | Windows Server | 192.168.1.20  |
| VM2 | Serveur SIEM Wazuh                           | Ubuntu Server  | 192.168.1.30  |
| VM3 | Pare-feu pfSense                             | pfSense        | 192.168.1.1   |
| VM4 | Machine attaquante                           | Kali Linux     | 192.168.1.10  |

Les logs de l'Active Directory sont collectés par un agent Wazuh, et ceux du
pare-feu pfSense sont envoyés en syslog vers le serveur Wazuh.

## Scénarios d'attaque testés

- Force brute avec **Hydra** contre l'Active Directory
- Déni de service (SYN flood) avec **hping3**, puis blocage de l'adresse source sur pfSense
- Escalade de privilèges
- Scan réseau

## Contenu du dépôt

- `Rapport_SIEM_Wazuh.pdf` : rapport complet (59 pages)

## Technologies

Wazuh, pfSense, Active Directory, Windows Server, Ubuntu Server, Kali Linux,
Hydra, hping3, VMware

## Mots-clés

SIEM, Wazuh, supervision de sécurité, journaux, corrélation, Active Directory, pfSense
