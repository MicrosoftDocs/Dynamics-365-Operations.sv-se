---
title: Importera data från Excel-datatabellmallar med flera kalkylblad
description: Det här avsnittet beskriver hur du importerar data med hjälp av Excel-datatabellmallar till Microsoft Dynamics 365 for Finance and Operations.
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 48239b48cbc24e34d74bbac36e8f827a15d7b840
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "351273"
---
# <a name="import-data-from-excel-data-entity-templates-that-have-multiple-worksheets"></a><span data-ttu-id="9d31b-103">Importera data från Excel-datatabellmallar med flera kalkylblad</span><span class="sxs-lookup"><span data-stu-id="9d31b-103">Import data from Excel data entity templates that have multiple worksheets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d31b-104">Hantering av data i Microsoft Dynamics 365 for Finance and Operations stöder Microsoft Excel-baserade mallar för datatabeller.</span><span class="sxs-lookup"><span data-stu-id="9d31b-104">Data management in Microsoft Dynamics 365 for Finance and Operations supports Microsoft Excel-based templates for data entities.</span></span> <span data-ttu-id="9d31b-105">Mallarna kan innehålla ett eller flera kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="9d31b-105">These templates can contain one or more worksheets.</span></span> <span data-ttu-id="9d31b-106">Mallar med flera kalkylblad används ofta när det är lämpligt att hantera data i en fil och importera den till flera datatabeller.</span><span class="sxs-lookup"><span data-stu-id="9d31b-106">Templates with multiple worksheets are often used when it is convenient to manage data in a single file and import it to multiple data entities.</span></span> <span data-ttu-id="9d31b-107">Ett exempel är platser och lagerställen.</span><span class="sxs-lookup"><span data-stu-id="9d31b-107">An example would be sites and warehouses.</span></span>

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a><span data-ttu-id="9d31b-108">Överför en fil en gång och koppla den till alla entiteter</span><span class="sxs-lookup"><span data-stu-id="9d31b-108">Upload a file once and map it to all entities</span></span>
<span data-ttu-id="9d31b-109">Låt oss ta ett exempel där det finns en Excel-fil med kalkylblad kallat **Platser** och **Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="9d31b-109">Let's take an example where there is one Excel file with worksheets called **Sites** and **Warehouses**.</span></span> <span data-ttu-id="9d31b-110">Om du vill installera dataimportprojektet ska du lägga till den första datatabellen **platser** och överföra filen.</span><span class="sxs-lookup"><span data-stu-id="9d31b-110">To set up the data import project, you would add the first data entity, **Sites** and then upload the file.</span></span> <span data-ttu-id="9d31b-111">Du kan välja **platser** som kalkylblad som ska användas för den här entiteten.</span><span class="sxs-lookup"><span data-stu-id="9d31b-111">You will be able to select **Sites** as the worksheet to be used for this entity.</span></span>

<span data-ttu-id="9d31b-112">Om du lägger till den andra entiteten **lagerställen** utan att lämna formuläret **Lägg till fil** kommer kalkylbladets sökning låta dig välja kalkylbladet **lagerställen** utan att behöva överföra filen igen.</span><span class="sxs-lookup"><span data-stu-id="9d31b-112">If you add the second entity **Warehouses** without leaving the **Add file** form, the worksheet lookup will let you select the **Warehouses** worksheet without having to upload the file again.</span></span> <span data-ttu-id="9d31b-113">Enda skälet att överföra en ny fil skulle vara om **lagerställen**-data finns i en annan fil.</span><span class="sxs-lookup"><span data-stu-id="9d31b-113">The only reason to upload a new file would be if the **Warehouses** data was in a different file.</span></span>

![Flera kalkylblad](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a><span data-ttu-id="9d31b-115">Korrigera kalkylblad till entitetsmappning</span><span class="sxs-lookup"><span data-stu-id="9d31b-115">Fix worksheet to entity mapping</span></span>

<span data-ttu-id="9d31b-116">Mappningen av ett kalkylblad till en datatabell i importjobbet kan åtgärdas i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d31b-116">The mapping of the worksheet to a data entity in the import job can be fixed from the grid.</span></span> <span data-ttu-id="9d31b-117">Kolumnen **kalkylblad** i rutnätet innehåller kalkylblad från filen som har mappats.</span><span class="sxs-lookup"><span data-stu-id="9d31b-117">The **Worksheet** column in the grid shows the worksheets from the file that was mapped.</span></span> <span data-ttu-id="9d31b-118">Du kan välja ett annat kalkylblad på menyn.</span><span class="sxs-lookup"><span data-stu-id="9d31b-118">You can choose a different worksheet from the drop-down menu.</span></span> <span data-ttu-id="9d31b-119">Om det valda kalkylbladet redan är mappat till en entitet i projektet data, ber systemet dig att bekräfta ändringen.</span><span class="sxs-lookup"><span data-stu-id="9d31b-119">If the chosen worksheet is already mapped to an entity in the data project, the system asks you to confirm the change.</span></span> <span data-ttu-id="9d31b-120">Vi rekommenderar att du har åtgärdat alla mappningar i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="9d31b-120">We recommend that you fix all mappings in the grid.</span></span>

![Uppdatera kalkylbladsmappning](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a><span data-ttu-id="9d31b-122">Mappa till en ny fil</span><span class="sxs-lookup"><span data-stu-id="9d31b-122">Re-map to a new file</span></span>

<span data-ttu-id="9d31b-123">I fall där en ny version av samma fil eller en helt ny fil måste läsas in för befintliga entiteter i ett dataprojekt måste du använda upplevelsen **Lägg till filen** och lägga till entiteterna igen som om de lades till för första gången.</span><span class="sxs-lookup"><span data-stu-id="9d31b-123">In cases where a new version of the same file or a completely new file must be uploaded for existing entities in a data project, you must use the **Add file** experience, and add the entities again as if they were being added for the first time.</span></span> <span data-ttu-id="9d31b-124">Systemet bekräftar att du vill skriva över de befintliga entiteterna i dataprojektet innan du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="9d31b-124">The system will confirm that you want to overwrite the existing entities in the data project before proceeding.</span></span> <span data-ttu-id="9d31b-125">Entiteter som inte läggs till igen (eller över) fortsätter att hålla tidigare mappningar från den föregående filen.</span><span class="sxs-lookup"><span data-stu-id="9d31b-125">Entities that are not added again (or overwritten) will continue to hold the previous mappings from the previous file.</span></span>

## <a name="upload-a-file-using-run-project"></a><span data-ttu-id="9d31b-126">Överför en fil genom att använda Kör projekt</span><span class="sxs-lookup"><span data-stu-id="9d31b-126">Upload a file using Run project</span></span>

<span data-ttu-id="9d31b-127">Du kan överföra en Excel-fil när du använder alternativet **Köra projekt** som kör ett importprojekt.</span><span class="sxs-lookup"><span data-stu-id="9d31b-127">You can upload an Excel file while using the **Run project** option to execute an import project.</span></span> <span data-ttu-id="9d31b-128">Du måste vara noga med att överföra filer som har samma kalkylblad som de befintliga mappningarna för datatabellerna i dataprojektet.</span><span class="sxs-lookup"><span data-stu-id="9d31b-128">You must be careful to upload only files that have the same worksheets as the existing mappings on the data entities in the data project.</span></span> <span data-ttu-id="9d31b-129">Om ett kalkylblad inte finns i den nyligen överförda filen, visas ett fel i systemet och importen avbryts.</span><span class="sxs-lookup"><span data-stu-id="9d31b-129">If a worksheet is not found in the newly uploaded file, the system displays an error and will stop the import.</span></span> <span data-ttu-id="9d31b-130">Om mappningen till kalkylbladet måste ändras för en entitet och mappningarna i dataprojektet måste först uppdateras från i inne i dataprojektet innan du använder filen i upplevelsen **Kör projekt**.</span><span class="sxs-lookup"><span data-stu-id="9d31b-130">If the mapping to the worksheet must be changed for an entity, then the mappings in the data project must be first updated from within the data project before using the file in the **Run project** experience.</span></span>
