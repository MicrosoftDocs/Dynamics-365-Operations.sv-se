---
title: Garanti på tillgångar och tillgångstyper
description: Det här avsnittet förklarar hur du ställer in garantier på tillgångar och tillgångstyper i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 75de9a51560dcd8fea7998425fee14a27e891972
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437807"
---
# <a name="warranties-on-assets-and-asset-types"></a><span data-ttu-id="4348d-103">Garanti på tillgångar och tillgångstyper</span><span class="sxs-lookup"><span data-stu-id="4348d-103">Warranties on assets and asset types</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="4348d-104">Det här avsnittet förklarar hur du ställer in garantier på tillgångar och tillgångstyper i Tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="4348d-104">This topic explains how to set up warranties on assets and asset types in Asset Management.</span></span>

## <a name="set-up-a-warranty-on-an-asset-type"></a><span data-ttu-id="4348d-105">Ställa in garanti på en tillgångstyp</span><span class="sxs-lookup"><span data-stu-id="4348d-105">Set up a warranty on an asset type</span></span>

1. <span data-ttu-id="4348d-106">Välj **tillgångshantering** \> **inställningar** \> **tillgångstyper** \> **tillgångstyper**.</span><span class="sxs-lookup"><span data-stu-id="4348d-106">Select **Asset management** \> **Setup** \> **Asset types** \> **Asset types**.</span></span>
2. <span data-ttu-id="4348d-107">I det vänstra fönstret väljer du den tillgångstyp att koppla ett leverantörsgarantiavtal till och väljer sedan **Standardtyp för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="4348d-107">In the left pane, select the asset type to attach a vendor warranty agreement to, and then select **Asset type defaults**.</span></span>
3. <span data-ttu-id="4348d-108">Välj avtalet på snabbfliken **Allmänt**, i fältet **Leverantörsgaranti**.</span><span class="sxs-lookup"><span data-stu-id="4348d-108">On the **General** FastTab, in the **Vendor warranty** field, select the agreement.</span></span>

## <a name="set-up-a-warranty-on-an-asset"></a><span data-ttu-id="4348d-109">Ställa in garanti på en tillgång</span><span class="sxs-lookup"><span data-stu-id="4348d-109">Set up a warranty on an asset</span></span>

1. <span data-ttu-id="4348d-110">Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar**</span><span class="sxs-lookup"><span data-stu-id="4348d-110">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="4348d-111">Välj tillgången och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="4348d-111">Select the asset, and then select **Edit**.</span></span>
3. <span data-ttu-id="4348d-112">På snabbfliken **Leverantör** i avsnittet **Leverantörsgaranti** väljer du garantiavtalet i fältet **Garanti**.</span><span class="sxs-lookup"><span data-stu-id="4348d-112">On the **Vendor** FastTab, in the **Vendor warranty** section, in the **Warranty** field, select the warranty agreement.</span></span>
4. <span data-ttu-id="4348d-113">Välj start- och slutdatum i fälten **Garantistart** och **Garantislut**.</span><span class="sxs-lookup"><span data-stu-id="4348d-113">In the **Warranty start** and **Warranty end** fields, select the start and end dates.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4348d-114">Om ett datum har valts i fältet **Garantistart** på en arbetsorder, blir garantin giltigt för arbetsordern på det datumet.</span><span class="sxs-lookup"><span data-stu-id="4348d-114">If a date is selected in the **Warranty start** field on a work order, the warranty becomes valid for the work order on that date.</span></span> <span data-ttu-id="4348d-115">När du skapar en arbetsorder anges fältet **Garantistart** automatiskt till skapandedatumet.</span><span class="sxs-lookup"><span data-stu-id="4348d-115">When you create a work order, the **Warranty start** field is automatically set to the date of creation.</span></span> <span data-ttu-id="4348d-116">Du kan dock ändra datumet så att det motsvarar t.ex. startdatum för ett garantiavtal.</span><span class="sxs-lookup"><span data-stu-id="4348d-116">However, you can change the date so that it corresponds to, for example, the start date of a warranty agreement.</span></span>
    >
    > ![Sidan Arbetsorder](media/02-warranty.png)

> [!NOTE]
> <span data-ttu-id="4348d-118">När du skapar en arbetsorder för en tillgång som täcks av en leverantörsgaranti, och arbetsordern har ett förväntat startdatum under garantiperioden, får du ett meddelande om garantiavtalet.</span><span class="sxs-lookup"><span data-stu-id="4348d-118">When you create a work order for an asset that is covered by a vendor warranty, if the work order has an expected start date during the warranty period, you receive a notification about the warranty agreement.</span></span> <span data-ttu-id="4348d-119">Du kan sedan avbryta arbets ordern efter behov.</span><span class="sxs-lookup"><span data-stu-id="4348d-119">You can then cancel the work order, as you require.</span></span>
