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
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a><span data-ttu-id="7150b-103">Talent visas inte bland Microsoft Dynamics 365-appar (Common Data Service 1.0)</span><span class="sxs-lookup"><span data-stu-id="7150b-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (Common Data Service 1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7150b-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="7150b-104">**Issue**</span></span>

<span data-ttu-id="7150b-105">Kunden finns inte i Microsoft Dynamics 365 Talent-app bland Microsoft Dynamics365-appar.</span><span class="sxs-lookup"><span data-stu-id="7150b-105">The customer doesn't see the Microsoft Dynamics 365 Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="7150b-106">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="7150b-106">**Resolution**</span></span>

<span data-ttu-id="7150b-107">Användaren måste läggas till rollen Environment Maker för miljön i Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="7150b-107">The user must be added to the Environment Maker role for the environment in Microsoft PowerApps.</span></span>

1. <span data-ttu-id="7150b-108">Administratörsanvändare med en licens för PowerApps Plan 2 måste öppna den i [PowerApps administrationsportal](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="7150b-108">The admin user who has a PowerApps Plan 2 license must open the [PowerApps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="7150b-109">Välj **Miljöer** och välj rätt miljön för Talent.</span><span class="sxs-lookup"><span data-stu-id="7150b-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="7150b-110">På fliken **Säkerhet** på fliken **Miljöroller**, välj **Environment Maker**.</span><span class="sxs-lookup"><span data-stu-id="7150b-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Fliken Miljöroller](media/environment-roles.png)

4. <span data-ttu-id="7150b-112">På fliken **Användare** lägger du till användaren eller organisationen.</span><span class="sxs-lookup"><span data-stu-id="7150b-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Fliken Användare](media/environment-maker.png)

5. <span data-ttu-id="7150b-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7150b-114">Select **Save**.</span></span>
6. <span data-ttu-id="7150b-115">Användaren måste nu logga in på [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="7150b-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="7150b-116">Välj **Synkronisera** för att uppdatera användarapparna.</span><span class="sxs-lookup"><span data-stu-id="7150b-116">Select **Sync** to update the user apps.</span></span>

    ![Knappen Synkronisera](media/get-more.png)

    <span data-ttu-id="7150b-118">När synkroniseringen är klar visas Talent på startsidan.</span><span class="sxs-lookup"><span data-stu-id="7150b-118">After synchronization is completed, Talent will appear on the home page.</span></span>
