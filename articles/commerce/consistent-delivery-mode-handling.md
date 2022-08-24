---
title: Aktivera konsekvent hantering av leveranssätt i näthandelskanaler
description: I denna artikel beskrivs hur du aktiverar konsekvent hantering av leveranssätt för att hantera möjliga problem relaterade till avgiftsflöden i Microsoft Dynamics 365 Commerce-näthandelskanaler.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 43450c9d380bd57c234bb1c9acfbe296ab115f14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279661"
---
# <a name="enable-consistent-delivery-mode-handling-in-e-commerce-channels"></a>Aktivera konsekvent hantering av leveranssätt i näthandelskanaler 

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du aktiverar konsekvent hantering av leveranssätt för att hantera möjliga problem relaterade till avgiftsflöden i Microsoft Dynamics 365 Commerce-näthandelskanaler.

I Dynamics 365 Commerce tillämpas icke-proportionerliga huvudnivåavgifter inte som standard i näthändelskanaler. Detta beteende kan orsaka ett eller båda av följande problem i näthändelskanaler:

- Icke-prportionerliga avgifter på huvudnivå visas inte.
- Tilläggen för leveranssätten är inte konsekvent mellan leveransurvalet och sammanfattningen av kassaordern.

Du löser de här problemen genom att aktivera funktionen **Aktivera konsekvent hantering av leveranssätt i kanal**. Den här funktionen säkerställer att icke-proportionerliga tillägg på huvudnivå visas i näthändelskanaler och att leveransinformationen för försäljningsorder hanteras på ett konsekvent sätt i samma arbetsflöde för förfrågningar.

## <a name="turn-on-the-enable-consistent-delivery-mode-handling-in-channel-feature"></a>Aktivera konsekvent hantering av leveranssätt i kanalfunktionen

Aktivera funktionen **Aktivera konsekvent hantering av leveransläge i kanal** i Commerce headquarters genom att följa dessa steg.

1. Öppna arbetsytan **Funktionshantering** (**Systemadministration \> Arbetsytor \> Funktionshantering**).
1. Sök efter och välj **Aktivera konsekvent leveranssättshantering i kanal** i listan med tillgängliga funktioner.
1. Välj **Aktivera nu** i höger fönster.
