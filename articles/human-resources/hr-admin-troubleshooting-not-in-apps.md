---
title: Personalresurser visas inte i Microsoft Dynamics 365-appar
description: Det här avsnittet beskriver vad du gör om kunden inte ser Microsoft Dynamics 365 Human Resources-appen bland Microsoft Dynamics 365-appar.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: d78199cf0e76ffd0676a26961a8e646938dc7333
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114341"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a><span data-ttu-id="ec5d5-103">Personalresurser visas inte i Microsoft Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="ec5d5-103">Human Resources doesn't appear in Microsoft Dynamics 365 apps</span></span>

<span data-ttu-id="ec5d5-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="ec5d5-104">**Issue**</span></span>

<span data-ttu-id="ec5d5-105">Kunden ser inte Dynamics 365 Human Resources bland Microsoft Dynamics 365-apparna.</span><span class="sxs-lookup"><span data-stu-id="ec5d5-105">The customer doesn't see Dynamics 365 Human Resources among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="ec5d5-106">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="ec5d5-106">**Resolution**</span></span>

<span data-ttu-id="ec5d5-107">Användaren måste läggas till rollen Environment Maker för miljön i Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="ec5d5-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="ec5d5-108">Administratörsanvändare med en licens för Power Apps Plan 2 måste öppna den i [Power Apps administrationsportal](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="ec5d5-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>

2. <span data-ttu-id="ec5d5-109">Välj **Miljöer** och välj rätt miljön för Personal.</span><span class="sxs-lookup"><span data-stu-id="ec5d5-109">Select **Environments**, and select the correct environment for Human Resources.</span></span>

3. <span data-ttu-id="ec5d5-110">På fliken **Säkerhet** på fliken **Miljöroller**, välj **Environment Maker**.</span><span class="sxs-lookup"><span data-stu-id="ec5d5-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Fliken Miljöroller](media/environment-roles.png)

4. <span data-ttu-id="ec5d5-112">På fliken **Användare** lägger du till användaren eller organisationen.</span><span class="sxs-lookup"><span data-stu-id="ec5d5-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Fliken Användare](media/environment-maker.png)

5. <span data-ttu-id="ec5d5-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ec5d5-114">Select **Save**.</span></span>

6. <span data-ttu-id="ec5d5-115">Användaren måste nu logga in på [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="ec5d5-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>

7. <span data-ttu-id="ec5d5-116">Välj **Synkronisera** för att uppdatera användarapparna.</span><span class="sxs-lookup"><span data-stu-id="ec5d5-116">Select **Sync** to update the user apps.</span></span>

    ![Knappen Synkronisera](media/get-more.png)

    <span data-ttu-id="ec5d5-118">När synkroniseringen är klar visas Personal på startsidan.</span><span class="sxs-lookup"><span data-stu-id="ec5d5-118">After synchronization is completed, Human Resources will appear on the home page.</span></span>
