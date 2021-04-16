---
title: Skapa en postmall för att förenkla datainmatning
description: Det här avsnittet visar hur du skapar en postmall så att fältvärden som ofta används inte uttryckligen behöver anges för varje ny post.
author: margoc
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f6a2eec8d730cb4c63c854433cf6160c475ce660
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753974"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="1b2aa-103">Skapa en postmall för att förenkla datainmatning</span><span class="sxs-lookup"><span data-stu-id="1b2aa-103">Create a record template to facilitate data entry</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1b2aa-104">Det här avsnittet visar hur du skapar en postmall så att fältvärden som ofta används inte uttryckligen behöver anges för varje ny post.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-104">This topic demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="1b2aa-105">I den här proceduren ska du skapa en ny post för nya bärbara datorer som ska läggas till bland anläggningstillgångarna.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-105">In this procedure, you'll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="1b2aa-106">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="1b2aa-107">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Anläggningstillgångar > Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="1b2aa-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-108">Select **New**.</span></span>
3. <span data-ttu-id="1b2aa-109">Ange eller välj ett värde i fältet **Anläggningstillgångsgrupp.**</span><span class="sxs-lookup"><span data-stu-id="1b2aa-109">In the **Fixed asset group** field, enter or select a value.</span></span>
4. <span data-ttu-id="1b2aa-110">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-110">In the **Name** field, type a value.</span></span> <span data-ttu-id="1b2aa-111">Ange till exempel **Bärbar dator för företags-lead**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-111">For example, enter **Corporate lead laptop**.</span></span>  
5. <span data-ttu-id="1b2aa-112">Ange ett värde i fältet **Söknamn**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-112">In the **Search name** field, type a value.</span></span> <span data-ttu-id="1b2aa-113">Ange till exempel **bärbar dator**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-113">For example, enter **laptop**.</span></span>  
6. <span data-ttu-id="1b2aa-114">Expandera avsnittet **Teknisk information**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-114">Expand the **Technical information** section.</span></span>
7. <span data-ttu-id="1b2aa-115">Ange värden i fälten **Fabrikat**, **Modell** och **Modellår**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-115">In the **Make**, **Model**, and **Model year** fields, type values.</span></span>
8. <span data-ttu-id="1b2aa-116">Välj **Alternativ** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-116">On the Action Pane, select **Options**.</span></span>
9. <span data-ttu-id="1b2aa-117">Välj **Postinfo**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-117">Select **Record info**.</span></span>
10. <span data-ttu-id="1b2aa-118">Välj **Användarmall**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-118">Select **User template**.</span></span>
11. <span data-ttu-id="1b2aa-119">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-119">In the **Name** field, type a value.</span></span>
12. <span data-ttu-id="1b2aa-120">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-120">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="1b2aa-121">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-121">Select **OK**.</span></span>
14. <span data-ttu-id="1b2aa-122">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="1b2aa-122">Select **Close**.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]