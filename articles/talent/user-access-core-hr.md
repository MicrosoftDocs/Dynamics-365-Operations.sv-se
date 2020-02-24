---
title: Användarna kan komma åt Personal men inte Onboard eller Attract
description: Det här avsnittet beskriver hur du löser problem där en användare kan komma åt Microsoft Dynamics 365 Talent - Personal, men inte Attract eller Onboard.
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
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006320"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a><span data-ttu-id="992db-103">Användarna kan komma åt Personal men inte Onboard eller Attract</span><span class="sxs-lookup"><span data-stu-id="992db-103">User can access Human Resources but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="992db-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="992db-104">**Environment details**</span></span>

- <span data-ttu-id="992db-105">Microsoft Dynamics Lifecycle Services (LCS)-distributionen gjordes av användare A.</span><span class="sxs-lookup"><span data-stu-id="992db-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="992db-106">Användare A lade till användare B som användare av Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="992db-106">User A added user B as a user to Microsoft Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="992db-107">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="992db-107">**Issue**</span></span>

<span data-ttu-id="992db-108">Användare B kan komma åt Personal, men inte Talent: Attract eller Talent: appen Onboard.</span><span class="sxs-lookup"><span data-stu-id="992db-108">User B can access Human Resources, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="992db-109">När användaren försöker gå till **Upplevelsappar** tas den till en utvärderingsversion istället.</span><span class="sxs-lookup"><span data-stu-id="992db-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="992db-110">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="992db-110">**Solution**</span></span>

<span data-ttu-id="992db-111">Användare B måste tilldelas behörighet för att visa den Microsoft Power Apps-miljö som användaren skapat under etableringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="992db-111">User B must be assigned the rights to view the Microsoft Power Apps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="992db-112">Information finns i avsnittet ”beviljar behörighet för miljön” i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="992db-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="992db-113">**Långsiktig lösning**</span><span class="sxs-lookup"><span data-stu-id="992db-113">**Long-term solution**</span></span>

<span data-ttu-id="992db-114">Microsoft överväger att automatiskt tilldela rätt behörigheter till Onboard och Attract när en användare läggs till Personal.</span><span class="sxs-lookup"><span data-stu-id="992db-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Human Resources.</span></span>
