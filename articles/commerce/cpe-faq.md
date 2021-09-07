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
ms.openlocfilehash: e8a3e760353b351d42aff82c0d372d2aca350cd2
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343568"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>Dynamics 365 Commerce utvärderingsmiljö – Vanliga frågor och svar

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller vanliga frågor och svar om bedömningsmiljö för Microsoft Dynamics 365 Commerce.

## <a name="can-we-use-the-commerce-evaluation-environment-as-an-e-commerce-storefront-for-customers-that-currently-implement-retail"></a>Kan vi använda bedömningsmiljön för Commerce som ett näthandelsskyltfönstret för kunder som för närvarande implementerar Retail?

Nr. Commerce bedömningsmiljön är endast till för utvärdering. Om du behöver en miljö för en kund som implementerar Retail kontaktar du Microsoft.

## <a name="can-the-commerce-evaluation-environment-be-used-to-provision-the-e-commerce-features-on-top-of-an-existing-applicationenvironment-that-implements-retail"></a>Kan bedömningsmiljön för Commerce användas för att etablera näthandelsfunktioner ovanpå ett befintligt program/miljö som implementerar Retail?

Nej (oftast). Commerce bedömningskomponenterna är bara tillgängliga för miljöer som matchar de konfigurationer som anges i guiden för förutsättningar. Dessutom är de nödvändiga grundläggande demodata inte tillgängliga i miljöer som distribuerades med en första utgåva som är tidigare än 10.0.8. 

## <a name="what-costs-are-involved-in-deploying-the-commerce-evaluation-environment-on-microsoft-azure-via-microsoft-dynamics-lifecycle-services-lcs"></a>Vilka kostnader är inblandade i att distribuera bedömningsmiljö för Commerce på Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?

En traditionell Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce huvudkontoret demomiljö (virtuell dator \[VM\]) kommer att finnas i Azure-prenumeration. Du kan använda [Azure priskalkylatorn](https://azure.microsoft.com/pricing/calculator/) för att uppskatta den här kostnaden.

Andra komponenter, t.ex. Commerce Scale Unit, Commerce webbplatsskaparen och din näthandelssajt kommer att vara tillgängliga som en tjänst (SaaS) och värd från Microsoft.

## <a name="which-azure-geographies-are-currently-supported-for-the-commerce-evaluation-environment"></a>Vilka Azure-geografiska områden stöds för närvarande i bedömningsmiljön Commerce?

Bedömningsmiljö för Commerce kan endast distribueras i Nordamerikas geografi.

## <a name="is-there-a-downloadable-virtual-hard-disk-vhd-that-has-the-complete-onebox-virtual-machine-vm-option"></a>Finns det en nedladdningsbar virtuell hårddisk (VHD) som har alternativet fullständig OneBox virtuell dator (VM)?

Dynamics 365 Commerce och Commerce Scale Unit är helt programvara som en tjänst (SaaS) och måste vara molnbaserade.

## <a name="how-long-can-the-commerce-evaluation-environment-be-used"></a>Hur länge kan bedömningsmiljön för Commerce användas?

Commerce bedömningsmiljön har en tidsgräns på 30 dagar från det datum då SaaS-komponenter som Commerce Scale Unit, Commerce webbplatsskaparen och din näthandelssajt etableras.

## <a name="can-i-extend-the-time-limit-for-my-commerce-evaluation-environment"></a>Kan jag förlänga tidsgränsen för min bedömningsmiljö för Commerce?

Förlängning av tidsgränsen är ett undantag från normen och beaktas från fall till fall. Du bör kontakta din Microsoft-partnerkontakt för hjälp.

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce bedömningsmiljö – översikt](cpe-overview.md)

[Etablera en Dynamics 365 Commerce bedömningsmiljön](provisioning-guide.md)

[Konfigurera en Dynamics 365 Commerce bedömningsmiljö](cpe-post-provisioning.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö](cpe-bopis.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
