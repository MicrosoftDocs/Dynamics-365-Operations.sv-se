---
title: Importera eller skapa postnummer manuellt
description: "Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format. Det här avsnittet innehåller information om funktioner som har lagts till för Microsoft Dynamics 365 for Finance and Operations."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: db7090e47301aad9ab56a62efd807140db62ab3b
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="import-or-manually-create-postal-codes"></a><span data-ttu-id="c0eac-104">Importera eller skapa postnummer manuellt</span><span class="sxs-lookup"><span data-stu-id="c0eac-104">Import or manually create postal codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0eac-105">Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format.</span><span class="sxs-lookup"><span data-stu-id="c0eac-105">This topic explains how to import and manually create postal codes in the correct format.</span></span> <span data-ttu-id="c0eac-106">Det här avsnittet innehåller information om funktioner som har lagts till för Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c0eac-106">This topic includes information about feature that was added for Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="c0eac-107">Genom importen kan du uppdatera postnummer för ett visst land/en viss region.</span><span class="sxs-lookup"><span data-stu-id="c0eac-107">The import process lets you update the ZIP/postal codes for a specific country/region.</span></span> <span data-ttu-id="c0eac-108">Du kan också skapa postnummer manuellt.</span><span class="sxs-lookup"><span data-stu-id="c0eac-108">You can also create postal codes manually.</span></span>

## <a name="import-zippostal-codes"></a><span data-ttu-id="c0eac-109">Importera postnr</span><span class="sxs-lookup"><span data-stu-id="c0eac-109">Import ZIP/postal codes</span></span>
<span data-ttu-id="c0eac-110">Du kan använda sidan **Importera postnummer** för att importera nya postnummer till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c0eac-110">You can use the **Import ZIP/postal codes** page to import new postal codes into Finance and Operations.</span></span> <span data-ttu-id="c0eac-111">När du importerar koderna ersätts befintliga postnummer och postkoder med det nya formatet, och alla nya nummer/koder läggs till.</span><span class="sxs-lookup"><span data-stu-id="c0eac-111">When you import the codes, the existing ZIP or postal codes are replaced with the new format, and any new codes are added.</span></span>

<span data-ttu-id="c0eac-112">I vissa länder måste du använda ramverket för datahantering för att importera koder, medan för andra länder bara den överförda filen krävs.</span><span class="sxs-lookup"><span data-stu-id="c0eac-112">For some countries, you must use the Data management framework to import codes, while for other countries only an upload file is required.</span></span> <span data-ttu-id="c0eac-113">Belgien, Nederländerna och Sverige kräver en fil att överföra.</span><span class="sxs-lookup"><span data-stu-id="c0eac-113">Belgium, Netherlands, and Sweden require a file to upload.</span></span>

> [!NOTE]
> -   <span data-ttu-id="c0eac-114">För Belgien tillhandahåller det belgiska postverkets hemsida en officiell lista över postnumren och motsvarande ortsnamn.</span><span class="sxs-lookup"><span data-stu-id="c0eac-114">For Belgium, the official webpage from the Belgian Post provides an official list of the postcodes and the corresponding city names.</span></span> <span data-ttu-id="c0eac-115">Importen stöder html-filformat.</span><span class="sxs-lookup"><span data-stu-id="c0eac-115">The import supports html file format.</span></span>
> -   <span data-ttu-id="c0eac-116">För Nederländerna tillhandahåller en tredjepartsorganisation den fil som innehåller postnummer.</span><span class="sxs-lookup"><span data-stu-id="c0eac-116">For Netherlands, a third-party organization provides the file that contains postal codes.</span></span> <span data-ttu-id="c0eac-117">När importen har slutförts visas alla postnummer i formatet (NNNN AA).</span><span class="sxs-lookup"><span data-stu-id="c0eac-117">After the import is completed, all postal codes will appear in the format (NNNN AA).</span></span>
> -   <span data-ttu-id="c0eac-118">För Sverige finns Postnummerservice.se, som tillhandahåller två typer av filer: svenska postnummer och svenska adresser.</span><span class="sxs-lookup"><span data-stu-id="c0eac-118">For Sweden, Postnummerservice.se provides two types of files: Swedish postal codes and Swedish addresses.</span></span> <span data-ttu-id="c0eac-119">Importen stöder textfilsformat för båda typer.</span><span class="sxs-lookup"><span data-stu-id="c0eac-119">The import supports text file format for both types.</span></span>


## <a name="create-zippostal-codes-manually"></a><span data-ttu-id="c0eac-120">Skapa postnummer/postkoder manuellt</span><span class="sxs-lookup"><span data-stu-id="c0eac-120">Create ZIP/postal codes manually</span></span>
<span data-ttu-id="c0eac-121">I stället för att importera koder kan du använda sidan **Adressinställningar** för att manuellt lägga till nya postnummer.</span><span class="sxs-lookup"><span data-stu-id="c0eac-121">Instead of importing codes, you can use the **Address setup** page to manually add new ZIP/postal codes.</span></span>



