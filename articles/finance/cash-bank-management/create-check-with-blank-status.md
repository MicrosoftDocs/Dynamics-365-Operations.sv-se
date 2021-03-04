---
title: Skapa checkar med statusvärdet Tom
description: I det här avsnittet beskrivs hur du skapar en tom check för ett bankkonto på sidan Checkar.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: aa1c4c33b977c0173da98aee409389b9242980fb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976471"
---
# <a name="create-checks-that-have-blank-status"></a><span data-ttu-id="d2fe9-103">Skapa checkar med statusvärdet Tom</span><span class="sxs-lookup"><span data-stu-id="d2fe9-103">Create checks that have Blank status</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2fe9-104">I det här avsnittet beskrivs hur du skapar tomma checkar.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-104">This topic explains how to create blank checks.</span></span> <span data-ttu-id="d2fe9-105">Du kan till exempel skapa en tom check om du vill registrera en check som har skadats och inte kan användas för betalning.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-105">For example, you might create a blank check to record a check that has been damaged and can't be used for payment.</span></span>

<span data-ttu-id="d2fe9-106">Du utför underhåll för checkar på sidan **Checkar**.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-106">On the **Checks** page, you perform maintenance tasks for checks.</span></span> <span data-ttu-id="d2fe9-107">Du kan till exempel skapa nya checknummer och ta bort checkar.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-107">For example, you can create new check numbers and delete checks.</span></span> <span data-ttu-id="d2fe9-108">Du kan också skapa checkar som har statusvärdet **Tom**.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-108">You can also create checks that have a status of **Blank**.</span></span> <span data-ttu-id="d2fe9-109">När du har skapat tomma checkar kan de inte tas bort eller återanvändas i systemet.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-109">After blank checks are created, they can't be deleted or reused in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="d2fe9-110">Den här funktionen är bara tillgänglig på sidan **Checkar** om du aktiverar funktionen **Skapa checkar med tom status på sidan Checkar** på sidan **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-110">This feature is available on the **Checks** page only if you turn on the **Create checks with a blank status on the Checks page** feature on the **Feature management** page.</span></span> <span data-ttu-id="d2fe9-111">Om funktionen inte är aktiverad kan du bara skapa checkar med statusvärdet **Tom** från dialogrutan **Betalning med check** under betalningsgenereringen i Leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-111">If the feature isn't turned on, checks that have **Blank** status can be created only from the **Payment by check** dialog box during the payment generation process in Accounts payable.</span></span>

<span data-ttu-id="d2fe9-112">Du öppnar sidan **Checkar** genom att gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton** och sedan välja **Checkar** på fliken **Hantera betalningar** i gruppen **Relaterad information** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-112">To open the **Checks** page, go to **Cash and bank management \> Bank accounts \> Bank accounts**, and then, on the Action Pane, on the **Manage payments** tab, in the **Related information** group, select **Checks**.</span></span> <span data-ttu-id="d2fe9-113">Du kan också gå till **Kassa- och bankhantering \> Förfrågningar och rapporter \> Checkar**.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-113">Alternatively, go to **Cash and bank management \> Inquiries and reports \> Checks**.</span></span>

<span data-ttu-id="d2fe9-114">Du skapar sedan checkar med statusvärdet **Tom** genom att välja **Skapa tomma checkar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-114">Then, to create checks that have **Blank** status, on the Action Pane, select **Create blank checks**.</span></span> <span data-ttu-id="d2fe9-115">Medan de tomma checkarna skapas inaktiveras det associerade bankkontot tillfälligt.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-115">While the system is creating blank checks, the associated bank account is temporarily inactivated.</span></span> <span data-ttu-id="d2fe9-116">På grund av detta minskar risken för att betalningar genereras samtidigt som tomma checkar skapas.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-116">This behavior reduces the risk that payments will be generated at the same time that blank checks are created.</span></span> <span data-ttu-id="d2fe9-117">När processen är klar återaktiveras det associerade bankkontot.</span><span class="sxs-lookup"><span data-stu-id="d2fe9-117">When the processing is completed, the associated bank account is reactivated.</span></span>
