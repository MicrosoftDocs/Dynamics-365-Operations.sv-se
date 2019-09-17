---
title: Felsöka integrering med LinkedIn och Microsoft Dynamics 365 for Talent - Attract
description: I det här avsnittet beskrivs hur du felsöker problem när du försöker bokföra jobb till LinkedIn från Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
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
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 82ba7c505ba09e47f3c517c74c22e6aef7cd4e65
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739367"
---
# <a name="troubleshoot-integration-with-linkedin"></a><span data-ttu-id="665fc-103">Felsöka integration med LinkedIn</span><span class="sxs-lookup"><span data-stu-id="665fc-103">Troubleshoot integration with LinkedIn</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="665fc-104">Använd följande information för att felsöka problem som du kanske har när du försöker bokföra jobb till LinkedIn från Microsoft Dynamics 365 for Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="665fc-104">Use the following information to help troubleshoot issues that you might have when you try to post jobs to LinkedIn from Microsoft Dynamics 365 for Talent: Attract.</span></span>

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a><span data-ttu-id="665fc-105">Du kan inte logga in på LinkedIn från Attract</span><span class="sxs-lookup"><span data-stu-id="665fc-105">You can't sign in to LinkedIn from Attract</span></span>

<span data-ttu-id="665fc-106">Om du har problem med att logga in på LinkedIn från Attract kan du försöka med följande:</span><span class="sxs-lookup"><span data-stu-id="665fc-106">If you're having trouble signing in to LinkedIn from Attract, try these steps:</span></span>

1. <span data-ttu-id="665fc-107">Kontrollera att autentiseringsuppgifterna för LinkedIn som du angav i Attract är korrekta.</span><span class="sxs-lookup"><span data-stu-id="665fc-107">Verify that the LinkedIn credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="665fc-108">Om autentiseringsuppgifterna är korrekta kan du kontakta [LinkedIn-support](https://www.linkedin.com/help/linkedin).</span><span class="sxs-lookup"><span data-stu-id="665fc-108">If the credentials are valid and correct, contact [LinkedIn support](https://www.linkedin.com/help/linkedin).</span></span>
3. <span data-ttu-id="665fc-109">Om problemet kvarstår kontaktar du [Microsoft support](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="665fc-109">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a><span data-ttu-id="665fc-110">Jobbpubliceringar från Attract visas inte på LinkedIn</span><span class="sxs-lookup"><span data-stu-id="665fc-110">Job posts from Attract don't appear on LinkedIn</span></span>

<span data-ttu-id="665fc-111">Om jobbet inte visas på LinkedIn efter 24 timmar gör du så här:</span><span class="sxs-lookup"><span data-stu-id="665fc-111">If your job hasn't appeared on LinkedIn after 24 hours, try these steps:</span></span>

1. <span data-ttu-id="665fc-112">Se till att ditt LinkedIn företags-ID mappas till din LinkedIn företagssida och att det anges korrekt i administrationscentret för Attract.</span><span class="sxs-lookup"><span data-stu-id="665fc-112">Make sure that your LinkedIn Company ID maps to your LinkedIn company page and is correctly entered in the Attract Admin center.</span></span> <span data-ttu-id="665fc-113">Mer information om hur du ändrar LinkedIn-inställningar i administrationscentret finns i [ställa in integrering med LinkedIn](attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="665fc-113">For more information about how to change LinkedIn settings in the Admin center, see [Set up integration with LinkedIn](attract-admin-linkedin.md).</span></span> <span data-ttu-id="665fc-114">För mer information om LinkedIn företags-ID:n, se [associera ditt LinkedIn företags-ID med LinkedIn jobbtavla - Vanliga frågor](https://www.linkedin.com/help/linkedin/answer/98972).</span><span class="sxs-lookup"><span data-stu-id="665fc-114">For more information about LinkedIn Company IDs, see [Associating your LinkedIn Company ID with the LinkedIn Job Board - Frequently Asked Questions](https://www.linkedin.com/help/linkedin/answer/98972).</span></span>
2. <span data-ttu-id="665fc-115">Kontrollera att adressen är fullständig genom att granska jobbinformationen på LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="665fc-115">Check the job details on LinkedIn to make sure that the address is complete.</span></span> <span data-ttu-id="665fc-116">För att kunna publicera ett jobb måste LinkedIn ha minst ort och land eller region för jobbet.</span><span class="sxs-lookup"><span data-stu-id="665fc-116">To post a job successfully, LinkedIn needs at least the city and country or region of the job.</span></span>
3. <span data-ttu-id="665fc-117">Kontrollera att jobbet inte duplicerar ett annat jobb som har publicerats på LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="665fc-117">Make sure that the job doesn't duplicate another job that has been posted on LinkedIn.</span></span> <span data-ttu-id="665fc-118">LinkedIn publicerar inte jobb som är dubbletter av antingen LinkedIn Premium jobbplatser eller begränsade listor från en annan källa.</span><span class="sxs-lookup"><span data-stu-id="665fc-118">LinkedIn won't post jobs that are duplicates of either LinkedIn Premium Job Slots or Limited Listings from another source.</span></span> <span data-ttu-id="665fc-119">Kontrollera att en annan person i företaget inte redan har publicerat jobbet manuellt.</span><span class="sxs-lookup"><span data-stu-id="665fc-119">Verify that another person at your company didn't already post the job manually.</span></span>

## <a name="see-also"></a><span data-ttu-id="665fc-120">Se även</span><span class="sxs-lookup"><span data-stu-id="665fc-120">See also</span></span>

[<span data-ttu-id="665fc-121">Vanliga frågor LinkedIn</span><span class="sxs-lookup"><span data-stu-id="665fc-121">LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="665fc-122">Publicera jobb på LinkedIn från Attract</span><span class="sxs-lookup"><span data-stu-id="665fc-122">Post jobs to LinkedIn from Attract</span></span>](./attract-post-jobs-to-linkedin.md)

[<span data-ttu-id="665fc-123">Hitta kandidater med LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="665fc-123">Source candidates with LinkedIn Recruiter</span></span>](./attract-linkedin-recruiter.md)

[<span data-ttu-id="665fc-124">Skapa jobb</span><span class="sxs-lookup"><span data-stu-id="665fc-124">Create jobs</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="665fc-125">Felsöka integration med LinkedIn</span><span class="sxs-lookup"><span data-stu-id="665fc-125">Troubleshoot integration with LinkedIn</span></span>](./attract-troubleshoot-linkedin.md)
