---
title: Periodiska kredithanteringsuppgifter
description: I det här avsnittet beskrivs de periodiska uppgifter som är en nödvändig del i processen för hantering av kreditgränser för kunder.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: b41b87cd3e2e80b87318c5c771d45a4d0e5d4b85
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971713"
---
# <a name="periodic-credit-management-tasks"></a><span data-ttu-id="d8587-103">Periodiska kredithanteringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="d8587-103">Periodic credit management tasks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8587-104">I det här avsnittet beskrivs de periodiska uppgifter som är en nödvändig del i processen för hantering av kreditgränser för kunder.</span><span class="sxs-lookup"><span data-stu-id="d8587-104">This topic describes the periodic tasks that are a necessary part of the process of managing credit limits for customers.</span></span>

## <a name="update-risk-scores"></a><span data-ttu-id="d8587-105">Uppdatera riskpoäng</span><span class="sxs-lookup"><span data-stu-id="d8587-105">Update risk scores</span></span>

<span data-ttu-id="d8587-106">Eftersom företag utvecklas och omständigheterna ändras, kan kreditriskerna för en viss kund också ändras.</span><span class="sxs-lookup"><span data-stu-id="d8587-106">As businesses evolve and circumstances change, the credit risks for a given customer can also change.</span></span> <span data-ttu-id="d8587-107">För att upprätthålla lämpliga kreditgränser för kunderna måste du regelbundet granska kriterierna för varje riskpoäng och uppdatera poängen för varje kund.</span><span class="sxs-lookup"><span data-stu-id="d8587-107">To help maintain appropriate credit limits for your customers, you must periodically review the criteria for each risk score and update the scores for each customer.</span></span> <span data-ttu-id="d8587-108">Du kan uppdatera följande resultat med hjälp av sidan **uppdatera riskresultat** (**kredit och inkasso \> periodiska uppgifter \> kredithantering \> uppdatera riskresultat**).</span><span class="sxs-lookup"><span data-stu-id="d8587-108">You can update the following scores by using the **Update risk scores** page (**Credit and collections \> Periodic tasks \> Credit management \> Update risk scores**).</span></span> <span data-ttu-id="d8587-109">Alla användardefinierade beräkningar bearbetas också.</span><span class="sxs-lookup"><span data-stu-id="d8587-109">All user-defined calculations are also processed.</span></span>

- <span data-ttu-id="d8587-110">**Genomsnittligt betalningsdagar** – denna poäng är det genomsnittliga antalet dagar som en kund tar på sig att betala fakturor.</span><span class="sxs-lookup"><span data-stu-id="d8587-110">**Average payment days** – This score is the average number of days that a customer takes to pay invoices.</span></span>
- <span data-ttu-id="d8587-111">**Kund sedan** – detta är antalet år som kunden har varit kund i din organisation.</span><span class="sxs-lookup"><span data-stu-id="d8587-111">**Customer since** – This score is the number of years that a customer has been a customer of your organization.</span></span>
- <span data-ttu-id="d8587-112">**I företaget sedan** – detta är antalet år som kunden har varit i rörelse.</span><span class="sxs-lookup"><span data-stu-id="d8587-112">**In business since** – This score is the number of years that a customer has been in business.</span></span> <span data-ttu-id="d8587-113">Den använder värdet på fältet **Affärsstart** på sidan **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="d8587-113">It uses the value of the **Business start** field on the **Customers** page.</span></span>
- <span data-ttu-id="d8587-114">**Antal dagar som kan vara utestående** – det här resultatet baseras på kundens saldo i kundreskontra, försäljningsintäkter och antal dagar för föregående tolv månaders period.</span><span class="sxs-lookup"><span data-stu-id="d8587-114">**Days sales outstanding** – This score is based on the accounts receivable balance, sales revenue, and number of days for the previous 12-month period.</span></span>
- <span data-ttu-id="d8587-115">**Genomsnittligt saldo** – det här resultatet baseras på den föregående tolv månaders periodens saldo i kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="d8587-115">**Average balance** – This score is based on the accounts receivable balance for the previous 12-month period.</span></span>
- <span data-ttu-id="d8587-116">**Kredithanteringsgrupp**, **Kontostatus** och **Land** – dessa resultat använder information från kunden.</span><span class="sxs-lookup"><span data-stu-id="d8587-116">**Credit management group**, **Account status**, and **Country** – These scores use information from the customer.</span></span>

## <a name="update-customer-balance-statistics"></a><span data-ttu-id="d8587-117">Uppdatera kundsaldostatistik</span><span class="sxs-lookup"><span data-stu-id="d8587-117">Update customer balance statistics</span></span>

<span data-ttu-id="d8587-118">Du kan köra processen **Uppdatera statistik för kundsaldo** för att uppdatera beräkningen av saldostatistik som visas på sidan **Fråga om saldostatistik**.</span><span class="sxs-lookup"><span data-stu-id="d8587-118">You can run the **Update customer balance statistics** process to update the calculation of balance statistics that is shown on the **Balance statistics inquiry** page.</span></span> <span data-ttu-id="d8587-119">Den här informationen används för att beräkna riskresultat och värden som visas i faktarutorna för kreditstatistik på sidan **kund**.</span><span class="sxs-lookup"><span data-stu-id="d8587-119">This information is used to calculate risk scores and the values that are shown in the credit statistics FactBoxes on the **Customer** page.</span></span>

<span data-ttu-id="d8587-120">När du kör processen uppdaterar den kundsaldo för en enskild kund.</span><span class="sxs-lookup"><span data-stu-id="d8587-120">When you run the process, it updates customer balance statistics for a single customer.</span></span> <span data-ttu-id="d8587-121">Om du vill ställa in ett batchjobb som kör processen för flera kunder kan du använda sidan **Beräkna saldostatistik** (**Kredithantering \> periodiska uppgifter \> beräkna saldostatistik**).</span><span class="sxs-lookup"><span data-stu-id="d8587-121">To set up a batch job to run the process for multiple customers, you can use the **Calculate balance statistics** page (**Credit management \> Periodic tasks \> Calculate balance statistics**).</span></span>
