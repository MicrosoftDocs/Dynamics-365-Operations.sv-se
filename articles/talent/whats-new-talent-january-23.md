---
title: Nyheter och ändringar i Dynamics 365 for Talent Core HR (23 januari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 135be837a82af8cee22d83c015a78da3b89b7978
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306202"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-23-2019"></a><span data-ttu-id="e7eb8-103">Nyheter och ändringar i Dynamics 365 for Talent Core HR (23 januari 2019)</span><span class="sxs-lookup"><span data-stu-id="e7eb8-103">What's new or changed in Dynamics 365 for Talent Core HR (January 23, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e7eb8-104">**Skapa 8.1.2121**</span><span class="sxs-lookup"><span data-stu-id="e7eb8-104">**Build 8.1.2121**</span></span>

<span data-ttu-id="e7eb8-105">Det här ämnet beskriver nya eller ändrade funktioner i Core HR.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="e7eb8-106">Ändringar</span><span class="sxs-lookup"><span data-stu-id="e7eb8-106">Changes</span></span>

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a><span data-ttu-id="e7eb8-107">Import av medarbetarens fasta kompensation inte fungerar när du skapar nya fasta kompensationsposter</span><span class="sxs-lookup"><span data-stu-id="e7eb8-107">Import of employee fixed compensation not working when creating new fixed compensation records</span></span>
<span data-ttu-id="e7eb8-108">En har ändrats till entitetens medarbetarens fasta kompensation för att hämta kompensationsnivån vid importen.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-108">A change has been made to the employee fixed compensation entity to retrieve the compensation level upon import.</span></span> <span data-ttu-id="e7eb8-109">Innan den här versionen visades ett meddelande som anger hur krävdes.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-109">Prior to this release, a message was displayed indicating that the level was required.</span></span>

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a><span data-ttu-id="e7eb8-110">Ta bort fältet minimisaldo från dialogrutan begäran om ledighet</span><span class="sxs-lookup"><span data-stu-id="e7eb8-110">Remove the minimum balance field from the time off request dialog box</span></span>
<span data-ttu-id="e7eb8-111">Fältet **minimisaldo** från dialogrutan **begäran om ledighet**.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-111">The **Minimum balance** field has been removed from the **Time off request** dialog box.</span></span> <span data-ttu-id="e7eb8-112">Denna ändring påverkar överallt där ledig tid kan begäras.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-112">This change affects all areas where time off can be requested.</span></span>

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a><span data-ttu-id="e7eb8-113">Datauppgradering för uppdateras inte i samtliga fall kompensationsnivåer</span><span class="sxs-lookup"><span data-stu-id="e7eb8-113">Data upgrade for compensation levels not updating in all scenarios</span></span>
<span data-ttu-id="e7eb8-114">En ändring har gjorts för att uppdatera kompensationsnivån på fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-114">A change has been made to update the compensation level on fixed compensation plans.</span></span> <span data-ttu-id="e7eb8-115">Den här ändringen fyller kompensationsnivån på fasta planer för projektet som hör till medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-115">This change will populate the compensation level on fixed plans for the job assigned to the employee.</span></span>

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a><span data-ttu-id="e7eb8-116">Löneinformation på sidan Hantera ändringar gäller endast inloggad som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-116">Payroll information in the Manage changes page is only available when logged in as System Administrator</span></span>
<span data-ttu-id="e7eb8-117">Ändringen kan anställda med lön administratören åtkomst till löneinformationen på de **Ändrar tidslinje > Hantera ändringar** för befattningen.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-117">This change allows employees with the Payroll Administrator role access to the payroll information on the **Changes timeline > Manage changes** page for the position.</span></span>

### <a name="job-fields-default-to-positions"></a><span data-ttu-id="e7eb8-118">Fältet anpassas till befattningar för jobbet</span><span class="sxs-lookup"><span data-stu-id="e7eb8-118">Job fields default to positions</span></span>
<span data-ttu-id="e7eb8-119">När du byter jobb på befattning, jobbfält överförs som standard till befattningen.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-119">When changing the job on a position, job fields will default to the position.</span></span> <span data-ttu-id="e7eb8-120">Ett varningsmeddelande visas som du kan acceptera standardvärdena eller behålla de befintliga värdena för fälten.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-120">An alert message will appear giving an option to accept the default values or keep the existing values for those fields.</span></span>

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a><span data-ttu-id="e7eb8-121">Provanställning och kalender visas inte för framtida anställda.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-121">Probation period and calendar are not displayed for future hired employees.</span></span>
<span data-ttu-id="e7eb8-122">Förutom denna skillnad fält **provanställning** och **kalender** har lagts till i sida **hantera ändringar** om du vill tillåta för datainmatning för tidigare och framtida anställda.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-122">With this change, **Probation period** and **Calendar** fields have been added to the **Manage changes** page to allow for data entry for future and past employees.</span></span>

### <a name="platform-update-23"></a><span data-ttu-id="e7eb8-123">Plattform update 23</span><span class="sxs-lookup"><span data-stu-id="e7eb8-123">Platform update 23</span></span>
<span data-ttu-id="e7eb8-124">Mindre felkorrigeringar har ingår i plattformsuppdatering 23.</span><span class="sxs-lookup"><span data-stu-id="e7eb8-124">Minor bug fixes have been included as part of Platform update 23.</span></span> <span data-ttu-id="e7eb8-125">Mer information finns i [vad är nya eller ändrade i Dynamics 365 for Finance and Operations plattformsuppdatering 23 (januari 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span><span class="sxs-lookup"><span data-stu-id="e7eb8-125">For more information, see [What's new or changed in Dynamics 365 for Finance and Operations platform update 23 (January 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span></span> 