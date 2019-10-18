---
title: Talent visas inte bland Microsoft Dynamics 365-appar (Common Data Service 1.0)
description: Det här avsnittet beskriver vad du gör om kunden inte ser Microsoft Dynamics 365 Talent-appen bland Microsoft Dynamics 365-appar.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 956af80a8ab2f454d9f523d3c74dda754ef0f793
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009387"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a>Talent visas inte bland Microsoft Dynamics 365-appar (Common Data Service 1.0)

[!include [banner](includes/banner.md)]

**Utleverans**

Kunden finns inte i Microsoft Dynamics 365 Talent-app bland Microsoft Dynamics365-appar.

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
