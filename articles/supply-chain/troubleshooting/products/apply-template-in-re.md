---
title: Du kan inte använda en mall på en frisläppt produkt
description: Du kan inte använda en mall på en frisläppt produkt.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026908"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a><span data-ttu-id="54610-103">Du kan inte använda en mall för att skapa en frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="54610-103">You can't apply a template to create a released product</span></span>

<span data-ttu-id="54610-104">KB-nummer: 4612097</span><span class="sxs-lookup"><span data-stu-id="54610-104">KB number: 4612097</span></span>

## <a name="symptoms"></a><span data-ttu-id="54610-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="54610-105">Symptoms</span></span>

<span data-ttu-id="54610-106">När du skapar en ny frisläppt produkt med hjälp av dialogrutan **Ny frisläppt produkt** kan du välja en mall.</span><span class="sxs-lookup"><span data-stu-id="54610-106">When you create a new released product by using the **New released product** dialog box, you can select a template.</span></span> <span data-ttu-id="54610-107">Mallen bör innehålla standardinställningar för många fält i den nya frisläppta produkten.</span><span class="sxs-lookup"><span data-stu-id="54610-107">The template is supposed to provide default settings for many fields of the new released product.</span></span> <span data-ttu-id="54610-108">Vissa eller alla fält anges dock inte när du har valt mallen.</span><span class="sxs-lookup"><span data-stu-id="54610-108">However, some or all of the fields aren't set after you select the template.</span></span>

## <a name="cause"></a><span data-ttu-id="54610-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="54610-109">Cause</span></span>

<span data-ttu-id="54610-110">På många sidor i Microsoft Dynamics 365 Supply Chain Management kan du skapa en mall som fastställer de första inställningarna för de poster som visas på dessa sidor.</span><span class="sxs-lookup"><span data-stu-id="54610-110">Many pages in Microsoft Dynamics 365 Supply Chain Management let you create a template that establishes initial settings for the records that are shown on those pages.</span></span> <span data-ttu-id="54610-111">Du kan skapa en av dessa mallar genom att välja **Postinfo** under fliken **Alternativ** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="54610-111">You can create one of these templates by selecting **Record info** on the **Options** tab of the Action Pane.</span></span> <span data-ttu-id="54610-112">Frisläppta produkter är dock mycket mer komplexa än de flesta andra typer av poster.</span><span class="sxs-lookup"><span data-stu-id="54610-112">However, released products are much more complex than most other types of records.</span></span> <span data-ttu-id="54610-113">Även om du kan välja **Postinfo** på sidan **Frisläppta produkter** för att skapa en mall, och även om du kan välja mallen när du skapar en frisläppt produkt, innehåller inte mallen de förväntade fältvärdena för den nya frisläppta produkten.</span><span class="sxs-lookup"><span data-stu-id="54610-113">Although you can select **Record info** on the **Released products** page to create a template, and although you can select that template when you create a released product, the template won't provide the expected field values for the new released product.</span></span> <span data-ttu-id="54610-114">Därför kan du inte använda "postinformation"-mallar för frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="54610-114">Therefore, you can't use "record info" templates for released products.</span></span> <span data-ttu-id="54610-115">I stället måste du skapa dedikerade produktmallar.</span><span class="sxs-lookup"><span data-stu-id="54610-115">Instead, you must create dedicated product templates.</span></span>

## <a name="resolution"></a><span data-ttu-id="54610-116">Upplösning</span><span class="sxs-lookup"><span data-stu-id="54610-116">Resolution</span></span>

<span data-ttu-id="54610-117">För att skap en produktmall använder du menyn **Mall** under fliken **Produkt** i åtgärdsfönstret, inte knappen **Postinfo** under fliken **Alternativ**.</span><span class="sxs-lookup"><span data-stu-id="54610-117">To create a product template, use the **Template** menu on the **Product** tab of the Action Pane, not the **Record info** button on the **Options** tab.</span></span>

1. <span data-ttu-id="54610-118">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="54610-118">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="54610-119">I åtgärdsfönstret, under fliken **Produkt**, i gruppen **Ny**, väljer du **Mall** och sedan antingen **Skapa personlig mall** eller **Skapa delad mall**, beroende på vad som är lämpligt.</span><span class="sxs-lookup"><span data-stu-id="54610-119">On the Action Pane, on the **Product** tab, in the **New** group, select **Template**, and then select either **Create personal template** or **Create shared template**, as appropriate.</span></span>
