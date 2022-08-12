---
title: Ställa in säkerhet för kostnadsredovisningsanalys Power BI-innehåll
description: Den här artikeln beskriver hur du kan sprida säkerhet för åtkomstnivå i kostnadsredovisning till säkerhet för radnivå i Microsoft Power BI.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom:
- "270294"
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.openlocfilehash: 555a815446a6aaca51ed973b5fa43a0a5ab3df83
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206247"
---
# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Ställa in säkerhet för kostnadsredovisningsanalys Power BI-innehåll

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du kan sprida säkerhet för åtkomstnivå i kostnadsredovisning till säkerhet för radnivå i Microsoft Power BI. Dessa funktioner hjälper till att säkerställa att användare bara ser Power BI-data som de har beviljats åtkomst till.

## <a name="overview"></a>Översikt

**Kostnadsredovisningsanalys** Microsoft Power BI-innehållet använder Power BI-säkerhet på radnivå för att begränsa en användares åtkomst. Säkerheten baseras på den organisationshierarki på åtkomstnivå som har ställts in i parametrar för kostnadsredovisning. Mer information om **Kostnadsredovisningsanalys** Power BI-innehåll finns i [Kostnadsredovisningsanalys för Power BI-innehåll](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Konfigurera
Om du vill sprida säkerhet på åtkomstnivå till Power BI måste Power BI-innehållet följa dessa steg.

> [!NOTE]
> Användare som publicerar **Kostnadsredovisningsanalys** för Power BI-innehåll blir automatiskt ägare. Endast en ägare kan ställa in säkerhet i Power BI. Dessutom, tills ägaren lägger till andra användare i PowerBI.com kan ingen förutom ägaren se några data i **Kostnadsredovisningsanalys** för Power BI-innehåll.

1. Publicera definitionsfilen till Power BI.
2. Logga in på PowerBI.com.
3. Hitta datamängden för **Kostnadsredovisningsanalys** för Power BI-innehåll.
4. Öppna säkerhetssidan.

    ![Öppna säkerhetssidan.](./media/CA-picture-1.png)

5. Rollen **Kostnadsobjektcontroller** har redan skapats. Lägg till andra medlemmar som ingår i organisationshierarkin på åtkomstnivå för kostnadsredovisning.

    ![Lägga till medlemmar.](./media/CA-picture-2.png)

Användare som läggs till i rollen **Kostnadsobjektcontroller** kommer endast att se de data som de får tillstånd att se enligt definitionen i organisationshierarkin på åtkomstnivå för kostnadsredovisning.

> [!NOTE]
> Säkerhet på radnivå som gäller för paneler och rapporter som bäddas in från Power BI.

## <a name="updating-security"></a>Uppdatera säkerhet
Om uppdateringar görs av säkerhet på åtkomstnivå i kostnadsredovisningen och du vill att Power BI ska återspegla dessa uppdateringarna, måste du uppdatera enhetsbutiken **Kostnadsredovisningsanalys** för Power BI-innehåll. När du har slutfört uppdateringen av enhetsbutiken måste du uppdatera artefakterna på PowerBI.com. Mer information om hur du gör en uppdatering av enhetsbutik finns i [Power BI-integrering med enhetsbutik](power-bi-integration-entity-store.md#update-entity-store). Ägaren av **Kostnadsredovisningsanalys** för Power BI-innehåll måste också göra en uppdatering av enhetsbutiken om nya användare beviljas åtkomst till organisationshierarkin. Dessutom måste ägaren lägga till nya användare till rollen **Kostnadsobjektcontroller** i PowerBI.com, så att säkerhet på radnivå tillämpas för dem.

## <a name="disabling-security"></a>Inaktivera säkerhet
Vi utgår från att din organisation vill begränsa dataåtkomst. Om säkerhetsparametrarna av någon anledning är inaktiverade när du kör kostnadsredovisning måste ägaren istället lägga till rollen **Kostnadsredovisare** i Power BI. Om du ändrar säkerhet från ett aktiverat tillstånd till inaktiverat är det en bra idé att ta bort användare från rolleb **Kostnadsobjektcontroller**. Och tvärtom när du aktiverar säkerhet igen. Användare kan tillhöra båda rollerna. Gemensam åtkomst är unionen av båda rollerna. I fallet **Kostnadsredovisningsanalys** för Power BI-innehåll får användare som har gemensam åtkomst obegränsad dataåtkomst. Om målet är att använda begränsad åtkomst får användarna endast tilldelas rollen **Kostnadsobjektcontroller**. Dessa säkerhetsuppdateringar på radnivå börjar gälla omedelbart. Berörda användare bör uppdatera sina webbläsare.

## <a name="additional-resources"></a>Ytterligare resurser
Mer information om säkerhet för Power BI på radnivå finns i [Hantera säkerheten av din modell i Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-rls/#manage-security-on-your-model).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
