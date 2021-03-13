---
title: Kostnad för underhållsschema
description: I det här avsnittet beskrivs underhållsschemakostnad i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9befa52d27a1a12e7a2d9f2615c2ce8e5f1ebe53
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018006"
---
# <a name="maintenance-schedule-cost"></a><span data-ttu-id="c0ad4-103">Kostnad för underhållsschema</span><span class="sxs-lookup"><span data-stu-id="c0ad4-103">Maintenance schedule cost</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="c0ad4-104">I Tillgångshantering kan du beräkna budgetkostnader för rader i underhållsscheman.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-104">In Asset Management, you can calculate budget costs on maintenance schedule lines.</span></span> <span data-ttu-id="c0ad4-105">Detta är användbart om du vill få en översikt över förväntade kostnader, t.ex. kostnader som rör planerade förebyggande underhållsjobb för nästa år.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-105">This is useful if you want to get an overview of expected costs, for example, costs relating to planned preventive maintenance jobs for the next year.</span></span> <span data-ttu-id="c0ad4-106">Beräkningarna baseras på befintliga underhållsschemarader av typen "Underhållsplaner" och "Underhållsomgångar" och "Underhållsbegäranden".</span><span class="sxs-lookup"><span data-stu-id="c0ad4-106">The calculations are based on existing maintenance schedule lines of type "Maintenance plans" and "Maintenance rounds" and "Maintenance requests".</span></span>

1. <span data-ttu-id="c0ad4-107">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Kostnad för underhållsschema**.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-107">Click **Asset management** > **Inquiries** > **Assets** > **Maintenance schedule cost**.</span></span>

2. <span data-ttu-id="c0ad4-108">I dialogrutan **Kostnad för underhållsschema** kan du välja en **ekonomisk dimensionsuppsättning** om du vill se kostnader grupperade i ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-108">In the **Maintenance schedule cost** dialog, you can select a **Financial dimension set** if you want to see costs grouped in financial dimensions.</span></span>

>[!NOTE]
><span data-ttu-id="c0ad4-109">Ekonomiska dimensionsuppsättningar ställs in i **Redovisning** > **Kontoplan** > **Dimensioner** > **Ekonomiska dimensionsuppsättningar**.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-109">Financial dimension sets are set up in **General ledger** > **Chart of accounts** > **Dimensions** > **Financial dimension sets**.</span></span>

3. <span data-ttu-id="c0ad4-110">Du kan använda fältet **Nivå** för att indikera hur detaljerade underhållsschemaraderna ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-110">You can use the **Level** field to indicate how detailed you want the maintenance schedule lines to be regarding functional locations.</span></span> <span data-ttu-id="c0ad4-111">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsschemarader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="c0ad4-112">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsschemarader på alla de funktionsplatsnivåer som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="c0ad4-113">Om du vill göra beräkningar för vissa tillgångar klickar du på **Filter** på snabbfliken **Poster som ska ingå** och väljer relevanta tillgångar.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-113">If you want to make a calculation for specific assets, click **Filter** on the **Records to include** FastTab, and select the relevant assets.</span></span> <span data-ttu-id="c0ad4-114">Om det behövs kan du även ange ett datum för **Förväntad start** för kostnadsberäkningen eller välja en annan **status** för kostnadsberäkningen</span><span class="sxs-lookup"><span data-stu-id="c0ad4-114">If required, you can also specify an **Expected start** date for the cost calculation or select a different **Status** for the cost calculation</span></span>

5. <span data-ttu-id="c0ad4-115">Klicka på **OK** för att starta kostnadsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-115">Click **OK** to start the cost calculation.</span></span>

6. <span data-ttu-id="c0ad4-116">På fliken **Kostnad för underhållsschema** > i åtgärdsfönstergrupperna **Gruppera efter...** klickar du på relevanta knappar om du vill visa den obligatoriska detaljnivån för kostnadsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-116">On the **Maintenance schedule cost** tab > in the **Group by...** Action Pane groups, click the relevant buttons to show the required detail level of the cost calculation.</span></span> <span data-ttu-id="c0ad4-117">De valda knapparna i åtgärdsfönstergruppen markeras.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-117">The selected Action Pane group buttons are highlighted.</span></span> <span data-ttu-id="c0ad4-118">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-118">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="c0ad4-119">Klicka på knappen **Beräkna kostnad** om du vill göra en ny kostnadsberäkning.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-119">Click the **Calculate cost** button if you want to make a new cost calculation.</span></span>

<span data-ttu-id="c0ad4-120">Bilden nedan visar resultaten av en kostnadsberäkning för underhållsscheman.</span><span class="sxs-lookup"><span data-stu-id="c0ad4-120">The illustration below shows the results of a maintenance schedule cost calculation.</span></span>

![Figur 1](media/17-preventive-maintenance.png)

