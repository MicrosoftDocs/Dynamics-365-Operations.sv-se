---
title: Dynamics 365 Commerce utvärderingsmiljö – översikt
description: Det här ämnet ger en översikt över utvärderingsmiljö i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 25c0574e8d4502bcb846fba0ddf913d81eded87b
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599777"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a>Dynamics 365 Commerce utvärderingsmiljö – översikt

[!include [banner](includes/banner.md)]

Det här ämnet ger en översikt över utvärderingsmiljö i Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Commerce utvärderingsmiljöer är i allmänhet inte tillgängliga och ges till partners och kunder för varje enskild begäran. För mer information, kontakta din Microsoft-partnerkontakt.

## <a name="overview"></a>Översikt

Commerce utvärderingsmiljö är en valfri komplett miljö av Dynamics 365 Commerce som låter partners och potentiella kunder prova Commerce-produkten.

Utvärderingsmiljöer är delvis förkonfigurerade för att minska de nödvändiga åtgärderna efter etablering.

Bortsett från några mindre begränsningar som inte påverkar funktioner eller funktioner, tillhandahåller utvärderingsmiljö för Commerce den kompletta handels upplevelsen och kan användas av kunder och implementeringspartners för att utvärdera produkten, ge återkoppling och göra passform/gap-analys.

## <a name="limitations-of-the-commerce-evaluation-environment"></a>Begränsningar i utvärderingsmiljö Commerce

Även om utvärderingsmiljö Commerce innehåller en fullständig uppsättning handelsfunktioner och funktioner finns det några mindre begränsningar:

- Även om utvärderingsmiljö Commerce inte har några geografiska begränsningar, kan komponenter i miljön, till exempel Retail Cloud Scale Unit (RCSU) och e-handelsprogram, endast etableras i USA.
- Användning av utvärderingsmiljö för Commerce är begränsad till 30 dagar från det datum då e-handel etableras.
- Utvärderingsmiljö för Commerce kan distribueras och initieras endast i en miljö som använder demotopologin, där alla komponenter i en miljö distribueras i en enda molnstyrd virtuell dator (VM). Den huvudsakliga begränsningen för denna topologi är antalet samtidiga användare som miljön kan stödja.

## <a name="get-started"></a>Kom igång

Om du vill etablera utvärderingsmiljö för Commerce, se [Etablera en utvärderingsmiljö för Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Etablera en Dynamics 365 Commerce utvärderingsmiljön](provisioning-guide.md)

[Konfigurera en Dynamics 365 Commerce utvärderingsmiljö](cpe-post-provisioning.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce utvärderingsmiljö](cpe-bopis.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce utvärderingsmiljö](cpe-optional-features.md)

[Dynamics 365 Commerce utvärderingsmiljö – vanliga frågor](cpe-faq.md)
