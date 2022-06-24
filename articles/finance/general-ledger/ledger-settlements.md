---
title: Redovisningskvittningar
description: Den här artikeln beskriver hur du använder sidan Redovisningskvittningar för att kvitta redovisningstransaktioner och återföra kvittningar.
author: kweekley
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 39fd6c6677565a4b1e9a9bf6f43a4c630cb5e07b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902499"
---
# <a name="ledger-settlements"></a>Redovisningskvittningar

[!include [banner](../includes/banner.md)]

Redovisningskvittning är processen för att matcha debet- och kredittransaktioner i huvudboken. Kvittningen av debet- och kreditbeloppen används för att stämma av saldot på redovisningskontot med de detaljerade transaktioner som utgör saldot.

Kvittade transaktioner kan utelämnas från förfrågningar och rapporter. På det här sättet är det enklare att analysera de öppna redovisningstransaktioner som utgör saldot på redovisningskontot.

> [!IMPORTANT] 
> Modulerna Leverantörsreskontra (AP) och Kundreskontra (AR) har även avräkning av fakturor och betalningar. När avräkning sker i kundreskontra och leverantörsreskontra, avräknas inte motsvarande redovisningsposter automatiskt.

## <a name="ledger-settlement-features"></a>Funktioner för redovisningskvittning
I Microsoft Dynamics 365 Finance version 10.0.21 har alternativet **Aktivera avancerad redovisningskvittning** tagits bort från sidan **Allmänna redovisningsparametrar**. Avancerad redovisningskvittning är nu alltid aktiverad.
I Ekonomi version 10.0.25, funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** introducerades. Med denna funktion ändras de grundläggande funktionerna vid både redovisningskvittning och stängning av redovisningsmodulen. Innan du aktiverar den här funktionen i arbetsytan **funktionshantering** finns i [Medvetenhet mellan redovisningskvittning och årsbokslut](awareness-between-ledger-settlement-year-end-close.md).

## <a name="set-up-ledger-settlement"></a>Ställa in redovisningskvittning
Du måste välja de huvudkonton som du vill redovisningskvittning för. Det finns två sätt att välja dessa huvudkonton.

1. Gå till **Redovisning** > **Redovisningsinställning** > **Redovisningsparametrar**.
2. På fliken **Redovisningskvittningar** väljer du de kontoplanerna som du vill välja huvudkonton från.
3. Välj huvudkontot att göra redovisningskvittning för. Eftersom kontoplanerna är globala tilldelas alla företag som de valda kontoplanerna tilldelas till samma huvudkonton för redovisningskvittning.

  - eller -

1. Gå till **Redovisning** > **Periodiska uppgifter** > **Redovisningskvittningar**.
2. Välj **redovisningkvittningskonton**.
3. Välj i dialogrutan de kontoplan och huvudkonton som du vill göra redovisningskvittning för. Den här dialogrutan är en genväg. Alla huvudkonton som du lägger till här återspeglas också på sidan **Allmänna redovisningsparametrar**.

Du kan använda samma grundläggande procedurer när du vill ta bort huvudkonton från redovisningskvittning. Borttagningen av ett huvudkonto påverkar inte tidigare redovisningkvittningar. Huvudkontot och transaktionerna visas dock inte längre på sidan **Redovisningkvittning**.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Kvitta transaktioner
Om du vill kvitta redovisningstransaktioner följer du dessa steg.

1. Gå till **Redovisning** > **Periodiska uppgifter** > **Redovisningskvittningar**.
2. Ställ in filtren längst upp på sidan:

    - Välj ett datumintervall. Alternativt kan du välja en datumintervallkod för att automatiskt fylla i datumintervallet. Du bör inte redovisningskvittning för transaktioner som gäller flera räkenskapsår.
    - Ändra bokföringsskiktet efter behov. Du kan inte kvitta transaktioner som finns i olika bokföringsskikt.
    - Om du vill visa huvudkonto och dimensioner separat, välj en uppsättning av ekonomiska dimensioner.

3. Välj **Visa transaktioner** för att visa alla transaktioner som matchar de filter som du anger och listan över konton som du angav när du ställde in listan med kontoplanen i föregående avsnitt.

    - Om du ändrar något av filtren eller dimensionsuppsättningarna måste du markera **Visa transaktioner** igen.
    - Om du vill filtrera transaktionerna till ett enskilt huvudkonto använder du filtret i fältet **Redovisningskonto**. Vi rekommenderar inte att du kvittar redovisningen för transaktioner som bokförs på olika huvudkonton.

4. Markera rader för kvittning. Värdet på fältet **markerade belopp** längst upp på sidan höjs eller sänks med för att återspegla det totala beloppet på de valda raderna.
5. När du är klar med att välja transaktioner väljer du **Markera valda**. För varje vald transaktion visas en bockmarkering i kolumnen **Markerad**. Dessutom ökar eller minskar värdet på fältet **markerat belopp** ovanför rutnätet ökar eller minskar för att återspegla den totala mängden på de markerade raderna.
6. När värdet i fältet **markerade belopp** är **0** (noll), välj **Kvitta markerade transaktioner**. Status för de markerade transaktionerna uppdateras till **Kvittad**.

    > [!IMPORTANT]
    > Alla transaktioner som du har markerat för kvittning för den aktiva juridiska personen kvittas, även om de inte visas på sidan Redovisningskvittning eftersom du har använt ett filter.

## <a name="make-transactions-easier-to-find"></a>Göra det lättare att hitta transaktioner
Sidan **Redovisningskvittningar** innehåller funktioner som gör det lättare att visa de transaktioner som behövs för kvittning.

- Använd filtret **Markerade** låter dig filtrera transaktioner utifrån om kryssrutan **Markerade** har markerats för dem.
- Använd filtret **Status** för att filtrera transaktioner utifrån deras status.
- Välj **Sortera efter absolut belopp** om du vill sortera beloppen efter absolut värde. På det här sättet kan du gruppera debet- och kredit som har samma belopp.

## <a name="reverse-a-settlement"></a>Återföra en kvittning
Du kan återföra en kvittning som har gjorts av misstag.

1. Följ stegen 1 till 3 i avsnittet [Kvitta transaktioner](#settle-transactions) för att visa de transaktioner som du är intresserad av.
2. I fältet **Status** markerar du **Kvittad**.
3. Markera rader för återföring.
4. Välj **Återför markerade transaktioner**. Statusvärdet för alla transaktioner som har samma kvittnings-ID uppdateras till **Inte kvittad**.

    > [!IMPORTANT]
    > Alla transaktioner som har samma kvittnings-ID återförs, även om de inte är markerade. Till exempel har fyra rader markerats och kvitterats. Alla fyra raderna har samma kvittnings-ID. Om du markerar en av dessa fyra rader och sedan väljer **Återföra markerade transaktioner** kommer alla fyra raderna att återföras.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
