---
title: "Användare kan komma åt Core HR men inte appen Onboard eller Attract"
description: "Det här avsnittet beskriver hur du löser problem där en användare kan komma åt Microsoft Dynamics 365 for Talent Core HR men inte apparna Attract eller Onboard."
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
ms.openlocfilehash: 2e5d0b1bf993aec89c7d2c6d4916732f5824310d
ms.contentlocale: sv-se
ms.lasthandoff: 12/04/2018

---

# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a><span data-ttu-id="d5f95-103">Användare kan komma åt Core HR men inte appen Onboard eller Attract</span><span class="sxs-lookup"><span data-stu-id="d5f95-103">User can access Core HR but not the Onboard or Attract app</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d5f95-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="d5f95-104">**Environment details**</span></span>

- <span data-ttu-id="d5f95-105">Microsoft Dynamics Lifecycle Services (LCS)-distributionen gjordes av användare A.</span><span class="sxs-lookup"><span data-stu-id="d5f95-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="d5f95-106">Användare A lade till användare B som användare av Microsoft Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="d5f95-106">User A added user B as a user to Microsoft Dynamics 365 for Talent Core HR.</span></span>

<span data-ttu-id="d5f95-107">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="d5f95-107">**Issue**</span></span>

<span data-ttu-id="d5f95-108">Användare B kan komma åt Core HR, men inte Talent: Attract eller Talent: appen Onboard.</span><span class="sxs-lookup"><span data-stu-id="d5f95-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="d5f95-109">När användaren försöker gå till **Upplevelsappar** tas den till en utvärderingsversion istället.</span><span class="sxs-lookup"><span data-stu-id="d5f95-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="d5f95-110">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="d5f95-110">**Solution**</span></span>

<span data-ttu-id="d5f95-111">Användare B måste tilldelas behörighet för att visa den Microsoft PowerApps-miljö som användaren skapat under etableringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="d5f95-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="d5f95-112">Information finns i avsnittet ”beviljar behörighet för miljön” i [Etablera Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="d5f95-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="d5f95-113">**Långsiktig lösning**</span><span class="sxs-lookup"><span data-stu-id="d5f95-113">**Long-term solution**</span></span>

<span data-ttu-id="d5f95-114">Microsoft överväger att automatiskt tilldela rätt behörigheter till Onboard och Attract när en användare läggs till Core HR.</span><span class="sxs-lookup"><span data-stu-id="d5f95-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>

