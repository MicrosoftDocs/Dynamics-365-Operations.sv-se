---
title: Personalresurser visas inte i Microsoft Dynamics 365-appar
description: I detta ämne beskrivs vad du ska göra om Microsoft Dynamics 365 Human Resources inte finns bland Microsoft Dynamics365-apparna.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dfed82463eece882bed66c7b2dac1dd30e04720e
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413411"
---
# <a name="human-resources-app-doesnt-appear-in-microsoft-dynamics-365-apps"></a>Human Resources-appen visas inte i bland Microsoft Dynamics 365-apparna

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problem**

Kunden ser inte Dynamics 365 Human Resources bland Microsoft Dynamics 365-apparna.

**Upplösning**

Användaren måste läggas till rollen Environment Maker för miljön i Microsoft Power Apps.

1. Administratörsanvändare med en licens för Power Apps Plan 2 måste öppna den i [Power Apps administrationsportal](https://preview.admin.powerapps.com/).

2. Välj **Miljöer** och välj rätt miljön för Personal.

3. På fliken **Säkerhet** på fliken **Miljöroller**, välj **Environment Maker**.

    ![Fliken Miljöroller.](media/environment-roles.png)

4. På fliken **Användare** lägger du till användaren eller organisationen.

    ![Fliken Användare.](media/environment-maker.png)

5. Välj **Spara**.

6. Användaren måste nu logga in på [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Välj **Synkronisera** för att uppdatera användarapparna.

    ![Knappen Synkronisera.](media/get-more.png)

    När synkroniseringen är klar visas Personal på startsidan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
