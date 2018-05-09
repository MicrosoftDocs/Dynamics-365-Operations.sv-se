---
title: "Utöka funktionerna i Microsoft Dynamics 365 for Talent"
description: "Om du har skapat några Microsoft-PowerApps kan du starta programmen från länkar i Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 03/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4befe02a59d0d617f80174e6c7fbcf00db95adb2
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a><span data-ttu-id="4935e-103">Utöka funktionerna i Microsoft Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="4935e-103">Extend the functionality of Microsoft Dynamics 365 for Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4935e-104">Om du har skapat några Microsoft-PowerApps kan du starta programmen från länkar i Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="4935e-104">If you’ve created any Microsoft PowerApps, you can start those applications from links within Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="4935e-105">Om du vill konfigurera åtkomsten till dina program måste du ange viss information i Talent på en konfigurationssida som kan öppnas från arbetsytan **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="4935e-105">To set up access to your applications, you’ll need to set up some information in Talent on a configuration page that you can open from the **System administration** workspace.</span></span>

## <a name="configuring-embedded-powerapps-within-talent"></a><span data-ttu-id="4935e-106">Konfigurera inbäddade PowerApps i Talent</span><span class="sxs-lookup"><span data-stu-id="4935e-106">Configuring embedded PowerApps within Talent</span></span>
<span data-ttu-id="4935e-107">Använd sidan **Ange inbäddade Microsoft PowerApps** för att konfigurera Talent-sidor så att dessa startar PowerApps-program.</span><span class="sxs-lookup"><span data-stu-id="4935e-107">Use the **Set embedded Microsoft PowerApps** page to configure Talent pages to start PowerApps applications.</span></span> <span data-ttu-id="4935e-108">För att öppna sidan **Ange inbäddade Microsoft PowerApps**, öppna arbetsytan **Systemadministration** och öppna sedan fliken **Länkar**. Välj **Microsoft PowerApps** i gruppen **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4935e-108">To open the **Set embedded Microsoft PowerApps** page, open the **System administration** workspace and then open the **Links** tab. Select **Microsoft PowerApps** from the **Setup** group.</span></span> 

<span data-ttu-id="4935e-109">Följande information anges eller konfigureras på den här sidan:</span><span class="sxs-lookup"><span data-stu-id="4935e-109">The following information is entered or set on this page:</span></span> 

 -  <span data-ttu-id="4935e-110">Ett beskrivande namn eller ID för respektive PowerApps-program.</span><span class="sxs-lookup"><span data-stu-id="4935e-110">A descriptive name or identifier for each PowerApps application.</span></span>
 -  <span data-ttu-id="4935e-111">En unik identifierare (GUID) för respektive program som du lägger till på en Talent-sida.</span><span class="sxs-lookup"><span data-stu-id="4935e-111">A unique identifier (GUID) for each application that you add to a Talent page.</span></span> <span data-ttu-id="4935e-112">Program-ID:t finns på PowerApps-webbplatsen [powerapps.com](http://powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="4935e-112">The app ID is available on the PowerApps site, [powerapps.com](http://powerapps.com/).</span></span> 
 -  <span data-ttu-id="4935e-113">Sidan där användare öppnar ett program eller en rapport.</span><span class="sxs-lookup"><span data-stu-id="4935e-113">The page from which users can open an application or report.</span></span> <span data-ttu-id="4935e-114">Inte alla Talent-sidor stöder inbäddade PowerApps- och Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="4935e-114">Not all Talent pages support embedded PowerApps and Power BI reports.</span></span> 

 > [!NOTE]
 >  <span data-ttu-id="4935e-115">Ange det interna namnet på sidan i stället för det namn som visas överst på sidan.</span><span class="sxs-lookup"><span data-stu-id="4935e-115">Enter the internal name of the page, rather than the display name that appears at the top of the page.</span></span> <span data-ttu-id="4935e-116">För att hitta det interna namnet, öppna sidan för vilken du behöver det interna namnet och klicka var som helst på sidan.</span><span class="sxs-lookup"><span data-stu-id="4935e-116">To find the internal name, open the page that you need the internal name of, and right-click anywhere on the page.</span></span> <span data-ttu-id="4935e-117">När menyn öppnas, för då muspekaren över artikeln **Formulärinformation**.</span><span class="sxs-lookup"><span data-stu-id="4935e-117">When the menu opens, hover over the **Form information** item.</span></span> <span data-ttu-id="4935e-118">Det interna formulärnamnet visas bredvid menyalternativet **Formulärinformation**.</span><span class="sxs-lookup"><span data-stu-id="4935e-118">The internal form name is displayed next to the **Form information** item in the menu.</span></span>
 
-   <span data-ttu-id="4935e-119">Ange den formulärstyrning varifrån programmet hämtar kontextdata.</span><span class="sxs-lookup"><span data-stu-id="4935e-119">Specify the form control from which the application can retrieve context data.</span></span> <span data-ttu-id="4935e-120">Ett program kan till exempel använda data om en arbetare.</span><span class="sxs-lookup"><span data-stu-id="4935e-120">For example, an application might use data about a worker.</span></span> <span data-ttu-id="4935e-121">Om du anger sidan **Arbetare** i fältet **Kontext** kommer sidan **Arbetare** att öppnas när du startar programmet.</span><span class="sxs-lookup"><span data-stu-id="4935e-121">If you enter the **Worker** page in the **Context** field, the **Worker** page will open when you start the application.</span></span> <span data-ttu-id="4935e-122">En post i **kontextfältet** är valfritt.</span><span class="sxs-lookup"><span data-stu-id="4935e-122">An entry in the **Context field** is optional.</span></span> 
-   <span data-ttu-id="4935e-123">Ange storleken på dialogrutan där PowerApps-programmet ska köras.</span><span class="sxs-lookup"><span data-stu-id="4935e-123">Set the size of the dialog box on which the PowerApps application will run.</span></span> <span data-ttu-id="4935e-124">Dialogrutorna betecknas som ”liten” eller ”stor” i syfte att optimera användargränssnittet när programmet körs på en telefon respektive en större enhet.</span><span class="sxs-lookup"><span data-stu-id="4935e-124">The dialog boxes are designated as “small” or “large” to optimize the user interface when your application for running on a phone or a larger device, respectively.</span></span> 


<span data-ttu-id="4935e-125">Du kan även ange vilka juridiska personer som ett program blir tillgängligt för, eller också kan du göra det tillgängligt för alla dina juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="4935e-125">You can also specify which legal entities an application will be available for, or you can make it available to all your legal entities.</span></span> <span data-ttu-id="4935e-126">Som standard är dina PowerApps-program tillgängliga för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="4935e-126">By default, your PowerApps applications are available to all legal entities.</span></span>

## <a name="opening-an-application"></a><span data-ttu-id="4935e-127">Öppna ett program</span><span class="sxs-lookup"><span data-stu-id="4935e-127">Opening an application</span></span>
<span data-ttu-id="4935e-128">När du har konfigurerat inbäddade PowerApps-program läggs länkar till angivna program till på sidorna i Talent.</span><span class="sxs-lookup"><span data-stu-id="4935e-128">When you’ve configured embedded PowerApps applications, links to the applications that you specified will be added to the pages within Talent.</span></span> <span data-ttu-id="4935e-129">Klicka på en länk för att öppna ett program.</span><span class="sxs-lookup"><span data-stu-id="4935e-129">Click a link to open an application.</span></span> 



