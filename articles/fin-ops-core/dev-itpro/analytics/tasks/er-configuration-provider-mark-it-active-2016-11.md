---
title: Skapa konfigurationsleverantörer och markera dem som aktiva
description: I detta avsnitt beskriver följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör för elektronisk rapportering (ER).
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5f238a492dbc3f9318b1bd1d3ea5657e92b33fb
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142119"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="015b6-103">Skapa konfigurationsleverantörer och markera dem som aktiva</span><span class="sxs-lookup"><span data-stu-id="015b6-103">Create configuration providers and mark them as active</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="015b6-104">I detta avsnitt beskriver följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="015b6-104">This topic explains how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="015b6-105">Alla ER-konfigurationer refererar till leverantören som författare av konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="015b6-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="015b6-106">I det här exemplet ska du skapa en konfigureringsleverantör för exempelföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringsleverantörer delas mellan alla företag.</span><span class="sxs-lookup"><span data-stu-id="015b6-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>

## <a name="create-a-provider"></a><span data-ttu-id="015b6-107">Skapa en leverantör</span><span class="sxs-lookup"><span data-stu-id="015b6-107">Create a provider</span></span>
1. <span data-ttu-id="015b6-108">Gå till **navigerings fönstret** i det övre vänstra hörnet och välj **organisationsadministration**.</span><span class="sxs-lookup"><span data-stu-id="015b6-108">Go to the **navigation pane** in the upper left corner and select **Organization administration**.</span></span>
2. <span data-ttu-id="015b6-109">Gå till **Arbetsytor > Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="015b6-109">Go to **Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="015b6-110">Gå till **relaterade länkar > konfigurationsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="015b6-110">Go to **Related links > Configuration providers**.</span></span>
4. <span data-ttu-id="015b6-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="015b6-111">Select **New**.</span></span>
    - <span data-ttu-id="015b6-112">En leverantörspost har ett unikt namn och en unik webbadress.</span><span class="sxs-lookup"><span data-stu-id="015b6-112">A provider record has a unique name and URL.</span></span> <span data-ttu-id="015b6-113">Granska innehållet på den här sidan och hoppa över den här proceduren om en post för Litware, Inc (https://www.litware.com) redan finns.</span><span class="sxs-lookup"><span data-stu-id="015b6-113">Review the content of this page and skip this procedure if a record for Litware, Inc. (https://www.litware.com) already exists.</span></span>  
5. <span data-ttu-id="015b6-114">I fältet Namn skriver du `Litware, Inc.`.</span><span class="sxs-lookup"><span data-stu-id="015b6-114">In the Name field, type `Litware, Inc.`.</span></span>
6. <span data-ttu-id="015b6-115">Skriv in "`https://www.litware.com`" i fältet för Internetadress.</span><span class="sxs-lookup"><span data-stu-id="015b6-115">In the Internet address field, type `https://www.litware.com`.</span></span>
7. <span data-ttu-id="015b6-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="015b6-116">Select **Save**.</span></span>
8. <span data-ttu-id="015b6-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="015b6-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="015b6-118">Välj som en aktiv leverantör</span><span class="sxs-lookup"><span data-stu-id="015b6-118">Select as an active provider</span></span>
1. <span data-ttu-id="015b6-119">Välj leverantören "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="015b6-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="015b6-120">Ställ in **Ange aktiva**.</span><span class="sxs-lookup"><span data-stu-id="015b6-120">Select **Set active**.</span></span>

![Sidan Arbetsytan för elektronisk rapportering](../media/GER-Task-ActiveProvider-1.png)
