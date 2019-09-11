---
title: Skicka arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skickar arbetsorder i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3b1621cf0f1e47d7bd5fe2fa0b41fbcd61f14def
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887215"
---
# <a name="dispatch-work-order"></a><span data-ttu-id="8cf8f-103">Skicka arbetsorder</span><span class="sxs-lookup"><span data-stu-id="8cf8f-103">Dispatch work order</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="8cf8f-104">Du kan schemalägga en arbetsorder eller arbetsorderjobb till en arbetare med funktionen **Skicka ut**.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-104">You can schedule one work order or work order jobs to one worker using the **Dispatch** functionality.</span></span>

1. <span data-ttu-id="8cf8f-105">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="8cf8f-106">Välj arbetsordern i listan.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-106">Select the work order in the list.</span></span>

3. <span data-ttu-id="8cf8f-107">Klicka på **Skicka ut** på fliken **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-107">On the **General** tab, click **Dispatch**.</span></span>

4. <span data-ttu-id="8cf8f-108">I dialogrutan **Schemalägg arbetsorder** väljer du arbetaren i fältet **Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-108">n the **Schedule work order** dialog, select the worker in the **Worker** field.</span></span>

5. <span data-ttu-id="8cf8f-109">I fältet **Schemalägg timmar** kan du infoga förväntade arbetstimmar i fall förväntade arbetstimmar skiljer sig från prognostimmar.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-109">In the **Schedule hours** field, you can insert expected work hours in case expected work hours differ from forecast hours.</span></span>

6. <span data-ttu-id="8cf8f-110">I fältet **Schemalagd start** kan du ändra startdatum och starttid om det behövs.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-110">In the **Scheduled start** field, you can edit start date and time, if required.</span></span>

7. <span data-ttu-id="8cf8f-111">Om tidsplaneringsprocessen ska ta hänsyn till kapacitetsbegränsningar för resurser som redan har schemalagts för andra jobb, kontrollera att växlingsknapparna **Tillgång**, **Verktyg** och **Arbetare** är inställda på "Ja".</span><span class="sxs-lookup"><span data-stu-id="8cf8f-111">If the scheduling process should observe capacity limitations regarding resources already scheduled on other jobs, make sure that the **Asset**, **Tool**, and **Worker** toggle buttons are set to "Yes".</span></span> <span data-ttu-id="8cf8f-112">Om du vill visa detaljerad information om tidsplaneringsprocessen väljer du "Ja"på växlingsknappen **Utförligt**.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-112">If you want to see detailed information about the scheduling process, select "Yes" on the **Verbose** toggle button.</span></span> <span data-ttu-id="8cf8f-113">Det innebär att detaljerad information om de beräknade poängen på arbetsordern visas i informationsloggen.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-113">This means detailed information about the calculated scores on the work order is shown in the Infolog.</span></span>

8. <span data-ttu-id="8cf8f-114">Välj "Ja" på växlingsknappen **Ignorera schema** om du vill ignorera stängda dagar i kalendern (gäller för till gång, arbetare och verktyg).</span><span class="sxs-lookup"><span data-stu-id="8cf8f-114">Select "Yes" on the **Ignore schedule** toggle button to ignore closed days in the calendar (applies to asset, worker, and tools).</span></span> <span data-ttu-id="8cf8f-115">Välj "Ja" på växlingsknappen **Ignorera schemalagt utförande** om du vill ignorera begränsningar som kan ha valts på arbetsordern om planeringen.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-115">Select "Yes" on the **Ignore scheduled execution** toggle button to ignore limitations that may have been selected on the work order regarding scheduling.</span></span> <span data-ttu-id="8cf8f-116">Information om hur ställer in schemalagt utförande finns i avsnittet [Schemalagt utförande](../setup-for-work-orders/scheduled-execution.md).</span><span class="sxs-lookup"><span data-stu-id="8cf8f-116">Refer to the [Scheduled execution](../setup-for-work-orders/scheduled-execution.md) section for information on the setup of scheduled execution.</span></span>

9. <span data-ttu-id="8cf8f-117">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-117">Click **OK**.</span></span> <span data-ttu-id="8cf8f-118">Livscykeltillståndet för arbetsordern uppdateras automatiskt till tillståndet "Schemalagt"som anges i **Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Livscykelmodeller**.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-118">The work order lifecycle state is automatically updated to the "Scheduled" lifecycle state specified **Asset management** > **Setup** > **Work orders** > **Lifecycle models**.</span></span>

<span data-ttu-id="8cf8f-119">I bilden nedan visas ett exempel på val för skicka ut i dialogrutan **Schemalägg arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-119">The figure below shows an example of dispatch selections in the **Schedule work order** dialog.</span></span>

![Figur 1](media/04-work-order-scheduling.png)

>[!NOTE]
><span data-ttu-id="8cf8f-121">Om du vill ta bort schemat för en arbetsorder gör du det genom att välja arbetsordern i **Alla arbets order** och klicka på **Ta bort schema** på fliken **Allmänt**. Kom ihåg att uppdatera arbetsorderns livscykeltillstånd manuellt om du tar bort schemat.</span><span class="sxs-lookup"><span data-stu-id="8cf8f-121">If you want to delete the schedule on a work order, this is done by selecting the work order in **All work orders** and clicking **Delete schedule** on the **General** tab. Remember to manually update the work order lifecycle state if you delete the schedule.</span></span>

