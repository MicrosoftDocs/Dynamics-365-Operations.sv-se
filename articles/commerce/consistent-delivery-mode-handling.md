---
title: Aktivera konsekvent hantering av leveranssätt i näthändelskanaler
description: I det här avsnittet beskrivs hur du aktiverar konsekvent hantering av leveranssätt för att hantera möjliga problem relaterade till avgiftsflöden i Microsoft Dynamics 365 Commerce-näthandelskanaler.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 4cecd70dacd72572afc8e6cb65530bf2be4cc93d
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349965"
---
# <a name="enable-consistent-delivery-mode-handling-in-e-commerce-channels"></a>Aktivera konsekvent hantering av leveranssätt i näthändelskanaler 

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du aktiverar konsekvent hantering av leveranssätt för att hantera möjliga problem relaterade till avgiftsflöden i Microsoft Dynamics 365 Commerce-näthandelskanaler.

I Dynamics 365 Commerce tillämpas icke-proportionerliga huvudnivåavgifter inte som standard i näthändelskanaler. Detta beteende kan orsaka ett eller båda av följande problem i näthändelskanaler:

- Icke-prportionerliga avgifter på huvudnivå visas inte.
- Tilläggen för leveranssätten är inte konsekvent mellan leveransurvalet och sammanfattningen av utcheckningsordern.

Du löser de här problemen genom att aktivera funktionen **Aktivera konsekvent hantering av leveranssätt i kanal**. Den här funktionen säkerställer att icke-proportionerliga tillägg på huvudnivå visas i näthändelskanaler och att leveransinformationen för försäljningsorder hanteras på ett konsekvent sätt i samma arbetsflöde för förfrågningar.

## <a name="turn-on-the-enable-consistent-delivery-mode-handling-in-channel-feature"></a>Aktivera konsekvent hantering av leveranssätt i kanalfunktionen

Aktivera funktionen **Aktivera konsekvent hantering av leveransläge i kanal** i Commerce-administrationen genom att följa dessa steg.

1. Öppna arbetsytan **Funktionshantering** (**Systemadministration \> Arbetsytor \> Funktionshantering**).
1. Sök efter och välj **Aktivera konsekvent leveranssättshantering i kanal** i listan med tillgängliga funktioner.
1. Välj **Aktivera nu** i höger fönster.
