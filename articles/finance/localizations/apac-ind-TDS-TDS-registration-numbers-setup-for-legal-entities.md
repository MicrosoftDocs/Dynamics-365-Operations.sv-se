---
title: Ställ in TDS-registreringsnummer för juridiska personer
description: I det här avsnittet beskrivs hur du ställer in registreringsnummer för juridiska personer för funktionen Skatteavdrag vid källa (TDS).
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
ms.openlocfilehash: 3550b2b7b305702ffc337ba0a9bb79f60a9de120
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023595"
---
# <a name="set-up-tds-registration-numbers-for-legal-entities"></a><span data-ttu-id="542fa-103">Ställ in TDS-registreringsnummer för juridiska personer</span><span class="sxs-lookup"><span data-stu-id="542fa-103">Set up TDS registration numbers for legal entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="542fa-104">I det här avsnittet beskrivs hur du ställer in registreringsnummer för juridiska personer för funktionen Skatteavdrag vid källa (TDS).</span><span class="sxs-lookup"><span data-stu-id="542fa-104">This topic explains how to set up Tax Deducted at Source (TDS) registration numbers for legal entities.</span></span>

1. <span data-ttu-id="542fa-105">Gå till **Organisationsadministration \> Organisationer \> Juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="542fa-105">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>

    <span data-ttu-id="542fa-106">[![Sidan Juridiska personer](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span><span class="sxs-lookup"><span data-stu-id="542fa-106">[![Legal entities page](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span></span>

2. <span data-ttu-id="542fa-107">Under snabbfliken **Skatteinformation**, fältet **Permanent kontonummer**, anger du det permanenta kontonumret (PAN) för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="542fa-107">On the **Tax information** FastTab, in the **Permanent account number** field, enter the permanent account number (PAN) of the legal entity.</span></span>
3. <span data-ttu-id="542fa-108">I fältet **Cirkelnummer** anger du cirkelnumret för TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="542fa-108">In the **Circle number** field, enter the circle number of the TDS authority.</span></span>
4. <span data-ttu-id="542fa-109">I fältet **Avdelningsnummer** anger du avdelningsnumret för TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="542fa-109">In the **Ward number** field, enter the ward number of the TDS authority.</span></span>
5. <span data-ttu-id="542fa-110">I fältet **Bedömningsansvarig** anger du informationen för bedömningsansvarig inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="542fa-110">In the **Assessing officer** field, enter the details of the assessing officer for the TDS authority.</span></span>
6. <span data-ttu-id="542fa-111">I fältet **Typ av avdrag** anger du typen av avdragskategori för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="542fa-111">In the **Type of deductor** field, select the deductor type category for the legal entity.</span></span>
7. <span data-ttu-id="542fa-112">I åtgärdsfönstret väljer du **Registrerings-ID** för att öppna sidan **Hantera adresser**.</span><span class="sxs-lookup"><span data-stu-id="542fa-112">On the Action Pane, select **Registration IDs** to open the **Manage addresses** page.</span></span>
8. <span data-ttu-id="542fa-113">Under snabbfliken **Skatteinformation** väljer du **Lägg till** eller **Redigera** för att öppna sidan **Hantera skatteinformation**, där du kan bibehålla skatteregistreringsposten.</span><span class="sxs-lookup"><span data-stu-id="542fa-113">On the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>

    <span data-ttu-id="542fa-114">[![Sidan Hantera adresser](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span><span class="sxs-lookup"><span data-stu-id="542fa-114">[![Manage addresses page](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span></span>

9. <span data-ttu-id="542fa-115">Under snabbfliken **Källskatt**, i fältet **Skattekontonummer (TAN)**, anger du registreringsnumret.</span><span class="sxs-lookup"><span data-stu-id="542fa-115">On the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the registration number.</span></span> <span data-ttu-id="542fa-116">Detta nummer måste bestå av fyra alfabetiska tecken, därefter fem numeriska tecken och därefter ett alfabetiskt tecken.</span><span class="sxs-lookup"><span data-stu-id="542fa-116">This number must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="542fa-117">Här är ett exempel: **AXDF87645F**.</span><span class="sxs-lookup"><span data-stu-id="542fa-117">Here is an example: **AXDF87645F**.</span></span>
10. <span data-ttu-id="542fa-118">I fältet **Namn eller beskrivning** anger du en beskrivning av registreringsnumret för källskatt.</span><span class="sxs-lookup"><span data-stu-id="542fa-118">In the **Name or description** field, enter a description of the withholding tax registration number.</span></span>

    <span data-ttu-id="542fa-119">[![Sidan Hantera skatteinformation](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span><span class="sxs-lookup"><span data-stu-id="542fa-119">[![Manage tax information page](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span></span>

11. <span data-ttu-id="542fa-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="542fa-120">Close the page.</span></span>
