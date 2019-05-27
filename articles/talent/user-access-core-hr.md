---
title: Användare kan komma åt Core HR men inte appen Onboard eller Attract
description: Det här avsnittet beskriver hur du löser problem där en användare kan komma åt Dynamics 365 for Talent Core HR, men inte apparna Attract eller Onboard.
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
ms.openlocfilehash: ece6a81c54ef1421284fc79ab82ed3e31a972255
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519134"
---
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a><span data-ttu-id="fe7bb-103">Användarna kan komma åt Core HR men inte appen Onboard eller Attract</span><span class="sxs-lookup"><span data-stu-id="fe7bb-103">User can access Core HR but not the Onboard or Attract app</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe7bb-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="fe7bb-104">**Environment details**</span></span>

- <span data-ttu-id="fe7bb-105">Microsoft Dynamics Lifecycle Services (LCS)-distributionen gjordes av användare A.</span><span class="sxs-lookup"><span data-stu-id="fe7bb-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="fe7bb-106">Användare A lade till användare B som användare av Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="fe7bb-106">User A added user B as a user to Microsoft Dynamics 365 for Talent Core HR.</span></span>

<span data-ttu-id="fe7bb-107">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="fe7bb-107">**Issue**</span></span>

<span data-ttu-id="fe7bb-108">Användare B kan komma åt Core HR, men inte Talent: Attract eller Talent: appen Onboard.</span><span class="sxs-lookup"><span data-stu-id="fe7bb-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="fe7bb-109">När användaren försöker gå till **Upplevelsappar** tas den till en utvärderingsversion istället.</span><span class="sxs-lookup"><span data-stu-id="fe7bb-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="fe7bb-110">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="fe7bb-110">**Solution**</span></span>

<span data-ttu-id="fe7bb-111">Användare B måste tilldelas behörighet för att visa den Microsoft PowerApps-miljö som användaren skapat under etableringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="fe7bb-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="fe7bb-112">Information finns i avsnittet ”beviljar behörighet för miljön” i [Etablera Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="fe7bb-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="fe7bb-113">**Långsiktig lösning**</span><span class="sxs-lookup"><span data-stu-id="fe7bb-113">**Long-term solution**</span></span>

<span data-ttu-id="fe7bb-114">Microsoft överväger att automatiskt tilldela rätt behörigheter till Onboard och Attract när en användare läggs till Core HR.</span><span class="sxs-lookup"><span data-stu-id="fe7bb-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
