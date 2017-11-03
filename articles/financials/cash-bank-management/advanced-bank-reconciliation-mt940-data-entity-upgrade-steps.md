---
title: "Avancerad MT940-import för bankavstämning - uppgradering för sammansatt dataenhet"
description: "Ett sekvensnummer måste läggas till bankutdragimportenheten för att stödja MT940-formatet."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a76558d220e98de85060d23d6e5d8df1c0cd1baf
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="6d84b-103">Avancerad MT940-import för bankavstämning - uppgradering för sammansatt dataenhet</span><span class="sxs-lookup"><span data-stu-id="6d84b-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6d84b-104">Ett sekvensnummer måste läggas till bankutdragimportenheten för att stödja MT940-formatet.</span><span class="sxs-lookup"><span data-stu-id="6d84b-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="6d84b-105">Använd följande steg när du vill lägga till bankutdragimportenheten för att stödja MT940-formatet.</span><span class="sxs-lookup"><span data-stu-id="6d84b-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="6d84b-106">Kompilera och synkronisera följande:</span><span class="sxs-lookup"><span data-stu-id="6d84b-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="6d84b-107">Sammansatt enhet\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="6d84b-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="6d84b-108">Enhet\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="6d84b-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="6d84b-109">Enhet\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="6d84b-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="6d84b-110">Enhet\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="6d84b-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="6d84b-111">ENhet\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="6d84b-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="6d84b-112">Register\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="6d84b-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="6d84b-113">Datahantering\\dataprojekt.</span><span class="sxs-lookup"><span data-stu-id="6d84b-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="6d84b-114">Läs in MT940-importprojekt</span><span class="sxs-lookup"><span data-stu-id="6d84b-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="6d84b-115">Ändra XSLT.</span><span class="sxs-lookup"><span data-stu-id="6d84b-115">Change XSLT.</span></span>
            -   <span data-ttu-id="6d84b-116">Klicka på **Visa karta**.</span><span class="sxs-lookup"><span data-stu-id="6d84b-116">Click **View map**.</span></span>
            -   <span data-ttu-id="6d84b-117">Klicka på **Visa karta** på bankutdragsdokumentet.</span><span class="sxs-lookup"><span data-stu-id="6d84b-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="6d84b-118">Klicka på **Transformeringar**</span><span class="sxs-lookup"><span data-stu-id="6d84b-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="6d84b-119">Ta bort filen BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="6d84b-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="6d84b-120">Lägg till den nya versionen av BankReconiliation-to-Composite.xsl.</span><span class="sxs-lookup"><span data-stu-id="6d84b-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="6d84b-121">Visa layouten **Löpnummer** på **Källdata**.</span><span class="sxs-lookup"><span data-stu-id="6d84b-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="6d84b-122">Källdataformat = XML-Element.</span><span class="sxs-lookup"><span data-stu-id="6d84b-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="6d84b-123">Enhetsnamn = Bankutdrag.</span><span class="sxs-lookup"><span data-stu-id="6d84b-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="6d84b-124">Överföra datafil = ny version SampleBankCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="6d84b-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="6d84b-125">Klicka på **Ja** om du vill skriva över den befintliga filen.</span><span class="sxs-lookup"><span data-stu-id="6d84b-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="6d84b-126">Klicka på **Ja** om du vill generera en ny mappning.</span><span class="sxs-lookup"><span data-stu-id="6d84b-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="6d84b-127">Kontrollera att S**equenceNumber** mappas.</span><span class="sxs-lookup"><span data-stu-id="6d84b-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="6d84b-128">Klicka på **Visa karta** på bankutdraget.</span><span class="sxs-lookup"><span data-stu-id="6d84b-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="6d84b-129">Kontrollera att **SequenceNumber** mappas från Källa till Mellanlagring.</span><span class="sxs-lookup"><span data-stu-id="6d84b-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="6d84b-130">Importera det nya utdraget.</span><span class="sxs-lookup"><span data-stu-id="6d84b-130">Import the new statement.</span></span>





