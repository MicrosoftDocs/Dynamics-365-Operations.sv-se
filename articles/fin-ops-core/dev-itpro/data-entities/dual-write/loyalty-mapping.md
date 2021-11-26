---
title: Kundförmånskort och belöningspoäng
description: I det här avsnittet beskrivs hur du integrerar data om kundförmånskort och belöningspoäng med dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 919ce0d57fb306b39cdcdd8655ac9f0b9e26847e
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781674"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Kundförmånskort och belöningspoäng

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Företag klassificerar kunder och tillhandahåller sofistikerade tjänster, baserat på kundernas shopping- och utgiftsmönster. Exempelvis har Dynamics 365 Commerce infrastrukturen och funktionerna för att underlätta och hantera kundförmånskort, belöningspoäng, förmånspriser och förmånsbaserade shoppingupplevelser. När data om kundförmånskort och belöningspoäng i Commerce synkroniseras med Dataverse, kan kundengagemangsappar använda dessa data. Exempel: Användare av Dynamics 365 Customer Service kan använda data för att tillhandahålla samma sofistikerade tjänster via supportavdelningen.

## <a name="templates"></a>Mallar

Finance and Operations-appar | Kundengagemangsappar     | beskrivning
|-----------------------------|-----------------------------------|-------------|
[Förmånskort](mapping-reference.md#149) | msdyn_loyaltycards | Den här mallen synkroniserar information om förmånskort. |
[Lojalitetsnivåer](mapping-reference.md#226) | msdyn_loyaltylevels | Den här mallen synkroniserar information om kundbelöningspoäng. |
[Förmånsbelöningspoäng](mapping-reference.md#150) | msdyn_loyaltyrewardpoints | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
