---
title: Kostnads- och datumkontroll
description: I denna artikel förklaras kostnads- och datumkontrollen i Tillgångshantering.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetBICostControlWorkspace, EntAssetWorkOrderDateControl, EntAssetWorkOrderForecastCostInfoPart, EntAssetMaintenanceCostTrans, EntAssetWorkOrderDateControlCalcDialog, EntAssetCostControl, EntAssetCostObjectCalendar, EntAssetWorkOrderCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 643e5afda7d3abaff926e81ff75186ca195a8cb1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861056"
---
# <a name="cost-and-date-control"></a>Kostnads- och datumkontroll

[!include [banner](../../includes/banner.md)]

I Tillgångshantering kan du beräkna kostnader för att få en översikt över de faktiska kostnaderna jämfört med budgetkostnader för tillgångar, funktionsplatser och arbetsorder. Faktiska kostnader baseras på bokförda transaktioner.

Du kan också göra en datumberäkning om du vill jämföra planerade start- och slutdatum med faktiska start- och slutdatum på arbetsorder.

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>Kostnadskontroll för tillgångar, funktionsplatser och arbetsorder

De beräkningar som görs för tillgångar, funktionsplatser och arbetsorder är nästan identiska. Den enda skillnaden är att för tillgångar och funktionsplatser kan du även inkludera underresurser och underplatser i beräkningen. Datumet är transaktionsdatumet när registreringen gjordes.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Kostnadskontroll för tillgång** eller **Kostnadskontroll för funktionsplats**, eller **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Kostnadskontroll för arbetsorder**.

2. I dialogrutan **Kostnadskontroll för tillgång** / **Kostnadskontroll för funktionsplats** / **Kostnadskontroll för arbetsorder** väljer du ett tidsintervall som ska beräknas.

3. Välj vid behov en ekonomisk dimensionsuppsättning som ska inkluderas i beräkningen.

4. Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller kostnaden noll.

5. Du kan använda fältet **Nivå** för att indikera hur detaljerad kostnadskontrollraderna ska vara gällande funktionsplatser. 

    Om du till exempel infogar siffran "1" i fältet och har en funktionsplatshierarki med flera nivåer, visas alla kostnadskontrollrader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.

    Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla kostnadskontrollrader på alla den funktionsplatsnivå som de är relaterade till.

6. Välj "Ja" på växlingsknappen **Visa öppen utfäst kostnad** om du vill inkludera den kolumnen i beräkningen.

7. Välj "Ja" på växlingsknappen **Inkludera undertillgångar** om du vill visa kostnader som är relaterade till undertillgångar som separata rader.

8. Om du vill begränsa sökningen kan du välja specifika tillgångar/funktionsplatser/arbetsorder på snabbfliken **Poster som ska ingå**.

9. Klicka på **OK** för att starta beräkningen.

    I bilden nedan visas ett exempel på dialogrutan **Kostnadskontroll för tillgång**.

    ![Dialogrutan Kostnadskontroll för tillgång.](media/01-controlling-and-reporting.png)

10. På sidan **Kostnadskontroll för tillgång**, välj knapparna **Gruppera efter** för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna **Gruppera efter** markeras. Klicka på en knapp för att aktivera och inaktivera den.

## <a name="example-of-calculation-results-in-asset-cost-control"></a>Exempel på beräkningsresultat i kostnadskontroll för tillgång

I skärmbilden nedan visas ett exempel på beräkningsresultat i **Kostnadskontroll för tillgång**.

- I fältet **Ursprunglig budget** visas budgetkostnader från arbetsorderprognosen. 
- Fältet **Utfästa kostnader** visar det totala beloppet för utgifter som en juridisk person har lovat att betala. 
- I fältet **Öppen utfäst kostnad** visas utfästelser som ska betalas för artiklar, timmar och tjänster som du har beställt eller tagit emot men ännu inte betalt för. 
- **Faktisk kostnad** fältet visar relaterade kostnader efter att alla förbrukningsregistreringar har bokförts.

![Exempel på beräkningsresultat i Kostnadskontroll för tillgång.](media/02-controlling-and-reporting.png)

Ett annat sätt att göra en kostnadsberäkning är att använda flera tillgångar i **Alla tillgångar** eller **Aktiva tillgångar**. Klicka sedan på knappen **Kostnadskontroll** på fliken **Allmänt**. I dialogrutan **Kostnadskontroll för tillgång** infogas de valda tillgångarna automatiskt i fältet **Tillgång** på snabbfliken **Poster som ska ingå**. Klicka på **OK** och en kostnadsberäkning för valda tillgångar visas. Samma procedur kan utföras för funktionsplatser i **Alla funktionsplatser** eller **Aktiva funktionsplatser**, och för arbetsorder i **Alla arbetsorder** eller **Aktiva arbetsorder**.

## <a name="work-order-date-control"></a>Datumkontroll för arbetsorder

Använd den här sidan om du vill få en översikt över förväntade start- och slutdatum i förhållande till faktiska start- och slutdatum på arbetsorder.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Datumkontroll för arbetsorder**.

2. Klicka på **Beräkna**.

3. Välj en funktionsplats i fältet **Funktionsplats**.

4. Infoga den intervall för vilken du vill utföra beräkningen i fälten **Från datum** och **Till datum**. Alla arbetsorder med förväntad startdatum inom intervallet inkluderas.

5. Klicka på **OK**.

6. Klicka på knapparna **Gruppera efter...** för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna **Gruppera efter** markeras. Klicka på en knapp för att aktivera och inaktivera den.

## <a name="example-of-calculation-results-in-work-order-date-control"></a>Exempel på beräkningsresultat i datumkontroll för arbetsorder

I bildskärmen nedan visas ett exempel på beräkningsresultat i **Datumkontroll för arbetsorder**.

- Fältet **Genomsnittlig startfördröjning** visar skillnaden i dagar mellan det schemalagda startdatumet för en arbetsorder jämfört med faktiskt startdatum. Om till exempel det verkliga startdatumet infaller två dagar före det schemalagda startdatumet visas "-2" i det här fältet.  
- Fältet **Genomsnittlig slutfördröjning** visar skillnaden i dagar mellan det schemalagda slutdatumet för en arbetsorder jämfört med faktiskt slutdatum. Om till exempel det faktiska slutdatumet infaller tre dagar efter det schemalagda slutdatumet visas "3" i det här fältet.  
- I fälten **Förekomster** visas antalet gånger avvikelser uppträder i relation till schemalagt och faktiskt startdatum, samt schemalagt och faktiskt slutdatum på arbetsordern.

![Exempel på beräkningsresultat i Datumkontroll för arbetsorder.](media/03-controlling-and-reporting.png)




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]