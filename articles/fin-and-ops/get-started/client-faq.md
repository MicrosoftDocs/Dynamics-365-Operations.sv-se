---
title: Vanliga frågor och svar om Finance and Operations-klienten
description: Det här avsnittet innehåller vanliga frågor och svar om den Microsoft Dynamics 365 for Finance and Operations-klienten.
author: jasongre
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74f85f7a1c390d1f21d0423a794ff16c7250d9fa
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546857"
---
# <a name="finance-and-operations-client-faq"></a><span data-ttu-id="b0d10-103">Vanliga frågor och svar om Finance and Operations-klienten</span><span class="sxs-lookup"><span data-stu-id="b0d10-103">Finance and Operations client FAQ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0d10-104">Det här avsnittet innehåller vanliga frågor och svar om den Microsoft Dynamics 365 for Finance and Operations-klienten.</span><span class="sxs-lookup"><span data-stu-id="b0d10-104">This article provides answers to frequently asked questions about the Microsoft Dynamics 365 for Finance and Operations client.</span></span>

## <a name="why-arent-symbols-loaded-when-i-use-finance-and-operations"></a><span data-ttu-id="b0d10-105">Varför läses inte symboler in när jag använder Finance and Operations?</span><span class="sxs-lookup"><span data-stu-id="b0d10-105">Why aren't symbols loaded when I use Finance and Operations?</span></span>

<span data-ttu-id="b0d10-106">Säkerhetinställningarna i din webbläsare kan hindra symbolerna från att läsas in korrekt.</span><span class="sxs-lookup"><span data-stu-id="b0d10-106">The security settings on your browser might prevent the symbols from being loaded correctly.</span></span> <span data-ttu-id="b0d10-107">Lös problemet genom att pröva följande steg:</span><span class="sxs-lookup"><span data-stu-id="b0d10-107">To resolve this issue, try the following steps:</span></span>

- <span data-ttu-id="b0d10-108">Om du upplever problemet i Internet Explorer, klicka på **Verktyg** och klicka sedan på **Internetalternativ**.</span><span class="sxs-lookup"><span data-stu-id="b0d10-108">If you're experiencing this issue in Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span> <span data-ttu-id="b0d10-109">I dialogrutan Internet-alternativ på fliken **Sekretess** klickar du på **Anpassad nivå**, och kontrollerar att alternativet **Hämtning av teckensnitt** är valt.</span><span class="sxs-lookup"><span data-stu-id="b0d10-109">In the Internet Options dialog box, on the **Privacy** tab, click **Custom level**, and make sure the **Font download** option is selected.</span></span>
- <span data-ttu-id="b0d10-110">I annat fall måste du kanske lägga till Finance and Operations-webbplatsen i listan över betrodda webbplatser.</span><span class="sxs-lookup"><span data-stu-id="b0d10-110">Otherwise, you might have to add the Finance and Operations site to the list of trusted sites.</span></span>

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a><span data-ttu-id="b0d10-111">Jag saknar menyfliken från Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="b0d10-111">I miss the ribbon from Dynamics AX 2012.</span></span> <span data-ttu-id="b0d10-112">Kan jag ha åtgärdsfönstrets flikar öppna hela tiden?</span><span class="sxs-lookup"><span data-stu-id="b0d10-112">Can I keep Action Pane tabs open all the time?</span></span>

<span data-ttu-id="b0d10-113">Vi planerar att implementera den här funktionen snart.</span><span class="sxs-lookup"><span data-stu-id="b0d10-113">We are planning to implement this feature soon.</span></span> <span data-ttu-id="b0d10-114">Användarna kan sedan välja att behålla flikarna i åtgärdfönstren öppna hela tiden.</span><span class="sxs-lookup"><span data-stu-id="b0d10-114">Users will then be able to choose to keep the tabs on Action Panes open all the time.</span></span> <span data-ttu-id="b0d10-115">Annars döljs flikarna när de inte används för att få mer skärmyta för sidan.</span><span class="sxs-lookup"><span data-stu-id="b0d10-115">Otherwise, the tabs will be collapsed when they aren't being used, to gain more screen space for the page.</span></span>

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a><span data-ttu-id="b0d10-116">Varför visas ibland olika snabbmenyer när jag högerklickar?</span><span class="sxs-lookup"><span data-stu-id="b0d10-116">Why do I sometimes see different shortcut menus when I right click?</span></span>

<span data-ttu-id="b0d10-117">Om du högerklickar i ett redigerbart fält (eller när text markeras) visas webbläsarens snabbmenyer.</span><span class="sxs-lookup"><span data-stu-id="b0d10-117">If you right-click in an editable field (or if text is selected), the browser's shortcut menu is displayed.</span></span> <span data-ttu-id="b0d10-118">Menyn ger tillgång till **Klipp ut**, **Kopiera** och **Klistra in**.</span><span class="sxs-lookup"><span data-stu-id="b0d10-118">This menu gives you access to the **Cut**, **Copy**, and **Paste** commands.</span></span> <span data-ttu-id="b0d10-119">Vi kan inte bädda in dessa kommandon i snabbmenyerna i Finance and Operations, detta eftersom webbläsarna av säkerhetsskäl inte tillåter oss att öppna systemurklipp via programmering.</span><span class="sxs-lookup"><span data-stu-id="b0d10-119">We can't embed these commands into the Finance and Operations shortcut menus because, for security reasons, browsers don't allow us to programmatically access the system clipboard.</span></span>

<span data-ttu-id="b0d10-120">Om du högerklickar på en fältetikett eller ett värde i en skrivskyddad kontroll visas snabbmenyn för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b0d10-120">If you right-click a field label or the value of a read-only control, you'll see the Finance and Operations shortcut menu.</span></span>

<span data-ttu-id="b0d10-121">Vi vill göra det enklare att komma åt tangentbordet, så vi planerar att implementera ett tangentbordskortkommando som öppnar snabbmenyn i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b0d10-121">To make keyboard access easier, we plan to implement a keyboard shortcut in the future that will open the Finance and Operations shortcut menu.</span></span>

## <a name="where-is-the-view-details-functionality-in-finance-and-operations"></a><span data-ttu-id="b0d10-122">Var är funktionen Visa information i Finance and Operations?</span><span class="sxs-lookup"><span data-stu-id="b0d10-122">Where is the View details functionality in Finance and Operations?</span></span>

<span data-ttu-id="b0d10-123">Alternativet **Visa information** är tillgängligt på flera sätt:</span><span class="sxs-lookup"><span data-stu-id="b0d10-123">The **View details** option is available in a couple of ways:</span></span>

- <span data-ttu-id="b0d10-124">Om en kontroll har funktionen **Visa information** och dessutom ett värde, kan värdet visas som en hyperlänk.</span><span class="sxs-lookup"><span data-stu-id="b0d10-124">If a control has **View details** capabilities, and if the control has a value, that value is displayed as a hyperlink.</span></span> <span data-ttu-id="b0d10-125">Du kan klicka på hyperlänken när du vill öppna en sida som innehåller mer information.</span><span class="sxs-lookup"><span data-stu-id="b0d10-125">You can click the hyperlink to open a page that contains additional details.</span></span>
- <span data-ttu-id="b0d10-126">**Visa information** är också ett alternativ på snabbmenyerna i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b0d10-126">**View details** is also an option on Finance and Operations shortcut menus.</span></span> <span data-ttu-id="b0d10-127">Mer information om när snabbmenyerna i Finance and Operations visas när du högerklickar finns i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b0d10-127">For more information about when Finance and Operations shortcut menus are displayed when you right-click, see the previous section.</span></span>
