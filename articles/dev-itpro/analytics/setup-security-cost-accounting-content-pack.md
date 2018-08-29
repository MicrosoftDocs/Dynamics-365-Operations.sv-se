---
title: "Ställ in säkerhet för kostnadsredovisningsanalys för Power BI"
description: "Det här avsnittet beskriver hur du kan sprida säkerhet för åtkomstnivå i kostnadsredovisning till säkerhet för radnivå i Microsoft Power BI. Dessa funktioner hjälper till att säkerställa att användare bara ser Power BI-data som de har beviljats åtkomst till."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 15d25274b02b0e9423fd4670b82c2e398316a1fa
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Ställ in säkerhet för kostnadsredovisningsanalys för Power BI

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du kan sprida säkerhet för åtkomstnivå i kostnadsredovisning till säkerhet för radnivå i Microsoft Power BI. Dessa funktioner hjälper till att säkerställa att användare bara ser Power BI-data som de har beviljats åtkomst till.

<a name="overview"></a>Översikt
--------

**Kostnadsredovisningsanalys** Microsoft Power BI-innehållet använder Power BI säkerhet på radnivå för att begränsa en användares åtkomst. Säkerheten baseras på den organisationshierarki på åtkomstnivå som har ställts in i parametrar för kostnadsredovisning. Mer information om **Kostnadsredovisningsanalys** för Power BI-innehåll finns i [Kostnadsredovisningsanalys för Power BI-innehåll](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Inställningar
Om du vill sprida säkerhet på åtkomstnivå till Power BI måste Power BI-innehållet följa dessa steg. **Obs!** Användare som publicerar **Kostnadsredovisningsanalys** för Power BI-innehåll blir automatiskt ägare. Endast en ägare kan ställa in säkerhet i Power BI. Dessutom, tills ägaren lägger till andra användare i PowerBI.com kan ingen förutom ägaren se några data i **Kostnadsredovisningsanalys** för Power BI-innehåll.

1.  Publicera definitionsfilen till Power BI.
2.  Logga in på PowerBI.com.
3.  Hitta datamängden för **Kostnadsredovisningsanalys** för Power BI content.
4.  Öppna säkerhetssidan. 

    ![Öppna säkerhetssidan](./media/CA-picture-1.png)

5.  Rollen **Kostnadsobjektcontroller** har redan skapats. Lägg till andra medlemmar som ingår i organisationshierarkin på åtkomstnivå för kostnadsredovisning. 

    ![Lägga till medlemmar](./media/CA-picture-2.png)

Användare som läggs till i rollen **Kostnadsobjektcontroller** kommer endast att se de data som de får tillstånd att se enligt definitionen i organisationshierarkin på åtkomstnivå för kostnadsredovisning. **Obs!** Säkerhet på radnivå som gäller paneler och rapporter i Microsoft Dynamics 365 for Finance and Operations som är inbäddade från Power BI.

## <a name="updating-security"></a>Uppdatera säkerhet
Om uppdateringar görs av säkerhet på åtkomstnivå i kostnadsredovisningen och du vill att Power BI ska återspegla dessa uppdateringarna, måste du uppdatera enhetsbutiken **Kostnadsredovisningsanalys** för Power BI-innehåll. När du har slutfört uppdateringen av enhetsbutiken från Finance and Operations måste du uppdatera artefakterna på PowerBI.com. Mer information om hur du gör en uppdatering av enhetsbutik finns [Uppdatera enhetsbutik](power-bi-integration-entity-store.md#update-entity-store). Ägaren av **Kostnadsredovisningsanalys** för Power BI-innehåll måste också göra en uppdatering av enhetsbutiken om nya användare beviljas åtkomst till organisationshierarkin. Dessutom måste ägaren lägga till nya användare till rollen **Kostnadsobjektcontroller** i PowerBI.com, så att säkerhet på radnivå tillämpas för dem.

## <a name="disabling-security"></a>Inaktivera säkerhet
Vi utgår från att din organisation vill begränsa dataåtkomst. Om säkerhetsparametrarna av någon anledning är inaktiverade när du kör kostnadsredovisning måste ägaren istället lägga till rollen **Kostnadsredovisare** i Power BI. Om du ändrar säkerhet från ett aktiverat tillstånd till inaktiverat är det en bra idé att ta bort användare från rolleb **Kostnadsobjektcontroller**. Och tvärtom när du aktiverar säkerhet igen. Användare kan tillhöra båda rollerna. Gemensam åtkomst är unionen av båda rollerna. I fallet **Kostnadsredovisningsanalys** för Power BI-innehåll får användare som har gemensam åtkomst obegränsad dataåtkomst. Om målet är att använda begränsad åtkomst får användarna endast tilldelas rollen **Kostnadsobjektcontroller**. Dessa säkerhetsuppdateringar på radnivå börjar gälla omedelbart. Berörda användare bör uppdatera sina webbläsare.

## <a name="additional-resources"></a>Ytterligare resurser
Mer information om säkerhet för Power BI på radnivå finns i [Hantera säkerheten av din modell i Power BI](https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).




