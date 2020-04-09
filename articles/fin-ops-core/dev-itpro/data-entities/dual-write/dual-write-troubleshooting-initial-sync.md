---
title: Felsöka problem under första synkroniseringen
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172724"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="3e150-103">Felsöka problem under första synkroniseringen</span><span class="sxs-lookup"><span data-stu-id="3e150-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="3e150-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3e150-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="3e150-105">Det ger särskilt information som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.</span><span class="sxs-lookup"><span data-stu-id="3e150-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3e150-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="3e150-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="3e150-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="3e150-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="3e150-108">Sök efter inledande synkroniseringsfel i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="3e150-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="3e150-109">När du har aktiverat mappningsmallen ska status för mappningarna **köras**.</span><span class="sxs-lookup"><span data-stu-id="3e150-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="3e150-110">Om status **inte körs** har fel uppstått vid den ursprungliga synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="3e150-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="3e150-111">Om du vill visa felen väljer du fliken **Information om initial synkronisering** på sidan **Dubbelriktad skrivning**.</span><span class="sxs-lookup"><span data-stu-id="3e150-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Fliken Information om initial synkronisering](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="3e150-113">Det går inte att slutföra den första synkroniseringen: 400 Felaktig begäran</span><span class="sxs-lookup"><span data-stu-id="3e150-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="3e150-114">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="3e150-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="3e150-115">Följande felmeddelande kan visas när du försöker köra mappningen och den första synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="3e150-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="3e150-116">*Fjärrservern returnerade ett fel: (400) felaktig begäran.) AX, exporten upptäckte ett fel*</span><span class="sxs-lookup"><span data-stu-id="3e150-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="3e150-117">Här följer ett exempel på det fullständiga felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="3e150-117">Here is an example of the full error message.</span></span>

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

<span data-ttu-id="3e150-118">Om detta fel inträffar konsekvent och du inte kan slutföra den ursprungliga synkroniseringen följer du stegen nedan för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="3e150-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="3e150-119">Logga in på den virtuella datorn (VM) för Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="3e150-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="3e150-120">Öppna Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="3e150-120">Open Microsoft Management Console.</span></span> 
3. <span data-ttu-id="3e150-121">I fönstret **tjänster** ser du till att tjänsten ramverk för dataimport och export av Microsoft Dynamics 365 körs.</span><span class="sxs-lookup"><span data-stu-id="3e150-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="3e150-122">Starta om den om den har stoppats eftersom den första synkroniseringen kräver det.</span><span class="sxs-lookup"><span data-stu-id="3e150-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="3e150-123">Fel vid första synkronisering: 403 förbud</span><span class="sxs-lookup"><span data-stu-id="3e150-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="3e150-124">Följande felmeddelande kan visas under första synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="3e150-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="3e150-125">*(\[Förbjudet\], Fjärrservern returnerade ett fel: (403) Förbjudet.), AX-exporten upptäckte ett fel*</span><span class="sxs-lookup"><span data-stu-id="3e150-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="3e150-126">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="3e150-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="3e150-127">Logga in på Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="3e150-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="3e150-128">På sidan **Azure Active Directory-appar** ta bort klienten **DtAppID** och lägg sedan till den igen.</span><span class="sxs-lookup"><span data-stu-id="3e150-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Lista över Azure AD-appar](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a><span data-ttu-id="3e150-130">Självrefererande fel vid inledande synkronisering</span><span class="sxs-lookup"><span data-stu-id="3e150-130">Self-reference failures during initial synchronization</span></span>

<span data-ttu-id="3e150-131">Ett felmeddelande av följande slag kan visas om någon av dina mappningar har självreferenser:</span><span class="sxs-lookup"><span data-stu-id="3e150-131">You might receive an error message that resembles the following example if any of your mappings have self-references:</span></span>

<span data-ttu-id="3e150-132">*På leverantör V2, visas följande fel: Post-ID: ny post, ErrorMessage: Det gick inte att matcha GUID för fältet: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Uppslagsvärdet hittades inte: CN-001. Prova denna UR för att kontrollera om referensdata existerar: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` t.ex. 'CN-001'*</span><span class="sxs-lookup"><span data-stu-id="3e150-132">*On the Vendors V2, the following error: Record Id: new record, ErrorMessage: Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup value was not found: CN-001. Try this URL(s) to check if the reference data exists: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span></span>

<span data-ttu-id="3e150-133">Den här typen av fel inträffar under den första synkroniseringen av mappningar som innehåller självreferenser.</span><span class="sxs-lookup"><span data-stu-id="3e150-133">This type of error occurs during initial synchronization of mappings that have self-references.</span></span> <span data-ttu-id="3e150-134">I föregående exempel refererar fältet fakturakonto till leverantörsenheten.</span><span class="sxs-lookup"><span data-stu-id="3e150-134">In the preceding example, the field invoice account references the vendor entity.</span></span>

<span data-ttu-id="3e150-135">Du kan åtgärda problemet genom att köra mappningen två gånger innan den inledande synkroniseringen lyckas.</span><span class="sxs-lookup"><span data-stu-id="3e150-135">To fix the issue, you might have to run the mapping two times before the initial synchronization is successful.</span></span>

