---
title: Utöka Talent med Power Apps och Power Automate
description: Den här artikeln beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Talent - Attract som använder Microsoft Power Apps och Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: cfdf36e9486aa4853d3bf674afa73ec3a4d1c161
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529644"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Utöka Talent med Power Apps och Power Automate

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Talent: Attract som använder Microsoft Power Apps och Microsoft Power Automate. Du kan importera lösningspaketet som associeras med varje exempel i din Power Apps-miljö. Du kan sedan använda paketen antingen som vägledning eller som utgångspunkt för att implementera scenarier som gäller för din organisation.

> [!IMPORTANT]
> Om du vill använda de mallar och program som beskrivs i den här artikeln ”i befintligt skick” bör du testa dem och se till att de täcker alla de scenarier som avser implementeringen.


## <a name="prerequisites"></a>Förutsättningar

- Om du vill importera paket måste användarna ha behörighet **Environment Maker**.
- Användare måste ha en Power Apps Plan 2-licens eller en Power Apps Plan 2 utvärderingslicens för att exportera eller importera appar.

## <a name="power-automate--form-connect"></a>Power Automate – formuläret Ansluta

Mallen **Power Automate – formuläret Ansluta** kan användas för att läsa data från Microsoft Forms och lagra det i en Common Data Service-enhet.

Den här mallen kan utökas så att den kan användas för andra scenarier. Nedan följer några exempel:

- Hämta kandidatens bedömningar.
- Hämta resultaten från kursens enkäter.
- Kompilera ett bibliotek med intervjufrågor för personaladministratörer (HR).
- Hämta kandidatens utvärdering av intervjuprocessen

I Microsoft Dynamics 365: Attract, kan du använda formulär i kandidatportalen och kandidater kan fylla i information. Du kan också bädda in formulär som aktiviteter i en jobbmall.

När en kandidat skickar ett formulär, hämtar Microsoft Power Automate formuläröverföringen, läser in data och lagrar den Common Data Service-enhet.

För att hämta mallen **Power Automate – formuläret Ansluta** och anpassad entitetsstruktur, gå till [Power Automate – formuläret Ansluta](https://go.microsoft.com/fwlink/?linkid=2081988) på Microsoft Download Center.

## <a name="power-automate--sharepoint-integration"></a>Power Automate – SharePoint-integration

Mallen **Power Automate – SharePoint-integration** kan användas för att läsa in data från en Microsoft SharePoint-lista, jämföra listan med fältvärden för någon Common Data Service entitet och skicka resultatet av jämförelsen som ett e-postmeddelande. 

En organisation kan ha en uppsättning med kunskaper som den kräver snarast. Dessa kunskaper kan lagras i SharePoint som en SharePoint lista. Då en kandidat ansöker om ett jobb som en uppsättning kunskaper anges för, om det finns en betydande matchning mellan kandidatens kunskaper och de kunskaper som är lagrade i SharePoint skickas ett e-postmeddelande. På så sätt fylls befattningar som krävs snarast snabbare eftersom meddelanden hjälper rekryterare att anställa kandidater i hela organisationen.

Den här mallen kan utökas så att den kan användas för vissa situationer som omfattar SharePoint-integration.

För att hämta mallen **Power Automate – SharePoint-integration** gå till [Power Automate – SharePoint-integration](https://go.microsoft.com/fwlink/?linkid=2082109) på Microsoft Download Center.

## <a name="referral-app"></a>Appen Hänvisning

Du kan använda appen Hänvisning för att lägga till kandidater till en delad talangpool. Hänvisaren kan ange **förnamn**, **efternamn**, **e-postadress** och **Linkedln-adress** när han eller hon skickar en kandidat. Kandidatens metadata för källan fylls sedan i med hänvisarens information.

Du kan bädda in den här appen i Självbetjäning för medarbetare för att skicka referenser eller använda den som en hyperlänk i företagsportalen och köra den som en fristående app.

Hämta **Appen Hänvisning** genom att gå till [Dynamics 365 Talent utbyggbarhetslösning: appen Hänvisning](https://www.microsoft.com/download/details.aspx?id=58497) i Microsoft Download Center. Du kan importera den här appen och anpassa den om du vill lägga till fler funktioner.

## <a name="additional-resources"></a>Ytterligare resurser

[Appen Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[Migrera mellan innehavare och program](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)


[!INCLUDE[footer-include](../includes/footer-banner.md)]