---
title: Ställa in TDS-redovisningskonton
description: I det här avsnittet beskrivs hur du ställer in redovisningskonton för funktionen Skatteavdrag vid källa (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 93d4cb54488ec0eeee40ca56f3e46f30012f54f5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023597"
---
# <a name="set-up-tds-ledger-accounts"></a><span data-ttu-id="cc99e-103">Ställa in TDS-redovisningskonton</span><span class="sxs-lookup"><span data-stu-id="cc99e-103">Set up TDS ledger accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc99e-104">I det här avsnittet beskrivs hur du ställer in redovisningskonton för funktionen Skatteavdrag vid källa (TDS).</span><span class="sxs-lookup"><span data-stu-id="cc99e-104">This topic explains how to set up ledger accounts for the Tax Deducted at Source (TDS) feature.</span></span> <span data-ttu-id="cc99e-105">Du använder sidan **Kontoplan** för att ställa in redovisningskonton för TDS.</span><span class="sxs-lookup"><span data-stu-id="cc99e-105">You use the **Chart of accounts** page to set up ledger accounts for TDS.</span></span>

1. <span data-ttu-id="cc99e-106">Gå till **Redovisning \> Kontoplan \> Konton \> Huvudkonton**.</span><span class="sxs-lookup"><span data-stu-id="cc99e-106">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**.</span></span>
2. <span data-ttu-id="cc99e-107">Under fliken **Översikt** väljer du **Alt+N** för att skapa ett TDS-redovisningskonto och anger den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="cc99e-107">On the **Overview** tab, select **Alt+N** to create a TDS ledger account, and enter the required details.</span></span>
3. <span data-ttu-id="cc99e-108">Under fliken **Konfiguration**, i fältet **Bokföringstyp**, väljer du **Källskatt**.</span><span class="sxs-lookup"><span data-stu-id="cc99e-108">On the **Setup** tab, in the **Posting type** field, select **Withholding tax**.</span></span>     

    > [!NOTE]
    > <span data-ttu-id="cc99e-109">Redovisningskonton med bokföringstypen **Källskatt** kan endast definieras som kundreskontrakonton som används för att bokföra TDS-fordransbeloppet för en TDS-skattekod.</span><span class="sxs-lookup"><span data-stu-id="cc99e-109">Ledger accounts that have a posting type of **Withholding tax** can be defined only as receivable accounts that are used to post the TDS receivable amount for a TDS tax code.</span></span>

4. <span data-ttu-id="cc99e-110">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="cc99e-110">Close the page.</span></span>
