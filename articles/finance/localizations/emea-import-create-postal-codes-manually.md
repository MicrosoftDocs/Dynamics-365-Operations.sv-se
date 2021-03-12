---
title: Importera eller skapa postnummer manuellt
description: Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7ef7d8d042c9c0d78c1ea3e56eda2ff3597a9781
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962680"
---
# <a name="import-or-manually-create-postal-codes"></a><span data-ttu-id="0f73b-103">Importera eller skapa postnummer manuellt</span><span class="sxs-lookup"><span data-stu-id="0f73b-103">Import or manually create postal codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f73b-104">Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format.</span><span class="sxs-lookup"><span data-stu-id="0f73b-104">This topic explains how to import and manually create postal codes in the correct format.</span></span> 

<span data-ttu-id="0f73b-105">Genom importen kan du uppdatera postnummer för ett visst land/en viss region.</span><span class="sxs-lookup"><span data-stu-id="0f73b-105">The import process lets you update the ZIP/postal codes for a specific country/region.</span></span> <span data-ttu-id="0f73b-106">Du kan också skapa postnummer manuellt.</span><span class="sxs-lookup"><span data-stu-id="0f73b-106">You can also create postal codes manually.</span></span>

## <a name="import-zippostal-codes"></a><span data-ttu-id="0f73b-107">Importera postnr</span><span class="sxs-lookup"><span data-stu-id="0f73b-107">Import ZIP/postal codes</span></span>
<span data-ttu-id="0f73b-108">Du kan använda sidan **Importera postnummer** för att importera nya postnummer till Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="0f73b-108">You can use the **Import ZIP/postal codes** page to import new postal codes into Dynamics 365 Finance.</span></span> <span data-ttu-id="0f73b-109">När du importerar koderna ersätts befintliga postnummer och postkoder med det nya formatet, och alla nya nummer/koder läggs till.</span><span class="sxs-lookup"><span data-stu-id="0f73b-109">When you import the codes, the existing ZIP or postal codes are replaced with the new format, and any new codes are added.</span></span>

<span data-ttu-id="0f73b-110">I vissa länder måste du använda ramverket för datahantering för att importera koder, medan för andra länder bara den överförda filen krävs.</span><span class="sxs-lookup"><span data-stu-id="0f73b-110">For some countries, you must use the Data management framework to import codes, while for other countries only an upload file is required.</span></span> <span data-ttu-id="0f73b-111">Belgien, Nederländerna och Sverige kräver en fil att överföra.</span><span class="sxs-lookup"><span data-stu-id="0f73b-111">Belgium, Netherlands, and Sweden require a file to upload.</span></span>

> [!NOTE]
> -   <span data-ttu-id="0f73b-112">För Belgien tillhandahåller det belgiska postverkets hemsida en officiell lista över postnumren och motsvarande ortsnamn.</span><span class="sxs-lookup"><span data-stu-id="0f73b-112">For Belgium, the official webpage from the Belgian Post provides an official list of the postcodes and the corresponding city names.</span></span> <span data-ttu-id="0f73b-113">Importen stöder html-filformat.</span><span class="sxs-lookup"><span data-stu-id="0f73b-113">The import supports html file format.</span></span>
> -   <span data-ttu-id="0f73b-114">För Nederländerna tillhandahåller en tredjepartsorganisation den fil som innehåller postnummer.</span><span class="sxs-lookup"><span data-stu-id="0f73b-114">For Netherlands, a third-party organization provides the file that contains postal codes.</span></span> <span data-ttu-id="0f73b-115">När importen har slutförts visas alla postnummer i formatet (NNNN AA).</span><span class="sxs-lookup"><span data-stu-id="0f73b-115">After the import is completed, all postal codes will appear in the format (NNNN AA).</span></span>
> -   <span data-ttu-id="0f73b-116">För Sverige finns Postnummerservice.se, som tillhandahåller två typer av filer: svenska postnummer och svenska adresser.</span><span class="sxs-lookup"><span data-stu-id="0f73b-116">For Sweden, Postnummerservice.se provides two types of files: Swedish postal codes and Swedish addresses.</span></span> <span data-ttu-id="0f73b-117">Importen stöder textfilsformat för båda typer.</span><span class="sxs-lookup"><span data-stu-id="0f73b-117">The import supports text file format for both types.</span></span>


## <a name="create-zippostal-codes-manually"></a><span data-ttu-id="0f73b-118">Skapa postnummer/postkoder manuellt</span><span class="sxs-lookup"><span data-stu-id="0f73b-118">Create ZIP/postal codes manually</span></span>
<span data-ttu-id="0f73b-119">I stället för att importera koder kan du använda sidan **Adressinställningar** för att manuellt lägga till nya postnummer.</span><span class="sxs-lookup"><span data-stu-id="0f73b-119">Instead of importing codes, you can use the **Address setup** page to manually add new ZIP/postal codes.</span></span>


