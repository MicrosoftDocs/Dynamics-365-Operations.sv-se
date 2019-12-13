---
title: Dokumentera tillstånd och livscykel
description: I det här avsnittet beskrivs olika dokumentlägen för sidelement i Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a34d10edbf84ac1814afdc7107727aea68a303e0
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770445"
---
# <a name="document-states-and-lifecycle"></a>Dokumentera tillstånd och livscykel

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs olika dokumentlägen för sidelement i Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Dokumenttillståndbeskrivning

I avsnittet [sidelement](page-elements-overview.md) visas olika dokumenttyper i innehållshanteringssystem (CMS). Dessa dokumenttyper kan ha flera lägen i redigeringsverktyget. Dokumenttillstånd bidrar till att förhindra datakonflikter och att använda versionskontroll. De bestämmer vem som kan ändra dokumenten, när dokumenten kan ändras och när andra personer kan visa dem.

I följande tabell visas de möjliga dokumenttillstånden för sidelement i handel.

| Dokumenttillstånd | Beskrivning |
|---|---|
| Utcheckad | När ett CMS-objekt är utcheckat till dig kan det inte redigeras av andra autentiserade systemanvändare. Alla ändringar du gör i objektet är bara synliga för dig. |
| Incheckad | När ett CMS-objekt checkas in, visas alla ändringar för andra autentiserade systemanvändare och dessa användare kan sedan checka ut objektet och redigera det. Varje incheckning skapar en dokumentversionspost i historiken för artikeln. |
| Publicerad | När ett CMS-objekt publiceras flyttas det till den aktiva platsen och kan upptäckas på Internet av icke-autentiserade externa användare. Artiklar kan bara publiceras om de har checkats in. |
| Sparade | Ändringar som har gjorts i ett utcheckat CMS-objekt kan sparas till CMS-filen innan objektet checkas in eller publiceras. De sparade ändringarna syns inte för andra autentiserade systemanvändare förrän objektet checkas in. De visas inte för externa användare förrän objektet har publicerats. |
| Ignorerade utcheckning | När ett utcheckat CMS-objekt ignoreras tas alla sparade ändringar bort och objektet återgår till den senaste incheckade versionen. |

## <a name="additional-resources"></a>Ytterligare resurser

[Sätt att lägga till innehåll](add-manage-content.md)

[Ordlista för sidmodell](page-elements-overview.md)

[Arbeta med moduler](work-with-modules.md)

[Arbeta med fragment](work-with-fragments.md)

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Anpassa webbplatsnavigeringen](customize-site-navigation.md)
