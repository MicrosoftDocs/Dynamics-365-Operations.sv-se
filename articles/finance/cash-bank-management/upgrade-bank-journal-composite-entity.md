---
title: Uppdatera den sammansatta enheten för bankjournal
description: Följande steg behövs för att lägga till det ytterligare BankTransactionType-fältet till den sammansatta enheten för bankjournal (BankJournalEntity).
author: ShylaThompson
manager: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ec196600a54a2aed4565cf422dc386d6646ff524
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447872"
---
# <a name="update-the-bank-journal-composite-entity"></a><span data-ttu-id="b83c7-103">Uppdatera den sammansatta enheten för bankjournal</span><span class="sxs-lookup"><span data-stu-id="b83c7-103">Update the bank journal composite entity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b83c7-104">Följande steg behövs för att lägga till det ytterligare BankTransactionType-fältet till den sammansatta enheten för bankjournal (BankJournalEntity).</span><span class="sxs-lookup"><span data-stu-id="b83c7-104">The following steps are needed in order to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

<span data-ttu-id="b83c7-105">Gör på följande sätt när du vill lägga till det ytterligare BankTransactionType-fältet till den sammansatta enheten för bankjournal (BankJournalEntity).</span><span class="sxs-lookup"><span data-stu-id="b83c7-105">Use the following steps to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

1.  <span data-ttu-id="b83c7-106">Kompilera och synkronisera följande sammansatta enheter, enheter och mellanlagringsregister:</span><span class="sxs-lookup"><span data-stu-id="b83c7-106">Compile and synchronize the following bank journal composite entities, entities, and staging tables:</span></span>
    -   <span data-ttu-id="b83c7-107">Sammansatt enhet\\BankJournalEntity</span><span class="sxs-lookup"><span data-stu-id="b83c7-107">Composite Entity\\BankJournalEntity</span></span>
    -   <span data-ttu-id="b83c7-108">Enhet\\BankJournalHeaderEntity</span><span class="sxs-lookup"><span data-stu-id="b83c7-108">Entity\\BankJournalHeaderEntity</span></span>
    -   <span data-ttu-id="b83c7-109">Enhet\\BankJournalLineEntity</span><span class="sxs-lookup"><span data-stu-id="b83c7-109">Entity\\BankJournalLineEntity</span></span>
    -   <span data-ttu-id="b83c7-110">Tabell\\BankJournalHeaderStaging</span><span class="sxs-lookup"><span data-stu-id="b83c7-110">Table\\BankJournalHeaderStaging</span></span>
    -   <span data-ttu-id="b83c7-111">Tabell\\BankJournalLineStaging</span><span class="sxs-lookup"><span data-stu-id="b83c7-111">Table\\BankJournalLineStaging</span></span>

2.  <span data-ttu-id="b83c7-112">Datahantering\\dataprojekt</span><span class="sxs-lookup"><span data-stu-id="b83c7-112">Data management\\data projects</span></span>
    -   <span data-ttu-id="b83c7-113">Exponera typen **Banktransaktion** i layouten **Källdata**.</span><span class="sxs-lookup"><span data-stu-id="b83c7-113">Expose the **Bank Transaction** type on **Source Data** layout.</span></span>
        -   <span data-ttu-id="b83c7-114">Källdataformat = XML-Element</span><span class="sxs-lookup"><span data-stu-id="b83c7-114">Source data format = XML-Element</span></span>
        -   <span data-ttu-id="b83c7-115">Enhetsnamn = Bank Journal</span><span class="sxs-lookup"><span data-stu-id="b83c7-115">Entity name = Bank Journal</span></span>
        -   <span data-ttu-id="b83c7-116">Överföra datafil = den nya versionen SampleBankJournalCompositeEntity.xml</span><span class="sxs-lookup"><span data-stu-id="b83c7-116">Upload data file = new version SampleBankJournalCompositeEntity.xml</span></span>
        -   <span data-ttu-id="b83c7-117">Klicka på **Ja** om du vill skriva över den befintliga filen.</span><span class="sxs-lookup"><span data-stu-id="b83c7-117">Click **Yes** to overwrite the existing file.</span></span>
        -   <span data-ttu-id="b83c7-118">Klicka på **Ja** för att generera mappning från grunden.</span><span class="sxs-lookup"><span data-stu-id="b83c7-118">Click **Yes** to generate mapping from scratch.</span></span>
        -   <span data-ttu-id="b83c7-119">Kontrollera att typen Banktransaktion har mappats.</span><span class="sxs-lookup"><span data-stu-id="b83c7-119">Verify that the Bank Transaction Type is mapped.</span></span>
            -   <span data-ttu-id="b83c7-120">Klicka på **Visa karta** på enheten Line.</span><span class="sxs-lookup"><span data-stu-id="b83c7-120">Click **View map** on Line entity.</span></span>
            -   <span data-ttu-id="b83c7-121">Kontrollera att banktransaktionstypen mappas från källa (Source) till mellanlagring (Staging).</span><span class="sxs-lookup"><span data-stu-id="b83c7-121">Verify that Bank Transaction type is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="b83c7-122">Importera det nya utdraget.</span><span class="sxs-lookup"><span data-stu-id="b83c7-122">Import the new statement.</span></span>




