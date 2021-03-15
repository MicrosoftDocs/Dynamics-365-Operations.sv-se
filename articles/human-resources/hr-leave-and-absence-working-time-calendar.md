---
title: Skapa en arbetstidskalender
description: Definiera en arbetstidskalender, semestrar och ej arbetstider i Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ccf7901ebbea655b7f795a48944c6f03f9cf210a
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115112"
---
# <a name="create-a-working-time-calendar"></a>Skapa en arbetstidskalender

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
   - Om du vill lägga till ledig tid, som lunch eller raster, väljer du **Lägg till** under **EJ ARBETSTID** och anger namn och tidsintervall.

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