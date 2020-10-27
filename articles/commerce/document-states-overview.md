---
title: Dokumentera tillstånd och livscykel
description: I det här avsnittet beskrivs olika dokumentlägen för sidelement i Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
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
ms.openlocfilehash: 8aad7ef8425e46182c669686710dfc178abc418f
ms.sourcegitcommit: 83ec80382bfeb693d5c5949b6f65296bd50eed12
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "3974040"
---
# <a name="document-states-and-lifecycle"></a>Dokumentera tillstånd och livscykel

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs olika dokumentlägen för sidelement i Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Dokumenttillståndbeskrivning

I avsnittet [sidelement](page-elements-overview.md) visas olika dokumenttyper i innehållshanteringssystem (CMS). Dessa dokumenttyper kan ha flera lägen i redigeringsverktyget. Dokumenttillstånd bidrar till att förhindra datakonflikter och att använda versionskontroll. De bestämmer vem som kan ändra dokumenten, när dokumenten kan ändras och när andra personer kan visa dem.

I följande tabell visas de möjliga dokumenttillstånden för sidelement i handel.

| Dokumenttillstånd      | Åtgärd för webbplatsskaparen        | beskrivning                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| Utcheckad         | Välj **Redigera**.           | Det tillämpliga dokumentet är utcheckat till dig. När ett dokument är i det här tillståndet kan det inte ändras av andra autentiserade systemanvändare, och alla ändringar som du gör i dokumentet visas bara för dig. |
| Sparades               | Välj **Spara**.           | Ändringar som har gjorts i ett utcheckat dokument sparas i databasen men dokumentet har inte checkats in eller publicerats. De sparade ändringarna syns inte för andra autentiserade systemanvändare förrän författaren väljer **Avsluta redigering**. De visas inte för externa användare förrän objektet har publicerats. |
| Ignorerade utcheckning | Välj **ignorera redigeringar**.  | Alla ändringar av det utcheckade dokumentet ignoreras och objektet återgår till den senast incheckade versionen. |
| Incheckad          | Välj **Slutför redigering**. | Det redigerade dokumentet är incheckat. Alla ändringar är synliga för andra autentiserade systemanvändare och dessa användare kan sedan redigera dokumentet. Varje incheckning skapar en dokumentversionspost i historiken för artikeln. |
| Publicerat           | Markera **Publicera**.        | Dokumentet publiceras och ändringarna överförs till den aktiva webbplatsen och blir synliga för externa användare. Artiklar kan bara publiceras om de har checkats in först genom att du väljer **Slutför redigering**. |

## <a name="additional-resources"></a>Ytterligare resurser

[Sätt att lägga till innehåll](add-manage-content.md)

[Ordlista för sidmodell](page-elements-overview.md)

[Arbeta med publiceringsgrupper](publish-groups.md)

[Aktivera och använda delning av flera kanaler](cross-channel-sharing.md)

[Arbeta med moduler](work-with-modules.md)

[Arbeta med fragment](work-with-fragments.md)

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Anpassa webbplatsnavigeringen](customize-site-navigation.md)
