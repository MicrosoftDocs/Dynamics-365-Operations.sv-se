---
title: Felsöka problem som rör uppgraderingar av Finance and Operations-appar
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som är relaterade till uppgradering av Finance and Operations-appar.
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
ms.openlocfilehash: 59384d8e8d043eb14231a471c7218ced2dddf739
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172887"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a><span data-ttu-id="5554a-103">Felsöka problem som rör uppgraderingar av Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="5554a-103">Troubleshoot issues related to upgrades of Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="5554a-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5554a-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="5554a-105">Särskilt ger de information som kan hjälpa dig att åtgärda problem som är relaterade till uppgradering av Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="5554a-105">Specifically, it provides information that can help you fix issues that are related to upgrades of Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5554a-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="5554a-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="5554a-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="5554a-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="database-synchronization-errors"></a><span data-ttu-id="5554a-108">Databassynkroniseringsfel</span><span class="sxs-lookup"><span data-stu-id="5554a-108">Database synchronization errors</span></span>

<span data-ttu-id="5554a-109">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="5554a-109">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="5554a-110">Ett felmeddelande av följande slag kan visas när du försöker använda entiteten **DualWriteProjectConfiguration** för att uppdatera en Finance and Operations-app till plattformsuppdatering 30.</span><span class="sxs-lookup"><span data-stu-id="5554a-110">You might receive an error message that resembles the following example when you try to use the **DualWriteProjectConfiguration** entity to update a Finance and Operations app to Platform update 30.</span></span>

```console
Infolog diagnostic message: 'Cannot select a record in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

<span data-ttu-id="5554a-111">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="5554a-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="5554a-112">Logga in på den virtuella datorn (VM) för Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="5554a-112">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="5554a-113">Öppna Visual Studio som administratör och öppna programobjektträd (AOT).</span><span class="sxs-lookup"><span data-stu-id="5554a-113">Open Visual Studio as an admin, and open the Application Object Tree (AOT).</span></span>
3. <span data-ttu-id="5554a-114">Sök efter **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="5554a-114">Search for **DualWriteProjectConfiguration**.</span></span>
4. <span data-ttu-id="5554a-115">I programobjektträdet högerklickar du på **DualWriteProjectConfiguration**och väljer **Lägg till i nytt projekt**.</span><span class="sxs-lookup"><span data-stu-id="5554a-115">In the AOT, right-click **DualWriteProjectConfiguration**, and select **Add to new project**.</span></span> <span data-ttu-id="5554a-116">Välj **OK** om du vill skapa det nya projekt som använder standardalternativ.</span><span class="sxs-lookup"><span data-stu-id="5554a-116">Select **OK** to create the new project that uses default options.</span></span>
5. <span data-ttu-id="5554a-117">I Solution Explorer, högerklicka på **projektegenskaper** och ställ in **Synkronisera databas i version** till **Sant**.</span><span class="sxs-lookup"><span data-stu-id="5554a-117">In Solution Explorer, right-click **Project properties**, and set **Synchronize Database on Build** to **True**.</span></span>
6. <span data-ttu-id="5554a-118">Skapa projektet och bekräfta att versionen lyckades.</span><span class="sxs-lookup"><span data-stu-id="5554a-118">Build the project, and confirm that the build is successful.</span></span>
7. <span data-ttu-id="5554a-119">I menyn **Dynamics 365** väljer du **Synkronisera databas**.</span><span class="sxs-lookup"><span data-stu-id="5554a-119">On the **Dynamics 365** menu, select **Synchronize database**.</span></span>
8. <span data-ttu-id="5554a-120">Välj **synkronisera** om du vill utföra en fullständig databassynkronisering.</span><span class="sxs-lookup"><span data-stu-id="5554a-120">Select **Synchronize** to do a full database synchronization.</span></span>
9. <span data-ttu-id="5554a-121">När den fullständiga databassynkroniseringen lyckas kör du steget för databassynkronisering i Microsoft Dynamics Lifecycle Services (LCS) och använder de manuella uppgraderingsskripten så att du kan fortsätta med uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="5554a-121">After the full database synchronization is successful, rerun the database synchronization step in Microsoft Dynamics Lifecycle Services (LCS) and use the manual upgrade scripts as applicable, so that you can proceed with the update.</span></span>

## <a name="missing-entity-fields-issue-on-maps"></a><span data-ttu-id="5554a-122">Entitetsfält som saknas problem i kartor</span><span class="sxs-lookup"><span data-stu-id="5554a-122">Missing entity fields issue on maps</span></span>

<span data-ttu-id="5554a-123">**Den roll som krävs för att åtgärda problemet:** systemadministratör</span><span class="sxs-lookup"><span data-stu-id="5554a-123">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="5554a-124">På sidan **dubbelriktad skrivning** kan du få ett felmeddelande som liknar följande exempel:</span><span class="sxs-lookup"><span data-stu-id="5554a-124">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="5554a-125">*Källfält \<fältnamn\> saknas i schemat.*</span><span class="sxs-lookup"><span data-stu-id="5554a-125">*Missing source field \<field name\> in the schema.*</span></span>

![Exempel på felmeddelandet för källfält saknas](media/error_missing_field.png)

<span data-ttu-id="5554a-127">Lös problemet genom att först följa de här stegen för att kontrollera att fälten finns i entiteten.</span><span class="sxs-lookup"><span data-stu-id="5554a-127">To fix the issue, first follow these steps to make sure that the fields are in the entity.</span></span>

1. <span data-ttu-id="5554a-128">Logga in på den virtuella datorn för Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="5554a-128">Sign in to the VM for the Finance and Operations app.</span></span>
2. <span data-ttu-id="5554a-129">Gå till **Arbetsytor \> Datahantering**, välj panelen **Rramverksparametrar** och sedan på fliken **Entitetsinställningar** välj **Uppdatera entitetslistan** för att uppdatera enheterna.</span><span class="sxs-lookup"><span data-stu-id="5554a-129">Go to **Workspaces \> Data management**, select the **Framework parameters** tile, and then, on the **Entity settings** tab, select **Refresh entity list** to refresh the entities.</span></span>
3. <span data-ttu-id="5554a-130">Gå till **Arbetsytor \> Datahantering**, välj fliken **Dataentiteter** och kontrollera att entiteten finns med i listan.</span><span class="sxs-lookup"><span data-stu-id="5554a-130">Go to **Workspaces \> Data management**, select the **Data entities** tab, and make sure that the entity is listed.</span></span> <span data-ttu-id="5554a-131">Om entiteten inte finns med loggar du in på den virtuella datorn för Finance and Operations-appen och ser till att enheten är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="5554a-131">If the entity isn't listed, sign in to the VM for the Finance and Operations app, and make sure the entity is available.</span></span>
4. <span data-ttu-id="5554a-132">Öppna sidan **entitetsmappning** från sidan **dubbelriktad skrivning** i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="5554a-132">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="5554a-133">Markera **uppdatera entitetslista** om du vill fylla i fälten i entitetsmappningarna automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5554a-133">Select **Refresh entity list** to automatically fill the fields in the entity mappings.</span></span>

<span data-ttu-id="5554a-134">Om problemet fortfarande inte är åtgärdat följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="5554a-134">If the issue still isn't fixed, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5554a-135">De här stegen vägleder dig genom processen att ta bort en enhet och sedan lägga till den igen.</span><span class="sxs-lookup"><span data-stu-id="5554a-135">These steps guide you through the process of deleting an entity and then adding it again.</span></span> <span data-ttu-id="5554a-136">Se till att du följer stegen exakt om du vill undvika problem.</span><span class="sxs-lookup"><span data-stu-id="5554a-136">To avoid issues, be sure to follow the steps exactly.</span></span>

1. <span data-ttu-id="5554a-137">I Finance and Operations-appen, gå till **Arbetsytor \> Datahantering** och välj panelen **Dataentiteter**.</span><span class="sxs-lookup"><span data-stu-id="5554a-137">In the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Data entities** tile.</span></span>
2. <span data-ttu-id="5554a-138">Sök efter den entitet som saknar fältet.</span><span class="sxs-lookup"><span data-stu-id="5554a-138">Find the entity that is missing the field.</span></span> <span data-ttu-id="5554a-139">Anteckna målentiteten, mellanlagringstabell, entitetsnamn och andra kolumnvärden.</span><span class="sxs-lookup"><span data-stu-id="5554a-139">Make a note of the target entity, staging table, entity name, and other column values.</span></span>
3. <span data-ttu-id="5554a-140">Om någon av dina bearbetningsgrupper är beroende av denna entitet ska du vidta lämpliga åtgärder för bearbetningsgrupperna innan du tar bort enheten.</span><span class="sxs-lookup"><span data-stu-id="5554a-140">If any of your processing groups depend on this entity, take appropriate action for the processing groups before you delete the entity.</span></span>
4. <span data-ttu-id="5554a-141">Ta bort den entitet som saknar fältet.</span><span class="sxs-lookup"><span data-stu-id="5554a-141">Delete the entity that is missing the field.</span></span>
5. <span data-ttu-id="5554a-142">Välj **ny** och lägg tillbaka entiteten.</span><span class="sxs-lookup"><span data-stu-id="5554a-142">Select **New**, and add the entity back.</span></span> <span data-ttu-id="5554a-143">Ange de värden du angav en anmärkning för i steg 2.</span><span class="sxs-lookup"><span data-stu-id="5554a-143">Specify the values that you made a note of in step 2.</span></span>
6. <span data-ttu-id="5554a-144">Öppna sidan **entitetsmappning** från sidan **dubbelriktad skrivning** i Finance and Operations-appen.</span><span class="sxs-lookup"><span data-stu-id="5554a-144">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
7. <span data-ttu-id="5554a-145">Markera **uppdatera entitetslista** om du vill fylla i fälten i entitetsmappningarna automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5554a-145">Select **Refresh entity list** to automatically fill the fields in the entity mappings.</span></span>
