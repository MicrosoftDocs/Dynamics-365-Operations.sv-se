---
title: Förhandsversionsmiljö för Commerce – översikt
description: Det här ämnet ger en översikt över förhandsversionsmiljö i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
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
ms.openlocfilehash: 901583afde4739be5313fa129ff0e52f11326881
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906080"
---
# <a name="commerce-preview-environment-overview"></a>Förhandsversionsmiljö för Commerce – översikt

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här ämnet ger en översikt över förhandsversionsmiljö i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Commerce förhandsversionsmiljön är en valfri förhandsversionsmiljö av Dynamics 365 Commerce som låter potentiella kunder prova Commerce-produkten innan den allmänna utgåvan släpps till allmänheten.

Bortsett från några mindre begränsningar som inte påverkar funktioner eller funktioner, tillhandahåller förhandsversionsmiljön för Commerce den kompletta handels upplevelsen och kan användas av kunder och implementeringspartners för att utvärdera produkten, ge återkoppling och göra passform/gap-analys.

## <a name="limitations-of-the-commerce-preview-environment"></a>Begränsningar i förhandsversionsmiljö Commerce

Även om förhandsversionsmiljön Commerce innehåller en fullständig uppsättning handelsfunktioner och funktioner finns det några mindre begränsningar:

- Även om förhandsversionsmiljö Commerce inte har några geografiska begränsningar, kan komponenter i miljön, till exempel Retail Cloud Scale Unit (RCSU) och e-handelsprogram, endast etableras i USA.
- Användning av förhandsversionsmiljö för Commerce är begränsad till 30 dagar från det datum då e-handel etableras.
- Förhandsversionsmiljö för Commerce kan distribueras och initieras endast i en miljö som använder demotopologin, där alla komponenter i en miljödistribueras i en enda virtuell dator (VM). Den huvudsakliga begränsningen för denna OneBox VM-topologi är antalet samtidiga användare som förhandsversionen miljön kan stödja.
- Förhandsversionsmiljö för Commerce kan endast utvärderas till den allmänna tillgängligheten (GA) för Commerce-produkten. Nya demomiljöer kommer att finnas tillgängliga efter GA.

## <a name="get-started"></a>Kom igång

Om du vill etablera förhandsversionsmiljö för Commerce, se [Etablera en förhandsversionsmiljö för Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Etablera en förhandsversionsmiljö för Commerce](provisioning-guide.md)

[Konfigurera en förhandsversionsmiljö för Commerce](cpe-post-provisioning.md)

[Konfigurera valfria funktioner för en förhandsversionsmiljö för Commerce](cpe-optional-features.md)

[Förhandsversionsmiljö för Commerce – vanliga frågor och svar](cpe-faq.md)
