---
title: Instrumentpanel för användningshantering
description: I det här ämnet beskrivs hur du använder instrumentpanelen för användningshantering för att övervaka användningen av den elektroniska faktureringstjänsten och fortsatt efterleva standarder.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130516"
---
# <a name="usage-management-dashboard"></a><span data-ttu-id="c9887-103">Instrumentpanel för användningshantering</span><span class="sxs-lookup"><span data-stu-id="c9887-103">Usage management dashboard</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9887-104">Med hjälp av instrumentpanelen för **användarhantering** kan du övervaka användningen av den elektroniska faktureringstjänsten och på så sätt hjälpa organisationen att fortsatt efterleva standarder i fråga om dess månatliga användning.</span><span class="sxs-lookup"><span data-stu-id="c9887-104">The **Usage management** dashboard helps you monitor usage of the Electronic Invoicing service, and therefore helps your organization remain compliant in terms of its monthly usage.</span></span> <span data-ttu-id="c9887-105">Efterlevnaden avgörs genom att beräkna insändningsvolymen och jämföra denna med den anskaffade insändningsvolymen i syfte att identifiera eventuella avvikelser mellan den anskaffade volymen och den använda volymen.</span><span class="sxs-lookup"><span data-stu-id="c9887-105">Compliance is determined by calculating the submission volume and comparing it with the acquired volume of submissions to identify any deviations between the acquired volume and the used volume.</span></span>

<span data-ttu-id="c9887-106">Instrumentpanelen innehåller följande indikatorer:</span><span class="sxs-lookup"><span data-stu-id="c9887-106">The dashboard includes the following indicators:</span></span>

- <span data-ttu-id="c9887-107">En kostnadsindikator som du kan använda för att övervaka förbrukning i licensefterlevnadssyfte:</span><span class="sxs-lookup"><span data-stu-id="c9887-107">One cost indicator that you can use to monitor consumption for licensing compliance purposes:</span></span>

    - <span data-ttu-id="c9887-108">Användning per månad (export)</span><span class="sxs-lookup"><span data-stu-id="c9887-108">Usage per month (export)</span></span>

- <span data-ttu-id="c9887-109">Tre driftindikatorer som du kan använda för att spåra användningen av den elektroniska faktureringstjänsten i hanteringssyfte:</span><span class="sxs-lookup"><span data-stu-id="c9887-109">Three operational indicators that you can use to track usage of the Electronic Invoicing service for management purposes:</span></span>

    - <span data-ttu-id="c9887-110">Användning per funktion</span><span class="sxs-lookup"><span data-stu-id="c9887-110">Usage by feature</span></span>
    - <span data-ttu-id="c9887-111">Användning per miljö</span><span class="sxs-lookup"><span data-stu-id="c9887-111">Usage by environment</span></span>
    - <span data-ttu-id="c9887-112">Användning per månad (import)</span><span class="sxs-lookup"><span data-stu-id="c9887-112">Usage per month (import)</span></span>

## <a name="measurement-scope"></a><span data-ttu-id="c9887-113">Måttomfång</span><span class="sxs-lookup"><span data-stu-id="c9887-113">Measurement scope</span></span>

- <span data-ttu-id="c9887-114">Måttenhet:</span><span class="sxs-lookup"><span data-stu-id="c9887-114">Unit of measure:</span></span> 

    <span data-ttu-id="c9887-115">Instrumentpanelen för **användarhantering** räknar sändningen av affärsdokument och importerade elektroniska fakturor.</span><span class="sxs-lookup"><span data-stu-id="c9887-115">The **Usage management** dashboard counts the submission of business documents and imported electronic invoices.</span></span>

- <span data-ttu-id="c9887-116">Organisation:</span><span class="sxs-lookup"><span data-stu-id="c9887-116">Organization:</span></span> 

    <span data-ttu-id="c9887-117">Inventeringen sammanfattas efter organisationens klientorganisations-ID, oavsett antalet instanser av Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management eller det antal juridiska personer där tjänsten för elektronisk fakturering har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="c9887-117">Counting is summarized by the tenant ID of your organization, regardless of the number of instances of Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management, or the number of legal entities where the Electronic Invoicing service is enabled.</span></span>


## <a name="indicator-usage-per-month-export"></a><span data-ttu-id="c9887-118">Indikator: Användning per månad (export)</span><span class="sxs-lookup"><span data-stu-id="c9887-118">Indicator: Usage per month (export)</span></span>

<span data-ttu-id="c9887-119">Denna indikator ger information om de elektroniska fakturor som din organisation utfärdar under en angiven period.</span><span class="sxs-lookup"><span data-stu-id="c9887-119">This indicator provides details about the electronic invoices that your organization issues during a defined period.</span></span>

### <a name="scope"></a><span data-ttu-id="c9887-120">Omfattning</span><span class="sxs-lookup"><span data-stu-id="c9887-120">Scope</span></span>
- <span data-ttu-id="c9887-121">Antalet affärsdokument som skickas från Finance och Supply Chain Management till den elektroniska faktureringstjänsten, oavsett antalet rader som dessa affärsdokument innehåller.</span><span class="sxs-lookup"><span data-stu-id="c9887-121">The number of business documents that are submitted from Finance and Supply Chain Management to the Electronic Invoicing service, regardless of number of lines that those business documents contain.</span></span>
- <span data-ttu-id="c9887-122">Antalet skickade affärsdokument som har bearbetats av den elektroniska faktureringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="c9887-122">The number of submitted business documents that are successfully processed by the Electronic Invoicing service.</span></span> <span data-ttu-id="c9887-123">Ett dokument betraktas som färdigbearbetat när det åtgärdsflöde som har definierats i funktionsinställningarna har slutförts.</span><span class="sxs-lookup"><span data-stu-id="c9887-123">A document is considered successfully processed when the flow of actions that are defined in the feature setup is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="c9887-124">När en elektronisk faktura skickas till en extern webbtjänst är inventeringen oberoende av resultatet av webbtjänstbearbetningen (godkänd, avvisad eller schemavalideringsfel).</span><span class="sxs-lookup"><span data-stu-id="c9887-124">When an electronic invoice is submitted to an external web service, counting is independent of the results of web service processing (accepted, rejected, or schema validation error).</span></span> <span data-ttu-id="c9887-125">Om webbtjänsten har tagits emot och svarat på en begäran från den elektroniska faktureringstjänsten betraktas sändningen som en giltig inventering.</span><span class="sxs-lookup"><span data-stu-id="c9887-125">If the web service received and responded to the request from the Electronic Invoicing service, the submission is considered a valid counting.</span></span>

- <span data-ttu-id="c9887-126">**Undantag:** Affärsdokument räknas inte om de skickas om från Finance och Supply Chain Management till den elektroniska faktureringstjänsten, t. ex. i de scenarier där en ny sändning av samma affärsdokument krävs för att ändra statusen för den elektroniska fakturan.</span><span class="sxs-lookup"><span data-stu-id="c9887-126">**Exception:** Business documents aren't counted if they are resubmitted from Finance and Supply Chain Management to the Electronic Invoicing service, such as in the scenarios where a resubmission of the same business document is required to change the status of the electronic invoice.</span></span> <span data-ttu-id="c9887-127">Till exempel räknas utfärdandet av en elektronisk brasiliansk faktura (skattedokument) som giltigt, men annulleringsförfrågan för den räknas inte.</span><span class="sxs-lookup"><span data-stu-id="c9887-127">For example, issuance of a Brazilian electronic invoice (fiscal document) is counted as valid, but the cancellation request for it isn't counted.</span></span>


### <a name="calculation"></a><span data-ttu-id="c9887-128">Beräkning</span><span class="sxs-lookup"><span data-stu-id="c9887-128">Calculation</span></span>

<span data-ttu-id="c9887-129">Beräkningen av saldot beräknas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="c9887-129">The calculation of the balance is calculated as follows:</span></span>

<span data-ttu-id="c9887-130">Saldo = Kostnadsfri + Inköpt – Används</span><span class="sxs-lookup"><span data-stu-id="c9887-130">Balance = Free + Purchased – Used</span></span>

<span data-ttu-id="c9887-131">Där:</span><span class="sxs-lookup"><span data-stu-id="c9887-131">Where:</span></span>

- <span data-ttu-id="c9887-132">Kostnadsfritt:</span><span class="sxs-lookup"><span data-stu-id="c9887-132">Free:</span></span>
  
    <span data-ttu-id="c9887-133">Ett kostnadsfritt antal affärsdokument som kunden kan skicka per månad.</span><span class="sxs-lookup"><span data-stu-id="c9887-133">A free volume of business documents the customer can submit per month.</span></span> <span data-ttu-id="c9887-134">Detta omfattar ett paket om 100 affärsdokument som kan skickas till den elektroniska faktureringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="c9887-134">It includes a package of 100 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="c9887-135">Den kostnadsfria volymen ackumuleras inte, och eventuella återstående saldon flyttas inte över till nästa period.</span><span class="sxs-lookup"><span data-stu-id="c9887-135">Free volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="c9887-136">Inköpt:</span><span class="sxs-lookup"><span data-stu-id="c9887-136">Purchased:</span></span>
  
    <span data-ttu-id="c9887-137">Ett paket om 1 000 affärsdokument som kan skickas till den elektroniska faktureringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="c9887-137">A package of 1,000 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="c9887-138">Detta paket måste förvärvas för din organisation en gång i månaden.</span><span class="sxs-lookup"><span data-stu-id="c9887-138">This package must be acquired for your organization on a monthly basis.</span></span> <span data-ttu-id="c9887-139">Inköpt volym ackumuleras inte, och eventuella återstående saldon flyttas inte över till nästa period.</span><span class="sxs-lookup"><span data-stu-id="c9887-139">Purchased volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="c9887-140">Används:</span><span class="sxs-lookup"><span data-stu-id="c9887-140">Used:</span></span> 

    <span data-ttu-id="c9887-141">Antalet affärsdokument som skickas till den elektroniska faktureringstjänsten enligt definierade kriterier.</span><span class="sxs-lookup"><span data-stu-id="c9887-141">The count of business document submissions to the Electronic Invoicing service according to defined criteria.</span></span>
   
> [!IMPORTANT]
> <span data-ttu-id="c9887-142">Om din organisation tänker överskrida månadsvolymen på 100 gratisutskick ska du köpa in toppvolymen så att du förblir kompatibel med Microsofts licenspolicy för den elektroniska faktureringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="c9887-142">If your organization plans to exceed the monthly volume of 100 free submissions, purchase the peak volume to ensure that you remain compliant with the Microsoft licensing policy for the Electronic Invoicing service.</span></span>
>
> <span data-ttu-id="c9887-143">För närvarande måste inköpt volym anges manuellt, enligt anskaffningsdatum, som flera paket med 1 000 sändningar.</span><span class="sxs-lookup"><span data-stu-id="c9887-143">Currently, purchased volume must be manually entered, according to the date of acquisition, as multiple packages of 1,000 submissions.</span></span>

## <a name="indicator-usage-by-feature"></a><span data-ttu-id="c9887-144">Indikator: Användning efter funktion</span><span class="sxs-lookup"><span data-stu-id="c9887-144">Indicator: Usage by feature</span></span>

<span data-ttu-id="c9887-145">Denna indikator visar användningen av elektroniska faktureringsfunktioner för utfärdande av elektroniska fakturor under en angiven period.</span><span class="sxs-lookup"><span data-stu-id="c9887-145">This indicator shows the usage of electronic invoicing features for issuance of electronic invoices during a defined period.</span></span>

- <span data-ttu-id="c9887-146">Beräkning:</span><span class="sxs-lookup"><span data-stu-id="c9887-146">Calculation:</span></span>
  
    <span data-ttu-id="c9887-147">Använd = Räkningen av hur många gånger som respektive elektronisk faktureringsfunktion har använts under överföringen av affärsdokument till den elektroniska faktureringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="c9887-147">Used = The count of how many times each electronic invoicing feature was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-by-environment"></a><span data-ttu-id="c9887-148">Indikator: Användning efter miljö</span><span class="sxs-lookup"><span data-stu-id="c9887-148">Indicator: Usage by environment</span></span>

<span data-ttu-id="c9887-149">Denna indikator visar användningen av miljöer för elektroniska faktureringstjänster under en angiven period.</span><span class="sxs-lookup"><span data-stu-id="c9887-149">This indicator shows the usage of electronic invoicing service environments during a defined period.</span></span>

- <span data-ttu-id="c9887-150">Beräkning:</span><span class="sxs-lookup"><span data-stu-id="c9887-150">Calculation:</span></span>
    
    <span data-ttu-id="c9887-151">Använd = Räkningen av hur många gånger som respektive miljö för elektronisk faktureringstjänst har använts under överföringen av affärsdokument till den elektroniska faktureringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="c9887-151">Used = The count of how many times each electronic invoicing service environment was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-per-month-import"></a><span data-ttu-id="c9887-152">Indikator: Användning per månad (import)</span><span class="sxs-lookup"><span data-stu-id="c9887-152">Indicator: Usage per month (import)</span></span>

<span data-ttu-id="c9887-153">Denna indikator visar importvolymen för elektroniska fakturor för tjänsten för elektronisk fakturering till Finance och Supply Chain Mangement under en angiven period.</span><span class="sxs-lookup"><span data-stu-id="c9887-153">This indicator shows the volume of importation of electronic invoices by Electronic Invoicing service into Finance and Supply Chain Management during a defined period.</span></span>

- <span data-ttu-id="c9887-154">Omfång:</span><span class="sxs-lookup"><span data-stu-id="c9887-154">Scope:</span></span>

    <span data-ttu-id="c9887-155">Elektroniska fakturor som importeras till Finance och Supply Chain Management, oavsett hur många rader de elektroniska fakturorna innehåller.</span><span class="sxs-lookup"><span data-stu-id="c9887-155">Electronic invoices that are imported into Finance and Supply Chain Management, regardless of the number of lines that those electronic invoices contain.</span></span>

- <span data-ttu-id="c9887-156">Beräkning:</span><span class="sxs-lookup"><span data-stu-id="c9887-156">Calculation:</span></span>

    <span data-ttu-id="c9887-157">Mottaget = Antalet importerade elektroniska fakturor till Finance och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c9887-157">Received = The count of imported electronic invoices into Finance and Supply Chain Management.</span></span>

## <a name="functions"></a><span data-ttu-id="c9887-158">Funktioner</span><span class="sxs-lookup"><span data-stu-id="c9887-158">Functions</span></span>
### <a name="purchase"></a><span data-ttu-id="c9887-159">Inköp</span><span class="sxs-lookup"><span data-stu-id="c9887-159">Purchase</span></span>

<span data-ttu-id="c9887-160">På fliken **Användning per månad (export)** väljer du **Inköp** om du vill registrera antalet anskaffade inskick manuellt.</span><span class="sxs-lookup"><span data-stu-id="c9887-160">On the **Usage per month (export)** tab, select **Purchase** to manually register the amount of acquired submissions.</span></span>

<span data-ttu-id="c9887-161">För ett visst datum väljer du **Ny** och anger antalet **Paket** som förvärvats på det datumet.</span><span class="sxs-lookup"><span data-stu-id="c9887-161">For a given date, select **New** and enter the number of **Packages** acquired for on that date.</span></span>

<span data-ttu-id="c9887-162">**Kvantiteten** beräknas som:</span><span class="sxs-lookup"><span data-stu-id="c9887-162">The **Quantity** is calculated as:</span></span>

<span data-ttu-id="c9887-163">Kvantitet = Paket \* 1 000</span><span class="sxs-lookup"><span data-stu-id="c9887-163">Quantity = Packages \* 1.000</span></span>

<span data-ttu-id="c9887-164">Den beräknade **Kvantiteten** visas i **Inköpt** från indikatorn **Användning per månad (export)**.</span><span class="sxs-lookup"><span data-stu-id="c9887-164">The calculated **Quantity** reflects in the **Purchased** from the indicator **Usage per month (export)**.</span></span>

### <a name="update"></a><span data-ttu-id="c9887-165">Uppdatera</span><span class="sxs-lookup"><span data-stu-id="c9887-165">Update</span></span>

<span data-ttu-id="c9887-166">I åtgärdsfönstret väljer du **Uppdatera** för att uppdatera beräkningen och uppdatera de data som anges på sidan och i tabellen.</span><span class="sxs-lookup"><span data-stu-id="c9887-166">On the Action Pane, select **Update** to refresh the calculation and update the data shown on the page and in the chart.</span></span>

### <a name="reset-history-data"></a><span data-ttu-id="c9887-167">Återställ historikdata</span><span class="sxs-lookup"><span data-stu-id="c9887-167">Reset history data</span></span>

<span data-ttu-id="c9887-168">I åtgärdsfönstret väljer du **Återställ historikdata** för att uppdatera databasen där indikatorerna beräknas.</span><span class="sxs-lookup"><span data-stu-id="c9887-168">On the Action Pane, select **Reset history data** to refresh the database from where the indicators are calculated.</span></span>




> [!NOTE]
> <span data-ttu-id="c9887-169">Instrumentpanelen **Användarhantering** visar inga monetära belopp.</span><span class="sxs-lookup"><span data-stu-id="c9887-169">The **Usage management** dashboard doesn't show monetary amounts.</span></span> <span data-ttu-id="c9887-170">Istället visas bara volymen för räknade inskick och importerade dokument.</span><span class="sxs-lookup"><span data-stu-id="c9887-170">Instead, it shows only the volume of counted submissions and imported documents.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
