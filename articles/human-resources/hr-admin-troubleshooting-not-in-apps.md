---
title: Personalresurser visas inte i Microsoft Dynamics 365-appar
description: Det här avsnittet beskriver vad du gör om kunden inte ser Microsoft Dynamics 365 Human Resources-appen bland Microsoft Dynamics 365-appar.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 17a454cd32a08db105a13577c32368ad819bed1c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053386"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a>Personalresurser visas inte i Microsoft Dynamics 365-appar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Utleverans**

Kunden ser inte Dynamics 365 Human Resources bland Microsoft Dynamics 365-apparna.

**Upplösning**

Användaren måste läggas till rollen Environment Maker för miljön i Microsoft Power Apps.

1. Administratörsanvändare med en licens för Power Apps Plan 2 måste öppna den i [Power Apps administrationsportal](https://preview.admin.powerapps.com/).

2. Välj **Miljöer** och välj rätt miljön för Personal.

3. På fliken **Säkerhet** på fliken **Miljöroller**, välj **Environment Maker**.

    ![Fliken Miljöroller](media/environment-roles.png)

4. På fliken **Användare** lägger du till användaren eller organisationen.

    ![Fliken Användare](media/environment-maker.png)

5. Välj **Spara**.

6. Användaren måste nu logga in på [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Välj **Synkronisera** för att uppdatera användarapparna.

    ![Knappen Synkronisera](media/get-more.png)

    När synkroniseringen är klar visas Personal på startsidan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]