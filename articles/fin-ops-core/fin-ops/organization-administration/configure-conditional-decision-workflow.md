---
title: Konfigurera villkorsbeslut i ett arbetsflöde
description: Använd följande procedur om du vill konfigurera egenskaperna för ett villkorsbeslut.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 278773a5ad8be35f9b6dcd1ec0d0a35e32222bb1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180060"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a><span data-ttu-id="dce94-103">Konfigurera villkorsbeslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="dce94-103">Configure conditional decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dce94-104">Använd följande procedur om du vill konfigurera egenskaperna för ett villkorsbeslut.</span><span class="sxs-lookup"><span data-stu-id="dce94-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="dce94-105">Ett villkorligt beslut är en punkt vid vilken ett arbetsflöde delas i två grenar.</span><span class="sxs-lookup"><span data-stu-id="dce94-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="dce94-106">Högerklicka på villkorsbeslutet och klicka sedan på **Properties** i arbetsflödesredigeraren för att öppna formuläret **Properties** om du vill konfigurera ett villkorsbeslut.</span><span class="sxs-lookup"><span data-stu-id="dce94-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="dce94-107">Namnge ett beslut</span><span class="sxs-lookup"><span data-stu-id="dce94-107">Name a decision</span></span>

<span data-ttu-id="dce94-108">Följ dessa steg när du vill ange ett namn för ett villkorsbeslut.</span><span class="sxs-lookup"><span data-stu-id="dce94-108">Follow these steps to enter a name for a conditional decision.</span></span>

1. <span data-ttu-id="dce94-109">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="dce94-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="dce94-110">I fältet **Namn** anger du ett unikt namn för villkorsbeslutet.</span><span class="sxs-lookup"><span data-stu-id="dce94-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="dce94-111"> Ange villkor</span><span class="sxs-lookup"><span data-stu-id="dce94-111">Set conditions</span></span>

<span data-ttu-id="dce94-112">Systemet avgör vilken gren som ska användas genom att utvärdera det skickade dokumentet för att bestämma om det uppfyller specifika villkor.</span><span class="sxs-lookup"><span data-stu-id="dce94-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>

1. <span data-ttu-id="dce94-113">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="dce94-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="dce94-114">Klicka på **Lägg till villkor**.</span><span class="sxs-lookup"><span data-stu-id="dce94-114">Click **Add condition**.</span></span>
3. <span data-ttu-id="dce94-115">Ange ett villkor.</span><span class="sxs-lookup"><span data-stu-id="dce94-115">Enter a condition.</span></span>
4. <span data-ttu-id="dce94-116">Ange ytterligare villkor vid behov.</span><span class="sxs-lookup"><span data-stu-id="dce94-116">Enter additional conditions, if they are required.</span></span>
5. <span data-ttu-id="dce94-117">Slutför följande steg för att bekräfta att de villkor som du har angett har ställts in korrekt:</span><span class="sxs-lookup"><span data-stu-id="dce94-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="dce94-118">Klicka på **Testa** för att öppna formuläret **Testa arbetsflödesvillkor**.</span><span class="sxs-lookup"><span data-stu-id="dce94-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="dce94-119">Markera en post i området **Validera villkor** i formuläret.</span><span class="sxs-lookup"><span data-stu-id="dce94-119">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="dce94-120">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="dce94-120">Click **Test**.</span></span> <span data-ttu-id="dce94-121">Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.</span><span class="sxs-lookup"><span data-stu-id="dce94-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="dce94-122">Klicka på **OK** eller **Avbryt** för att återgå till formuläret **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="dce94-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>
