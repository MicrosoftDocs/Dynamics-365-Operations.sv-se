---
title: Ställ in källskattemyndigheter för TDS-skattetypen
description: I det här avsnittet beskrivs hur du konfigurerar myndigheter för skatteavdrag vid källan (TDS).
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
ms.openlocfilehash: 5375363a9b1383a83e80fc3c4b841780adab4172
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023590"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a><span data-ttu-id="5a524-103">Ställ in källskattemyndigheter för TDS-skattetypen</span><span class="sxs-lookup"><span data-stu-id="5a524-103">Set up withholding tax authorities for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5a524-104">I det här avsnittet beskrivs hur du konfigurerar myndigheter för skatteavdrag vid källan (TDS).</span><span class="sxs-lookup"><span data-stu-id="5a524-104">This topic explains how to set up Tax Deducted at Source (TDS) authorities.</span></span>

1. <span data-ttu-id="5a524-105">Gå till **Skatt \> Indirekt skatt \> Källskattemyndigheter**.</span><span class="sxs-lookup"><span data-stu-id="5a524-105">Go to **Tax \> Indirect taxes \> Withholding tax authorities**.</span></span>

    <span data-ttu-id="5a524-106">[![Sidan Källskattemyndigheter](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span><span class="sxs-lookup"><span data-stu-id="5a524-106">[![Withholding tax authorities page](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span></span>

2. <span data-ttu-id="5a524-107">I fältet **Skattetyp** väljer du **TDS** för att konfigurera källskattemyndigheter för skattetypen TDS.</span><span class="sxs-lookup"><span data-stu-id="5a524-107">In the **Tax type** field, select **TDS** to set up withholding tax authorities for the TDS tax type.</span></span>
3. <span data-ttu-id="5a524-108">I åtgärdsfönstret, välj **Ny** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="5a524-108">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="5a524-109">I fältet **Källskattemyndigheter** anger du ett namn på TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="5a524-109">In the **Withholding tax authority** field, enter a name for the TDS authority.</span></span>
5. <span data-ttu-id="5a524-110">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="5a524-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="5a524-111">Under snabbfliken **Allmänt**, i fältet **Leverantörskonto**, väljer du leverantörskontot för TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="5a524-111">On the **General** FastTab, in the **Vendor account** field, select the vendor account for the TDS authority.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a524-112">Du måste ange namnet på den bank där skulder till TDS-myndighetens leverantör ska sättas in.</span><span class="sxs-lookup"><span data-stu-id="5a524-112">You must define the name of the bank where funds that are owed to the TDS authority vendor will be deposited.</span></span> <span data-ttu-id="5a524-113">Bankens namn definieras på sidan **Bankkonton** (**Leverantörsreskontra \> Alla leverantörer \> Leverantör \> Konfigurera \> Bankkonton**).</span><span class="sxs-lookup"><span data-stu-id="5a524-113">The bank's name is defined on the **Bank accounts** page (**Accounts payable \> All vendors \> Vendor \> Set up \> Bank accounts**).</span></span>

7. <span data-ttu-id="5a524-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5a524-114">Close the page.</span></span>
