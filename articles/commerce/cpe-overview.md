---
title: Ställ in en Dynamics 365 Commerce utvärderingsmiljö – översikt
description: Det här ämnet ger en översikt över bedömningsmiljö i Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f225db13fba91ce78287adfda9c6d084dea20af33e62287f517e51cc5a296352
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752522"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a>Ställ in en Dynamics 365 Commerce utvärderingsmiljö – översikt

[!include [banner](includes/banner.md)]

Det här ämnet ger en översikt över bedömningsmiljö i Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Commerce bedömningsmiljöer är i allmänhet inte tillgängliga och ges till partners och kunder för varje enskild begäran. För mer information, kontakta din Microsoft-partnerkontakt.

Commerce bedömningsmiljö är en valfri komplett miljö av Dynamics 365 Commerce som låter partners och potentiella kunder prova Commerce-produkten.

Bedömningsmiljöer är delvis förkonfigurerade för att minska de nödvändiga åtgärderna efter etablering.

Bortsett från några mindre begränsningar som inte påverkar funktioner eller funktioner, tillhandahåller bedömningsmiljö för Commerce den kompletta handels upplevelsen och kan användas av kunder och implementeringspartners för att utvärdera produkten, ge återkoppling och göra passform/gap-analys.

## <a name="limitations-of-the-commerce-evaluation-environment"></a>Begränsningar i bedömningsmiljö Commerce

Även om bedömningsmiljö Commerce innehåller en fullständig uppsättning handelsfunktioner och funktioner finns det några mindre begränsningar:

- Även om bedömningsmiljö Commerce inte har några geografiska begränsningar, kan komponenter i miljön, till exempel Retail Cloud Scale Unit (RCSU) och näthandelsprogram, endast etableras i USA.
- Användning av bedömningsmiljö för Commerce är begränsad till 30 dagar från det datum då näthandel etableras.
- Bedömningsmiljö för Commerce kan distribueras och initieras endast i en miljö som använder demotopologin, där alla komponenter i en miljö distribueras i en enda molnstyrd virtuell dator (VM). Den huvudsakliga begränsningen för denna topologi är antalet samtidiga användare som miljön kan stödja.

## <a name="get-started"></a>Kom igång

Om du vill etablera bedömningsmiljö för Commerce, se [Etablera en bedömningsmiljö för Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Etablera en Dynamics 365 Commerce bedömningsmiljön](provisioning-guide.md)

[Konfigurera en Dynamics 365 Commerce bedömningsmiljö](cpe-post-provisioning.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö](cpe-bopis.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö](cpe-optional-features.md)

[Dynamics 365 Commerce bedömningsmiljö – vanliga frågor](cpe-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
