---
title: Underhållsbegäranden
description: Denna artikel innehåller en översikt över hantering av underhållsbegäran i Tillgångshantering
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 488b6505aba246aa3a6ea69436514a274403bf49
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015650"
---
# <a name="maintenance-requests"></a>Underhållsbegäranden

[!include [banner](../../includes/banner.md)]

Underhållsbegäran är anteckningar eller deklarationer som skapas för att meddela en chef eller planerare att en tillgång kan kräva ett underhålls- eller reparationsjobb, men utan att skapa en arbetsorder. Om innehållet i en underhållsbegäran anses vara giltigt, kan en arbetsorder skapas baserat på underhållsbegäran.

Underhållsbegäran kan skapas för alla tillgångar i Tillgångshantering. Olika typer av underhållsbegäran kan skapas, beroende på hur ditt företag använder underhållsbegäran. Nedan följer några exempel:

- Underhållsbegäranden
- Anteckningar
- Korrigeringar eller förbättringar
- Investeringar
- Depåreparation (den här typen används när du tar emot tillgångar från en annan plats så att du kan utföra ett underhålls- eller reparationsjobb och sedan returnera tillgången när jobbet har slutförts.)

## <a name="view-maintenance-requests"></a>Visa underhållsbegäranden

Om du vill visa underhållsbegäran, välj **Tillgångshantering** \> **underhållsbegäran** \> **alla underhållsbegäran**, **aktiva underhållsbegäran** eller **mina underhållsbegäran för funktionsplats**. Varje listsida visar en del av den information som är relaterad till en underhållsbegäran.

![Visa underhållsbegäranden.](media/01-manage-maintenance-requests.png)

> [!NOTE]
> Använd listsidan **mina underhållsbegäran för funktionsplats** för att visa en lista över underhållsbegäran som innehåller antingen funktionsplatser som du är relaterad till som en anställd eller tillgångar som är installerade på funktionsplatser som du relaterade till som arbetstagare. (Information om hur du konfigurerar funktionsplatser på underhållsarbetare finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).)
> 
> Även om kundkontoinformation är tillgänglig i tillgångsservicehantering (externt underhåll), är den inte tillgänglig i Tillgångshantering (internt underhåll).

Om du vill öppna detaljvyn för en post väljer du listsidan **Alla underhållsbegäran** i rutnätsvyn och väljer en länk i kolumnen **Underhållsbegäran**.

![Visa information om underhållsbegäran:](media/02-manage-maintenance-requests.png)

Knapparna i åtgärdsfönstret är ordnade på flikar. I följande tabell beskrivs kortfattat knappar som är relaterade till Tillgångshantering.

| Namn på knapp                      | Beskrivning |
|----------------------------------|-------------|
| Redigera                             | Redigera den valda underhållsbegäran. |
| Nytt                              | Skapa en ny underhållsbegäran. |
| Radera                           | Radera vald underhållsbegäran. |
| Arbetsorderpool                  | Anslut den valda underhållsbegäran till en arbetsorderpool. |
| Arbetsorder                       | Skapa enarbetsorder baserad på den valda underhållsbegäran. |
| Tillgångsfel                      | Klicka **Tillgångsfel**, där du kan skapa en felregistrering på den valda underhållsbegäran. |
| Arbetsorder                      | Visa en lista över alla arbetsorder som är kopplade till den valda underhållsbegäran. |
| Uppdatera tillstånd för underhållsbegäran | Uppdatera tillstånd för underhållsbegäran |
| Logg för livscykeltillstånd              | Visa en logg som visar livscykeltillstånden för den valda underhållsbegäran. |
| Information om underhållsbegäran      | Skriv ut en rapport som visar information om den valda underhållsbegäran. |
| Skicka utlåningstillgång                  | Välj en utlåningstillgång som ska vara en temporär ersättning för tillgången som valts i den valda underhållsbegäran. |
| Lämna tillbaka utlåningstillgång                | Registrera utlåningstillgången som returnerad. |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]