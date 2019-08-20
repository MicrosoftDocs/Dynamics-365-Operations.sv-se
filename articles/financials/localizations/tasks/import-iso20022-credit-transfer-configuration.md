---
title: Importera konfiguration av ISO20022-kreditöverföring
description: Denna procedur visar hur du importerar en elektronisk rapporteringkonfiguration för leverantörsbetalning.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee7e69611d31d2577ebafdfc059b0936aef0520b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848801"
---
# <a name="import-iso20022-credit-transfer-configuration"></a><span data-ttu-id="01ef5-103">Importera konfiguration av ISO20022-kreditöverföring</span><span class="sxs-lookup"><span data-stu-id="01ef5-103">Import ISO20022 credit transfer configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="01ef5-104">Denna procedur visar hur du importerar en elektronisk rapporteringkonfiguration för leverantörsbetalning.</span><span class="sxs-lookup"><span data-stu-id="01ef5-104">This procedure shows how to import a vendor payment electronic reporting configuration.</span></span> <span data-ttu-id="01ef5-105">Det tyska ISO 20022-formatet för kreditöverföring används som exempel.</span><span class="sxs-lookup"><span data-stu-id="01ef5-105">The German ISO 20022 credit transfer format is used as an example.</span></span> <span data-ttu-id="01ef5-106">Denna procedur kan användas för andra tillgängliga, elektroniska rapporteringsformat.</span><span class="sxs-lookup"><span data-stu-id="01ef5-106">This procedure can be used for other available electronic reporting format.</span></span> 

<span data-ttu-id="01ef5-107">Denna uppgift skapades med hjälp av demonstrationdataföretaget DEMF, men du kan använda valfritt demonstrationsdataföretag för att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="01ef5-107">This task was created using the demo data company DEMF but you can use any demo data company to complete this task.</span></span>

<span data-ttu-id="01ef5-108">Detta är den första av fem uppgifter som tillsammans illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="01ef5-108">This is the first of five tasks, that together illustrate the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="01ef5-109">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="01ef5-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="01ef5-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="01ef5-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="01ef5-111">I listan över tillgängliga konfigurationsleverantörer väljer du Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01ef5-111">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="01ef5-112">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="01ef5-112">Click Set active.</span></span>
4. <span data-ttu-id="01ef5-113">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="01ef5-113">Click Repositories.</span></span>
5. <span data-ttu-id="01ef5-114">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="01ef5-114">Click Open.</span></span>
6. <span data-ttu-id="01ef5-115">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="01ef5-115">Click Show filters.</span></span>
7. <span data-ttu-id="01ef5-116">Använd följande filter: I fältet ”Configuration name” anger du filtervärdet "ISO20022 Credit transfer (DE)" med hjälp av filteroperatorn ”begins with”.</span><span class="sxs-lookup"><span data-stu-id="01ef5-116">Apply the following filters: Enter a filter value of "ISO20022 Credit transfer (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="01ef5-117">Du kan också söka efter konfigurationen i listan, markera den och sedan flytta den till importuppgiften.</span><span class="sxs-lookup"><span data-stu-id="01ef5-117">Alternatively, you can find the configuration in the list, select it, and then move it to the Import task.</span></span>  
8. <span data-ttu-id="01ef5-118">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="01ef5-118">Click Import.</span></span>
    * <span data-ttu-id="01ef5-119">Om importknappen inte är tillgänglig innebär det att konfigureringen redan har importerats.</span><span class="sxs-lookup"><span data-stu-id="01ef5-119">If the Import button is not available, it means that the configuration has  already been imported.</span></span>  
9. <span data-ttu-id="01ef5-120">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="01ef5-120">Click Yes.</span></span>

