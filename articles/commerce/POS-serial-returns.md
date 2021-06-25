---
title: Returserienummerkontrollerade produkter i kassan
description: I detta ämne beskrivs möjligheterna att validera serialiserade artiklar som en del av returprocessen i Microsoft Dynamics 365 Commerce-kassaprogrammet (POS).
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7a067994828f3df577c0dc4146d26ac81990d4ac
ms.sourcegitcommit: 927574c77f4883d906e5c7bddf0af9b717e492bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129831"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a><span data-ttu-id="542ee-103">Returserienummerkontrollerade produkter i kassan</span><span class="sxs-lookup"><span data-stu-id="542ee-103">Return serial number–controlled products in POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="542ee-104">I detta ämne beskrivs möjligheterna att validera serialiserade artiklar som en del av returprocessen i Microsoft Dynamics 365 Commerce-kassaprogrammet (POS).</span><span class="sxs-lookup"><span data-stu-id="542ee-104">This topic describes the capabilities for validating serialized items as part of the return process in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

> [!NOTE]
> <span data-ttu-id="542ee-105">I Commerce-versionen 10.0.20 och senare finns en ny funktion kallad **Enhetlig returbearbetningserfarenhet i kassan**.</span><span class="sxs-lookup"><span data-stu-id="542ee-105">In the Commerce version 10.0.20 release and later, a new feature that is named **Unified return processing experience in POS** is available.</span></span> <span data-ttu-id="542ee-106">Om du vill använda serienummervalidering under returorderbearbetning i POS måste du aktivera funktionen.</span><span class="sxs-lookup"><span data-stu-id="542ee-106">To use serial number validation during return order processing in POS, you must turn on this feature.</span></span> <span data-ttu-id="542ee-107">Mer information om andra funktioner som den här funktionen tillhandahåller när den aktiveras finns i [Skapa returer i kassan](POS-returns.md).</span><span class="sxs-lookup"><span data-stu-id="542ee-107">For information about others capabilities that this feature provides when it's turned on, see [Create returns in POS)](POS-returns.md).</span></span>
>
> <span data-ttu-id="542ee-108">När funktionen har aktiverats kan den inte stängas av.</span><span class="sxs-lookup"><span data-stu-id="542ee-108">After the feature is turned on, it can't be turned off.</span></span>

## <a name="options-for-validating-serialized-returns"></a><span data-ttu-id="542ee-109">Alternativ för validering av serialiserade returer</span><span class="sxs-lookup"><span data-stu-id="542ee-109">Options for validating serialized returns</span></span>

<span data-ttu-id="542ee-110">När funktionen **Bearbetningsupplevelse för enhetliga returer i kassan** är aktiverad kan organisationer validerar returer av serienummerkontrolelrade artiklar via kassan.</span><span class="sxs-lookup"><span data-stu-id="542ee-110">When the **Unified return processing experience in POS** feature is turned on, organizations can perform a validation on returns of serial number–controlled items through POS.</span></span> <span data-ttu-id="542ee-111">Denna funktion kan varna användare om serienumret som returneras skiljer sig från det ursprungliga serienummer som såldes.</span><span class="sxs-lookup"><span data-stu-id="542ee-111">This capability can warn users if the serial number that is being returned differs from the original serial number that was sold.</span></span> <span data-ttu-id="542ee-112">I Commerce version 10.0.20 och senare är meddelandet som användarna får endast ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="542ee-112">In the Commerce version 10.0.20 release and later, the message that users receive is only a warning message.</span></span> <span data-ttu-id="542ee-113">Användarna kan fortsätta att bearbeta en retur mot ett serienummer som skiljer sig från serienumret som ursprungligen såldes.</span><span class="sxs-lookup"><span data-stu-id="542ee-113">Users can continue to process a return against a serial number that differs from the serial number that was originally sold.</span></span>

<span data-ttu-id="542ee-114">Om du vill konfigurera serienummervalidering för en organisation efter det att funktionen **Upplevelsen för enhetlig returbearbetning i kassan** har aktiverats går du till **Butik och handel \> Administrationsinställning \> Parametrar \> Commerce-parametrar** i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="542ee-114">To configure serial number validation for an organization after the **Unified return processing experience in POS** feature is turned on, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters** in Commerce headquarters.</span></span> <span data-ttu-id="542ee-115">På fliken **Lager**, på snabbfliken **Lagra lageråtgärder** anger du alternativet **Aktivera validering av serienummer för kassareturer** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="542ee-115">On the **Inventory** tab, on the **Store inventory operations** FastTab, set the **Enable validation of serial numbers on POS returns** option to **Yes**.</span></span>

## <a name="process-returns-for-serialized-items-in-pos"></a><span data-ttu-id="542ee-116">Bearbeta returer för serialiserade artiklar i kassan</span><span class="sxs-lookup"><span data-stu-id="542ee-116">Process returns for serialized items in POS</span></span>

<span data-ttu-id="542ee-117">Om alternativet **Aktivera validering av serienummer för kassareturer** har angetts som **Ja** kan användaren ange returens serienummer i informationsfönstret på sidan **Returnerbara produkter** när en serienummerkontrollerad artikel returneras via kassan.</span><span class="sxs-lookup"><span data-stu-id="542ee-117">If the **Enable validation of serial numbers on POS returns** option has been set to **Yes**, when a serial number–controlled item is returned through POS, the user can enter the serial number for the return line in the details pane on the **Returnable products** page.</span></span> <span data-ttu-id="542ee-118">Om det angivna serienumret inte matchar det ursprungliga serienummer som såldes för försäljningstransaktionen får användaren ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="542ee-118">If the serial number that is entered doesn't match the original serial number that was sold for the sales transaction, the user receives a warning message.</span></span> <span data-ttu-id="542ee-119">Programmet hindrar emellertid inte användaren från att fortsätta bokföra returen.</span><span class="sxs-lookup"><span data-stu-id="542ee-119">However, the application doesn't prevent the user from continuing to post the return.</span></span>

> [!NOTE]
> <span data-ttu-id="542ee-120">Kassa (POS) stöder för närvarande endast validering av serienummer på returrader där den ursprungliga beställda kvantiteten inte är större än ett.</span><span class="sxs-lookup"><span data-stu-id="542ee-120">Currently, POS supports validation of serial numbers only on return lines where the original ordered quantity is no more than one.</span></span> <span data-ttu-id="542ee-121">Om den ursprungliga försäljningsorderraden skapades i en icke-kassa-kanal, och om kvantiteten som beställts för den serialiserade artikeln på en given försäljningsrad är mer än ett, kan artikeln inte returneras korrekt via kassan.</span><span class="sxs-lookup"><span data-stu-id="542ee-121">If the original sales order line was created in a non-POS channel, and if the quantity that was ordered for the serialized item on a given sales line is more than one, the item can't be correctly returned through POS.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="542ee-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="542ee-122">Additional resources</span></span>

[<span data-ttu-id="542ee-123">Skapa returer i kassan</span><span class="sxs-lookup"><span data-stu-id="542ee-123">Create returns in POS</span></span>](POS-returns.md)
