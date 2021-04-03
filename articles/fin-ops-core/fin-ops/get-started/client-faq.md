---
title: Frågor och svar för klient
description: Det här avsnittet innehåller vanliga frågor och svar om den Finance and Operations-klienten.
author: jasongre
manager: AnnBe
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a7d311bfcd65e23e4062f105435d05cb1ceda6b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567050"
---
# <a name="client-faq"></a>Frågor och svar för klient

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller vanliga frågor och svar om den Finance and Operations-klienten.

## <a name="why-arent-symbols-loaded"></a>Varför läses inte symboler in?

Säkerhetinställningarna i din webbläsare kan hindra symbolerna från att läsas in korrekt. Lös problemet genom att pröva följande steg:

- Om du upplever problemet i Internet Explorer, klicka på **Verktyg** och klicka sedan på **Internetalternativ**. I dialogrutan Internet-alternativ på fliken **Sekretess** klickar du på **Anpassad nivå**, och kontrollerar att alternativet **Hämtning av teckensnitt** är valt.
- I annat fall måste du kanske lägga till appwebbplatsen i listan över betrodda webbplatser.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Jag saknar menyfliken från Dynamics AX 2012. Kan jag ha åtgärdsfönstrets flikar öppna hela tiden?

Vi planerar att implementera den här funktionen snart. Användarna kan sedan välja att behålla flikarna i åtgärdfönstren öppna hela tiden. Annars döljs flikarna när de inte används för att få mer skärmyta för sidan.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a>Varför visas ibland olika snabbmenyer när jag högerklickar?

Om du högerklickar i ett redigerbart fält (eller när text markeras) visas webbläsarens snabbmenyer. Menyn ger tillgång till **Klipp ut**, **Kopiera** och **Klistra in**. Du kan inte bädda in dessa kommandon i snabbmenyerna eftersom webbläsarna av säkerhetsskäl inte tillåter oss att öppna systemurklipp via programmering.

Om du högerklickar på en fältetikett eller värdet i en skrivskyddad kontroll visas snabbmenyn.

Vi vill göra det enklare att komma åt tangentbordet, så vi planerar att implementera ett tangentbordskortkommando som öppnar snabbmenyn.

## <a name="where-is-the-view-details-functionality"></a>Var är funktionen Visa information?

Alternativet **Visa information** är tillgängligt på flera sätt:

- Om en kontroll har funktionen **Visa information** och dessutom ett värde, kan värdet visas som en hyperlänk. Du kan klicka på hyperlänken när du vill öppna en sida som innehåller mer information.
- **Visa information** är även ett alternativ på snabbmenyerna. Mer information om när snabbmenyerna visas när du högerklickar finns i föregående avsnitt.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]