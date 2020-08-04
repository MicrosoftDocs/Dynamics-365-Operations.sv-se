---
title: Dynamics 365 Commerce utvärderingsmiljö – vanliga frågor
description: Det här avsnittet innehåller vanliga frågor och svar om utvärderingsmiljö för Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 637714e28b9f8f4aa66e251e709d8f78bff2739d
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599780"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>Dynamics 365 Commerce utvärderingsmiljö – vanliga frågor

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller vanliga frågor och svar om utvärderingsmiljö för Microsoft Dynamics 365 Commerce.

**Kan vi använda utvärderingsmiljön för Commerce som ett e-handelsskyltfönstret för kunder som för närvarande implementerar Retail?**

Nr. Commerce utvärderingsmiljön är endast till för utvärdering. Om du behöver en miljö för en kund som implementerar Retail kontaktar du Microsoft.

**Kan utvärderingsmiljön för Commerce användas för att etablera e-handelsfunktioner ovanpå ett befintligt program/miljö som implementerar Retail?**

Nej (oftast). Commerce utvärderingskomponenterna är bara tillgängliga för miljöer som matchar de konfigurationer som anges i guiden för förutsättningar. Dessutom är de nödvändiga grundläggande demodata inte tillgängliga i miljöer som distribuerades med en första utgåva som är tidigare än 10.0.8. 

**Vilka kostnader är inblandade i att distribuera utvärderingsmiljö för Commerce Microsoft Azure på Microsoft Dynamics Lifecycle Services (LCS)?**

En traditionell Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce huvudkontoret demomiljö (virtuell dator \[VM\]) kommer att finnas i Azure-prenumeration. Du kan använda [Azure priskalkylatorn](https://azure.microsoft.com/pricing/calculator/) för att uppskatta den här kostnaden.

Andra komponenter, t.ex. Commerce Scale Unit, Commerce webbplatsskaparen och din e-handelswebbplats kommer att vara tillgängliga som en tjänst (SaaS) och värd från Microsoft.

**Vilka Azure-geografiska områden stöds för närvarande i utvärderingsmiljön Commerce?**

Utvärderingsmiljö för Commerce kan endast distribueras i Nordamerikas geografi.

**Finns det en nedladdningsbar virtuell hårddisk (VHD) som har alternativet fullständig OneBox virtuell dator (VM)?**

Dynamics 365 Commerce och Commerce Scale Unit är helt programvara som en tjänst (SaaS) och måste vara molnbaserade.

**Hur länge kan utvärderingsmiljön för Commerce användas?**

Commerce utvärderingsmiljön har en tidsgräns på 30 dagar från det datum då SaaS-komponenter som Commerce Scale Unit, Commerce webbplatsskaparen och din e-handelswebbplats etableras.

**Kan jag förlänga tidsgränsen för min utvärderingsmiljö för Commerce?**

Förlängning av tidsgränsen är ett undantag från normen och beaktas från fall till fall. Du bör kontakta din Microsoft-partnerkontakt för hjälp.

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce utvärderingsmiljö – översikt](cpe-overview.md)

[Etablera en Dynamics 365 Commerce utvärderingsmiljön](provisioning-guide.md)

[Konfigurera en Dynamics 365 Commerce utvärderingsmiljö](cpe-post-provisioning.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce utvärderingsmiljö](cpe-bopis.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce utvärderingsmiljö](cpe-optional-features.md)
