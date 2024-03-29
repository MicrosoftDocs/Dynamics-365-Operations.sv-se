---
title: Arbetstidskontroll
description: I denna artikel förklaras arbetstidskontroll i Tillgångshantering.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetHourControl
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f5f5dbb23c4d6c86bee7612c4ade65ef4b1cee8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869761"
---
# <a name="work-hour-control"></a>Arbetstidskontroll

[!include [banner](../../includes/banner.md)]

 

I Tillgångshantering kan du beräkna timmar för att få en översikt över de faktiska timmarna jämfört med budgeterade timmar för tillgångar, funktionsplatser och arbetsorder. Faktiska timmar baseras på bokförda transaktioner.

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a>Arbetstidskontroll för tillgångar, funktionsplatser och arbetsorder

De beräkningar som görs för tillgångar, funktionsplatser och arbetsorder är nästan identiska. Enda skillnad är att för tillgångar och funktionsplatser kan du även inkludera underresurser och underplatser i beräkningen. Datumet är transaktionsdatumet när registreringen gjordes.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Timkontroll för tillgång** eller **Timkontroll för funktionsplats**, eller **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Timkontroll för arbetsorder**.

2. I dialogrutan **Timkontroll för tillgång**.

3. I dialogrutan **Timkontroll för tillgång** / **Timkontroll för funktionsplats** / **Timkontroll för arbetsorder** väljer du en period som ska beräknas i fälten **Från datum** och **Till datum**.

4. Välj vid behov en **ekonomisk dimensionsuppsättning** som ska inkluderas i beräkningen.

5. Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller noll timmar.

6. Du kan använda fältet **Nivå** för att indikera hur detaljerad timkontrollraderna ska vara gällande funktionsplatser. 

    Om du till exempel infogar siffran "1" i fältet och har en funktionsplatshierarki med flera nivåer, visas alla timkontrollrader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. 
    
    Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla timkontrollrader på alla de funktionsplatsnivåer som de är relaterade till.

7. Välj "Ja" på växlingsknappen **Inkludera undertillgångar** om du vill visa kostnader som är relaterade till undertillgångar som separata rader.

8. Om du vill begränsa sökningen kan du välja specifika tillgångar/funktionsplatser/arbetsorder på snabbfliken **Poster som ska ingå**.

9. Klicka på **OK** för att starta beräkningen.

10. På sidan **Timkontroll för tillgång**, välj knapparna **Gruppera efter** för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna **Gruppera efter** markeras. Klicka på en knapp för att aktivera och inaktivera den.

## <a name="example"></a>Exempel

I skärmbilden nedan visas ett exempel på ett beräkningsresultat i **Timkontroll för tillgång**.

- I fältet **Ursprunglig budget** visas budgettimmar från arbetsorderprognosen. 
- I fältet **Faktiska timmar** visas bokförda timmar på arbetsorder. 
- I fältet **Utfäst tid** visas det totala antalet timmar som ditt företag är förpliktigat att utföra i relation till arbetsorder.

![Exempel på beräkning av timkontroll för tillgång.](media/04-controlling-and-reporting.png)

Ett annat sätt att göra en timberäkning är att använda flera tillgångar i **Alla tillgångar** eller **Aktiva tillgångar**. Klicka sedan på knappen **Timkontroll** på snabbfliken **Allmänt**. De valda tillgångarna infogas automatiskt i fältet **Tillgång** på snabbfliken **Poster som ska ingå**. Klicka på **OK** i dialogrutan **Timkontroll för tillgång** och beräkningen för de valda tillgångarna visas. Samma procedur kan utföras för funktionsplatser i **Alla funktionsplatser** eller **Aktiva funktionsplatser**, och för arbetsorder i **Alla arbetsorder** eller **Aktiva arbetsorder**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]