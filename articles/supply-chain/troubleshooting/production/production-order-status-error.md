---
title: Fel vid ändring av status från Rapporterat som färdigt till Slut
description: Du kan få ett felmeddelande när du ändrar statusen för en produktionsorder från Rapporterad som avslutad till Slut. På den här sidan beskrivs hur du begränsar problemet.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 744637f5cccffe44b85f77c1a9df2034012fac40
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477638"
---
# <a name="error-when-changing-status-of-production-order-from-reported-as-finished-to-end"></a>Fel vid ändring av status för produktionsorder från Rapporterat som färdigt till Slut

## <a name="symptoms"></a>Symtom

När statusen för en produktionsorder ändras från Rapporterad som färdig till Slut får du ett av följande felmeddelanden:

> Uppdateringskonflikt. Standardkostnaden matchar inte det ekonomiska lagervärdet efter uppdateringen.

> Ett allvarligt fel har uppstått i funktionen InventCostMovement.checkVariance.

## <a name="cause"></a>Orsak

Det här problemet beror på att underliggande data har ändrats av en annan process. Processen kommer att försöka uppdatera data upp till fem gånger. Om det fortfarande finns en konflikt efter fem försök visas något av felmeddelandena ovan.

## <a name="resolution"></a>Lösning

Detta beteende är av design. Du kan undvika problemet genom att återuppta batch-jobbet. Den ska köras.

Om batchjobbet misslyckas när du har återaktiverat det kontrollerar du att avrundnings precisionen för redovisningens standardvaluta är kompatibel med avrundning som tillämpas på värdena i registret InventSum. Om avrundningsprecisionen har ändrats till ett icke-kompatibelt värde måste du förmodligen ändra tillbaka till ett kompatibelt värde. Leta efter **ModifiedDateTime**. I det här fallet visar värdet normalt att avrundningsprecisionen nyligen ändrades.
