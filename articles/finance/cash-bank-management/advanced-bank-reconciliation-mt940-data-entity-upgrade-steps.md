---
title: Avancerad MT940-import för bankavstämning - uppgradering för sammansatt dataenhet
description: Ett sekvensnummer måste läggas till bankutdragimportenheten för att stödja MT940-formatet.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 91100c3e3c33462e5b19ca239a784cdb720210ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772017"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="84836-103">Avancerad MT940-import för bankavstämning - uppgradering för sammansatt dataenhet</span><span class="sxs-lookup"><span data-stu-id="84836-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84836-104">Ett sekvensnummer måste läggas till bankutdragimportenheten för att stödja MT940-formatet.</span><span class="sxs-lookup"><span data-stu-id="84836-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="84836-105">Använd följande steg när du vill lägga till bankutdragimportenheten för att stödja MT940-formatet.</span><span class="sxs-lookup"><span data-stu-id="84836-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="84836-106">Kompilera och synkronisera följande:</span><span class="sxs-lookup"><span data-stu-id="84836-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="84836-107">Sammansatt enhet\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="84836-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="84836-108">Enhet\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="84836-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="84836-109">Enhet\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="84836-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="84836-110">Enhet\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="84836-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="84836-111">ENhet\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="84836-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="84836-112">Register\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="84836-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="84836-113">Datahantering\\dataprojekt.</span><span class="sxs-lookup"><span data-stu-id="84836-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="84836-114">Läs in MT940-importprojekt</span><span class="sxs-lookup"><span data-stu-id="84836-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="84836-115">Ändra XSLT.</span><span class="sxs-lookup"><span data-stu-id="84836-115">Change XSLT.</span></span>
            -   <span data-ttu-id="84836-116">Klicka på **Visa karta**.</span><span class="sxs-lookup"><span data-stu-id="84836-116">Click **View map**.</span></span>
            -   <span data-ttu-id="84836-117">Klicka på **Visa karta** på bankutdragsdokumentet.</span><span class="sxs-lookup"><span data-stu-id="84836-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="84836-118">Klicka på **Transformeringar**</span><span class="sxs-lookup"><span data-stu-id="84836-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="84836-119">Ta bort filen BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="84836-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="84836-120">Lägg till den nya versionen av BankReconiliation-to-Composite.xsl.</span><span class="sxs-lookup"><span data-stu-id="84836-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="84836-121">Visa layouten **Löpnummer** på **Källdata**.</span><span class="sxs-lookup"><span data-stu-id="84836-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="84836-122">Källdataformat = XML-Element.</span><span class="sxs-lookup"><span data-stu-id="84836-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="84836-123">Enhetsnamn = Bankutdrag.</span><span class="sxs-lookup"><span data-stu-id="84836-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="84836-124">Överföra datafil = ny version SampleBankCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="84836-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="84836-125">Klicka på **Ja** om du vill skriva över den befintliga filen.</span><span class="sxs-lookup"><span data-stu-id="84836-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="84836-126">Klicka på **Ja** om du vill generera en ny mappning.</span><span class="sxs-lookup"><span data-stu-id="84836-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="84836-127">Kontrollera att S**equenceNumber** mappas.</span><span class="sxs-lookup"><span data-stu-id="84836-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="84836-128">Klicka på **Visa karta** på bankutdraget.</span><span class="sxs-lookup"><span data-stu-id="84836-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="84836-129">Kontrollera att **SequenceNumber** mappas från Källa till Mellanlagring.</span><span class="sxs-lookup"><span data-stu-id="84836-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="84836-130">Importera det nya utdraget.</span><span class="sxs-lookup"><span data-stu-id="84836-130">Import the new statement.</span></span>




