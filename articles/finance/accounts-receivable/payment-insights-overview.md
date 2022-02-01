---
title: Customer payment insights (förhandsversion)
description: I det här ämnet beskrivs funktioner för betalningsinsikter som hjälper dig att bättre förstå en enskild kunds typiska betalningspraxis. Funktionen kan också hjälpa dig att identifiera omständigheter gör att du bör starta inkassoprocesser tidigare än vad du annars skulle ha gjort.
author: ShivamPandey-msft
ms.date: 11/06/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: d359e3ceef0fb7213d52aeb265da2e75120ae223
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984012"
---
# <a name="customer-payment-insights-preview"></a>Customer payment insights (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här ämnet beskrivs funktioner för betalningsinsikter som hjälper dig att bättre förstå en enskild kunds typiska betalningspraxis. Funktionen kan också hjälpa dig att identifiera omständigheter gör att du bör starta inkassoprocesser tidigare än vad du annars skulle ha gjort. 

## <a name="overview"></a>Översikt

Det kan vara svårt att förutsäga när en kund kommer att betala sina fakturor. Den här bristen på insyn leder till mindre korrekta kassaflödesprognoser, inkassoprocesser som startar för sent och order som kan levereras som standard till kunder. Kundbetalningsinsikter (förhandsversion) hjälper organisationer att förutsäga när en kundfaktura kommer att betalas. Denna information kan hjälpa organisationer att skapa inkassostrategier som förbättrar sannolikheten för att bli betald i tid. 

## <a name="predictions"></a>Förutsägelser

Med hjälp av betalningsförutsägelserna kan organisationerna förbättra sina affärsprocesser genom att hjälpa dem att enkelt identifiera fakturor som sannolikt kommer att betalas sent och vidta lämpliga åtgärder som förbättrar deras chans att bli betalda i tid.

Genom att använda en modell för maskininlärning som används för historiska fakturor, betalningar och kunddata, Customer Payment Insights (förhandsversion), förutsägs mer noggrant när en kund betalar en utestående faktura.

Kundbetalningsinsikter (förhandsversion) kan förutsäga tre sannolikheter för betalning för varje öppen faktura:

-   Sannolikhet för att betalningen görs i tid 
-   Sannolikhet för att betalningen görs sent
-   Sannolikhet för att betalningen görs mycket sent

Kundbetalningsinsikter (förhandsversion) tillhandahåller en aggregerad vy över förväntade betalningar, vilket kan hjälpa organisationer att första det totala betalningsbelopp de kan förvänta sig från en kund i en av tre buckets, I tid, Sent och Mycket sent.

[![Samlad vy över betalningsförutsägelser.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Dessutom tilldelas varje faktura en sannolikhet för betalning i tid. Om sannolikheten för betalning i tid är mindre än 50 %, är fakturorna taggade med en röd cirkel för att indikera att dessa fakturor kräver inkassouppmärksamhet. 

[![Lista över sannolikhet för betalning.](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Customer Payment Insights (förhandsversion) innehåller också sammanhangsbaserad information för att förklara förutsägelsen, t.ex. de främsta faktorer som påverkar förutsägelser, aktuell status för affärsverksamhet med kunden och detaljer om historiska kundbetalningar. I många företag har inkassoprocessen varit en reaktiv aktivitet. Inkassoprocessen startar inte förrän fakturorna förfaller. 

Med Customer Payment Insights (förhandsversion) kan organisationer vara mer proaktiva om inkasso. De behöver inte längre vänta på att transaktionerna ska bli klara för att inleda inkassoprocessen. I stället kan de använda funktionen betalningsförutsägelse för att avgöra om proaktiv inkasso förbättrar sannolikheten för att få betalt i tid. Med betalningsförutsägelse får företag också den information som behövs för att motivera inledningen av inkassoprocessen tidigt.

## <a name="methodology"></a>Metod

Det är svårt att utveckla och distribuera en AI-lösning. Det krävs ett team med dataforskare, ämnesexperter och tekniker som arbetar under en längre tid för att formulera, utveckla, distribuera och underhålla en användbar AI-lösning. Vi gör det enkelt att driftsätta och använda AI-lösningar i Finance. Vi har förpackade AI-lösningar i Finance som byggts ovanpå Microsoft AI Builder. En slutanvändare kan med knappen bara klicka på och distribuera AI-lösningen och börja använda fördelarna med intelligenta förutsägelser. Om en organisation inte är nöjd med noggrannheten i förutsägelser kan en priviligierad användare, med hjälp av ett enda klick, gå in i tillägget AI Builder och sedan markera eller avmarkera fälten som används för att generera förutsägelser. När de är klara kan de utbilda och publicera ändringarna och den nyutbildade modellen hämtas automatiskt för förutsägelser i Finance.

## <a name="how-to-get-customer-payment-insights-preview"></a>Hur du skaffar Customer Payment Insights (förhandsversion)

Skicka e-post till [Kundbetalningsinsikter (förhandsversion)](mailto:fiap@microsoft.com) om du vill testa Kundbetalningsinsikter (förhandsversion).

## <a name="privacy-notice"></a>Sekretesspolicy

Förhandsgranskningar (1) kan dessutom använda mindre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations (2) ingår inte i servicenivåavtalet för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterföljande krav, samt (4) har begränsad support.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]