---
title: Förbättrad hantering av batchspårade artiklar
description: I det här avsnittet beskrivs de förbättringar som gjorts av hanteringen av batchar för batchspårade artiklar under bokföringsprocessen av butiksutdrag.
author: josaw1
manager: AnnBe
ms.date: 05/28/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4456fc3d5bc4547fa8211642b11ca6df455fa187
ms.sourcegitcommit: aec1dcd44274e9b8d0770836598fde5533b7b569
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2019
ms.locfileid: "1617399"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Förbättrad hantering av batchspårade artiklar

I Microsoft Dynamics 365 for Retail-kassan kan batchnummer inte registreras för batchspårade artiklar vid försäljningstillfället. För specifika konfigurationer, när försäljning bokförs vid huvudkontoret genom kundorder- eller utdragsbokföring, förväntar sig Microsoft Dynamics-systemet att det finns giltiga batchnummer för batchspårade artiklar och att de ska användas under faktureringen.

Om det finns giltiga batchnummer för produkter används de vid faktureringsprocessen för kundorder och försäljningsorder från utdragsbokföringen. Annars kan faktureringen av kundorder inte bokföras och kassaanvändaren får ett felmeddelande. Utdragsbokföringen går sedan in i ett feltillstånd. Det här feltillståndet inträffar även när ett negativt lager har aktiverats för produkterna.

När negativt lager har aktiverats för batchspårade artiklar innebär de förbättringar som gjorts i Microsoft Dynamics for Retail version 10.0.4 och senare att faktureringen av kund- och försäljningsorder som görs via utdragsbokföring inte blockeras för dessa artiklar om lagret är 0 (noll) eller om det inte finns något batchnummer. Den nya funktionen använder ett standardiserat batch-ID för försäljningsrader när det inte finns batchnummer.

Du definierar standardvärdet för det batch-ID som används för kundorder i fältet **Standard-batch-ID**, på snabbfliken **Order**, på fliken **Kundorder** på sidan **Butiksparametrar**.

Du definierar standardvärdet för det batch-ID som används för försäljningsorder via utdragsbokföring i fältet **Standard-batch-ID**, på snabbfliken **Lageruppdatering**, på fliken **Bokföring** på sidan **Butiksparametrar**.

> [!NOTE]
> Den här funktionen är bara tillgänglig när avancerad lagerstyrning har aktiverats för det specifika butikslagret och artiklarna. I en senare version kommer funktionen också att fungera för tillfällen då avancerad lagerstyrning inte används.
