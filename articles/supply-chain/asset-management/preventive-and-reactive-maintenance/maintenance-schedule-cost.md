---
title: Kostnad för underhållsschema
description: I denna artikel beskrivs underhållsschemakostnad i Tillgångshantering.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 91481f9bcb778796255fad006c6187916d8e6bb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908755"
---
# <a name="maintenance-schedule-cost"></a>Kostnad för underhållsschema

[!include [banner](../../includes/banner.md)]

 

I Tillgångshantering kan du beräkna budgetkostnader för rader i underhållsscheman. Detta är användbart om du vill få en översikt över förväntade kostnader, t.ex. kostnader som rör planerade förebyggande underhållsjobb för nästa år. Beräkningarna baseras på befintliga underhållsschemarader av typen "Underhållsplaner" och "Underhållsomgångar" och "Underhållsbegäranden".

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Kostnad för underhållsschema**.

2. I dialogrutan **Kostnad för underhållsschema** kan du välja en **ekonomisk dimensionsuppsättning** om du vill se kostnader grupperade i ekonomiska dimensioner.

>[!NOTE]
>Ekonomiska dimensionsuppsättningar ställs in i **Redovisning** > **Kontoplan** > **Dimensioner** > **Ekonomiska dimensionsuppsättningar**.

3. Du kan använda fältet **Nivå** för att indikera hur detaljerade underhållsschemaraderna ska vara gällande funktionsplatser. Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsschemarader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsschemarader på alla de funktionsplatsnivåer som de är relaterade till.

4. Om du vill göra beräkningar för vissa tillgångar klickar du på **Filter** på snabbfliken **Poster som ska ingå** och väljer relevanta tillgångar. Om det behövs kan du även ange ett datum för **Förväntad start** för kostnadsberäkningen eller välja en annan **status** för kostnadsberäkningen

5. Klicka på **OK** för att starta kostnadsberäkningen.

6. På fliken **Kostnad för underhållsschema** > i åtgärdsfönstergrupperna **Gruppera efter...** klickar du på relevanta knappar om du vill visa den obligatoriska detaljnivån för kostnadsberäkningen. De valda knapparna i åtgärdsfönstergruppen markeras. Klicka på en knapp för att aktivera och inaktivera den.

7. Klicka på knappen **Beräkna kostnad** om du vill göra en ny kostnadsberäkning.

Bilden nedan visar resultaten av en kostnadsberäkning för underhållsscheman.

![Figur 1.](media/17-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]