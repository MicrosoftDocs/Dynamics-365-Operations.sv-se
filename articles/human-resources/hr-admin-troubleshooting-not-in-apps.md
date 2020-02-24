---
title: Personalresurser visas inte i Microsoft Dynamics 365-appar
description: Det här avsnittet beskriver vad du gör om kunden inte ser Microsoft Dynamics 365 Human Resources-appen bland Microsoft Dynamics 365-appar.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d39e6ef4168f08f20b92979a296ed088744ad0da
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010672"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a>Personalresurser visas inte i Microsoft Dynamics 365-appar

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
