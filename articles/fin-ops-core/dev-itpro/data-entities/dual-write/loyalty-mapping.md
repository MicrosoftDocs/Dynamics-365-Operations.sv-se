---
title: Kundförmånskort och belöningspoäng
description: I den här artikeln beskrivs hur du integrerar data om kundförmånskort och belöningspoäng med dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 399682b3042c32fbf6fa200213f1b4982ed97174
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289127"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Kundförmånskort och belöningspoäng

[!include [banner](../../includes/banner.md)]



Företag klassificerar kunder och tillhandahåller sofistikerade tjänster, baserat på kundernas shopping- och utgiftsmönster. Exempelvis har Dynamics 365 Commerce infrastrukturen och funktionerna för att underlätta och hantera kundförmånskort, belöningspoäng, förmånspriser och förmånsbaserade shoppingupplevelser. När data om kundförmånskort och belöningspoäng i Commerce synkroniseras med Dataverse, kan kundengagemangsappar använda dessa data. Exempel: Användare av Dynamics 365 Customer Service kan använda data för att tillhandahålla samma sofistikerade tjänster via supportavdelningen.

## <a name="templates"></a>Mallar

Finance and Operations-appar | Kundengagemangsappar     | beskrivning
|-----------------------------|-----------------------------------|-------------|
[Förmånskort](mapping-reference.md#149) | msdyn_loyaltycards | Den här mallen synkroniserar information om förmånskort. |
[Lojalitetsnivåer](mapping-reference.md#226) | msdyn_loyaltylevels | Den här mallen synkroniserar information om kundbelöningspoäng. |
[Förmånsbelöningspoäng](mapping-reference.md#150) | msdyn_loyaltyrewardpoints | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
