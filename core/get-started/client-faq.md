---
title: Dynamics 365 operationer klient FAQ
description: "Den här artikeln innehåller svar på vanliga frågor om Microsoft Dynamics 365 operationer klient."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 2c99b2e1f7ddecb61be62832ca1a8d3ac1fd21a8
ms.lasthandoff: 03/31/2017


---

# <a name="dynamics-365-for-operations-client-faq"></a>Dynamics 365 operationer klient FAQ

Den här artikeln innehåller svar på vanliga frågor om Microsoft Dynamics 365 operationer klient.

<a name="why-arent-symbols-loaded-when-i-use-dynamics-365-for-operations"></a>Varför inte symboler som läses in när jag använda Dynamics 365 för operationer?
-----------------------------------------------------------------

Säkerhetinställningarna i din webbläsare kan hindra symbolerna från att läsas in korrekt. Lös problemet genom att pröva följande steg:

-   Om du upplever problemet i Internet Explorer klickar du på **verktyg**, och klicka sedan på **Internetalternativ**.  I dialogrutan Internet-alternativ på den **sekretess** klickar du på **Anpassad nivå**, och kontrollera att den **hämtning av teckensnitt** alternativ är valt.
-   Annars kanske du måste lägga till Dynamics 365 för operationer platsen i listan över tillförlitliga platser.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Jag saknar menyfliken från Dynamics AX 2012. Kan jag förhindra att åtgärdsfönstret flikar öppna hela tiden?
Vi planerar att implementera den här funktionen snart. Användarna kan sedan välja att behålla flikarna i åtgärdsfönster öppna hela tiden. Annars döljs flikarna när de inte används för att få mer skärmyta för sidan.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-rightclick"></a>Varför ibland visas olika snabbmenyer när jag rightclick?
Om du högerklickar i ett redigerbart fält (eller när text markeras) visas webbläsarens snabbmenyer. Menyn ger tillgång till **Klipp ut**, **Kopiera** och **Klistra in**. Vi kan inte bädda in kommandona i Dynamics 365 för operationer snabbmenyer eftersom av säkerhetsskäl webbläsare inte möjliggör att programmatiskt komma åt systemets Urklipp.

Om du högerklickar på en fältetikett eller värdet för en skrivskyddad kontroll visas Dynamics 365 för operationer snabbmenyn.

Du kan förenkla kortkommandot kommer att implementera ett kortkommando i framtiden som Dynamics 365 för operationer snabbmenyn öppnas.

## <a name="where-is-the-view-details-functionality-in-dynamics-365-for-operations"></a>Var finns funktionen Visa information i Dynamics 365 för operationer?
Alternativet **Visa information** är tillgängligt på flera sätt:

-   Om en kontroll har funktionen **Visa information** och dessutom ett värde, kan värdet visas som en hyperlänk. Du kan klicka på hyperlänken när du vill öppna en sida som innehåller mer information.
-   **Visa detaljer** är också ett alternativ på Dynamics 365 för operationer snabbmenyer. Mer information om när Dynamics 365 för operationer snabbmenyerna visas när du högerklickar, finns i föregående avsnitt.



