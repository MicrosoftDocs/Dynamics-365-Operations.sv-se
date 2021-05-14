---
title: Incheckning för upphämtningsmodul
description: Det här avsnittet beskriver incheckningen för plockmodul samt förklarar hur du konfigurerar denna i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e7bae4ae7c2f3367132b03accb31c01c5f3b673e
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937619"
---
# <a name="check-in-for-pickup-module"></a><span data-ttu-id="cbbd9-103">Incheckning för upphämtningsmodul</span><span class="sxs-lookup"><span data-stu-id="cbbd9-103">Check-in for pickup module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="cbbd9-104">Det här avsnittet beskriver incheckningen för plockmodul samt förklarar hur du konfigurerar denna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-104">This topic covers the check-in for pickup module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="cbbd9-105">Incheckningen för upphämtningsmodulen innehåller en bekräftelsesida för kunder som använder incheckningsfunktionerna för kunder i Dynamics 365 Commerce och informerar en butik om att de är inkommande.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-105">The check-in for pickup module provides a confirmation page for customers who use the Dynamics 365 Commerce customer check-in capabilities to notify a store about their arrival.</span></span> <span data-ttu-id="cbbd9-106">Med incheckningen för upphämtningsmodulen kan du även konfigurera ett formulär som samlar in ytterligare information från kunder i syfte att underlätta orderleveransen.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-106">The check-in for pickup module also lets you configure a form that collects additional information from customers to facilitate order delivery.</span></span> <span data-ttu-id="cbbd9-107">Denna information inkluderar en kunds nummer på parkeringsplatsen samt fordonets märke och modell.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-107">This information includes a customer's parking spot number, and the make and model of their vehicle.</span></span> 

## <a name="module-properties"></a><span data-ttu-id="cbbd9-108">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="cbbd9-108">Module properties</span></span>

| <span data-ttu-id="cbbd9-109">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="cbbd9-109">Property name</span></span> | <span data-ttu-id="cbbd9-110">Värden</span><span class="sxs-lookup"><span data-stu-id="cbbd9-110">Values</span></span> | <span data-ttu-id="cbbd9-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="cbbd9-111">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="cbbd9-112">Bekräftelsetext</span><span class="sxs-lookup"><span data-stu-id="cbbd9-112">Confirmation text</span></span> | <span data-ttu-id="cbbd9-113">Textsträng</span><span class="sxs-lookup"><span data-stu-id="cbbd9-113">Text string</span></span> | <span data-ttu-id="cbbd9-114">Innehåll för rubriken som visas på incheckningsbekräftelsesidan.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-114">Content for the heading that appears on the check-in confirmation page.</span></span> |
| <span data-ttu-id="cbbd9-115">Visa QR-kod</span><span class="sxs-lookup"><span data-stu-id="cbbd9-115">Show QR code</span></span> | <span data-ttu-id="cbbd9-116">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="cbbd9-116">**True** or **False**</span></span> | <span data-ttu-id="cbbd9-117">När egenskapen har värdet **True** (sant) visar incheckningsbekräftelsesidan en QR-kod som representerar orderbekräftelse-ID:t.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-117">When this property is set to **True**, the check-in confirmation page shows a QR code that represents the order confirmation ID.</span></span> |
| <span data-ttu-id="cbbd9-118">Ytterligare informationsrubrik</span><span class="sxs-lookup"><span data-stu-id="cbbd9-118">Additional information heading</span></span> | <span data-ttu-id="cbbd9-119">Textsträng</span><span class="sxs-lookup"><span data-stu-id="cbbd9-119">Text string</span></span> | <span data-ttu-id="cbbd9-120">Innehåll för rubriken som visas när ytterligare informationsfält har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-120">Content for the heading that appears when additional information fields have been configured.</span></span> |
| <span data-ttu-id="cbbd9-121">Ytterligare informationsnycklar</span><span class="sxs-lookup"><span data-stu-id="cbbd9-121">Additional information keys</span></span> | <span data-ttu-id="cbbd9-122">Resurs-ID/resursvärdepar</span><span class="sxs-lookup"><span data-stu-id="cbbd9-122">Resource ID/resource value pair</span></span> | <span data-ttu-id="cbbd9-123">Varje nyckel skapar ett formulärfält och en tillhörande etikett som används för att samla in ytterligare information från kunder.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-123">Each key creates a form field and an associated label that are used to collect additional information from customers.</span></span> |
| <span data-ttu-id="cbbd9-124">Ytterligare informationsnycklar \> Resurs-ID</span><span class="sxs-lookup"><span data-stu-id="cbbd9-124">Additional information keys \> Resource ID</span></span> | <span data-ttu-id="cbbd9-125">Textsträng</span><span class="sxs-lookup"><span data-stu-id="cbbd9-125">Text string</span></span> | <span data-ttu-id="cbbd9-126">Varje informationsnyckel skapar ett formulärfält och en tillhörande etikett som används för att samla in ytterligare information från kunder.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-126">Each information key creates a form field and an associated label that are used to collect additional information from customers.</span></span> <span data-ttu-id="cbbd9-127">Denna egenskap identifierar den ytterligare informationsnyckeln.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-127">This property identifies the additional information key.</span></span> <span data-ttu-id="cbbd9-128">I uppgiften som skapas i kassan (POS) visas värdet för den här egenskapen som etiketten i instruktionsfältet.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-128">In the task that is created in point of sale (POS), the value of this property is shown as the label in the instructions field.</span></span> |
| <span data-ttu-id="cbbd9-129">Ytterligare informationsnycklar \> Resursvärde</span><span class="sxs-lookup"><span data-stu-id="cbbd9-129">Additional information keys \> Resource value</span></span> | <span data-ttu-id="cbbd9-130">Textsträng</span><span class="sxs-lookup"><span data-stu-id="cbbd9-130">Text string</span></span> | <span data-ttu-id="cbbd9-131">Etiketten för textfältet i uppgiften i kassan (POS).</span><span class="sxs-lookup"><span data-stu-id="cbbd9-131">The label for the text field in the task in POS.</span></span> |
| <span data-ttu-id="cbbd9-132">Ytterligare informationsnycklar \> Krävs</span><span class="sxs-lookup"><span data-stu-id="cbbd9-132">Additional information keys \> Required</span></span> | <span data-ttu-id="cbbd9-133">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="cbbd9-133">**True** or **False**</span></span> | <span data-ttu-id="cbbd9-134">Denna egenskap anger om kunderna måste fylla i formulärfältet innan de kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-134">This property specifies whether customers must fill in the form field before they can continue.</span></span> <span data-ttu-id="cbbd9-135">När denna egenskap är inställt på **True** visas en asterisk bredvid formulärsetiketten, och en "null"-kontroll sker i syfte att förhindra att kunden fortsätter om inget värde har angetts.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-135">When this property is set to **True**, an asterisk is rendered next to the form label, and a null check is done to prevent customers from continuing if no value is entered.</span></span> |

## <a name="add-the-check-in-for-pickup-module-to-a-page"></a><span data-ttu-id="cbbd9-136">Lägga till incheckningen för upphämtningsmodulen på en sida</span><span class="sxs-lookup"><span data-stu-id="cbbd9-136">Add the check-in for pickup module to a page</span></span>

<span data-ttu-id="cbbd9-137">Incheckningen för upphämtningsmodulen ska läggas till på den nya sidan som du skapar för incheckningsbekräftelsen.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-137">The check-in for pickup module should be added to the new page that you create for check-in confirmation.</span></span> <span data-ttu-id="cbbd9-138">Den sidan fungerar som incheckningsbekräftelseupplevelse för kunder som väljer länken **Jag är här** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-138">That page will serve as the check-in confirmation experience for customers who select the **I am here** link or button in their email.</span></span> 

## <a name="configure-the-additional-information-form"></a><span data-ttu-id="cbbd9-139">Konfigurera det ytterligare informationsformuläret</span><span class="sxs-lookup"><span data-stu-id="cbbd9-139">Configure the additional information form</span></span>

<span data-ttu-id="cbbd9-140">Om inga ytterligare informationsnycklar har konfigurerats visar modulen bekräftelsesidan för incheckning för kunderna.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-140">By default, if no additional information keys are configured, the module shows customers the check-in confirmation page.</span></span> <span data-ttu-id="cbbd9-141">När incheckningsbekräftelsen visas skapas en uppgift i kassan (POS) för butiken där ordern hämtas.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-141">As the check-in confirmation is shown, a task is created in POS for the store where the order is being picked up.</span></span>

<span data-ttu-id="cbbd9-142">När en eller flera ytterligare informationsnycklar konfigureras uppmanas kunder först att ange information.</span><span class="sxs-lookup"><span data-stu-id="cbbd9-142">When one or more additional information keys are configured, customers are first prompted to enter information.</span></span> <span data-ttu-id="cbbd9-143">När de väljer **Skicka** visas incheckningsbekräftelsen och en uppgift skapas i kassan (POS).</span><span class="sxs-lookup"><span data-stu-id="cbbd9-143">When they select **Submit**, they are shown the check-in confirmation, and a task is created in POS.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="cbbd9-144">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cbbd9-144">Additional resources</span></span>

[<span data-ttu-id="cbbd9-145">Aktivera incheckningsmeddelanden för kunder i kassan (POS)</span><span class="sxs-lookup"><span data-stu-id="cbbd9-145">Enable customer check-in notifications in point of sale (POS)</span></span>](enable-customer-check-in.md)
