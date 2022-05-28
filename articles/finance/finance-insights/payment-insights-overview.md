---
title: Kundbetalningsförutsägelser
description: I det här ämnet beskrivs funktioner för betalningsförutsägelse som kan hjälpa dig att bättre förstå en kunds typiska betalningspraxis. Den här funktionen kan också hjälpa till att identifiera omständigheter som gör att du kan starta inkassoprocesser tidigare än vad du annars skulle kunna starta.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f3d6f328ff3fd4da6ad3e7d4f3f751d3be692736
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713202"
---
# <a name="customer-payment-predictions"></a>Kundbetalningsförutsägelser

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs funktioner för betalningsförutsägelse som kan hjälpa dig att bättre förstå en kunds typiska betalningspraxis. Den här funktionen kan också hjälpa till att identifiera omständigheter som gör att du kan starta inkassoprocesser tidigare än vad du annars skulle kunna starta.

## <a name="overview"></a>Översikt

Organisationer finner det ofta svårt att förutsäga när en kund betalar sina fakturor. Denna bristande insikt kan orsaka följande problem:

- Mindre korrekta kassaflödesprognoser
- Inkassoprocesser som startar alltför sent
- Order som har frisläppts till kunder som kanske inte kommer att betala

Prediktioner av kundbetalning hjälper organisationer att förutsäga när en kundfaktura kommer att betalas. Därför kan de skapa inkassostrategier som ökar sannolikheten för att de ska betalas i tid.

## <a name="predictions"></a>Förutsägelser

Med hjälp av betalningsförutsägelser kan organisationer förbättra sina affärsprocesser genom att hjälpa dem att identifiera de fakturor som sannolikt kommer att betalas sent. Organisationen kan använda den informationen för att förbättra chanserna att de kommer att betalas i tid.

Funktionen Prediktioner av kundbetalning använder en maskininlärningsmodell för att mer korrekt förutsäga när en kund kommer att betala en utestående faktura. Den här maskininlärningsmodellen inkluderar historiska fakturor, betalningar och kunddata.

För varje öppen faktura tilldelar funktionen tre betalningssannolikheter:

- Sannolikheten för att betalningen ska göras i tid
- Sannolikheten för att betalningen ska göras sent
- Sannolikheten för att betalningen ska göras mycket sent

Funktionen tillhandahåller även en aggregerad vy över förväntade betalningar.

[![Samlad vy över betalningsförutsägelser.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Varje faktura tilldelas en sannolikhet för betalning i tid. Fakturor som har en sannolikheten för betalning i tid som är mindre än 50 procent taggas med en röd cirkel för att indikera att de kanske kräver uppmärksamhet från inkassohandläggare.

[![Lista över sannolikhet för betalning.](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Funktionen Prediktioner av kundbetalning ger också sammanhangsbaserad information för att förklara förutsägelsen. Den här informationen omfattar de viktigaste faktorer som påverkar förutsägelsen, det aktuella företagets affärsstatus och information om kundens historiska betalningsbeteende.

I många företag har inkassoprocessen varit en reaktiv aktivitet. Det innebär att inkassoprocessen inte startar förrän fakturorna förfaller. Med Prediktioner av kundbetalning kan organisationer vara mer proaktiva om inkasso. De behöver inte längre vänta på en transaktion ska förfalla för att inleda inkassoprocessen. I stället kan de använda funktionen för betalningsförutsägelse för att avgöra om proaktiv inkasso förbättrar sannolikheten för att de ska få betalt i tid.

## <a name="methodology"></a>Metod

Tidigare har det vanligtvis varit svårt att utveckla och distribuera en AI-lösning (artificiell intelligens). Processen krävde ett team med dataforskare, ämnesexperter (SME:er) och tekniker som arbetar under en längre tid för att formulera, utveckla, distribuera och underhålla en användbar AI-lösning. Prediktioner av kundbetalning gör det enkelt att distribuera och använda en AI-lösning i Microsoft Dynamics 365 Finance. Microsoft förförpackar AI-lösningar som byggts ovanpå Microsoft AI Builder. Därför kan användarna distribuera AI-lösningen med en enda musklickning för att dra nytta av fördelarna med intelligenta förutsägelser. Om du inte är nöjd med noggrannheten i förutsägelser kan en priviligierad användare (återigen med ett enda musklick) gå in i AI Builder-tilläggsupplevelsen och sedan markera eller avmarkera fälten som används för att generera förutsägelser. När du är klar kan du "träna" modellen och publicera ändringarna. Den nyligen tränade modellen hämtas automatiskt för att generera förutsägelser i Dynamics 365 Finance.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
