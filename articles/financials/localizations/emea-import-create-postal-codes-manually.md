---
title: Importera eller skapa postnummer manuellt
description: Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format. Det här avsnittet innehåller information om funktioner som lagts till eller ändrats för Microsoft Dynamics 365 for Finance and Operations.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: db7090e47301aad9ab56a62efd807140db62ab3b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559651"
---
# <a name="import-or-manually-create-postal-codes"></a><span data-ttu-id="fb4ec-104">Importera eller skapa postnummer manuellt</span><span class="sxs-lookup"><span data-stu-id="fb4ec-104">Import or manually create postal codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb4ec-105">Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-105">This topic explains how to import and manually create postal codes in the correct format.</span></span> <span data-ttu-id="fb4ec-106">Det här avsnittet innehåller information om funktioner som lagts till eller ändrats för Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-106">This topic includes information about feature that was added for Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="fb4ec-107">Genom importen kan du uppdatera postnummer för ett visst land/en viss region.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-107">The import process lets you update the ZIP/postal codes for a specific country/region.</span></span> <span data-ttu-id="fb4ec-108">Du kan också skapa postnummer manuellt.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-108">You can also create postal codes manually.</span></span>

## <a name="import-zippostal-codes"></a><span data-ttu-id="fb4ec-109">Importera postnr</span><span class="sxs-lookup"><span data-stu-id="fb4ec-109">Import ZIP/postal codes</span></span>
<span data-ttu-id="fb4ec-110">Du kan använda sidan **Importera postnummer** för att importera nya postnummer till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-110">You can use the **Import ZIP/postal codes** page to import new postal codes into Finance and Operations.</span></span> <span data-ttu-id="fb4ec-111">När du importerar koderna ersätts befintliga postnummer och postkoder med det nya formatet, och alla nya nummer/koder läggs till.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-111">When you import the codes, the existing ZIP or postal codes are replaced with the new format, and any new codes are added.</span></span>

<span data-ttu-id="fb4ec-112">I vissa länder måste du använda ramverket för datahantering för att importera koder, medan för andra länder bara den överförda filen krävs.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-112">For some countries, you must use the Data management framework to import codes, while for other countries only an upload file is required.</span></span> <span data-ttu-id="fb4ec-113">Belgien, Nederländerna och Sverige kräver en fil att överföra.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-113">Belgium, Netherlands, and Sweden require a file to upload.</span></span>

> [!NOTE]
> -   <span data-ttu-id="fb4ec-114">För Belgien tillhandahåller det belgiska postverkets hemsida en officiell lista över postnumren och motsvarande ortsnamn.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-114">For Belgium, the official webpage from the Belgian Post provides an official list of the postcodes and the corresponding city names.</span></span> <span data-ttu-id="fb4ec-115">Importen stöder html-filformat.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-115">The import supports html file format.</span></span>
> -   <span data-ttu-id="fb4ec-116">För Nederländerna tillhandahåller en tredjepartsorganisation den fil som innehåller postnummer.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-116">For Netherlands, a third-party organization provides the file that contains postal codes.</span></span> <span data-ttu-id="fb4ec-117">När importen har slutförts visas alla postnummer i formatet (NNNN AA).</span><span class="sxs-lookup"><span data-stu-id="fb4ec-117">After the import is completed, all postal codes will appear in the format (NNNN AA).</span></span>
> -   <span data-ttu-id="fb4ec-118">För Sverige finns Postnummerservice.se, som tillhandahåller två typer av filer: svenska postnummer och svenska adresser.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-118">For Sweden, Postnummerservice.se provides two types of files: Swedish postal codes and Swedish addresses.</span></span> <span data-ttu-id="fb4ec-119">Importen stöder textfilsformat för båda typer.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-119">The import supports text file format for both types.</span></span>


## <a name="create-zippostal-codes-manually"></a><span data-ttu-id="fb4ec-120">Skapa postnummer/postkoder manuellt</span><span class="sxs-lookup"><span data-stu-id="fb4ec-120">Create ZIP/postal codes manually</span></span>
<span data-ttu-id="fb4ec-121">I stället för att importera koder kan du använda sidan **Adressinställningar** för att manuellt lägga till nya postnummer.</span><span class="sxs-lookup"><span data-stu-id="fb4ec-121">Instead of importing codes, you can use the **Address setup** page to manually add new ZIP/postal codes.</span></span>


