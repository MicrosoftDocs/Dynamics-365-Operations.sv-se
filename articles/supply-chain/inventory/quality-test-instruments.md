---
title: Testinstrument för kvalitetshantering
description: I detta ämne beskrivs hur du skapar testinstrument som kan användas för tester på kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3806ca26b8909b03768dad54ddad0084e1cea4a6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021742"
---
# <a name="quality-management-test-instruments"></a><span data-ttu-id="ad59c-103">Testinstrument för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="ad59c-103">Quality management test instruments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad59c-104">I detta ämne beskrivs hur du skapar testinstrument som kan användas för tester på kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ad59c-104">This topic describes how to create test instruments that can be used for tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="ad59c-105">På sidan **Testinstrument** kan du definiera och visa information om de enheter som används för att utföra tester på kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="ad59c-105">You use the **Test instruments** page to define and view details about the devices that are used to perform tests on quality orders.</span></span> <span data-ttu-id="ad59c-106">Testinstrument är valfria.</span><span class="sxs-lookup"><span data-stu-id="ad59c-106">Test instruments are optional.</span></span> <span data-ttu-id="ad59c-107">De kan emellertid hjälpa kvalitetsmedarbetare att veta vilken enhet eller vilket verktyg de bör använda för att utföra ett visst test.</span><span class="sxs-lookup"><span data-stu-id="ad59c-107">However, they can help quality workers know which device or tool they should use to perform a specific test.</span></span>

## <a name="test-instrument-example"></a><span data-ttu-id="ad59c-108">Exempel på testinstrument</span><span class="sxs-lookup"><span data-stu-id="ad59c-108">Test instrument example</span></span>

<span data-ttu-id="ad59c-109">Du utför olika tester på elkomponenter.</span><span class="sxs-lookup"><span data-stu-id="ad59c-109">You're performing various tests on electrical components.</span></span> <span data-ttu-id="ad59c-110">Vissa tester är avsedda för komponenternas utdata, ett test gäller deras temperatur och ett test gäller deras vikt.</span><span class="sxs-lookup"><span data-stu-id="ad59c-110">Some tests are for the voltage output of the components, one test is for their temperature, and one test is for their weight.</span></span> <span data-ttu-id="ad59c-111">Olika verktyg, enheter eller utrustning används för att utföra respektive test.</span><span class="sxs-lookup"><span data-stu-id="ad59c-111">Different tools, devices, or equipment is used to perform each test.</span></span> <span data-ttu-id="ad59c-112">En spänningsmätare används för att mäta spänning, en termometer används för att mäta temperatur, och en våg används för att mäta vikt.</span><span class="sxs-lookup"><span data-stu-id="ad59c-112">For example, a voltage meter is used to measure voltage, a thermometer is used to measure temperature, and a scale is used to measure weight.</span></span> <span data-ttu-id="ad59c-113">Du kan konfigurera var och en av dessa enheter som ett testinstrument och ange måttenheten som testresultatet ska registreras i.</span><span class="sxs-lookup"><span data-stu-id="ad59c-113">You can configure each of these devices as a test instrument and indicate the unit of measure that the test results should be recorded in.</span></span> <span data-ttu-id="ad59c-114">Resultat från spänningsmätaren registreras till exempel i volt, resultat från termometern registreras i grader i Fahrenheit eller Celsius, och resultatet från vågen registreras i pund eller kilo.</span><span class="sxs-lookup"><span data-stu-id="ad59c-114">For example, results from the voltage meter are recorded in volts, results from the thermometer are recorded in degrees Fahrenheit or degrees Celsius, and results from the scale are recorded in pounds or kilograms.</span></span>

## <a name="create-a-test-instrument"></a><span data-ttu-id="ad59c-115">Skapa ett testinstrument</span><span class="sxs-lookup"><span data-stu-id="ad59c-115">Create a test instrument</span></span>

1. <span data-ttu-id="ad59c-116">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Testinstrument**.</span><span class="sxs-lookup"><span data-stu-id="ad59c-116">Go to **Inventory management \> Setup \> Quality control \> Test instruments**.</span></span>
1. <span data-ttu-id="ad59c-117">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="ad59c-117">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="ad59c-118">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="ad59c-118">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="ad59c-119">**Testinstrument** – Ange ett unikt ID eller namn för testinstrumentet.</span><span class="sxs-lookup"><span data-stu-id="ad59c-119">**Test instrument** – Enter a unique ID or name for the test instrument.</span></span>
    - <span data-ttu-id="ad59c-120">**Beskrivning** – Ange en detaljerad beskrivning av testinstrumentet.</span><span class="sxs-lookup"><span data-stu-id="ad59c-120">**Description** – Enter a detailed description of the test instrument.</span></span>
    - <span data-ttu-id="ad59c-121">**Enhet** – Välj den enhet som instrumentmåtten resulterar i.</span><span class="sxs-lookup"><span data-stu-id="ad59c-121">**Unit** – Select the unit that the instrument measures results in.</span></span> <span data-ttu-id="ad59c-122">Fältet **Precision** ställs automatiskt in utifrån den enhet du väljer.</span><span class="sxs-lookup"><span data-stu-id="ad59c-122">The **Precision** field is automatically set, based on the unit that you select.</span></span>

1. <span data-ttu-id="ad59c-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ad59c-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ad59c-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ad59c-124">Additional resources</span></span>

- [<span data-ttu-id="ad59c-125">Kvalitetshanteringstest</span><span class="sxs-lookup"><span data-stu-id="ad59c-125">Quality management test</span></span>](quality-tests.md)
- [<span data-ttu-id="ad59c-126">Testgrupper för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="ad59c-126">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
