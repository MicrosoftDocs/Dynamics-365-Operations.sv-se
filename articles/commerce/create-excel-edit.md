---
title: Skapa en Excel-arbetsbok för att redigera butikstransaktioner
description: I det här avsnittet beskrivs hur du skapar en Excel-arbetsbok så att du kan redigera butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b2b6e98db54e7747912aad26f4b8ae24b9ad5a6d
ms.sourcegitcommit: ce51ff2b6099c75dceb99de6dea9d53baf99772d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2020
ms.locfileid: "4459992"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a><span data-ttu-id="5b8c0-103">Skapa en Excel-arbetsbok för att redigera butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="5b8c0-103">Create an Excel workbook to edit retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b8c0-104">I det här avsnittet beskrivs hur du skapar en Excel-arbetsbok så att du kan redigera butikstransaktioner i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-104">This topic describes how to create an Excel workbook so that you can edit retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5b8c0-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="5b8c0-105">Overview</span></span>

<span data-ttu-id="5b8c0-106">Det finns en fördefinierad Excel-mall som kunder kan komma åt från olika delar av systemet och använda för att redigera och granska butikstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-106">There is a predefined Excel template that customers can access from different parts of the system and use to edit and audit retail transactions.</span></span> <span data-ttu-id="5b8c0-107">För detta ändamål går det dock också att skapa en anpassad Excel-arbetsbok.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-107">However, customers can also create a custom Excel workbook for this purpose.</span></span>

## <a name="create-and-configure-an-excel-workbook"></a><span data-ttu-id="5b8c0-108">Skapa och konfigurera en Excel-arbetsbok</span><span class="sxs-lookup"><span data-stu-id="5b8c0-108">Create and configure an Excel workbook</span></span>

<span data-ttu-id="5b8c0-109">Följ de här stegen om du vill skapa och konfigurera en Excel-arbetsbok så att du kan redigera butikstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-109">To create and configure an Excel workbook so that you can edit retail transactions, follow these steps.</span></span>

1. <span data-ttu-id="5b8c0-110">Öppna Excel och skapa en tom arbetsbok.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-110">Open Excel, and create a blank workbook.</span></span>
1. <span data-ttu-id="5b8c0-111">Välj **Mina tillägg** på fliken **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-111">On the **Insert** tab, select **My add-ins**.</span></span>
1. <span data-ttu-id="5b8c0-112">Välj länken **Lägg till serverinformation** i det högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-112">In the right pane, select the **Add server information** link.</span></span>
1. <span data-ttu-id="5b8c0-113">Ange serverns URL och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-113">Enter the server URL, and then select **OK**.</span></span>
1. <span data-ttu-id="5b8c0-114">Om felmeddelandet "Kunde inte hitta några registreringar av applet" visas följer du dessa steg för att lösa problemet:</span><span class="sxs-lookup"><span data-stu-id="5b8c0-114">If you receive a "No applet registrations found" error message, follow these steps to resolve the issue:</span></span>

    1. <span data-ttu-id="5b8c0-115">Gå till **Systemadministration \> Inställningar \> Office-programparametrar** i Commerce.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-115">In Commerce, go to **System administration \> Setup \> Office app parameters**.</span></span>
    1. <span data-ttu-id="5b8c0-116">Välj **Initiera programparametrar** på snabbfliken **Programparametrar**.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-116">On the **App parameters** FastTab, select **Initialize app parameters**.</span></span>
    1. <span data-ttu-id="5b8c0-117">Klicka på **OK** i bekräftelsemeddelandet.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-117">In the confirmation message box, select **OK**.</span></span>
    1. <span data-ttu-id="5b8c0-118">Välj **Initiera registrering av applet** på snabbfliken **Registrerade appletar**.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-118">On the **Registered applets** FastTab, select **Initialize applet registration**.</span></span>
    1. <span data-ttu-id="5b8c0-119">Upprepa de tre föregående stegen efter behov.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-119">Repeat the previous three steps as required.</span></span>

1. <span data-ttu-id="5b8c0-120">Välj **Design** och sedan **Lägg till tabell**.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-120">Select **Design**, and then select **Add table**.</span></span>
1. <span data-ttu-id="5b8c0-121">Välj de enheter som måste läggas till i Excel-arbetsboken för redigering, baserat på de data som ska ändras.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-121">Based on the data that has to be modified, select the entities that must be added to the Excel workbook for editing.</span></span> <span data-ttu-id="5b8c0-122">Använd följande tabell som referens.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-122">Use the following table as a reference.</span></span>

    | <span data-ttu-id="5b8c0-123">Transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="5b8c0-123">Transaction type</span></span> | <span data-ttu-id="5b8c0-124">Datatabeller som ska användas</span><span class="sxs-lookup"><span data-stu-id="5b8c0-124">Data entities to use</span></span> |
    |------------------|----------------------|
    | <span data-ttu-id="5b8c0-125">Hämtköpstransaktioner, Onlineorder, Asynkrona kundorder, Asynkrona kundofferter</span><span class="sxs-lookup"><span data-stu-id="5b8c0-125">Cash and carry transactions, Online orders, Async customer orders, Async customer quotes</span></span> | <span data-ttu-id="5b8c0-126">Transaktion (granskningsbar), Försäljningstransaktion (granskningsbar), Betalningstransaktioner (granskningsbara), Momstransaktioner (granskningsbara), Rabattransaktion (granskningsbar), Avgiftstransaktion (granskningsbar)</span><span class="sxs-lookup"><span data-stu-id="5b8c0-126">Transaction (auditable), Sales transaction (auditable), Payment transactions (auditable), Tax transactions (auditable), Discount transactions (auditable), Charge transactions (auditable)</span></span> |
    | <span data-ttu-id="5b8c0-127">Bankinsättning</span><span class="sxs-lookup"><span data-stu-id="5b8c0-127">Bank drop</span></span> | <span data-ttu-id="5b8c0-128">Transaktion (granskningsbar), Bokförda betalningsmedeltransaktioner (granskningsbara)</span><span class="sxs-lookup"><span data-stu-id="5b8c0-128">Transaction (auditable), Banked tender transactions (auditable)</span></span> |
    | <span data-ttu-id="5b8c0-129">Lämna pengar i kassaskåp</span><span class="sxs-lookup"><span data-stu-id="5b8c0-129">Safe drop</span></span> | <span data-ttu-id="5b8c0-130">Transaktion (granskningsbar), Betalningsmedelstransaktioner (kassaskåp) (granskningsbara)</span><span class="sxs-lookup"><span data-stu-id="5b8c0-130">Transaction (auditable), Safe tender transactions (auditable)</span></span> |
    | <span data-ttu-id="5b8c0-131">Kassaavstämning</span><span class="sxs-lookup"><span data-stu-id="5b8c0-131">Tender declaration</span></span> | <span data-ttu-id="5b8c0-132">Transaktion (granskningsbar), Kassaavstämningstransaktioner (granskningsbara)</span><span class="sxs-lookup"><span data-stu-id="5b8c0-132">Transaction (auditable), Tender declaration transactions (auditable)</span></span> |
    | <span data-ttu-id="5b8c0-133">Intäkt, Utgift</span><span class="sxs-lookup"><span data-stu-id="5b8c0-133">Income, Expense</span></span> | <span data-ttu-id="5b8c0-134">Transaktion (granskningsbar), Intäkts‑utgiftstransaktionen (granskningsbara), Betalningstransaktioner (granskningsbara)</span><span class="sxs-lookup"><span data-stu-id="5b8c0-134">Transaction (auditable), Income/Expense transactions (auditable), Payment transactions (auditable)</span></span> |
    | <span data-ttu-id="5b8c0-135">Deklarera startbelopp, Borttagning av betalningsmedel, Växelpost, Betalningsmedel för växel, Fakturabetalning, Kundinsättning</span><span class="sxs-lookup"><span data-stu-id="5b8c0-135">Declare starting amount, Tender removal, Float entry, Change tender, Invoice payment, Customer deposit</span></span> | <span data-ttu-id="5b8c0-136">Transaktion (granskningsbar), Betalningstransaktioner (granskningsbara)</span><span class="sxs-lookup"><span data-stu-id="5b8c0-136">Transaction (auditable), Payment transactions (auditable)</span></span> |

    > [!NOTE]
    > <span data-ttu-id="5b8c0-137">Det är viktigt att du bara lägger till en datatabell i varje Excel-arbetsbok.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-137">It's important that you add only one data entity to each Excel workbook.</span></span> <span data-ttu-id="5b8c0-138">Dessutom måste alla fält som markerats med en nyckelsymbol läggas till i relevant arbetsbok.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-138">Additionally, all fields that are marked by a key symbol must be added to the relevant workbook.</span></span>

1. <span data-ttu-id="5b8c0-139">När arbetsboken har konfigurerats ska du tillämpa de filter som behövs.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-139">After the workbook is configured, apply the required filters.</span></span> <span data-ttu-id="5b8c0-140">Se till att samma filter används på alla kalkylblad i filen.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-140">Be sure to apply the same filters to all the worksheets in the file.</span></span> <span data-ttu-id="5b8c0-141">Undvik att läsa in för stora datamängder i Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-141">Avoid loading very large amounts of data into the Excel file.</span></span> <span data-ttu-id="5b8c0-142">I annat fall kan prestandan påverkas vilket medför att Excel och systemet kan gå långsamt.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-142">Otherwise, performance might be affected, and Excel and your system might slow down.</span></span> <span data-ttu-id="5b8c0-143">Vi rekommenderar att du alltid använder "Företag" och antingen "Utdragsnummer" eller "Transaktionsnummer" som filter för filen.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-143">We recommend that you always use "Company" and either "Statement Number" or "Transaction Number" as filters for your file.</span></span>
1. <span data-ttu-id="5b8c0-144">När filtren har konfigurerats väljer du **Uppdatera** för att läsa in data.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-144">After the filters are configured, select **Refresh** to load the data.</span></span>
1. <span data-ttu-id="5b8c0-145">Redigera de data som behövs och publicera dem sedan.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-145">Edit the required data, and then publish it.</span></span> <span data-ttu-id="5b8c0-146">Om knappen **Publicera** inte är tillgänglig har vissa nyckelfält antagligen inte lagts till i Excel-arbetsboken.</span><span class="sxs-lookup"><span data-stu-id="5b8c0-146">If the **Publish** button is unavailable, some key fields probably weren't added to the Excel workbook.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b8c0-147">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5b8c0-147">Additional resources</span></span>

[<span data-ttu-id="5b8c0-148">Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering</span><span class="sxs-lookup"><span data-stu-id="5b8c0-148">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="5b8c0-149">Redigera och granska onlineorder- och asynkrona kundordertransaktioner</span><span class="sxs-lookup"><span data-stu-id="5b8c0-149">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="5b8c0-150">Redigera ekonomiska dimensioner för butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="5b8c0-150">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="5b8c0-151">Lägga till fält i en Excel-arbetsbok för att redigera butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="5b8c0-151">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)
