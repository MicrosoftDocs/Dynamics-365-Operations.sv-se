---
title: Förbered programdata att användas i RCS
description: Stegen i det här avsnittet förklarar hur en användare kan skapa en ny konfiguration av elektronisk rapporterings (ER) konfiguration som innehåller metadata för program för att utforma konfigurationer av ER-modellmappning i Regulatory Configuration Service (RCS).
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbc1ca45a39f2a5c3309276f9e2f5d2b7d2ba5f7
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684101"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a><span data-ttu-id="72ab7-103">Förbered programdata att användas i RCS</span><span class="sxs-lookup"><span data-stu-id="72ab7-103">Prepare application metadata to be used in RCS</span></span>
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72ab7-104">Följande steg i det här avsnittet förklarar hur användare i rollen i systemadministratör eller utvecklare av ekonomiska rapporter kan skapa en ny konfiguration av elektronisk rapporterings (ER) konfiguration som innehåller metadata för -program för att utforma konfigurationer av ER-modellmappning i Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="72ab7-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains application metadata for designing ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="72ab7-105">Den här konfigurationen används för att utforma ett exempel på en konfiguration av ER-modellmappning för åtkomst till utländska handelstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="72ab7-105">This configuration will be used for designing a sample ER model mapping configuration to access foreign trade transactions.</span></span> <span data-ttu-id="72ab7-106">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i något företag.</span><span class="sxs-lookup"><span data-stu-id="72ab7-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company.</span></span> <span data-ttu-id="72ab7-107">För att slutföra dessa steg måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="72ab7-107">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="72ab7-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="72ab7-108">Prerequisites</span></span>
1.    <span data-ttu-id="72ab7-109">Gå till **Organisationsadministration** > **Arbetsytor** > **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-109">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2.    <span data-ttu-id="72ab7-110">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="72ab7-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="72ab7-111">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="72ab7-111">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3.    <span data-ttu-id="72ab7-112">Klicka på **Metadatakonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-112">Click **Metadata configurations**.</span></span> 
4.    <span data-ttu-id="72ab7-113">Anta att RCS kommer att användas för att utforma en ER-lösning för ett Finance and Operation-program som genererar elektroniska dokument som innehåller information från affärsdomänen för utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="72ab7-113">Assume that RCS will be used to design an ER solution for a Finance and Operation application that will generate electronic documents that contain information from foreign trade business domain.</span></span> <span data-ttu-id="72ab7-114">Om du vill ange mappningen mellan ER-datamodellen och källorna till de data som krävs måste du i RCS få till gång till metadata för Finance and Operation-programmet.</span><span class="sxs-lookup"><span data-stu-id="72ab7-114">To specify the mapping between ER data model and sources of required data, in RCS we need to have access to metadata of the Finance and Operation application.</span></span> <span data-ttu-id="72ab7-115">Som en del av utformningen av ER-lösning konfigurerar du därför en ny konfiguration av ER-metadata som innehåller alla metadata som för närvarande krävs för att generera ER-rapporter för vald affärsdomän.</span><span class="sxs-lookup"><span data-stu-id="72ab7-115">Therefore, as part of designing ER solution we configure a new ER metadata configuration containing all metadata that is currently required for generation ER reports for selected business domain.</span></span> 

## <a name="add-metadata-configuration"></a><span data-ttu-id="72ab7-116">Lägg till metadatakonfiguration</span><span class="sxs-lookup"><span data-stu-id="72ab7-116">Add metadata configuration</span></span> 
1.    <span data-ttu-id="72ab7-117">Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="72ab7-117">Click **Create configuration** to open the drop dialog.</span></span> 
2.    <span data-ttu-id="72ab7-118">Ange metadata för utländsk handel i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-118">In the **Name** field, type 'Foreign trade metadata'.</span></span> 
3.    <span data-ttu-id="72ab7-119">Klicka på **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-119">Click **Create configuration**.</span></span> 
4.    <span data-ttu-id="72ab7-120">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-120">Click **Designer**.</span></span> 
5.    <span data-ttu-id="72ab7-121">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-121">Click **Add**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="72ab7-122">Du kan välja alla metadata för hela programmet eller valda modeller eller valda moduler.</span><span class="sxs-lookup"><span data-stu-id="72ab7-122">You can select all metadata for the entire application or selected models or selected modules.</span></span> <span data-ttu-id="72ab7-123">Tänk på att följande metadata kommer att läggas till automatiskt i det här fallet: register över poster, uppräkningar och utökade datatyper.</span><span class="sxs-lookup"><span data-stu-id="72ab7-123">Be aware that in this case the following metadata will be automatically added: tables of records, enumerations, and extended data types.</span></span> <span data-ttu-id="72ab7-124">Om det behövs ytterligare typer av metadata måste de läggas till manuellt.</span><span class="sxs-lookup"><span data-stu-id="72ab7-124">When additional types of metadata are needed, they must be added manually.</span></span> 
 
<span data-ttu-id="72ab7-125">Det finns vissa externa handelstransaktioner relaterade till metadata genom att markera metadataelement manuellt.</span><span class="sxs-lookup"><span data-stu-id="72ab7-125">We have some foreign trade transactions related metadata by selecting metadata items manually.</span></span> 
  
6.    <span data-ttu-id="72ab7-126">Klicka på **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-126">Click **Add data source**.</span></span> 
7.    <span data-ttu-id="72ab7-127">Klicka på **Tabellregister**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-127">Click **Table records**.</span></span> 
8.    <span data-ttu-id="72ab7-128">Använd snabbfiltret för att filtrera på fältet **Namn** med värdet Intrastat.</span><span class="sxs-lookup"><span data-stu-id="72ab7-128">Use the Quick Filter to filter on the **Name** field with a value of 'Intrastat'.</span></span> 
9.    <span data-ttu-id="72ab7-129">Väljtabellregister **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-129">Select the **Intrastat** table record.</span></span> 
10.    <span data-ttu-id="72ab7-130">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-130">Click **OK**.</span></span>
  
<span data-ttu-id="72ab7-131">Vi har lagt till metadatainformation om Intrastat-tabellen med poster.</span><span class="sxs-lookup"><span data-stu-id="72ab7-131">We added metadata information about the Intrastat table of records.</span></span> 
  
11.    <span data-ttu-id="72ab7-132">I trädet expanderar du **Tabellregister Intrastat**\>**Relationer**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-132">In the tree, expand **Table records Intrastat**\>**Relations**.</span></span> 
12.    <span data-ttu-id="72ab7-133">I trädet väljer du **Tabellregistr Intrastat**\>**Relations\IntrastatCommodity (Tabellregister EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-133">In the tree, select **Table records Intrastat**\>**Relations\IntrastatCommodity (Table records EcoResCategory)**.</span></span>     
13.    <span data-ttu-id="72ab7-134">Klicka på **Lägg till metadata**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-134">Click **Add metadata**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="72ab7-135">Du måste lägga till metadata för obligatoriska relationer för det valda register med poster manuellt.</span><span class="sxs-lookup"><span data-stu-id="72ab7-135">Metadata about required relations for selected table of records must be added manually.</span></span> 
  
16.    <span data-ttu-id="72ab7-136">Klicka på **Lägg till datakälla**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-136">Click **Add data source**.</span></span> 
17.    <span data-ttu-id="72ab7-137">Klicka **uppräkning**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-137">Click **Enumeration**.</span></span> 
18.    <span data-ttu-id="72ab7-138">Använd snabbfiltret för att filtrera på fältet **Namn** med värdet IntrastatDirection.</span><span class="sxs-lookup"><span data-stu-id="72ab7-138">Use the Quick Filter to filter on the **Name** field with a value of 'IntrastatDirection'.</span></span> 
19.    <span data-ttu-id="72ab7-139">Välj posten **IntrastatDirection enumeration**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-139">Select the **IntrastatDirection enumeration** record.</span></span> 
20.    <span data-ttu-id="72ab7-140">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-140">Click **OK**.</span></span> 
21.    <span data-ttu-id="72ab7-141">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-141">Click **Save**.</span></span>  
22.    <span data-ttu-id="72ab7-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72ab7-142">Close the page.</span></span> 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a><span data-ttu-id="72ab7-143">Fyll i utkastet av konfigurationen av metadata</span><span class="sxs-lookup"><span data-stu-id="72ab7-143">Complete the draft version of metadata configuration</span></span>
1.    <span data-ttu-id="72ab7-144">Klicka på **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-144">Click **Change status**.</span></span> 
2.    <span data-ttu-id="72ab7-145">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-145">Click **Complete**.</span></span> 
3.    <span data-ttu-id="72ab7-146">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-146">Click **OK**.</span></span> 
4.    <span data-ttu-id="72ab7-147">Väljden slutförda versionen **1**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-147">Select the completed version **1**.</span></span> 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a><span data-ttu-id="72ab7-148">Exportera den slutförda versionen av metadata-konfigurationen från programmet som XML-fil</span><span class="sxs-lookup"><span data-stu-id="72ab7-148">Export the completed version of metadata configuration from application as XML file</span></span>
1.    <span data-ttu-id="72ab7-149">Klicka på **Byt**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-149">Click **Exchange**.</span></span> 
2.    <span data-ttu-id="72ab7-150">Klicka på **Exportera som XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-150">Click **Export as XML file**.</span></span> 
3.    <span data-ttu-id="72ab7-151">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="72ab7-151">Click **OK**.</span></span> 
    
<span data-ttu-id="72ab7-152">Den skapade konfigurationen av ER-metadata har sparats som en XML-fil som kan importeras till RCS och användas som källa för information om metadata för den utländska handelsdomänen.</span><span class="sxs-lookup"><span data-stu-id="72ab7-152">The created ER metadata configuration has been saved as XML file that can be imported to RCS and used as the source of information about metadata for the foreign trade business domain.</span></span> <span data-ttu-id="72ab7-153">Utifrån den här informationen kan vi ange mappningen mellan programdata och ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="72ab7-153">Based on this information, we can specify the mapping between application metadata and ER data model.</span></span>
