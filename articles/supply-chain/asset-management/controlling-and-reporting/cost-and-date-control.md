---
title: Kostnads- och datumkontroll
description: I det här avsnittet förklaras kostnads- och datumkontrollen i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918405"
---
# <a name="cost-and-date-control"></a>Kostnads- och datumkontroll

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I Tillgångshantering kan du beräkna kostnader för att få en översikt över de faktiska kostnaderna jämfört med budgetkostnader för tillgångar, funktionsplatser och arbetsorder. Faktiska kostnader baseras på bokförda transaktioner. Du kan också göra en datumberäkning om du vill jämföra planerade start- och slutdatum med faktiska start- och slutdatum på arbetsorder.

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>Kostnadskontroll för tillgångar, funktionsplatser och arbetsorder

De beräkningar som görs för tillgångar, funktionsplatser och arbetsorder är nästan identiska. Enda skillnad är att för tillgångar och funktionsplatser kan du även inkludera underresurser och underplatser i beräkningen. Datumet är transaktionsdatumet när registreringen gjordes.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Kostnadskontroll för tillgång** eller **Kostnadskontroll för funktionsplats**, eller **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Kostnadskontroll för arbetsorder**.

2. I dialogrutan **Kostnadskontroll för tillgång** / **Kostnadskontroll för funktionsplats** / **Kostnadskontroll för arbetsorder** väljer du en period som ska beräknas.

3. Välj vid behov en ekonomisk dimensionsuppsättning som ska inkluderas i beräkningen.

4. Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller kostnaden noll.

5. Du kan använda fältet **Nivå** för att indikera hur detaljerad kostnadskontrollraderna ska vara gällande funktionsplatser. Om du till exempel infogar siffran "1" i fältet och har en funktionsplatshierarki med flera nivåer, visas alla kostnadskontrollrader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla kostnadskontrollrader på alla den funktionsplatsnivå som de är relaterade till.

6. Välj "Ja" på växlingsknappen **Visa öppen utfäst kostnad** om du vill inkludera den kolumnen i beräkningen.

7. Välj "Ja" på växlingsknappen **Inkludera undertillgångar** om du vill visa kostnader som är relaterade till undertillgångar som separata rader.

8. Om du vill begränsa sökningen kan du välja specifika tillgångar/funktionsplatser/arbetsorder på snabbfliken **Poster som ska ingå**.

9. Klicka på **OK** för att starta beräkningen.

I bilden nedan visas ett exempel på dialogrutan **Kostnadskontroll för tillgång**.

![Figur 1](media/01-controlling-and-reporting.png)

10. I åtgärdsfönstergrupperna **Gruppera efter...** på sidan **Kostnadskontroll för tillgång** klickar du på relevanta knappar om du vill visa den obligatoriska detaljnivån för beräkningen. De valda knapparna i åtgärdsfönstret markeras. Klicka på en knapp för att aktivera och inaktivera den.

I bilden nedan visas ett exempel på beräkningsresultat i **Kostnadskontroll för tillgång**.

![Figur 2](media/02-controlling-and-reporting.png)

Ett annat sätt att göra en kostnadsberäkning är att använda flera tillgångar i **Alla tillgångar** eller **Aktiva tillgångar**. Klicka sedan på knappen **Kostnadskontroll** på fliken **Allmänt**. I dialogrutan **Kostnadskontroll för tillgång** infogas de valda tillgångarna automatiskt i fältet **Tillgång** på snabbfliken **Poster som ska ingå**. Klicka på **OK** och en kostnadsberäkning för valda tillgångar visas. Samma procedur kan utföras för funktionsplatser i **Alla funktionsplatser** eller **Aktiva funktionsplatser**, och för arbetsorder i **Alla arbetsorder** eller **Aktiva arbetsorder**.

>[!NOTE]
>I fältet **Ursprunglig budget** visas budgetkostnader från arbetsorderprognosen. Fältet **Utfästa kostnader** visar det totala beloppet för utgifter som en juridisk person har lovat att betala. I fältet **Öppen utfäst kostnad** visas utfästelser som ska betalas för artiklar, timmar och tjänster som du har beställt eller tagit emot men ännu inte betalt för. När alla förbrukningsregistreringar har bokförts inkluderas de relaterade kostnaderna i fältet **Faktisk kostnad**.

## <a name="work-order-date-control"></a>Datumkontroll för arbetsorder

Använd den här sidan om du vill få en översikt över förväntade start- och slutdatum i förhållande till faktiska start- och slutdatum på arbetsorder.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Datumkontroll för arbetsorder**.

2. Klicka på **Beräkna**.

3. Välj en funktionsplats i fältet **Funktionsplats**.

4. Infoga den period för vilken du vill utföra beräkningen i fälten **Från datum** och **Till datum**. Alla arbetsorder med förväntad start inom perioden inkluderas.

5. Klicka på **OK**.

6. I **Gruppera efter...**-åtgärdsfönstergrupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna i åtgärdsfönstret markeras. Klicka på en knapp för att aktivera och inaktivera den.

I bilden nedan visas ett exempel på beräkningsresultat i **Datumkontroll för arbetsorder**.

![Figur 3](media/03-controlling-and-reporting.png)

- Fältet **Genomsnittlig startfördröjning** visar skillnaden i dagar mellan det schemalagda startdatumet för en arbetsorder jämfört med faktiskt startdatum. Om till exempel det verkliga startdatumet infaller två dagar före det schemalagda startdatumet visas "-2" i det här fältet.  
- Fältet **Genomsnittlig slutfördröjning** visar skillnaden i dagar mellan det schemalagda slutdatumet för en arbetsorder jämfört med faktiskt slutdatum. Om till exempel det faktiska slutdatumet infaller tre dagar efter det schemalagda slutdatumet visas "3" i det här fältet.  
- I fälten **Förekomster** visas antalet gånger avvikelser uppträder i relation till schemalagt och faktiskt startdatum, samt schemalagt och faktiskt slutdatum på arbetsordern.
