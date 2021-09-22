---
title: Lagerbehållning beaktas inte för batch ovan-artiklar
description: Vissa artikelplaceringsmallar tar inte hänsyn till aktuell lagerbehållning för batch ovan-artiklar. Batch- eller serienumret måste anges på efterfrågeordern.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: df5642b32f5e053144230eab3dbcf633f526279a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477632"
---
# <a name="slotting-templates-dont-consider-on-hand-inventory-for-batch-above-items"></a>Artikelplaceringsmallar tar inte hänsyn till lagerbehållning för batch ovan-artiklar

## <a name="symptoms"></a>Symtom

Artikelplaceringsmallar som har kriteriet om *platsbehållning* beaktas inte aktuell lagerbehållning för *batch ovan* artiklar. De överväger det bara om batchnumret anges på försäljningsorderraden.

När du använder *batch under*, den aktuella lagerinventeringen betraktas som förväntat.

Mer information finns i [Artikelplacering för distributionslager](/dynamics365/supply-chain/warehousing/warehouse-slotting).

## <a name="resolution"></a>Lösning

Spårmallens rubrik kan definieras för *Beställt*, *Reserverat* eller *Frisläppt* efterfrågestrategi. För strategin *Beställt* efterfrågestrategi, gäller samma reservationshierarki krav som gäller för reservation eller släppning till lagerprocesser. Därför för föremål som har *batch ovan* och *serie under* reservationshierarkier måste batchen eller serienumret anges på efterfrågeordern (försäljning eller överföring).

Alternativt kan strategin *Reserverad* efterfrågestrategi kan användas för att välja batch- eller serienummer innan efterfrågan på lagerlocket genereras.
