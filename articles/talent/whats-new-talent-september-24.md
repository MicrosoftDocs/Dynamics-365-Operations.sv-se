---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (24 september 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6001b3c777be005dfc0b22ca0b64d5c56a56cb1e
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010071"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-september-24-2018"></a><span data-ttu-id="b7849-103">Nyheter och ändringar i Dynamics 365 Talent: Core HR (24 september 2018)</span><span class="sxs-lookup"><span data-stu-id="b7849-103">What's new or changed in Dynamics 365 Talent: Core HR (September 24, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b7849-104">**Skapa 8.1.1015.0**</span><span class="sxs-lookup"><span data-stu-id="b7849-104">**Build 8.1.1015.0**</span></span>

<span data-ttu-id="b7849-105">Det här ämnet beskriver nya eller ändrade funktioner i Core HR.</span><span class="sxs-lookup"><span data-stu-id="b7849-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="currency-added-to-benefits"></a><span data-ttu-id="b7849-106">Valuta tillagd till Förmåner</span><span class="sxs-lookup"><span data-stu-id="b7849-106">Currency added to Benefits</span></span>

<span data-ttu-id="b7849-107">Förmånsplaner har uppdaterats med valutan för förmånen.</span><span class="sxs-lookup"><span data-stu-id="b7849-107">Benefit plans have been updated to include the currency of the benefit.</span></span> <span data-ttu-id="b7849-108">Det här nya fältet är också tillgängligt på förmåner som lönearbetaren är anmäld till.</span><span class="sxs-lookup"><span data-stu-id="b7849-108">This new field is also available on worker enrolled benefits.</span></span> <span data-ttu-id="b7849-109">Det här nya fältet är en del av säkerhetsprivilegiet Behåll förmåner och Visa en lista över förmåner.</span><span class="sxs-lookup"><span data-stu-id="b7849-109">This new field is part of the Maintain benefits and View a list of benefits security privilege.</span></span>

## <a name="update-proration-process--leave-and-absence"></a><span data-ttu-id="b7849-110">Uppdatera processen för proportionell fördelning - tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="b7849-110">Update proration process – Leave and Absence</span></span>

<span data-ttu-id="b7849-111">Organisationer tilldela ledig tid olika beroende på om medarbetarna börjar eller slutar på företaget.</span><span class="sxs-lookup"><span data-stu-id="b7849-111">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="b7849-112">För anställda som lämnar organisationen, kan vissa behöva upphöra med utmärkelsen vid uppsägningsdatum, medan andra är beroende av den sista dagen som arbetats för att stoppa periodiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b7849-112">For employees leaving the organization, some may need to end the award on the termination date, while others rely on the last day worked to stop the accrual process.</span></span> <span data-ttu-id="b7849-113">Ändringarna ger organisationer möjlighet att välja när de vill avsluta registrering under uppsägningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b7849-113">These changes provide organizations the ability to choose when to end enrollment during the termination process.</span></span> <span data-ttu-id="b7849-114">Dessa nya alternativ är en del av privilegierna för att säga upp en arbetare och säga upp en arbetare från självbetjäning för chef.</span><span class="sxs-lookup"><span data-stu-id="b7849-114">These new options are part of the privileges for Terminate a worker and Terminate a worker from manager self service.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="b7849-115">Andra ändringar</span><span class="sxs-lookup"><span data-stu-id="b7849-115">Other changes</span></span>

<span data-ttu-id="b7849-116">Den här versionen innehåller flera ytterligare felkorrigeringar.</span><span class="sxs-lookup"><span data-stu-id="b7849-116">This release includes several additional bug fixes.</span></span>

## <a name="known-issue"></a><span data-ttu-id="b7849-117">Kända problem</span><span class="sxs-lookup"><span data-stu-id="b7849-117">Known Issue</span></span>

-   <span data-ttu-id="b7849-118">**Problem:** när du lägger till en ny bilaga till en arbetare är knapparna **Ny** och **Redigera** nedtonade. **Lösning:** innan du öppnar bilagesidan, se till att faktarutorna på sidan **arbetare** är stängda.</span><span class="sxs-lookup"><span data-stu-id="b7849-118">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the fact boxes on the **Worker** page are closed.</span></span> <span data-ttu-id="b7849-119">Om faktarutorna är stängda när sidan **arbetare** hämtas, aktiveras bilageknapparna.</span><span class="sxs-lookup"><span data-stu-id="b7849-119">If the fact boxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="b7849-120">(Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)</span><span class="sxs-lookup"><span data-stu-id="b7849-120">(This issue will be fixed in the next platform update.)</span></span>
