---
title: "Visa sidor sida vid sida med hjälp av funktionen Öppna i nytt fönster"
description: "Denna artikel förklarar hur du visar sidor sida vid sida i Microsoft Dynamics 365 for Finance and Operations."
author: aneesmsft
manager: AnnBe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 8e3ef29618f11b0f247999e3a24e54bff44bf51a
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---

# <a name="show-pages-side-by-side-by-using-the-open-in-new-window-feature"></a><span data-ttu-id="9ba8f-103">Visa sidor sida vid sida med hjälp av funktionen Öppna i nytt fönster</span><span class="sxs-lookup"><span data-stu-id="9ba8f-103">Show pages side by side by using the Open in new window feature</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ba8f-104">Denna artikel förklarar hur du visar sidor sida vid sida i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-104">This article explains how to display pages side-by-side in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="9ba8f-105">Microsoft Dynamics 365 for Finance and Operations hjälper dig att utföra uppgifter effektivt.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-105">Microsoft Dynamics 365 for Finance and Operations helps you perform tasks efficiently.</span></span> <span data-ttu-id="9ba8f-106">I vissa fall vill du kanske visa flera sidor sida vid sida för att slutföra uppgifter snabbt.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-106">In some cases, you may want to view multiple pages side-by-side to complete tasks quickly.</span></span> <span data-ttu-id="9ba8f-107">Som ett exempel vill du kanske validera eller ange rader i mer än en journal.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-107">As an example, you might want to validate or enter lines in more than one journal.</span></span> <span data-ttu-id="9ba8f-108">För att göra detta måste vanligen du gå fram och tillbaka mellan sidan som visar en lista med journaler och sidan som visar rader för en viss journal.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-108">Typically, to do this you would have to go back and forth between the page that displays a list of journals, and the page that displays lines for a given journal.</span></span> <span data-ttu-id="9ba8f-109">Funktionen **Öppna i nytt fönster** gör det dock möjligt att visa dessa sidor sida vid sida så att du kan utföra dina uppgifter snabbt.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-109">However, the **Open in new window** feature enables you to display these pages side-by-side so that you can perform your tasks quickly.</span></span> 

<span data-ttu-id="9ba8f-110">Om vi fortsätter med exemplet ovan kan du klicka på ikonen **Öppna i nytt fönster** när du visar raderna.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-110">Continuing with the example mentioned above, when viewing the lines, you can click the **Open in new window** icon.</span></span> 

<span data-ttu-id="9ba8f-111">[![ikon-öppna-i-nytt-fönster](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)</span><span class="sxs-lookup"><span data-stu-id="9ba8f-111">[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)</span></span> 

<span data-ttu-id="9ba8f-112">Om du klickar på ikonen **Open in new window** öppnas radsidan i en ny popup-webbläsare, och navigerar sedan den ursprungliga webbläsaren bakåt i historiken till sidan som visade listan med journaler.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-112">Clicking the **Open in new window** icon opens the lines page in a new, pop-up browser, and then navigates the original browser back in history to the page that displayed the list of journals.</span></span> <span data-ttu-id="9ba8f-113">Du kan sedan visa båda sidorna sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-113">You can then display both pages side-by-side.</span></span> <span data-ttu-id="9ba8f-114">När du är klar med att visa en journal, kan du ändra den valda journalen på journallistsidan och radsidan i popup-fönstret visar automatiskt raderna i den nya valda journalen.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-114">When you are done viewing a journal, you can change the selected journal on the journal list page, and the lines page in the pop-up window will automatically display the lines of the newly selected journal.</span></span> 

<span data-ttu-id="9ba8f-115">[![visa-sidor-sida-vid-sida](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)</span><span class="sxs-lookup"><span data-stu-id="9ba8f-115">[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)</span></span> 

<span data-ttu-id="9ba8f-116">Den dynamiska länkningen och uppdateringen inträffar på grund av relationerna som finns mellan data bakom dessa sidor.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-116">The dynamic linking and refreshing happens due to the relations that exist between the data that is backing these pages.</span></span> <span data-ttu-id="9ba8f-117">Om systemet inte är medvetet om relationen mellan data, uppdateras inte popup-fönstret automatiskt som svar på en ändring i fönstret där det har sitt ursprung.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-117">If the system is not aware of the relation between the data, the pop-up window will not refresh automatically in response to a change in the window it originated from.</span></span> 

<span data-ttu-id="9ba8f-118">Vissa sidor har flera vyer, till exempel rutnät, huvudvy och detaljvy.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-118">Some pages have multiple views such as the Grid view, Header view, and Details view.</span></span> <span data-ttu-id="9ba8f-119">Ikonen **Öppna i nytt fönster** gör att hela sidan öppnas i det nya webbläsarfönstret.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-119">The **Open in new window** icon causes the entire page to be opened in the new browser window.</span></span> <span data-ttu-id="9ba8f-120">Du kan därför inte behålla två vyer av samma sida som sida vid sida med funktionen **Öppna i nytt fönster**.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-120">Therefore, you cannot keep two views of the same page side-by-side using the **Open in new window** feature.</span></span> <span data-ttu-id="9ba8f-121">Nästan alla sådana sidor har dock en navigeringslista som du kan använda för att växla mellan poster och uppnå en liknande effekt.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-121">However, almost all such pages have a navigation list that you can use to switch between records and achieve a similar experience.</span></span> 

<span data-ttu-id="9ba8f-122">Innan du använder funktionen **Öppna i nytt fönster** bör du konfigurera webbläsarens popup-blockerare så att denna tillåter popup-fönster från Finance and Operations-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-122">Before using the **Open in new window** feature, you should configure your browser's pop-up blocker to allow pop-ups from the URL of the Finance and Operations site.</span></span> <span data-ttu-id="9ba8f-123">Du kan exempelvis tillåta popup-fönster från "\*.dynamics.com".</span><span class="sxs-lookup"><span data-stu-id="9ba8f-123">As an example, you could allow pop-ups from "\*.dynamics.com".</span></span> 

<span data-ttu-id="9ba8f-124">Funktionen **Öppna i nytt fönster** är endast tillgänglig när det finns fler än en sida som är öppen i fönstret.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-124">The **Open in new window** feature is only available when there is more than one page open in the window.</span></span> <span data-ttu-id="9ba8f-125">Popup-fönstret stängs även automatiskt när det inte finns några fler öppna sidor (det vill säga när den sista sidan i det fönstret stängs.)</span><span class="sxs-lookup"><span data-stu-id="9ba8f-125">Also, the pop-up window automatically closes when there are no more pages open (that is, when the last page in that window is closed).</span></span> <span data-ttu-id="9ba8f-126">Finance and Operations stänger också öppna sidor när du navigerar till ett annat område i programmet.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-126">Finance and Operations also closes open pages when you navigate to a different area in the application.</span></span> <span data-ttu-id="9ba8f-127">Om du har öppna popup-fönster och navigerar till ett annat område i programmet stängs därför popup-fönster automatiskt, eftersom sidorna i dessa fönster stängdes av systemet.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-127">Therefore, if you have pop-up windows open and navigate to a different area in the application, the pop-up windows are automatically closed because the pages in those windows were closed by the system.</span></span> 

<span data-ttu-id="9ba8f-128">Det övre fältet i popup-fönster visar information om företaget som sidan öppnades i och är skrivskyddat.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-128">The top bar in the pop-up windows displays information about the company the page was opened in and is read-only.</span></span> <span data-ttu-id="9ba8f-129">Popup-fönster beror också på huvudwebbläsarfönstret för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-129">The pop-up windows also rely on the main Finance and Operations browser window.</span></span> <span data-ttu-id="9ba8f-130">Om huvudfönstret stängs eller uppdateras, blir alla öppna popup-fönster skrivskyddade.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-130">If the main window is closed or refreshed, all open pop-up windows will become read only.</span></span> <span data-ttu-id="9ba8f-131">Det innebär att du fortfarande kan visa informationen i dessa fönster, men du kan inte interagera med den.</span><span class="sxs-lookup"><span data-stu-id="9ba8f-131">This means that you can still view the information in these windows, but you will not be able to interact with it.</span></span>




