---
title: Medarbetare väljer planer via medarbetarnas självbetjäning (valfritt)
description: I det här avsnittet beskrivs hur medarbetare kan välja eller uppdatera sina förmåner.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 68aa401487a74b9fcd186ec6cbdb268cdb41168c
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743498"
---
# <a name="employees-select-plans-by-using-employee-self-service-optional"></a>Medarbetare väljer planer via medarbetarnas självbetjäning (valfritt)


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

När en ny medarbetare anställs, eller en livshändelse inträffar, kan den anställde använda **Självbetjäning för medarbetare** för att välja eller uppdatera deras förmåner under öppen registrering.

Om du vill få åtkomst till deras förmåner för anmälan använder **medarbetaren självbetjäning** och väljer sedan **Självbetjäning för förmåner** i panelen **Förmåner**.

På sidan **Självbetjäning för förmåner** grupperas förmånsplaner efter plantyp. Om du vill visa förmånsplanerna i en plantyp väljer medarbetaren en panel på sidan **Medarbetarförmåner**. Medarbetaren ser bara de förmåner som han eller hon är berättigad till.

> [!IMPORTANT]
> Innan en plantyp kan visas i **Självbetjäning för medarbetare** måste den konfigureras. Mer information finns i [Konfigurera självbetjäning för medarbetare](/dynamics365/human-resources/hr-benefits-setup-employee-self-service).

Beroende på plantypen kan en eller flera förmåner väljas för anmälan. En typ av medicinsk plan kan till exempel konfigureras för att begränsa medarbetaren till en medicinsk plan. En typ av livförsäkringsplan kan göra det möjligt för medarbetaren att välja flera försäkringsplaner.

När medarbetaren har bestämt vilken plan som ska registreras kan det vara obligatoriskt för medarbetaren att välja anhörig. Om medarbetaren har valt ett disponeringsalternativ som är beroende **Medarbetare +1**, **Medarbetare + barn** eller **Familj**, måste markeras. Mer information om täckningsalternativ finns i [Skapa disponeringsalternativ](/dynamics365/human-resources/hr-benefits-setup-coverage-options).

För att välja en förmånsplan väljer medarbetaren antingen ellipsknappen (**...**) eller **Lägg till i vagnen**. När medarbetaren har lagt till alla förmånsval i vagnen väljer de **Visa vagn**. Medarbetaren visas sedan på sidan **Planer** där han eller hon kan visa de valda förmånsplanerna.

Medarbetaren måste välja alternativet **Jag accepterar** innan han eller hon kan välja knappen **Checka ut**. Utdraget som visas till höger om alternativet **Jag accepterar** kan anpassas på fliken **Förmånshantering** på sidan **Delade parametrar för Personal**.

När medarbetaren bekräftar sina val av förmånsplaner med **självbetjäning för medarbetare**, dessa val registreras och visas på sidorna **Förmånsplaner för medarbetare** och **Uppdatering av gruppuppdatering för förmånsplaner för arbetare**.

När medarbetaren har valt sina planer visas statusen för förmånerna som **Markerad**. När medarbetaren väljer **Checka ut** på sidan **Självbetjäning för förmåner** markeras alternativet **Utcheckat**.

> [!IMPORTANT]
> Om du vill slutföra anmälan måste förmånsadministratören välja **Bekräfta** för varje medarbetarförmåner som har valts. Bekräftelse kan genomföras på sidan **förmånsplan för arbetare** eller **Uppdatering av gruppuppdatering för förmånsplaner för arbetare**.
>

Medarbetare behöver inte välja förmåner genom att använda **självbetjäning för medarbetare**. Förmåner kan väljas på uppdrag av en medarbetare på sidan **förmånsplan för arbetare** eller **Uppdatering av gruppuppdatering för förmånsplaner för arbetare**. Medarbetaren kan inte anmälas till de här förmånerna förrän förmånsadministratören bekräftar dem.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
