---
title: Nyheter och ändringar i Dynamics 365 Human Resources 19 november 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i den fristående Microsoft Dynamics 365 Human Resources 19 november 2021.
author: marcelbf
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 618d90f95637002f444b334e16d3fef466dda65e
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087484"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 19 november 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver nya, ändrade och kommande funktioner i Microsoft Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Dynamics 365 Human Resources 2021 utgivningsvåg 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

Den här versionen innehåller följande felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4591.

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan komma att uppdatera detta ämne i syfte att inkludera felkorrigeringar som kommit med i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem | Beskrivning |
|---|---|---|
| 626178 | Navigering saknas bland arbetaren när han eller hon är **Självbetjäning för chef** | Det här problemet är nu fast. Navigeringen är tillgänglig om du vill visa rapportinformation i **Självbetjäning för chef**. |
| 632573 | Det finns inget valideringsfel när du sparar en **kurs** | Det här problemet är nu fast. När vi skapar en kurs med **lägst antal deltagare** till större än 0 var fortfarande tillåten att sparas även när **högsta antal deltagare** är 0. |
| 615955 | Fel "Fält **syfte** måste fyllas i" när du skapar en ny plats för rekryteringsförfrågan. | När du skapar en adress för en ny plats för rekryteringsförfrågan får du felet: "Fält "Syfte" måste fyllas i." Men fältet **Syfte** är inte tillgängligt på sidan. |
| 620797 | Felet tomt **kön** beror på vilket fel som uppstår | Om inget kön har angetts för en personlig kontakt visas rapporten "Klicka eller hör här för att ange text" – Som beror på att det inte går att ange något i fältet. |
| 620800 | Länken för förmånsutdrag är dold | Förmånsutdraget kan inte visas som standard i **självbetjäning för medarbetare**.  En länk har lagts till höger om **självbetjäning för medarbetare** under avsnittet **Länkar** |
| 629778 | Prestandaproblem med CDS-integration. | Auktoriseringsrelaterad begäran orsakar prestandaproblem. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar och inaktiverar funktioner finns i [Hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
|---|---|---|
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>Kommer snart
En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Dynamics 365 och industrimoln: 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
