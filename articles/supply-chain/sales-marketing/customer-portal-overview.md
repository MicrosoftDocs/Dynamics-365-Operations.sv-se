---
title: Kundportal för Dynamics 365 Supply Chain Management översikt (innehåller video)
description: I det här avsnittet introduceras kundportalen och det beskrivs vilka personer som ska använda dem och hur de fungerar.
author: Henrikan
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c1383ee3c8e72f630d29a557de4150cdd3aa905f
ms.sourcegitcommit: ef0dd4245fc499907ffe00e2a32f59a6cd96e45d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/18/2021
ms.locfileid: "7937514"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>Kundportal för Dynamics 365 Supply Chain Management – översikt

[!include [banner](../includes/banner.md)]
[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="what-is-the-customer-portal"></a>Vad är kundportalen?

Moderna försörjningskedjesystem är beroende av integration. De kräver att lager, kund efter frågeställningen och försäljningsavdelningen integreras i olika silor. Kundportalen hjälper organisationer som kör Microsoft Dynamics 365 Supply Chain Management förbättra integrationen och effektivare hålla kunderna underrättade.

Kundportalen är en [Power Apps](/powerapps/maker/portals/overview)-mall för portaler som gör det möjligt för företag att skapa en externt tillverkande webbplats (B2B) för scenarier som rör bearbetning av försäljningsorder. Mallen använder [dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md), Supply Chain Management och Power Apps-portaler för att göra det möjligt för externa företagskunder att visa och skapa data från företagets Dynamics 365-miljö.

Kundportalmallen har alla anpassningsmöjligheter som de portalfunktioner Power Apps erbjuder. Mallen kan enkelt ändras för att representera företagets varumärke, lägga till fler funktioner och ändra användarupplevelsen. Alla funktioner som mallen ger ut från rutan kan ändras efter behov.

> [!IMPORTANT]
> Mallen förväntas inte vara helt funktionell. Den fungerar som en person som aktiverar kunder som vill skapa en extern webbplats så att företags kunder kan kommunicera med data från Supply Chain Management.

> [!NOTE]
> Kundportaldokumentationen riktar sig till administratörer, systemanpassare och systemintegrerare som ställer in kundportalen för en Supply Chain Management-installation. Med hjälp av termerna _kund_ och _användare_ kan du beskriva personer som är kunder i organisationen som kör Supply Chain Management och vem som ska använda den sista portalen.

## <a name="video"></a>Video

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ylwW]

[Översikten över kundportalmallen i Dynamics 365 Supply Chain Management](https://youtu.be/nPrqoLuHfV8) video (visas ovan) finns med i [Finance and Operations spellistan](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) tillgänglig på YouTube.

## <a name="who-should-use-it"></a>Vem ska använda den?

Kundportalen är utformad för företag som kör Supply Chain Management och har följande egenskaper:

- De vill skapa en extern webbplats som förmedlar orderbearbetningsinformation (t.ex. orderstatus eller kontoinformation) direkt från systemet för Supply Chain Management-system till sina företagskunder.
- De övergår från Dynamics AX 2012 till Supply Chain Management och tidigare använt [AX 2012 Customer Self Service-portal](/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal).

Följande typer av organisationer är **inte** bra kandidater för att implementera kundportalen:

- Företag som vill bygga en webbplats för andra än företagskunder. Dessa företag bör överväga att skapa en [Dynamics 365 Commerce näthandelswebbplats](../../commerce/create-ecommerce-site.md).
- Företag som redan använder en webbplats med en befintlig Power Apps-portal för ett liknande syfte. Dessa företag tar inte emot några ytterligare förmåner från kundportalen. Kundportalen levereras som en mall som fungerar som en mall och är en utgångspunkt för kunder som vill "ansluta punkter" mellan dubbelriktad skrivning, Supply Chain Management och Power Apps-portaler. Om du redan har ställt in en webbplats som tjänar det kanske du inte får mycket värde från att använda kundportal mal len för att återupprätta webbplatsen.

## <a name="how-does-it-work"></a>Hur fungerar det?

Kundportalen utgörs av en Power Apps-mall för portaler. Det beror på Power Apps-portaler och dubbelriktad skrivning.

[Power Apps-portaler](/powerapps/maker/portals/overview) är en funktion som gör att användarna kan skapa webbplatser på en extern webbplats som personer utanför företaget kan logga in på. Liten till ingen kod krävs för att göra portaler. Kundportalen är en av många [Dynamics 365-portalmallar](/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365) som är tillgängliga från Microsoft.

[Dubbelriktad skrivning](/powerapps/maker/portals/overview) är en medföljande infrastrukturptodukt som ger nära realtidssamverkan mellan kundengagemangsappar och Finance and Operations-appar. Dubbelriktad skrivning ger dubbelriktad integration mellan Finance and Operations-appar och Microsoft Dataverse. Därför ger den ett integrerat användargränssnitt mellan programmen. Kundportalen är beroende av tabeller som har synkroniserats med dubbelriktad skrivning. Innan data från Supply Chain Management kan placeras i kundportalen måste dubbelriktade skrivfunktioner aktiveras för alla lämpliga tabeller.

![Kundportalberoenden.](media/customer-portal-elements.png "Kundportalberoenden")

Kundportalen fungerar som utgångspunkt för organisationer som vill använda Power Apps-portaler för att skapa en extern webbplats som använder data från en installation av Supply Chain Management. Det hjälper organisationer att ansluta dubbelriktad, Supply Chain Management och Power Apps-portaler.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]