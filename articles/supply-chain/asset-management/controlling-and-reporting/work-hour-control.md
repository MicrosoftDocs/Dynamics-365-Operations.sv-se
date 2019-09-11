---
title: Arbetstidskontroll
description: I det här avsnittet förklaras arbetstidskontroll i Tillgångshantering.
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
ms.openlocfilehash: 916e7b8d5d494dbae0659504957f7f0798a6834b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918382"
---
# <a name="work-hour-control"></a>Arbetstidskontroll

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I Tillgångshantering kan du beräkna timmar för att få en översikt över de faktiska timmarna jämfört med budgeterade timmar för tillgångar, funktionsplatser och arbetsorder. Faktiska timmar baseras på bokförda transaktioner.

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a>Arbetstidskontroll för tillgångar, funktionsplatser och arbetsorder

De beräkningar som görs för tillgångar, funktionsplatser och arbetsorder är nästan identiska. Enda skillnad är att för tillgångar och funktionsplatser kan du även inkludera underresurser och underplatser i beräkningen. Datumet är transaktionsdatumet när registreringen gjordes.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Timkontroll för tillgång** eller **Timkontroll för funktionsplats**, eller **Tillgångshantering** > **Förfrågningar** > **Arbetsorder** > **Timkontroll för arbetsorder**.

2. I dialogrutan **Timkontroll för tillgång**.

3. I dialogrutan **Timkontroll för tillgång** / **Timkontroll för funktionsplats** / **Timkontroll för arbetsorder** väljer du en period som ska beräknas i fälten **Från datum** och **Till datum**.

4. Välj vid behov en **ekonomisk dimensionsuppsättning** som ska inkluderas i beräkningen.

5. Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller noll timmar.

6. Du kan använda fältet **Nivå** för att indikera hur detaljerad timkontrollraderna ska vara gällande funktionsplatser. Om du till exempel infogar siffran "1" i fältet och har en funktionsplatshierarki med flera nivåer, visas alla timkontrollrader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla timkontrollrader på alla de funktionsplatsnivåer som de är relaterade till.

7. Välj "Ja" på växlingsknappen **Inkludera undertillgångar** om du vill visa kostnader som är relaterade till undertillgångar som separata rader.

8. Om du vill begränsa sökningen kan du välja specifika tillgångar/funktionsplatser/arbetsorder på snabbfliken **Poster som ska ingå**.

9. Klicka på **OK** för att starta beräkningen.

10. I åtgärdsfönstergrupperna **Gruppera efter...** på sidan **Timkontroll för tillgång** klickar du på relevanta knappar om du vill visa den obligatoriska detaljnivån för beräkningen. De valda knapparna i åtgärdsfönstret markeras. Klicka på en knapp för att aktivera och inaktivera den.

I bilden nedan visas ett exempel på ett beräkningsresultat i **Timkontroll för tillgång**.

![Figur 1](media/04-controlling-and-reporting.png)

Ett annat sätt att göra en timberäkning är att använda flera tillgångar i **Alla tillgångar** eller **Aktiva tillgångar**. Klicka sedan på knappen **Timkontroll** på snabbfliken **Allmänt**. De valda tillgångarna infogas automatiskt i fältet **Tillgång** på snabbfliken **Poster som ska ingå**. Klicka på **OK** i dialogrutan **Timkontroll för tillgång** och beräkningen för de valda tillgångarna visas. Samma procedur kan utföras för funktionsplatser i **Alla funktionsplatser** eller **Aktiva funktionsplatser**, och för arbetsorder i **Alla arbetsorder** eller **Aktiva arbetsorder**.

>[!NOTE]
>I fältet **Ursprunglig budget** visas budgettimmar från arbetsorderprognosen. I fältet **Faktiska timmar** visas bokförda timmar på arbetsorder. I fältet **Utfäst tid** visas det totala antalet timmar som ditt företag är förpliktigat att utföra i relation till arbetsorder.

