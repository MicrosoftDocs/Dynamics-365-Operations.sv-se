---
title: Frågor och svar för klient
description: Det här avsnittet innehåller vanliga frågor och svar om den Finance and Operations-klienten.
author: jasongre
manager: AnnBe
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a7d311bfcd65e23e4062f105435d05cb1ceda6b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567050"
---
# <a name="client-faq"></a><span data-ttu-id="be50e-103">Frågor och svar för klient</span><span class="sxs-lookup"><span data-stu-id="be50e-103">Client FAQ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="be50e-104">Det här avsnittet innehåller vanliga frågor och svar om den Finance and Operations-klienten.</span><span class="sxs-lookup"><span data-stu-id="be50e-104">This article provides answers to frequently asked questions about the Finance and Operations client.</span></span>

## <a name="why-arent-symbols-loaded"></a><span data-ttu-id="be50e-105">Varför läses inte symboler in?</span><span class="sxs-lookup"><span data-stu-id="be50e-105">Why aren't symbols loaded?</span></span>

<span data-ttu-id="be50e-106">Säkerhetinställningarna i din webbläsare kan hindra symbolerna från att läsas in korrekt.</span><span class="sxs-lookup"><span data-stu-id="be50e-106">The security settings on your browser might prevent the symbols from being loaded correctly.</span></span> <span data-ttu-id="be50e-107">Lös problemet genom att pröva följande steg:</span><span class="sxs-lookup"><span data-stu-id="be50e-107">To resolve this issue, try the following steps:</span></span>

- <span data-ttu-id="be50e-108">Om du upplever problemet i Internet Explorer, klicka på **Verktyg** och klicka sedan på **Internetalternativ**.</span><span class="sxs-lookup"><span data-stu-id="be50e-108">If you're experiencing this issue in Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span> <span data-ttu-id="be50e-109">I dialogrutan Internet-alternativ på fliken **Sekretess** klickar du på **Anpassad nivå**, och kontrollerar att alternativet **Hämtning av teckensnitt** är valt.</span><span class="sxs-lookup"><span data-stu-id="be50e-109">In the Internet Options dialog box, on the **Privacy** tab, click **Custom level**, and make sure the **Font download** option is selected.</span></span>
- <span data-ttu-id="be50e-110">I annat fall måste du kanske lägga till appwebbplatsen i listan över betrodda webbplatser.</span><span class="sxs-lookup"><span data-stu-id="be50e-110">Otherwise, you might have to add the app site to the list of trusted sites.</span></span>

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a><span data-ttu-id="be50e-111">Jag saknar menyfliken från Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="be50e-111">I miss the ribbon from Dynamics AX 2012.</span></span> <span data-ttu-id="be50e-112">Kan jag ha åtgärdsfönstrets flikar öppna hela tiden?</span><span class="sxs-lookup"><span data-stu-id="be50e-112">Can I keep Action Pane tabs open all the time?</span></span>

<span data-ttu-id="be50e-113">Vi planerar att implementera den här funktionen snart.</span><span class="sxs-lookup"><span data-stu-id="be50e-113">We are planning to implement this feature soon.</span></span> <span data-ttu-id="be50e-114">Användarna kan sedan välja att behålla flikarna i åtgärdfönstren öppna hela tiden.</span><span class="sxs-lookup"><span data-stu-id="be50e-114">Users will then be able to choose to keep the tabs on Action Panes open all the time.</span></span> <span data-ttu-id="be50e-115">Annars döljs flikarna när de inte används för att få mer skärmyta för sidan.</span><span class="sxs-lookup"><span data-stu-id="be50e-115">Otherwise, the tabs will be collapsed when they aren't being used, to gain more screen space for the page.</span></span>

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a><span data-ttu-id="be50e-116">Varför visas ibland olika snabbmenyer när jag högerklickar?</span><span class="sxs-lookup"><span data-stu-id="be50e-116">Why do I sometimes see different shortcut menus when I right click?</span></span>

<span data-ttu-id="be50e-117">Om du högerklickar i ett redigerbart fält (eller när text markeras) visas webbläsarens snabbmenyer.</span><span class="sxs-lookup"><span data-stu-id="be50e-117">If you right-click in an editable field (or if text is selected), the browser's shortcut menu is displayed.</span></span> <span data-ttu-id="be50e-118">Menyn ger tillgång till **Klipp ut**, **Kopiera** och **Klistra in**.</span><span class="sxs-lookup"><span data-stu-id="be50e-118">This menu gives you access to the **Cut**, **Copy**, and **Paste** commands.</span></span> <span data-ttu-id="be50e-119">Du kan inte bädda in dessa kommandon i snabbmenyerna eftersom webbläsarna av säkerhetsskäl inte tillåter oss att öppna systemurklipp via programmering.</span><span class="sxs-lookup"><span data-stu-id="be50e-119">We can't embed these commands into the shortcut menus because, for security reasons, browsers don't allow us to programmatically access the system clipboard.</span></span>

<span data-ttu-id="be50e-120">Om du högerklickar på en fältetikett eller värdet i en skrivskyddad kontroll visas snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="be50e-120">If you right-click a field label or the value of a read-only control, you'll see the shortcut menu.</span></span>

<span data-ttu-id="be50e-121">Vi vill göra det enklare att komma åt tangentbordet, så vi planerar att implementera ett tangentbordskortkommando som öppnar snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="be50e-121">To make keyboard access easier, we plan to implement a keyboard shortcut in the future that will open the shortcut menu.</span></span>

## <a name="where-is-the-view-details-functionality"></a><span data-ttu-id="be50e-122">Var är funktionen Visa information?</span><span class="sxs-lookup"><span data-stu-id="be50e-122">Where is the View details functionality?</span></span>

<span data-ttu-id="be50e-123">Alternativet **Visa information** är tillgängligt på flera sätt:</span><span class="sxs-lookup"><span data-stu-id="be50e-123">The **View details** option is available in a couple of ways:</span></span>

- <span data-ttu-id="be50e-124">Om en kontroll har funktionen **Visa information** och dessutom ett värde, kan värdet visas som en hyperlänk.</span><span class="sxs-lookup"><span data-stu-id="be50e-124">If a control has **View details** capabilities, and if the control has a value, that value is displayed as a hyperlink.</span></span> <span data-ttu-id="be50e-125">Du kan klicka på hyperlänken när du vill öppna en sida som innehåller mer information.</span><span class="sxs-lookup"><span data-stu-id="be50e-125">You can click the hyperlink to open a page that contains additional details.</span></span>
- <span data-ttu-id="be50e-126">**Visa information** är även ett alternativ på snabbmenyerna.</span><span class="sxs-lookup"><span data-stu-id="be50e-126">**View details** is also an option on shortcut menus.</span></span> <span data-ttu-id="be50e-127">Mer information om när snabbmenyerna visas när du högerklickar finns i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="be50e-127">For more information about when shortcut menus are displayed when you right-click, see the previous section.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]