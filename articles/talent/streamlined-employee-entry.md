---
title: Strömlinjeformad medarbetarinmatning och navigering
description: Dataregistrering för arbetare i Dynamics 365 Talent har förbättrats för att möjliggöra snabbregistrering för alla medarbetare, tidigare, aktiva eller framtida. En förenklad/konsoliderad navigeringsmodell har uppdaterats för att snabbt hitta relaterad information och visa och göra nödvändiga uppdateringar.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: b73b420c2eb75077814fbfeb6cd17404c7efc11e
ms.sourcegitcommit: 436731d8b3889bebfe6f17922b0a31b1994f6796
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2020
ms.locfileid: "4462651"
---
# <a name="streamlined-employee-entry-and-navigation"></a>Strömlinjeformad medarbetarinmatning och navigering

Dynamics 365 Talent gör det möjligt att registrera medarbetar- och anställningsdata effektivt. Du kan snabbt uppdatera information om arbetshistorik för tidigare, aktiva och framtida medarbetare och leverantörer.

Du kan också aktivera en förenklad navigeringsupplevelse om du snabbt vill hitta relaterad information och göra nödvändiga ändringar. Den här funktionen är nu tillgänglig i alla miljöer med begränsat läge. Om du vill aktivera funktionen navigerar du till **Systemadministration > funktionshantering > ny > strömlinjeformad medarbetarpost > aktivera**. Detta aktiverar dessa ändringar för alla användare. Du kan stänga av det här alternativet när du vill.

## <a name="view-options"></a>Visningsalternativ

Du kan använda **visningsalternativen** i arbetarens formulär för att välja valfri kombination av medarbetare och leverantörer från en enda lista. Med dessa alternativ kan du visa arbetare över juridiska personer eller för den juridiska personen som du för närvarande är inloggad i. Du kan även visa aktiva, pågående och avslutade arbetare och du kan begränsa resultaten baserat på typen av arbetare (medarbetare eller leverantör). Om avancerad säkerhet är aktiverad visas endast medarbetare och leverantörer i de juridiska personer som du har tillgång till.

Kolumnerna i listvyn ändras utifrån dina val. När du t.ex. visar avslutade medarbetare visas uppsägningsdatum och orsakskoder som ytterligare kolumner i listan. 

[![Visningsalternativ](./media/Worker-view-option.png)](./media/worker-view-option.png)

## <a name="navigation-and-banner"></a>Navigering och banderoll

En banderoll visar viktig information för varje arbetare. Banderollen för aktiva arbetare visar följande fält:

- **Rubrik**
- **Avdelning**
- **Befattningstyp**
- **Typ av arbetare**
- **VD**
- **Juridisk person**

Banderollen för avslutade arbetare visar följande fält:

- **Avslutat den**
- **Orsak**

Banderollen för väntande arbetare visar följande fält:

- **Rubrik**
- **Avdelning**
- **Befattningstyp**
- **VD**
- **Startdatum**
- **Juridisk person**

Åtgärdsfönstret på arbetarsidan har ordnats om så att färre alternativ kan användas. Informationen ordnas nu i följande kategorier: 

- Arbete
- Person
- Tjänstledighet
- Kompensation
- Förmåner
- Regelefterlevnad

Dessutom ger en ny flik **länk** på huvudarbetarsidan användare en central plats för åtkomst till all relaterad information för en arbetare.

På grund av dessa ändringar kan information visas på en annan plats än du brukar. Löneinformation som tidigare har visats i formuläret arbetare visas till exempel i åtgärdsfönstret under **kompensation > lön** och fliken **personliga uppgifter** innehåller nu knappen **mer information** om du vill dölja fält som ofta används.

[![Banner](./media/Banner.png)](./media/Banner.png)

## <a name="work-history"></a>Arbetshistorik

Fliken **Arbetshistorik** visar arbetshistoriken för alla juridiska personer och den är tillgänglig för stängning, aktiv och väntande medarbetare och leverantörer. Du kan nu visa all arbetshistorik samtidigt för de juridiska personer som du har tillgång till. Dessutom kan du redigera information för varje post i arbetshistorik utan att ändra datakontexten. Du kan uppdatera all information direkt på sidan. 

[![Arbetshistorik](./media/Worker-work-history.png)](./media/Worker-work-history.png)

## <a name="position-history"></a>Positionshistorik

Fliken **befattningar** på huvudarbetarsidan ger en fullständig översikt över alla befattningar inom organisationen, inklusive tidigare, närvarande och eventuella framtida tilldelningar. Du kan fortfarande gå direkt till arbetarens befattningshistorik i åtgärdsfönstret.

[![Befattningar](./media/Worker-position-history.png)](./media/Worker-position-history.png)

