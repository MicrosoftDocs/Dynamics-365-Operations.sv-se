---
title: Skapa en arbetstidskalender
description: Definiera en arbetstidskalender, semestrar och ej arbetstider i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dac3ad583be9e4cbd6eacbc6d228819bd298628b
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323586"
---
# <a name="create-a-working-time-calendar"></a>Skapa en arbetstidskalender


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En arbetstidskalender i Dynamics 365 Human Resources visar de dagar och timmar som medarbetarna arbetar i din organisation. När en medarbetare skickar en ledighetsansökan behöver han inte bekymra dig om helgdagar och stängningar.

Om du vill effektivisera begäranden om ledighet konfigurerar du de här artiklarna för din organisation:

- Arbetstidskalender
- Helgdagar och stängningar
- Ej arbetstid

Du kan lägga till de sista två objekten medan du ställer in en arbetstidskalender. Du kan även konfigurera eller uppdatera dem separat.

## <a name="set-up-a-working-time-calendar"></a>Ställa in en arbetstidskalender

Skapa minst en arbetstidskalender som visar dina dagar och arbetstider. Om du har platser i flera länder och regioner kanske du vill skapa en arbetstidskalender för varje område.

1. På sidan **Organisationsadministration** klickar du på **kalendrar**.

2. Välj **Ny** och ange ett nytt namn på och en beskrivning för din kalender.

3. Under **Genereringsalternativ** väljer du arbetsdagar för organisationen och anger arbetstider. 
   - Om du vill lägga till en helgdag eller avslutning väljer du knappen **Lägg till** bredvid **helgdagar och stängningar**.
   - Om du vill lägga till ledig tid, som lunch eller raster, väljer du **Lägg till** under **Arbetsfri tid** och anger namn och tidsintervall.

4. Under **dagar**, välj **generera** för att generera dagar i kalendern. Ange datumintervallet för kalendern och välj sedan **generera dagar**.

5. Lägg till arbetsscheman genom att under **Arbetsschema** välja **Lägg till** och sedan ange tiderna för varje arbetsschema.

## <a name="configure-holidays-and-closures"></a>Konfigurera helgdagar och stängningar

Du kan lägga till eller ändra helgdagar och stängningar separat från en arbetstidskalender.

1. På sidan **Organisationsadministration** klickar du på **Helgdagar och stängningar**.

2. Välj **Ny** och ange ett nytt namn och datum för helgdag och stängning.

## <a name="configure-non-work-time"></a>Konfigurera ej arbetstid

Du kan lägga till eller ändra ej arbetstider separat från en arbetstidskalender.

1. På sidan **Organisationsadministration** klickar du på **ej arbetstid**.

2. Välj **Ny** och ange namnet och tidsintervallet för ej arbetstid.

Om du har aktiverat förhandsgranskningsfunktionen för ledighet och frånvaro i helgdagar använder Personal helgdagar och stängningsdatum för att bestämma antalet dagar som ska anpassas för anställda som är registrerade i kalendern.

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)
- [Konfigurera typer av tjänstledighet och frånvaro](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
