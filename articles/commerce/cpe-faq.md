---
title: Vanliga frågor om Dynamics 365 Commerce förhandsversionsmiljö
description: Det här avsnittet innehåller vanliga frågor och svar om förhandsversionsmiljön för Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 061a160380e500ea52afbc35f0a95fe84d971bcf
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024762"
---
# <a name="dynamics-365-commerce-preview-environment-faq"></a>Vanliga frågor om Dynamics 365 Commerce förhandsversionsmiljö

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller vanliga frågor och svar om förhandsversionsmiljön för Microsoft Dynamics 365 Commerce.

**Kan jag överföra min inbjudan för förhandsversionsmiljön för Commerce till en annan klientorganisation?**

Ja. För inbjudningsöverföringar kan du använda formuläret [förhandsgranskningsformulär för överföring av Commerce](https://aka.ms/Dynamics365CommercePreviewTransferForm).

**Hur lång tid tar inbjudningsöverföringen?**

Överföringen tar i genomsnitt cirka tre till fem arbetsdagar. Undantag kan dock gälla.

**Fungerar förhandsversionsmiljö för Commerce med Dynamics 365 Finance eller Dynamics 365 Supply Chain-projekt?**

Nr. Förhandsversionsmiljön för Commerce fungerar bara med Dynamics 365 Retail-projekt.

**Kan vi använda förhandsversionsmiljön för Commerce som ett e-handelsskyltfönstret för kunder som för närvarande implementerar Retail?**

Nr. Förhandsversionsmiljön för Commerce är bara utvärderingsmiljön. Om du behöver en miljö för en kund som implementerar Retail kontaktar du Microsoft.

**Kan förhandsversionsmiljön för Commerce användas för att etablera e-handelsfunktioner ovanpå ett befintligt program/miljö som implementerar Retail?**

Nr. Förhandsversionsmiljön för Commerce är för närvarande endast tillgänglig i nya miljöer som har distribuerats på projekt för Retail lagerhållningsenhet (SKU) som har demonstrationsdata från version 10.0.6.

**Vilka kostnader är inblandade i att distribuera förhandsversionsmiljön för Commerce Microsoft Azure på Microsoft Dynamics Lifecycle Services (LCS)?**

Retail är den enda komponent som är värd för din prenumeration. Andra komponenter som Retail Cloud Scale Unit (RCSU) och e-handel kommer att vara värd i Microsoft-prenumerationer. Du kan använda [Azure priskalkylatorn](https://azure.microsoft.com/pricing/calculator/) för att uppskatta den här kostnaden.

**Vilka Azure-geografiska områden stöds för närvarande i förhandsversionsmiljön Commerce?**

Förhandsversionsmiljön för Commerce kan endast distribueras i Nordamerikas geografi.

**Finns det en nedladdningsbar virtuell hårddisk (VHD) som har alternativet fullständig OneBox virtuell dator (VM)?**

Dynamics 365 Retail Cloud Scale Unit (RCSU) och e-handel är helt programvara som en tjänst (SaaS) och måste vara molnbaserade.

**Hur länge kan förhandsversionsmiljön för Commerce användas?**

Förhandsversionsmiljö för Commerce har en 30 dagars begränsning från det datum då e-handel etableras.

**Kan jag förlänga tidsgränsen för min förhandsversionsmiljö för Commerce?**

Ja. Du kan kontakta supportteamet med hjälp av [tilläggsformuläret förhandsversionsmiljö för Commerce](https://aka.ms/Dynamics365CommercePreviewExtensionForm).

**Kan vi göra flera förfrågningar om en förhandsversionsmiljö för Commerce?**

Vi beviljar en kvot för en förhandsversionsmiljö för Commerce för varje begäran som accepteras. Om du behöver mer än en förhandsgranskningsmiljö kontaktar du Microsoft. Se nästa avsnitt för kontaktinformation.

## <a name="dynamics-365-commerce-preview-environment-contact-information"></a>Dynamics 365 Commerce kontaktinformation för förhandsgranskningsmiljön

Om du vill kontakta Microsoft om du har frågor eller begäranden som är relaterade till förhandsversionsmiljö för Commerce, besök [förhandsversionsmiljö för Microsoft Dynamics 365 Commerce Yammer-grupp](https://aka.ms/Dynamics365CommercePreviewYammer) för att få hjälp.

Om du får problem när du försöker komma åt Yammer-gruppen kan du kontakta Microsoft via e-post på <Dynamics365Commerce@microsoft.com>. Den här e-postadressen övervakas inte aktivt. Förvänta dig därför en fördröjning i svaret.

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce förhandsversionsmiljö – översikt](cpe-overview.md)

[Etablera en Dynamics 365 Commerce förhandsversionsmiljö](provisioning-guide.md)

[Konfigurera en förhandsversionsmiljö för Dynamics 365 Commerce](cpe-post-provisioning.md)

[Konfigurera valfria funktioner för en förhandsversionsmiljö för Dynamics 365 Commerce](cpe-optional-features.md)
