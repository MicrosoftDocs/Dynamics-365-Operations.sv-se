---
title: Importera användare från Azure Active Directory
description: Den här proceduren kan användas av systemadministratörer för att manuellt importera valda användare eller att importera ett stort antal användare från Azure Active Directory.
author: peakerbl
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9f03ae7197790c1aac6ebf3cb94ff7963b1291e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745799"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="b1ab7-103">Importera användare från Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b1ab7-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="b1ab7-104">Importera valda användare</span><span class="sxs-lookup"><span data-stu-id="b1ab7-104">Import select users</span></span>

<span data-ttu-id="b1ab7-105">Den här proceduren kan användas av systemadministratörer för att importera valda användare från Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b1ab7-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="b1ab7-106">Användaren importeras med det aktuella sessionsföretaget som standardföretag.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="b1ab7-107">Ändra aktuellt företag vid behov innan användarna importeras.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="b1ab7-108">Gå till **Systemadministration > Användare > Användare**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="b1ab7-109">Klicka på **Importera användare**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-109">Click **Import users**.</span></span>
4. <span data-ttu-id="b1ab7-110">Markera de användare som ska importeras och välj **Importera användare**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="b1ab7-111">När importen är klar måste du tilldela användare roller.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="b1ab7-112">Massimportera användare</span><span class="sxs-lookup"><span data-stu-id="b1ab7-112">Import users in bulk</span></span>

<span data-ttu-id="b1ab7-113">Den här proceduren kan användas av systemadministratörer för att importera ett stort antal användare från Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="b1ab7-114">Observera att det inte är möjligt att välja användare när du använder alternativet för batchimport.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="b1ab7-115">Kör importen som ett batchjobb</span><span class="sxs-lookup"><span data-stu-id="b1ab7-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="b1ab7-116">Användaren importeras med det aktuella sessionsföretaget som standardföretag.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="b1ab7-117">Ändra aktuellt företag vid behov innan användarna importeras.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="b1ab7-118">Gå till **Systemadministration > Användare > Användare**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="b1ab7-119">Klicka på **Batchimport**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="b1ab7-120">Expandera avsnittet **Kör i bakgrunden**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="b1ab7-121">Välj **Ja** i fältet **Batchbearbetning**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-121">Select **Yes** in the **Batch processing** field.</span></span>
6. <span data-ttu-id="b1ab7-122">Ange eller välj ett värde i fältet **Batchgrupp**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="b1ab7-123">Detta steg är valfritt.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-123">This is an optional step.</span></span>  
7. <span data-ttu-id="b1ab7-124">Välj **Ja** i fältet **Privat**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="b1ab7-125">Detta steg är valfritt.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-125">This is an optional step.</span></span>  
8. <span data-ttu-id="b1ab7-126">Välj **Ja** i fältet **Kritiskt jobb**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="b1ab7-127">Detta steg är valfritt.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-127">This is an optional step.</span></span>  
9. <span data-ttu-id="b1ab7-128">Välj ett alternativ i fältet **Övervakningskategori**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-128">In the **Monitoring category** field, select an option.</span></span>
10. <span data-ttu-id="b1ab7-129">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-129">Click **OK**.</span></span>

<span data-ttu-id="b1ab7-130">När importen är klar måste användare tilldelas roller.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="b1ab7-131">Kör i ett begränsat läge</span><span class="sxs-lookup"><span data-stu-id="b1ab7-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="b1ab7-132">Välj **Batchimport**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="b1ab7-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1ab7-133">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]