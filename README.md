/**********************************************/
/*******************FRENCH*********************/
/**********************************************/
                    
# Luxman L-31 - Module Bluetooth & DAC Interne

Ce dépôt contient les fichiers de conception matérielle d'une carte d'extension Bluetooth conçue spécifiquement pour s'intégrer à l'intérieur d'un amplificateur intégré Luxman L-31.

L'objectif est d'ajouter une connectivité sans fil moderne (aptX-HD) sans dénaturer l'esthétique d'origine de l'appareil ni altérer la qualité de son chemin analogique.

## Architecture technique

La carte s'alimente directement sur le rail de puissance interne de l'amplificateur (environ 40V DC). Le basculement du signal audio est géré par un relais de signal pour garantir que les entrées analogiques d'origine restent totalement isolées lorsque le module est inactif.

Points clés de la conception :
* **Alimentation :** Utilisation d'un régulateur abaisseur (Buck) acceptant jusqu'à 65V en entrée pour tolérer les variations du rail d'alimentation du Luxman.
* **CEM et Bruit :** Le convertisseur Buck fonctionne en mode "Forced PWM" (fréquence fixe de 400 kHz) afin de repousser le bruit de découpage hors de la bande audible. Le routage sur 4 couches inclut des plans de masse dédiés, du via stitching et des zones d'exclusion RF strictes autour de l'antenne.
* **Chemin audio :** Les composants passifs traitant le signal analogique en sortie de DAC utilisent des condensateurs à diélectrique C0G/NP0 et des résistances à couche mince (thin film) pour éviter l'introduction de distorsions harmoniques.

## Spécifications matérielles

* **Logiciel CAO :** KiCad 10
* **PCB :** 4 couches
* **Régulateur 5V :** Texas Instruments LMR51606XFDBVR
* **LDO 3.3V :** Texas Instruments TPS7A2033PDBVR (avec décharge active)
* **DAC :** ESS Technology ES9023P
* **Module Bluetooth :** Feasycom FSC-BT1026E (sortie I2S/PCM)
* **Relais Audio :** Omron G6K-2F-Y DC3

## Structure du dépôt

Ce dépôt héberge uniquement les fichiers sources du projet KiCad (`.kicad_pro`, `.kicad_sch`, `.kicad_pcb` et BOM). Les fichiers de fabrication (Gerbers, fichiers de placement CPL) ne sont pas versionnés.

## Avertissement de sécurité

L'installation de ce module implique d'intervenir à l'intérieur d'un amplificateur relié au secteur et de manipuler des tensions continues de puissance. Ces modifications s'adressent à des personnes ayant les compétences requises en électronique. Toute modification est effectuée à vos propres risques.


/**********************************************/
/*******************ENGLISH********************/
/**********************************************/

# Luxman L-31 - Internal Bluetooth & DAC Module

This repository contains the hardware design files for a Bluetooth extension board specifically designed to be integrated inside a Luxman L-31 integrated amplifier.

The goal is to add modern wireless connectivity (aptX-HD) without altering the original aesthetics of the device or degrading its analog signal path.

## Technical Architecture

The board is powered directly from the amplifier's internal power rail (approx. 40V DC). Audio signal switching is handled by a signal relay to ensure the original analog inputs remain completely isolated when the module is inactive.

Key design points:
* **Power Supply:** Use of a step-down (Buck) regulator accepting up to 65V input to tolerate fluctuations in the Luxman's power rail.
* **EMC and Noise:** The Buck converter operates in "Forced PWM" mode (fixed 400 kHz frequency) to push switching noise out of the audible band. The 4-layer routing includes dedicated ground planes, via stitching, and strict RF keep-out zones around the antenna.
* **Audio Path:** Passive components handling the analog signal at the DAC output use C0G/NP0 dielectric capacitors and thin film resistors to prevent the introduction of harmonic distortion.

## Hardware Specifications

* **CAD Software:** KiCad 10
* **PCB:** 4 layers
* **5V Regulator:** Texas Instruments LMR51606XFDBVR
* **3.3V LDO:** Texas Instruments TPS7A2033PDBVR (with active discharge)
* **DAC:** ESS Technology ES9023P
* **Bluetooth Module:** Feasycom FSC-BT1026E (I2S/PCM output)
* **Audio Relay:** Omron G6K-2F-Y DC3

## Repository Structure

This repository hosts only the KiCad project source files (`.kicad_pro`, `.kicad_sch`, `.kicad_pcb` and BOM). Manufacturing files (Gerbers, CPL placement files) are not versioned.

## Safety Warning

Installing this module involves working inside a mains-connected amplifier and handling high-power DC voltages. These modifications are intended for individuals with the required electronics skills. All modifications are performed at your own risk.
