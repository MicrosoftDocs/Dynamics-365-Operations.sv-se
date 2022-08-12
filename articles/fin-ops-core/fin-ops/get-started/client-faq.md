---
title: Frågor och svar för klient
description: Det här avsnittet innehåller vanliga frågor och svar om Ekonomi och drift-klienten.
author: jasongre
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
ms.openlocfilehash: ca763f388bfc59951febf93f314d3df7e12c50cf
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124441"
---
# <a name="client-faq"></a>Vanliga frågor och svar för klient

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Det här avsnittet innehåller vanliga frågor och svar om Ekonomi och drift-klienten.

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
