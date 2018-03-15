---
title: Servicemallar
description: Du kan definiera ett serviceavtal som en mall och senare kopiera raderna i mallen till ett annat serviceavtal eller till en serviceorder.
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 09f2da382cd7f3e0e3d4bfa389e9cdf74f00b501
ms.openlocfilehash: ade518095b77141fb31b597a955dd23aaae119d7
ms.contentlocale: sv-se
ms.lasthandoff: 02/27/2018

---

# <a name="service-templates"></a><span data-ttu-id="ddaea-103">Servicemallar</span><span class="sxs-lookup"><span data-stu-id="ddaea-103">Service templates</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ddaea-104">Du kan definiera ett serviceavtal som en mall och senare kopiera raderna i mallen till ett annat serviceavtal eller till en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="ddaea-104">You can define a service agreement as a template and copy the lines of the template later into another service agreement or into a service order.</span></span>

## <a name="example"></a><span data-ttu-id="ddaea-105">Exempel</span><span class="sxs-lookup"><span data-stu-id="ddaea-105">Example</span></span>

<span data-ttu-id="ddaea-106">En kund som du tillhandahåller en tjänst för har identiska servicehissar på fem olika platser.</span><span class="sxs-lookup"><span data-stu-id="ddaea-106">A customer for whom you provide service has identical service elevators at five different locations.</span></span>

<span data-ttu-id="ddaea-107">Du vill ställa in fem serviceavtal för kunden, en för varje site.</span><span class="sxs-lookup"><span data-stu-id="ddaea-107">You want to set up five service agreements for the customer, one for each site.</span></span>
<span data-ttu-id="ddaea-108">För att minska inställningsarbetet, och vara säker på att inställningsinformationen i serviceavtalen blir identisk, skapar du ett serviceavtal och anger den som en mall för servicearbetet på hissarna.</span><span class="sxs-lookup"><span data-stu-id="ddaea-108">To limit repetitive setup work, and to make sure that the setup information in the service agreements is identical, you create a service agreement and specify it as a template for the service work on the elevators.</span></span>

<span data-ttu-id="ddaea-109">Du kan nu kopiera mallraderna till fem nya serviceavtal, så att varje serviceavtal fylls i med raderna från mallen.</span><span class="sxs-lookup"><span data-stu-id="ddaea-109">You can now copy the template lines into the five new service agreements, so that each service agreement is populated with the lines from the template.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="ddaea-110">Skapa en mall</span><span class="sxs-lookup"><span data-stu-id="ddaea-110">Create a template</span></span>

<span data-ttu-id="ddaea-111">När du skapar en servicemall skapar du ett serviceavtal, skapar de rader som behövs och kopplar sedan serviceavtalet till en servicemallgrupp.</span><span class="sxs-lookup"><span data-stu-id="ddaea-111">When you create a service template, you create a service agreement, create the required lines on it, and attach the service agreement to a service-template group.</span></span>

> [!NOTE]
> <span data-ttu-id="ddaea-112">Ett serviceavtal kan definieras som en mall bara om det inte har några serviceorder kopplade.</span><span class="sxs-lookup"><span data-stu-id="ddaea-112">A service agreement can be defined as a template only if it has no service orders attached to it.</span></span> <span data-ttu-id="ddaea-113">Inga serviceorder kan heller skapas från ett serviceavtal som definierats som en mall.</span><span class="sxs-lookup"><span data-stu-id="ddaea-113">Also, no service orders can be generated from a service agreement that is defined as a template.</span></span>

## <a name="copy-template-lines"></a><span data-ttu-id="ddaea-114">Kopiera mallrader</span><span class="sxs-lookup"><span data-stu-id="ddaea-114">Copy template lines</span></span>

<span data-ttu-id="ddaea-115">Du kan kopiera mallrader från en servicemall till ett annat serviceavtal eller till en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="ddaea-115">You can copy template lines from a service template into another service agreement or into a service order.</span></span>

<span data-ttu-id="ddaea-116">När du kopierar mallrader till dina serviceorder eller serviceavtal visas mallgrupperna i en trädvy där varje grupp kan utvidgas.</span><span class="sxs-lookup"><span data-stu-id="ddaea-116">When you copy template lines into your service orders or service agreements, your template groups are displayed in a tree view in which each group can be expanded.</span></span> <span data-ttu-id="ddaea-117">I den här vyn kan du visa alla mallar och mallrader.</span><span class="sxs-lookup"><span data-stu-id="ddaea-117">This display lets you view each template and template line.</span></span>

<span data-ttu-id="ddaea-118">Det är enklare att ta reda på vilka mallrader som du bör kopiera om du grupperar mallarna enligt namn som beskriver hur de ska användas.</span><span class="sxs-lookup"><span data-stu-id="ddaea-118">It is easier to determine the service-template lines that you want to copy if you have grouped the templates under names that reflect the use of the templates.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ddaea-119">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ddaea-119">Related topics</span></span>

[<span data-ttu-id="ddaea-120">Kopiera servicemallsrader</span><span class="sxs-lookup"><span data-stu-id="ddaea-120">Copy service templates lines</span></span>](copy-service-template-lines.md)

