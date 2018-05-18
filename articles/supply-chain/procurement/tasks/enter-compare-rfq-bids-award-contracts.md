--- 
title: "Ange och jämför anbudsförfråganbud och tilldela kontrakt"
description: "Den här proceduren visar dig hur du anger svar på en anbudsförfrågan, poäng och jämför bud, och sedan tilldelar budet till en av leverantörerna."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5dea9d7bfb1bf7b11f6c49cccaab1b73d4e58d16
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Ange och jämför anbudsförfråganbud och tilldela kontrakt

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar dig hur du anger svar på en anbudsförfrågan, poäng och jämför bud, och sedan tilldelar budet till en av leverantörerna. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Innan du startar måste du ha en anbudsförfrågan med två rader som har skickats till minst två leverantörer. Du kan köra proceduren ”Skapa en anbudsförfrågan” som en förutsättning för att skapa detta. Du måste ha ställt in ett poängkriterium innan du kan köra den här proceduren.


## <a name="enter-a-reply-from-a-vendor"></a>Ange ett svar från en leverantör
1. Gå till Anskaffning och källa > Anbudsförfrågningar > Alla anbudsförfrågningar.
2. Välj en anbudsförfrågan som har statusen Skickad och klicka på länken på Ärendenummer på anbudsförfrågan.
    * Anbudsförfrågan ska ha skickats till minst 2 leverantörer.  
3. Klicka på Rubrik om du vill gå till listan över leverantörer.
4. +Markera leverantören som du vill ange för ett svar på anbudsförfrågan.
5. Klicka på Ange svar.
6. Klicka på Svar i åtgärdsfönstret.
7. Klicka på Kopiera data för att svara.
    * Denna åtgärd kommer att kopiera valda data, till exempel kvantiteten från anbudsförfrågansärendet till svaret på anbudsförfrågan. Alternativt kan du hoppa över den här åtgärden och fylla i alla svarfälten manuellt när du redigerar svaret.  
8. Klicka på Redigera.
9. Ange ett tal i fältet Enhetspris.
10. Välj den andra offertraden.
11. Ange ett tal i fältet Enhetspris.

## <a name="score-the-bid"></a>Poängsätt budet
1. Klicka på Rubrik om du vill gå till budets poäng.
2. Visa avsnittet Poängsättning av bud.
3. Ange ett nummer för ett av poängkriterierna i fältet Poäng.
    * Om du hovrar över en av poängkriterierna visar en knappbeskrivning det intervall som poängen måste vara i. I denna demonstration kan du lägga till ett värde på mellan 1 och 5 till något av kriterierna.  
4. Välj ett annat poängkriterium.
5. Ange ett nummer i fältet Poäng.
6. Visa avsnittet Enkäter.
    * Om anbudsförfråganfallet har en enkät som skickats till leverantörerna, kan du ange sina svar i avsnittet Enkäter.  
7. Stäng sidan.

## <a name="enter-a-reply-for-another-vendor"></a>Ange ett svar för en annan leverantör
1. Välj nästa leverantör genom att avmarkera den leverantör som du precis har angett svaret för och välj sedan raden för nästa leverantör.
2. Hitta och markera önskad post i listan.
3. Klicka på Ange svar.
4. Klicka på Kopiera data för att svara.
5. Klicka på Redigera.
6. Ange ett tal i fältet Enhetspris.
7. Välj den andra offertraden.
8. Ange ett tal i fältet Enhetspris.

## <a name="score-the-second-bid"></a>Poängsätt det andra budet
1. Klicka på Rubrik om du vill gå till budets poäng.
2. Ange ett nummer i fältet Poäng.
3. Hitta och markera önskad post i listan.
4. Ange ett nummer i fältet Poäng.

## <a name="compare-the-replies"></a>Jämför svaren
1. Klicka på Allmänt i åtgärdsfönstret.
2. Klicka på Jämför svar.
3. Ange ett nummer i fältet Rangordning.
    * På den här sidan visas buden med rubriken och raderna och den totala på poängen på rubriknivån. Du kan jämföra raderna genom att sortera i rutnätet så att jämförbara rader finns bredvid varandra. Informationen innehåller även: Kvantitet: Den kvantitet som anges av leverantören. Detta kanske inte är lika med kvantiteten som specificerats i anbudsförfrågan.   Nettobelopp: priset som anges av en leverantör, att betala av eventuella rabatter, för artiklarna på raden.   Avvikelse: Antal dagar som leveransdatumet i budhuvud eller raden avviker från det begärda leveransdatumet i huvudet för anbudsförfrågan eller anbudsförfråganraden.   Du kan ange en ranking för varje bud.  
4. Välj rubrikrad för det andra budet som du vill rangordna.
5. Ange ett nummer i fältet Rangordning.
6. Klicka på Spara.

## <a name="reject-a-bid"></a>Avvisa ett bud
1. Välj rubrikrad för det budet som du vill avvisa.
    * Du kan bara godkänna, avvisa eller returnera ett bud eller rader inom ett bud i taget.  
2. Markera kryssrutan Markera.
    * Om du väljer Markera kryssrutan i budets Rubrik kommer även alla rader att markeras. Du kan också välja att markera en deluppsättning av raderna i budet om du vill avvisa eller godkänna dessa. Det går att acceptera en leverantörs bud för alla rader i en anbudsförfrågan och sedan tilldela andra anbudsförfrågansrader till en annan leverantör, men du måste göra detta i 2, ett bud i taget. Du kan bara godkänna antingen originalanbudsraden eller dess alternativ, men inte båda, om det finns alternativa rader.  
3. Klicka på Avvisa.
4. Klicka på Parametrar för att öppna dialogrutan.
5. Ange eller välj ett värde i fältet Orsak för avvisande.
    * Skälet till avvisande kommer att lagras på svaret.  
6. Klicka på OK.
7. Klicka på OK.
8. Stäng sidan.
9. Stäng sidan.
10. Uppdatera sidan.

## <a name="accept-a-bid"></a>Acceptera ett bud
1. Välj budet som du vill godkänna och klicka sedan på länken i fältet Anbudsförfrågan.
2. Klicka på Svar i åtgärdsfönstret.
3. Klicka på Godkänn.
    * Om du har valt specifika rader och inte andra kommer åtgärden godkänn endast att inkludera de markerade raderna. Om du vill godkänna alla rader på budet behöver du inte markera raderna.  
4. Klicka på Parametrar för att öppna dialogrutan.
    * På så sätt kan du registrera en orsak till att godkänna budet. Skälet till avvisande kommer att lagras på svaret.  
5. Ange eller välj ett värde i fältet Orsak till godkännande.
6. Klicka på OK.
7. Klicka på OK.
    * När du klickar på OK genererar detta en inköpsorder baserat på de rader som ingår i godkännandet av anbudsförfrågan. Om det finns andra bud som inte har bearbetats (godkända, avvisade eller returnerade) kommer systemet att uppmana dig att avvisa de återstående buden.  

## <a name="view-the-purchase-order-thats-been-generated"></a>Visa den inköpsorder som har genererats
1. Klicka på Allmänt i åtgärdsfönstret.
2. Klicka på Inköpsorder.
    * Här kan du se inköpsordern som genererades, när du godkände budet.  
3. Stäng sidan.
4. Stäng sidan.
5. Stäng sidan.
6. Stäng sidan.


