---
title: Kundförmånskort och belöningspoäng
description: I det här avsnittet beskrivs hur du integrerar data om kundförmånskort och belöningspoäng med dubbelriktad skrivning.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 39e1d5b0a73b198b164e51a18222dbd985192070
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568038"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Kundförmånskort och belöningspoäng

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Företag klassificerar kunder och tillhandahåller sofistikerade tjänster, baserat på kundernas shopping- och utgiftsmönster. Exempelvis har Dynamics 365 Commerce infrastrukturen och funktionerna för att underlätta och hantera kundförmånskort, belöningspoäng, förmånspriser och förmånsbaserade shoppingupplevelser. När data om kundförmånskort och belöningspoäng i Commerce synkroniseras med Dataverse, kan kundengagemangsappar använda dessa data. Exempel: Användare av Dynamics 365 Customer Service kan använda data för att tillhandahålla samma sofistikerade tjänster via supportavdelningen.

## <a name="templates"></a>Mallar

| Finance and Operations-appar | Modellstyrda appar i Dynamics 365 | beskrivning |
|-----------------------------|-----------------------------------|-------------|
| Förmånskort                | msdyn\_loyaltycards               | Den här mallen synkroniserar information om förmånskort. |
| Förmånsbelöningspoäng       | msdyn\_loyaltyrewardpoints        | Den här mallen synkroniserar information om kundbelöningspoäng. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]