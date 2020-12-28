---
title: " Skapa och associera register"
description: I den här proceduren visas hur du skapar ett kassaregister (POS).
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 001bdd61f9266798dadae2ac7c96a4f4c19dbb94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415891"
---
# <a name="create-and-associate-registers"></a><span data-ttu-id="d2a9e-103"> Skapa och associera register</span><span class="sxs-lookup"><span data-stu-id="d2a9e-103">Create and associate registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2a9e-104">I den här proceduren visas hur du skapar ett kassaregister (POS).</span><span class="sxs-lookup"><span data-stu-id="d2a9e-104">This procedure demonstrates how to create a point of sale (POS) register.</span></span> <span data-ttu-id="d2a9e-105">I den här proceduren används demonstrationsdataföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-105">This procedure uses the demo data company USRT.</span></span>

1. <span data-ttu-id="d2a9e-106">Gå till Butik och handel > kanalinställning > POS inställning > register.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-106">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
2. <span data-ttu-id="d2a9e-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-107">Click New.</span></span>
3. <span data-ttu-id="d2a9e-108">Skriv ett ID för den nya kassan i fältet Kassanummer.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-108">In the Register number field, type an ID for the new register.</span></span>
    * <span data-ttu-id="d2a9e-109">Register-ID:t innehåller vanligtvis koder som gör det enklare att mappa registret till butiken som det tillhör och platsen i butiken.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-109">The register ID typically includes codes that help map the register to the store to which it belongs, and the location within the store.</span></span>  
4. <span data-ttu-id="d2a9e-110">Ange ett beskrivande namn för den nya kassan i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-110">In the Name field, type a descriptive name for the register..</span></span>
5. <span data-ttu-id="d2a9e-111">Ange eller välj ett värde i fältet Butiksnummer.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-111">In the Store number field, enter or select a value.</span></span>
6. <span data-ttu-id="d2a9e-112">Ange eller välj ett värde i fältet Maskinvaruprofil.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-112">In the Hardware profile field, enter or select a value.</span></span>
    * <span data-ttu-id="d2a9e-113">Maskinvaruprofiler används för att ange den kringutrustning som kommer att kopplas till registret, som till exempel kassalåda och kvittoskrivare.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-113">Hardware profiles are used to specify the peripherals that will be connected to the register, such as cash drawer and receipt printer.</span></span>  
7. <span data-ttu-id="d2a9e-114">Ange eller välj ett värde i fältet Visuell profil.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-114">In the Visual profile field, enter or select a value.</span></span>
    * <span data-ttu-id="d2a9e-115">Visuella profiler används för att ange bilderna som används i kassabakgrunden och inloggningssidan samt teman för kassan.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-115">Visual profiles are used to specify the images used in the POS background and login page as well as themes for the POS.</span></span>  
8. <span data-ttu-id="d2a9e-116">Skriv ett värde i fältet EFT-kassanummer..</span><span class="sxs-lookup"><span data-stu-id="d2a9e-116">In the EFT POS register number field, type a value.</span></span>
    * <span data-ttu-id="d2a9e-117">EFT-kassanumret används för att informera betalningsprocessorn vilken betalningterminal som skickar auktoriseringförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-117">The EFT POS register number is used to inform the payment processor which payment terminal is sending authorization requests.</span></span> <span data-ttu-id="d2a9e-118">Det här värdet kallas ofta ”Terminal-ID ”eller ”Organisationsnummer”.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-118">This value is often called the "Terminal ID" or "TID".</span></span> <span data-ttu-id="d2a9e-119">Organisationsnumret hittas på klistermärke på betalningsenheten.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-119">The TID can generally be found on a sticker on the payment device.</span></span>  
9. <span data-ttu-id="d2a9e-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d2a9e-120">Click Save.</span></span>

