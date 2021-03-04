---
title: Attract-användare kan inte söka jobb från karriärportalen
description: I det här avsnittet beskrivs felsökning av problem där Attract-användare inte kan söka jobb från karriärportalen.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462556"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a>Attract-användare kan inte söka jobb från karriärportalen

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Utleverans

Attract-användare kan inte söka jobb från karriärportalen. När de försöker att söka ett jobb som har skapats i Dynamics 365 Talent: Attract läser webbläsaren in sidan kontinuerligt och utför inte åtgärden.

## <a name="cause"></a>Orsak

Det här problemet uppstår när talangrelationsgruppen inte har användarrollen Talang.

## <a name="resolution"></a>Upplösning

Tilldela användarrollen Talang till talangrelationsgruppen.

1. Logga in till [Power Platform administrationscentret](https://admin.powerplatform.microsoft.com) med någon av följande administratörsuppgifter:

   - Dynamics 365-administratör
   - Global administratör
   - Power Platform-administratör

2. I navigeringsfönstret väljer du **Miljöer** och sedan den miljö där användarrollen Talang ska tilldelas talangrelationsgruppen.

   ![Välj miljö](./media/attract-troubleshoot-career-portal-select-environment.png)

3. I fönstret **Miljöer** väljer du **miljöns URL** och loggar in på miljöns administratörsportal (till exempel https:<orgname>.crm.dynamics.com).

4. Välj **Inställningar** väljer du **System** och sedan **Säkerhet**.

   ![Navigera till Säkerhet](./media/attract-troubleshoot-career-portal-security.png)

5. Välj **Team**.

   ![Välj Team](./media/attract-troubleshoot-career-portal-security-teams.png)

6. Sök efter **Talangrelationsgrupp** i sökrutan och välj sedan teamet från sökresultaten.

7. Välj **HANTERA ROLLER** från menyfliken.

8. I dialogrutan **Hantera teamroller** väljer du **Talanganvändare** från listan över tillgängliga roller och väljer sedan **OK** för att tillämpa rollen.

   ![Tillämpa roll](./media/attract-troubleshoot-career-portal-apply-role.png)

9. Testa ändringarna:

   1. Logga in på karriärportalen från ett nytt webbläsarfönster.
   2. Sök jobbet från karriärportalen. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]