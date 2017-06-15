---
title: "Frågor och svar för Dynamics 365 for Operations-klienten"
description: "Det här avsnittet innehåller vanliga frågor och svar om Microsoft Dynamics 365 for Operations-klienten."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7e8f09b965403298630460ccb6669fd82abb0e8c
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="dynamics-365-for-operations-client-faq"></a>Frågor och svar för Dynamics 365 for Operations-klienten

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller vanliga frågor och svar om Microsoft Dynamics 365 for Operations-klienten.

<a name="why-arent-symbols-loaded-when-i-use-dynamics-365-for-operations"></a>Varför läses inte symboler in när jag använder Dynamics 365 for Operations?
-----------------------------------------------------------------

Säkerhetinställningarna i din webbläsare kan hindra symbolerna från att läsas in korrekt. Lös problemet genom att pröva följande steg:

-   Om du upplever problemet i Internet Explorer klickar du på **Verktyg** och sedan på **Internetalternativ**.  I dialogrutan Internet-alternativ på fliken **Sekretess** klickar du på **Anpassad nivå**, och kontrollerar att alternativet **Hämtning av teckensnitt** är valt.
-   Annars måste du kanske lägga till Dynamics 365 for Operations-webbplatsen i listan över betrodda webbplatser.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Jag saknar menyfliken från Dynamics AX 2012. Kan jag ha åtgärdsfönstrets flikar öppna hela tiden?
Vi planerar att implementera den här funktionen snart. Användarna kan sedan välja att behålla flikarna i åtgärdfönstren öppna hela tiden. Annars döljs flikarna när de inte används för att få mer skärmyta för sidan.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-rightclick"></a>Varför visas ibland olika snabbmenyer när jag högerklickar?
Om du högerklickar i ett redigerbart fält (eller när text markeras) visas webbläsarens snabbmenyer. Menyn ger tillgång till **Klipp ut**, **Kopiera** och **Klistra in**. Vi kan inte bädda in dessa kommandon i snabbmenyerna i Dynamics 365 for Operations, detta eftersom webbläsarna av säkerhetsskäl inte tillåter oss att öppna systemurklipp via programmering.

Om du högerklickar på en fältetikett eller ett värde i en skrivskyddad kontroll visas snabbmenyn för Dynamics 365 for Operations.

Vi vill göra det enklare att komma åt tangentbordet, så vi planerar att implementera ett tangentbordskortkommando som öppnar snabbmenyn i Dynamics 365 for Operations.

## <a name="where-is-the-view-details-functionality-in-dynamics-365-for-operations"></a>Var är funktionen Visa information i Dynamics 365 for Operations?
Alternativet **Visa information** är tillgängligt på flera sätt:

-   Om en kontroll har funktionen **Visa information** och dessutom ett värde, kan värdet visas som en hyperlänk. Du kan klicka på hyperlänken när du vill öppna en sida som innehåller mer information.
-   **Visa information** är också ett alternativ på snabbmenyerna i Dynamics 365 for Operations. Mer information om när snabbmenyerna i Dynamics 365 for Operations visas när du högerklickar finns i föregående avsnitt.




