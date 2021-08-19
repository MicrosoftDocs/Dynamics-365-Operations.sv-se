---
title: Dynamics 365 Commerce bedömningsmiljö – vanliga frågor
description: Det här avsnittet innehåller vanliga frågor och svar om bedömningsmiljö för Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1e69aa3cb81dceb7af4cd15536164ac40d234e5fbc7f661612bc84dbb0983837
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712776"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>Dynamics 365 Commerce utvärderingsmiljö – Vanliga frågor och svar

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller vanliga frågor och svar om bedömningsmiljö för Microsoft Dynamics 365 Commerce.

**Kan vi använda bedömningsmiljön för Commerce som ett näthandelsskyltfönstret för kunder som för närvarande implementerar Retail?**

Nr. Commerce bedömningsmiljön är endast till för utvärdering. Om du behöver en miljö för en kund som implementerar Retail kontaktar du Microsoft.

**Kan bedömningsmiljön för Commerce användas för att etablera näthandelsfunktioner ovanpå ett befintligt program/miljö som implementerar Retail?**

Nej (oftast). Commerce bedömningskomponenterna är bara tillgängliga för miljöer som matchar de konfigurationer som anges i guiden för förutsättningar. Dessutom är de nödvändiga grundläggande demodata inte tillgängliga i miljöer som distribuerades med en första utgåva som är tidigare än 10.0.8. 

**Vilka kostnader är inblandade i att distribuera bedömningsmiljö för Commerce Microsoft Azure på Microsoft Dynamics Lifecycle Services (LCS)?**

En traditionell Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce huvudkontoret demomiljö (virtuell dator \[VM\]) kommer att finnas i Azure-prenumeration. Du kan använda [Azure priskalkylatorn](https://azure.microsoft.com/pricing/calculator/) för att uppskatta den här kostnaden.

Andra komponenter, t.ex. Commerce Scale Unit, Commerce webbplatsskaparen och din näthandelssajt kommer att vara tillgängliga som en tjänst (SaaS) och värd från Microsoft.

**Vilka Azure-geografiska områden stöds för närvarande i bedömningsmiljön Commerce?**

Bedömningsmiljö för Commerce kan endast distribueras i Nordamerikas geografi.

**Finns det en nedladdningsbar virtuell hårddisk (VHD) som har alternativet fullständig OneBox virtuell dator (VM)?**

Dynamics 365 Commerce och Commerce Scale Unit är helt programvara som en tjänst (SaaS) och måste vara molnbaserade.

**Hur länge kan bedömningsmiljön för Commerce användas?**

Commerce bedömningsmiljön har en tidsgräns på 30 dagar från det datum då SaaS-komponenter som Commerce Scale Unit, Commerce webbplatsskaparen och din näthandelssajt etableras.

**Kan jag förlänga tidsgränsen för min bedömningsmiljö för Commerce?**

Förlängning av tidsgränsen är ett undantag från normen och beaktas från fall till fall. Du bör kontakta din Microsoft-partnerkontakt för hjälp.

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce bedömningsmiljö – översikt](cpe-overview.md)

[Etablera en Dynamics 365 Commerce bedömningsmiljön](provisioning-guide.md)

[Konfigurera en Dynamics 365 Commerce bedömningsmiljö](cpe-post-provisioning.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö](cpe-bopis.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]