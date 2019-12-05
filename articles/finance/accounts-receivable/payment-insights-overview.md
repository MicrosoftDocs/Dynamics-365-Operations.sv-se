---
title: Customer payment insights (förhandsversion)
description: I det här avsnittet beskrivs de möjligheter till betalningsinsikter som hjälper till att förbättra förståelsen av enskilda kunders typiska betalningspraxis och kan identifiera omständigheter som motiverar inledande insamlingsprocesser tidigare än vad du har gjort.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774050"
---
# <a name="customer-payment-insights-preview"></a>Customer payment insights (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs de möjligheter till betalningsinsikter som hjälper till att förbättra förståelsen av enskilda kunders typiska betalningspraxis och kan identifiera omständigheter som motiverar inledande insamlingsprocesser tidigare än vad du har gjort. 

## <a name="overview"></a>Översikt

Organisationer finner det ofta svårt att förutsäga när en kund betalar sina fakturor. Den här bristen på insyn leder till mindre korrekta kassaflödesprognoser, inkassoprocesser som startar för sent och order som kan levereras som standard till kunder. Customer Payment Insights (förhandsversion) hjälper organisationer att förutse när en kundfaktura kommer att betalas, vilket hjälper organisationen att skapa insamlingsstrategier som förbättrar sannolikheten för att betalas i tid. 

## <a name="predictions"></a>Förutsägelser

Med hjälp av betalningsförutsägelserna kan organisationerna förbättra sina affärsprocesser genom att hjälpa dem att enkelt identifiera fakturor som sannolikt kommer att betalas sent och vidta lämpliga åtgärder som förbättrar deras chans att bli betalda i tid.

Genom att använda en modell för maskininlärning som används för historiska fakturor, betalningar och kunddata, Customer Payment Insights (förhandsversion), förutsägs mer noggrant när en kund betalar en utestående faktura.

Customer Payment Insights (förhandsversion) förutsäger tre sannolikheter för betalning för respektive faktura:

-   Sannolikhet för att betalningen görs i tid 
-   Sannolikhet för att betalningen görs sent
-   Sannolikhet för att betalningen görs mycket sent

För att hjälpa organisationer att förstå det totala betalningsbeloppet som de kan förvänta sig från en kund i en av de tre grupper, i tid, sent och mycket sent, innehåller Customer Payment Insights (förhandsversion) också en sammansatt vy med förväntade betalningar.

[![Aggregerad vy över betalningsförutsägelser](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Dessutom tilldelas varje faktura en sannolikhet för betalning i tid. Om sannolikheten för betalning i tid är mindre än 50 %, är fakturorna taggade med en röd cirkel för att indikera att dessa fakturor kräver inkassouppmärksamhet. 

[![Lista över sannolikhet för betalning](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Customer Payment Insights (förhandsversion) innehåller också sammanhangsbaserad information för att förklara förutsägelsen, t.ex. de främsta faktorer som påverkar förutsägelser, aktuell status för affärsverksamhet med kunden och detaljer om historiska kundbetalningar. I många företag har inkassoprocessen varit en reaktiv aktivitet. Inkassoprocessen startar inte förrän fakturorna förfaller. 

Med Customer Payment Insights (förhandsversion) kan organisationer vara mer proaktiva om inkasso. De behöver inte längre vänta på att transaktionerna ska bli klara för att inleda inkassoprocessen. I stället kan de använda funktionen betalningsförutsägelse för att avgöra om proaktiv inkasso förbättrar sannolikheten för att få betalt i tid. Med betalningsförutsägelse får företag också den information som behövs för att motivera inledningen av inkassoprocessen tidigt.

## <a name="methodology"></a>Metod

Det är svårt att utveckla och distribuera en AI-lösning. Det krävs ett team med dataforskare, ämnesexperter och tekniker som arbetar under en längre tid för att formulera, utveckla, distribuera och underhålla en användbar AI-lösning. Vi gör det enkelt att driftsätta och använda AI-lösningar i Finance. Vi har förpackade AI-lösningar i Finance som byggts ovanpå Microsoft AI Builder. En slutanvändare kan med knappen bara klicka på och distribuera AI-lösningen och börja använda fördelarna med intelligenta förutsägelser. Om en organisation inte är nöjd med noggrannheten i förutsägelser kan en priviligierad användare, med hjälp av ett enda klick, gå in i tillägget AI Builder och sedan markera eller avmarkera fälten som används för att generera förutsägelser. När de är klara kan de utbilda och publicera ändringarna och den nyutbildade modellen hämtas automatiskt för förutsägelser i Finance.

## <a name="how-to-get-customer-payment-insights-preview"></a>Hur du skaffar Customer Payment Insights (förhandsversion)

Skicka e-post till [Customer Payment Insights (förhandsversion)](mailto:fiap@microsoft.com) om du vill testa Customer Payment Insights (förhandsversion).

## <a name="privacy-notice"></a>Sekretesspolicy

Förhandsversioner (1) kan dessutom använda mindre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations de (2) ingår inte i servicenivåavtalet för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterföljande krav, samt (4) har begränsad support.


