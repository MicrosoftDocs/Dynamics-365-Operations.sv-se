---
title: Talent visas inte bland Microsoft Dynamics 365-appar (CDS1.0)
description: "Det här avsnittet beskriver vad du gör om kunden inte ser Microsoft Dynamics 365 for Talent-appen bland Microsoft Dynamics 365-apparna."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: sv-se
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a>Talent visas inte bland Microsoft Dynamics 365-appar (CDS1.0)

[!include [banner](includes/banner.md)]

**Utleverans**

Kunden ser inte Microsoft Dynamics 365 for Talent-appen bland Microsoft Dynamics 365-apparna.

**Upplösning**

Användaren måste läggas till rollen Environment Maker för miljön i Microsoft PowerApps.

1. Administratörsanvändare med en licens för PowerApps Plan 2 måste öppna den i [PowerApps administrationsportal](https://preview.admin.powerapps.com/).
2. Välj **Miljöer** och välj rätt miljön för Talent.
3. På fliken **Säkerhet** på fliken **Miljöroller**, välj **Environment Maker**.

    ![Fliken Miljöroller](media/environment-roles.png)

4. På fliken **Användare** lägger du till användaren eller organisationen.

    ![Fliken Användare](media/environment-maker.png)

5. Välj **Spara**.
6. Användaren måste nu logga in på [Microsoft Dynamics 365](https://home.dynamics.com/).
7. Välj **Synkronisera** för att uppdatera användarapparna.

    ![Knappen Synkronisera](media/get-more.png)

    När synkroniseringen är klar visas Talent på startsidan.

