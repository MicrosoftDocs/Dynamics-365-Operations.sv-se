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
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "371839"
---
# <a name="import-or-manually-create-postal-codes"></a><span data-ttu-id="229cd-104">Importera eller skapa postnummer manuellt</span><span class="sxs-lookup"><span data-stu-id="229cd-104">Import or manually create postal codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="229cd-105">Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format.</span><span class="sxs-lookup"><span data-stu-id="229cd-105">This topic explains how to import and manually create postal codes in the correct format.</span></span> <span data-ttu-id="229cd-106">Det här avsnittet innehåller information om funktioner som lagts till eller ändrats för Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="229cd-106">This topic includes information about feature that was added for Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="229cd-107">Genom importen kan du uppdatera postnummer för ett visst land/en viss region.</span><span class="sxs-lookup"><span data-stu-id="229cd-107">The import process lets you update the ZIP/postal codes for a specific country/region.</span></span> <span data-ttu-id="229cd-108">Du kan också skapa postnummer manuellt.</span><span class="sxs-lookup"><span data-stu-id="229cd-108">You can also create postal codes manually.</span></span>

## <a name="import-zippostal-codes"></a><span data-ttu-id="229cd-109">Importera postnr</span><span class="sxs-lookup"><span data-stu-id="229cd-109">Import ZIP/postal codes</span></span>
<span data-ttu-id="229cd-110">Du kan använda sidan **Importera postnummer** för att importera nya postnummer till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="229cd-110">You can use the **Import ZIP/postal codes** page to import new postal codes into Finance and Operations.</span></span> <span data-ttu-id="229cd-111">När du importerar koderna ersätts befintliga postnummer och postkoder med det nya formatet, och alla nya nummer/koder läggs till.</span><span class="sxs-lookup"><span data-stu-id="229cd-111">When you import the codes, the existing ZIP or postal codes are replaced with the new format, and any new codes are added.</span></span>

<span data-ttu-id="229cd-112">I vissa länder måste du använda ramverket för datahantering för att importera koder, medan för andra länder bara den överförda filen krävs.</span><span class="sxs-lookup"><span data-stu-id="229cd-112">For some countries, you must use the Data management framework to import codes, while for other countries only an upload file is required.</span></span> <span data-ttu-id="229cd-113">Belgien, Nederländerna och Sverige kräver en fil att överföra.</span><span class="sxs-lookup"><span data-stu-id="229cd-113">Belgium, Netherlands, and Sweden require a file to upload.</span></span>

> [!NOTE]
> -   <span data-ttu-id="229cd-114">För Belgien tillhandahåller det belgiska postverkets hemsida en officiell lista över postnumren och motsvarande ortsnamn.</span><span class="sxs-lookup"><span data-stu-id="229cd-114">For Belgium, the official webpage from the Belgian Post provides an official list of the postcodes and the corresponding city names.</span></span> <span data-ttu-id="229cd-115">Importen stöder html-filformat.</span><span class="sxs-lookup"><span data-stu-id="229cd-115">The import supports html file format.</span></span>
> -   <span data-ttu-id="229cd-116">För Nederländerna tillhandahåller en tredjepartsorganisation den fil som innehåller postnummer.</span><span class="sxs-lookup"><span data-stu-id="229cd-116">For Netherlands, a third-party organization provides the file that contains postal codes.</span></span> <span data-ttu-id="229cd-117">När importen har slutförts visas alla postnummer i formatet (NNNN AA).</span><span class="sxs-lookup"><span data-stu-id="229cd-117">After the import is completed, all postal codes will appear in the format (NNNN AA).</span></span>
> -   <span data-ttu-id="229cd-118">För Sverige finns Postnummerservice.se, som tillhandahåller två typer av filer: svenska postnummer och svenska adresser.</span><span class="sxs-lookup"><span data-stu-id="229cd-118">For Sweden, Postnummerservice.se provides two types of files: Swedish postal codes and Swedish addresses.</span></span> <span data-ttu-id="229cd-119">Importen stöder textfilsformat för båda typer.</span><span class="sxs-lookup"><span data-stu-id="229cd-119">The import supports text file format for both types.</span></span>


## <a name="create-zippostal-codes-manually"></a><span data-ttu-id="229cd-120">Skapa postnummer/postkoder manuellt</span><span class="sxs-lookup"><span data-stu-id="229cd-120">Create ZIP/postal codes manually</span></span>
<span data-ttu-id="229cd-121">I stället för att importera koder kan du använda sidan **Adressinställningar** för att manuellt lägga till nya postnummer.</span><span class="sxs-lookup"><span data-stu-id="229cd-121">Instead of importing codes, you can use the **Address setup** page to manually add new ZIP/postal codes.</span></span>


