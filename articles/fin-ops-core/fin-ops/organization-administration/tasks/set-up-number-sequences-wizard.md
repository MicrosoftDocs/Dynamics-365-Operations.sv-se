---
title: Ställa in nummerserier med hjälp av en guide
description: I det här avsnittet förklaras hur du ställer in alla nödvändiga nummerserier samtidigt, med hjälp av en guide.
author: sericks007
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d91a619423d00509ceca2ae18cb2f0371b44ead1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747307"
---
# <a name="set-up-number-sequences-using-a-wizard"></a><span data-ttu-id="31a5f-103">Ställa in nummerserier med hjälp av en guide</span><span class="sxs-lookup"><span data-stu-id="31a5f-103">Set up number sequences using a wizard</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="31a5f-104">Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem.</span><span class="sxs-lookup"><span data-stu-id="31a5f-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="31a5f-105">En huvuddata eller en transaktionpost som kräver en identifierare, kallas för en referens.</span><span class="sxs-lookup"><span data-stu-id="31a5f-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="31a5f-106">Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen.</span><span class="sxs-lookup"><span data-stu-id="31a5f-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="31a5f-107">I det här avsnittet förklaras hur du ställer in alla nödvändiga nummerserier samtidigt, med hjälp av en guide.</span><span class="sxs-lookup"><span data-stu-id="31a5f-107">This topic explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="31a5f-108">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="31a5f-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="31a5f-109">Gå till **Navigering > Moduler > Organisationsadministration > Nummerserier > Nummerserier**.</span><span class="sxs-lookup"><span data-stu-id="31a5f-109">Go to **Navigation > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="31a5f-110">Välj **Generera**.</span><span class="sxs-lookup"><span data-stu-id="31a5f-110">Select **Generate**.</span></span>
3. <span data-ttu-id="31a5f-111">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="31a5f-111">Select **Next**.</span></span>

   - <span data-ttu-id="31a5f-112">På den här sidan kan du ändra identifieringskoden, det lägsta värdet och det högsta värdet.</span><span class="sxs-lookup"><span data-stu-id="31a5f-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="31a5f-113">Dessutom kan du ange om nummerserien måste vara löpande.</span><span class="sxs-lookup"><span data-stu-id="31a5f-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
   - <span data-ttu-id="31a5f-114">Välj inte alternativet **Kontinuerlig** om du måste förallokera nummer för nummerserien.</span><span class="sxs-lookup"><span data-stu-id="31a5f-114">Do not select the **Continuous** option if you must preallocate numbers for the number sequence.</span></span> <span data-ttu-id="31a5f-115">Om du vill lägga till ett omfångsegment till formatet för en nummerserie väljer du formatet i listan och väljer **Inkludera område i format**.</span><span class="sxs-lookup"><span data-stu-id="31a5f-115">To add a scope segment to the format of a number sequence, select the format in the list, and then select **Include scope in format**.</span></span> <span data-ttu-id="31a5f-116">Om du vill ta bort ett omfångsegment från formatet för en nummerserie väljer du formatet i listan och väljer **Ta bort område från format**.</span><span class="sxs-lookup"><span data-stu-id="31a5f-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then select **Remove scope from format**.</span></span> <span data-ttu-id="31a5f-117">Om du vill utesluta en nummerserie i den automatiska genereringen väljer du nummerserien i listan och väljer **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="31a5f-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then select **Delete**.</span></span>  

4. <span data-ttu-id="31a5f-118">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="31a5f-118">Select **Next**.</span></span>
5. <span data-ttu-id="31a5f-119">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="31a5f-119">Select **Finish**.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]