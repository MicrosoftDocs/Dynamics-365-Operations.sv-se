---
title: Ange och jämför anbudsförfråganbud och tilldela kontrakt
description: Det här ämnet förklarar hur du anger svar på en anbudsförfrågan (RFQ), poäng och jämför bud, och sedan tilldelar kontraktet till en av leverantörerna.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable, PurchTablePart, PurchRFQCompareLinePrices, PurchRFQCompareRFQ
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae7c43516fc90224439f6f7cfd5fd0a6058e8b39
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438097"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Ange och jämför anbudsförfråganbud och tilldela kontrakt

[!include [banner](../../includes/banner.md)]

Det här ämnet förklarar hur du anger svar på en anbudsförfrågan (RFQ), poäng och jämför bud, och sedan tilldelar kontraktet till en av leverantörerna. Du kan använda den här proceduren i demonstrationsdataföretaget **USMF**.

Innan du startar proceduren måste du ha en anbudsförfrågan med två rader som har skickats till minst två leverantörer. Om du vill skapa en anbudsförfrågan slutför du proceduren [skapa en anbudsförfrågan](create-request-quotation.md). Poängkriterier måste också ställas in innan du kan slutföra den här proceduren.

Du kan ange budet som antingen leverantör eller anskaffningsproffs. Mer information finns i [Ställa in och underhålla leverantörssamarbete](../set-up-maintain-vendor-collaboration.md).

## <a name="enter-a-reply-as-a-vendor"></a>Ange ett svar som leverantör

1. På instrumentpanelen väljer du **Budgivning av leverantör**.
2. I listan **Nya budinbjudningar**, hitta en anbudsförfrågan som precis skickades. Välj anbudsförfrågan som ska granskas efter önskemål.
3. Markera **bifogade anbudsförfrågan** för att granska bilagor som har lagts till.
4. Välj **bud** om du vill göra fälten redigerbara. Observera att fältet **budförlopp** är inställt **leverantören uppdaterar**.
5. Ange värden från anbudssvaret i rubriken och raderna.
6. Om bilagor ska läggas till i budet väljer **Budbilagor**
7. Välj snabbfliken **Objekt i riktlinjer för budgivning** för att visa om ett dokument krävs.
8. Välj snabbfliken **ändringar** för att visa om anbudsförfrågan har ändrats.
9. På snabbfliken **Enkät**. Alla enkäter som visas här måste besvaras.
10. Välj snabbfliken **radinformation** om du vill visa utökad information om raden.
11. Välj endast **Återställ från anbudsförfrågan** om du måste återställa de värden som har angetts för de ursprungliga värdena för anbudsförfrågan.
12. Du kan spara buden när som helst och göra ytterligare bearbetning senare under förutsättning att utgångsdatum och tid inte har passerat. I det här fallet kan du hitta budet i **Pågående bud** i arbetsytan **Budgivning av leverantör**.
13. När budet är klart att skickas väljer du **Skicka**. Om du inte vill lägga ett bud väljer du **Avslå**. Inskickade bud finns tillgängliga i listan **Skickade bud** i arbetsytan **leverantörens budgivning**.  
14. När budet har lämnats in kan du när som helst återkalla det före utgångsdatum och-tid. Observera att när ett budet återkallas, behandlas det inte som skickat. När budet accepteras eller avvisas av anskaffningsavdelningen visas det antingen i listan **Beviljade bud** eller **Förlorade bud** i arbetsytan **leverantörens budgivning**.  

## <a name="enter-a-reply-from-a-vendor-as-a-procurement-professional"></a>Ange ett svar från en leverantör som ett anskaffningsproffs

1. Kontrollera att behörigheten för att redigera leverantörsbudet har ställts in. Gå till **Anskaffning och källa \> Inställningar \> Anskaffnings- och källparametrar**. På fliken **Anbudsförfrågan**, ange alternativet **Köparen kan redigera leverantörens bud** till **Ja**.
2. Gå till **Anskaffning och källa \> Anbudsförfrågningar \> Alla anbudsförfrågningar**.
3. Välj en anbudsförfrågan som har statusen **Skickad** och välj sedan länken i fältet **Ärende i anbudsförfrågan**.
4. Välj **Hantera svar**. Sidan som visas visar en anbudsförfrågan för varje leverantör som är inbjuden att lägga ett bud.
5. Välj en anbudsförfrågan som inte har besvarats. (Fältet **svarsförlopp** ska anges till **ej startat**.)
6. Välj **Redigera \> Redigera svar på anbudsförfrågan**. Sidan **Svar på anbudsförfrågan** visas. Som inköpsproffs kan du nu ange svaret på uppdrag av leverantören. Observera att fältet **budförlopp** är inställt **inköparen uppdaterar**.  
7. Ange buddata. Välj **Skicka** när du är klar.

## <a name="score-the-bids"></a>Poängsätt bud

1. På sidan **Alla anbudsförfrågningar** väljer du det ärende för anbudsförfrågan som du vill att poäng ska besvaras.
2. Välj **Hantera svar**.
3. Markera svaret att poängsätta.
4. Välj **rubrik** så att du kan se poängen för budet.
5. På snabbfliken **Poängsättning av bud**, ange ett nummer i fältet **Poäng** för ett av poängsättningskriterierna. Om du hovrar över en av poängkriterierna visar en knappbeskrivning det intervall som poängen måste vara i. I denna demonstration kan du ange ett nummer mellan 1 och 5 för något av kriterierna.  
6. Upprepa steg 5 för ett annat poängsättningskriterium.
7. Om anbudsförfråganfallet har en enkät som skickats till leverantörerna, kan du ange leverantörens svar på snabbfliken **Enkäter**.
8. Stäng sidan.
9. Upprepa steg 1 till och med 8 för alla andra bud.

## <a name="compare-the-replies"></a>Jämför svaren

1. Välj **Jämför svar** på fliken **Allmänt** i åtgärdsfönstret.
2. I fältet **Rangordning** anger du ett nummer.  
    - På den här sidan visas buden med rubriken och radinformationen och den totala på poängen på rubriknivån. Du kan jämföra raderna genom att sortera i rutnätet så att jämförbara rader finns bredvid varandra. I det här avsnittet ingår även följande information:
    - **Kvantitet** - Kvantiteten som leverantören angav. Denna kvantitet kanske inte är lika med kvantiteten som specificerats i anbudsförfrågan.
    - **Nettobelopp**: priset som anges av en leverantör för artiklarna på raden minus eventuella rabatter.
    - **Avvikelse**: Antal dagar som leveransdatumet i budhuvud eller raden avviker från det begärda leveransdatumet i huvudet för anbudsförfrågan eller anbudsförfråganraden. Du kan ange en ranking för varje bud.  
3. Välj rubrikrad för det andra budet som du vill rangordna.
4. I fältet **Rangordning** anger du ett nummer.
5. Välj **Spara**.

## <a name="reject-a-bid"></a>Avvisa ett bud

1. Välj rubrikrad för det budet som du vill avvisa. Du kan bara godkänna, avvisa eller returnera ett bud eller raderna på ett bud i taget.
2. Markera kryssrutan **Markera**.  
    - Om du väljer kryssrutan **Markera** i budets rubrik kommer även alla rader att markeras. Om du bara vill avvisa eller acceptera några av raderna i budet markerar du enbart dessa rader. Du kan dessutom acceptera en leverantörs bud på alla rader på en anbudsförfrågan men tilldela andra rader i anbudsförfrågan till en annan leverantör. Du måste emellertid göra ett bud åt gången.  
    - Du kan godkänna antingen originalanbudsraden eller dess alternativ, men inte båda, om det finns alternativa rader.  
3. Välj **avvisa**.
4. Välj **parametrar** och ange sedan budet i fältet **Orsak för avvisande**, ange eller välj orsak för att avvisa budet. Orsaken lagras i svaret.  
5. Välj **OK**.
6. Välj **OK**.

## <a name="accept-a-bid"></a>Acceptera ett bud

1. Markera budet som ska accepteras och välj sedan länken i fältet **Anbudsförfrågan**. Om du är på sidan **Jämför svar på anbudsförfrågan** är det markerade budet som har fokus det bud som systemet kommer att beakta ha under åtgärden acceptera. Du kan bara ta emot rader från ett bud åt gången.  
2. Klicka på **Svar** i åtgärdsfönstret.
3. Välj **Godkänn**. Om du bara har markerat vissa rader tas endast de raderna med i åtgärden acceptera med. Om du vill godkänna alla rader på budet behöver du inte markera raderna.  
4. Välj **parametrar** och ange sedan i fältet **Orsak för godkännande**, ange eller välj orsak för att godkänna budet. Orsaken lagras i budet.  
5. Välj **OK**.
6. Välj **OK**. När du klickar på **OK** genererar detta en inköpsorder baserat på de rader som ingår i godkännandet av anbudsförfrågan. Om det finns andra bud som inte har bearbetats (godkända, avvisade eller returnerade) kommer systemet att uppmana dig att avvisa dem.  

## <a name="view-the-purchase-order-that-is-generated"></a>Visa den inköpsorder som har genererats

Välj **Inköpsorder** på fliken **Allmänt** i åtgärdsfönstret. Sidan som visas visar inköpsordern som genererades, när du godkände budet.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]