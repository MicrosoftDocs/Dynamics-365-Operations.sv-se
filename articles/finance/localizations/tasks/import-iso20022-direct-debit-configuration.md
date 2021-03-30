---
title: Importera konfiguration för ISO20022-autogiro
description: Denna procedur demonstrerar hur du importerar en elektronisk rapporteringkonfiguration för kundbetalning.
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
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 964f396625340d593a2fe3dd5be5a1b7da795e9a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218768"
---
# <a name="import-iso20022-direct-debit-configuration"></a><span data-ttu-id="2abb6-103">Importera konfiguration för ISO20022-autogiro</span><span class="sxs-lookup"><span data-stu-id="2abb6-103">Import ISO20022 direct debit configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2abb6-104">Denna procedur demonstrerar hur du importerar en elektronisk rapporteringkonfiguration för kundbetalning.</span><span class="sxs-lookup"><span data-stu-id="2abb6-104">This procedure demonstrates how to import a customer payment electronic reporting configuration.</span></span> <span data-ttu-id="2abb6-105">I den här proceduren används formatet ISO 20022 för autogiro som exempel.</span><span class="sxs-lookup"><span data-stu-id="2abb6-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> 



<span data-ttu-id="2abb6-106">Denna procedur skapades med hjälp av demonstrationdataföretaget DEMF, men du kan använda valfritt demonstrationsdataföretag för detta syfte.</span><span class="sxs-lookup"><span data-stu-id="2abb6-106">This procedure was created using the demo data company DEMF but you can use any demo data company for this purpose.</span></span>



<span data-ttu-id="2abb6-107">Detta är den första av fem procedurer av fem som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="2abb6-107">This is the first of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="2abb6-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="2abb6-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="2abb6-109">I listan över tillgängliga konfigurationsleverantörer väljer du Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2abb6-109">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="2abb6-110">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="2abb6-110">Click Set active.</span></span>
4. <span data-ttu-id="2abb6-111">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="2abb6-111">Click Repositories.</span></span>
5. <span data-ttu-id="2abb6-112">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="2abb6-112">Click Open.</span></span>
6. <span data-ttu-id="2abb6-113">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="2abb6-113">Click Show filters.</span></span>
7. <span data-ttu-id="2abb6-114">Använd följande filter: I fältet ”Configuration name” anger du filtervärdet "ISO20022 Direct debit (DE)" med hjälp av filteroperatorn ”begins with”.</span><span class="sxs-lookup"><span data-stu-id="2abb6-114">Apply the following filters: Enter a filter value of "ISO20022 Direct debit (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="2abb6-115">Du kan också hitta konfigurationen i listan, välja den och hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="2abb6-115">Optionally, you can find the configuration in the list, select it, and skip this step.</span></span>  
8. <span data-ttu-id="2abb6-116">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="2abb6-116">Click Import.</span></span>
    * <span data-ttu-id="2abb6-117">Om importknappen inte är tillgänglig innebär det att konfigureringen redan har importerats.</span><span class="sxs-lookup"><span data-stu-id="2abb6-117">If the Import button is not available, it means that the configuration has been imported already.</span></span>  
9. <span data-ttu-id="2abb6-118">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="2abb6-118">Click Yes.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]