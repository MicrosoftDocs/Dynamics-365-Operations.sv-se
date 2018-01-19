---
title: "Konfigurationer för leverantörsförfrågan"
description: "Det här avsnittet beskriver de fält som behöver ifyllas i en ny leverantörsförfrågan."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 7eecaf8c0d928a5aca5528bada5e5612218d3dcd
ms.contentlocale: sv-se
ms.lasthandoff: 01/19/2018

---

# <a name="vendor-request-configurations"></a><span data-ttu-id="d759f-103">Konfigurationer för leverantörsförfrågan</span><span class="sxs-lookup"><span data-stu-id="d759f-103">Vendor request configurations</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="d759f-104">Om du vill slutföra en leverantörsförfrågan måste en kontaktperson för leverantören slutföra registreringsguiden för potentiell leverantör.</span><span class="sxs-lookup"><span data-stu-id="d759f-104">To complete a vendor request, a vendor contact person must complete the prospective vendor registration wizard.</span></span>

<span data-ttu-id="d759f-105">I formuläret **Konfigurationer för leverantörsförfrågan** kan du skapa profiler som anger erforderliga och synliga fält i registreringsguiden för potentiell leverantör.</span><span class="sxs-lookup"><span data-stu-id="d759f-105">In the **Vendor request configurations** form, you can create profiles that specify required fields and visible fields in the prospective vendor registration wizard.</span></span>

<span data-ttu-id="d759f-106">Registreringsguiden för leverantör börjar med att fråga den potentiella leverantörsanvändaren vilket land/vilken region leverantören är verksam i.</span><span class="sxs-lookup"><span data-stu-id="d759f-106">The vendor registration wizard will start out by asking the prospective vendor user which country/region the vendor is doing business in.</span></span> <span data-ttu-id="d759f-107">Denna information bestämmer tillämpbar konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d759f-107">This information determines the applicable configuration.</span></span> <span data-ttu-id="d759f-108">Om ingen specifik konfiguration definieras för ett land/en region kommer en standardkonfiguration att användas.</span><span class="sxs-lookup"><span data-stu-id="d759f-108">If no specific configuration is defined for a country/region, a default configuration will be used.</span></span>

### <a name="set-up-a-vendor-request-configuration"></a><span data-ttu-id="d759f-109">Skapa en konfiguration för leverantörsförfrågan</span><span class="sxs-lookup"><span data-stu-id="d759f-109">Set up a vendor request configuration</span></span>

<span data-ttu-id="d759f-110">Som standard finns en leverantörskonfiguration i konfigurationsformuläret för leverantörsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="d759f-110">By default, there is a vendor configuration available in the Vendor request configurations form.</span></span>

<span data-ttu-id="d759f-111">Det går inte att välja länder/regioner för standardkonfigurationen, vilket innebär att avsnittet **Länder/regioner** inte kan ändras.</span><span class="sxs-lookup"><span data-stu-id="d759f-111">It is not possible to select country/regions for the default configuration, so the **Countries/regions** section cannot be changed.</span></span>

1.  <span data-ttu-id="d759f-112">Klicka på **Anskaffning och inköp** > **Inställningar** > **Leverantörer**, och klicka sedan på **Konfigurationer för leverantörsförfrågan**.</span><span class="sxs-lookup"><span data-stu-id="d759f-112">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="d759f-113">Klicka på fliken **Fält** för att ange status för listade fält.</span><span class="sxs-lookup"><span data-stu-id="d759f-113">Click the **Fields** tab to set the status of the listed fields.</span></span>
-   <span data-ttu-id="d759f-114">Dold (visas inte)</span><span class="sxs-lookup"><span data-stu-id="d759f-114">Hidden (Not visible)</span></span>
-   <span data-ttu-id="d759f-115">Visas (synlig men inte obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="d759f-115">Displayed (Visible but not mandatory)</span></span>
-   <span data-ttu-id="d759f-116">Obligatorisk (synlig och obligatorisk)</span><span class="sxs-lookup"><span data-stu-id="d759f-116">Required (Visible and mandatory)</span></span>
3.  <span data-ttu-id="d759f-117">Klicka på fliken **Innehåll** för att ange om texten ska visas i guiden och om det ska finnas en bekräftelse att den potentiella leverantörsanvändaren måste acceptera detta innan han/hon fortsätter till nästa steg i guiden.</span><span class="sxs-lookup"><span data-stu-id="d759f-117">Click the **Content** tab to specify if text is going to be shown on the wizard and if there should be an acknowledgement that the prospective vendor user must accept this before moving to the next step in the wizard.</span></span> <span data-ttu-id="d759f-118">Bekräftelsen kommer att begäras för alla villkor som användaren måste acceptera för att kunna fortsätta.</span><span class="sxs-lookup"><span data-stu-id="d759f-118">The acknowledgement will be requested for any terms and conditions that the user must accept to continue.</span></span>

<span data-ttu-id="d759f-119">Du kan även ange ett bekräftelsemeddelande som visas när guiden har slutförts, och du kan lägga till en eller flera frågeformulär.</span><span class="sxs-lookup"><span data-stu-id="d759f-119">You can also enter a confirmation message that will be displayed when the wizard is finalized, and you can add one or more questionnaires.</span></span>

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a><span data-ttu-id="d759f-120">Skapa en leverantörskonfiguration för ett visst land/en viss region</span><span class="sxs-lookup"><span data-stu-id="d759f-120">Create a vendor configuration for a specific country/region</span></span>
1.  <span data-ttu-id="d759f-121">Klicka på **Anskaffning och inköp** > **Inställningar** > **Leverantörer**, och klicka sedan på **Konfigurationer för leverantörsförfrågan**.</span><span class="sxs-lookup"><span data-stu-id="d759f-121">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="d759f-122">Klicka på **Ny** för att skapa en ny konfiguration, och ange ett namn för konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="d759f-122">Click **New** to create a new configuration, and provide a name for the configuration.</span></span>
3.  <span data-ttu-id="d759f-123">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d759f-123">Click **Save**.</span></span>
4.  <span data-ttu-id="d759f-124">Öppna fliken **Länder/regioner** för att välja det land/den region som konfigurationen ska användas för.</span><span class="sxs-lookup"><span data-stu-id="d759f-124">Open the **Country/regions** tab to select the country/region that the configuration should be used for.</span></span>
5.  <span data-ttu-id="d759f-125">Slutför konfigurationen genom att följa riktlinjerna för standardkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="d759f-125">Complete the configuration by following the guidelines for the default configuration.</span></span>


