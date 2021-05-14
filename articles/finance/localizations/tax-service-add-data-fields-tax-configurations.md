---
title: Lägga till datafält i momskonfigurationer
description: I det här avsnittet beskrivs hur du anpassar momskonfigurationer genom att lägga till datafält.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 197a2d1605dd39188841aba02a71d228c7138c54
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921199"
---
# <a name="add-data-fields-in-tax-configurations"></a><span data-ttu-id="6893f-103">Lägga till datafält i momskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="6893f-103">Add data fields in tax configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6893f-104">I det här avsnittet beskrivs hur du anpassar momskonfigurationer med hjälp av [datafält som läggs till i momsintegreringen](tax-service-add-data-fields-tax-integration-by-extension.md).</span><span class="sxs-lookup"><span data-stu-id="6893f-104">This topic explains how to customize tax configurations by using [data fields that are added in the tax integration](tax-service-add-data-fields-tax-integration-by-extension.md).</span></span>

## <a name="customize-the-tax-data-model"></a><span data-ttu-id="6893f-105">Anpassa momsdatamodellen</span><span class="sxs-lookup"><span data-stu-id="6893f-105">Customize the tax data model</span></span>

1. <span data-ttu-id="6893f-106">I Microsoft Dynamics 365 Finance, gå till **Elektronisk rapportering** \> **Momskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="6893f-106">In Microsoft Dynamics 365 Finance, go to **Electronic Reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="6893f-107">I konfigurationsträdet väljer du **Momsdatamodell – Europa**.</span><span class="sxs-lookup"><span data-stu-id="6893f-107">In the configuration tree, select **Tax Data Model - Europe**.</span></span> <span data-ttu-id="6893f-108">Klicka på **Skapa konfiguration** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6893f-108">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="6893f-109">I listrutan, välj alternativet **Beskattningsbar dokumentmodell härledd från Namn: Momsdatamodell – Europa, Microsoft**, ange ett namn för den nya momsdatamodellen och välj sedan **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6893f-109">In the drop-down dialog box, select the **Taxable document model derived from Name: Tax Data Model -- Europe, Microsoft** option, enter a name for the new tax data model, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="6893f-110">Välj den momsdatamodell som du just skapat och markera sedan **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6893f-110">Select the tax data model that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="6893f-111">Expandera datamodellträdet, välj **Rader** och välj sedan **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6893f-111">Expand the data model tree, select **Lines**, and then select **New**.</span></span>
6. <span data-ttu-id="6893f-112">Ange ett namn i dialogrutan **Skapa nod**, ange artikeltypen och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="6893f-112">In the **Create node** dialog box, enter a name, specify the item type, and then select **Add**.</span></span>
7. <span data-ttu-id="6893f-113">Lägg till alla kolumner som behövs.</span><span class="sxs-lookup"><span data-stu-id="6893f-113">Add any required columns.</span></span>
8. <span data-ttu-id="6893f-114">I åtgärdsrutan väljer du **Spara** och välj sedan **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="6893f-114">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="6893f-115">Stäng sidan och visa den fullständiga versionen av din momsdatamodell.</span><span class="sxs-lookup"><span data-stu-id="6893f-115">Close the page, and view the completed version of your tax data model.</span></span>

## <a name="customize-the-tax-configuration"></a><span data-ttu-id="6893f-116">Anpassa momskonfiguration</span><span class="sxs-lookup"><span data-stu-id="6893f-116">Customize the tax configuration</span></span>

1. <span data-ttu-id="6893f-117">I Finance , gå till **Elektronisk rapportering** \> **Momskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="6893f-117">In Finance, go to **Electronic reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="6893f-118">I konfigurationsträdet väljer du **Momskonfiguration – Europa**.</span><span class="sxs-lookup"><span data-stu-id="6893f-118">In the configuration tree, select **Tax Configuration -- Europe**.</span></span> <span data-ttu-id="6893f-119">Klicka på **Skapa konfiguration** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6893f-119">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="6893f-120">I listrutan, välj alternativet **Momstjänstkonfiguration härledd från Namn: Momskonfiguration – Europa, Microsoft** ange ett namn för den nya skattekonfigurationen och välj sedan **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6893f-120">In the drop-down dialog box, select the **Tax service configuration derived from Name: Tax Configuration -- Europe, Microsoft** option, enter a name for the new tax configuration, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="6893f-121">Välj den momskonfiguration som du just skapat och markera sedan **Designer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6893f-121">Select the tax configuration that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="6893f-122">I avsnitt **Egenskaper** i fältet **Datamodell** välj den anpassade momsdatamodellen som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="6893f-122">In the **Properties** section, in the **Data model** field, select the customized tax data model that you created earlier.</span></span>
6. <span data-ttu-id="6893f-123">I fältet **Datamodellversion**,välj den färdiga versionen av momsdatamodellen.</span><span class="sxs-lookup"><span data-stu-id="6893f-123">In the **Data model version** field, select the completed version of the tax data model.</span></span>
7. <span data-ttu-id="6893f-124">Välj **Lägg till** och lägg till de obligatoriska momsmåtten.</span><span class="sxs-lookup"><span data-stu-id="6893f-124">Select **Add**, and add the required tax measures.</span></span>
8. <span data-ttu-id="6893f-125">I åtgärdsrutan väljer du **Spara** och välj sedan **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="6893f-125">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="6893f-126">Stäng sidan och visa den fullständiga versionen av din momskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="6893f-126">Close page, and view the completed version of your tax configuration.</span></span>

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a><span data-ttu-id="6893f-127">Implementera momsfunktioner i den anpassade momskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="6893f-127">Implement tax features in the customized tax configuration</span></span>

1. <span data-ttu-id="6893f-128">I Regulatory Configuration Services (RCS) , gå till **Globaliseringsfunktioner** \> **Moms**.</span><span class="sxs-lookup"><span data-stu-id="6893f-128">In Regulatory Configuration Service (RCS), go to **Globalization Features** \> **Tax**.</span></span>
2. <span data-ttu-id="6893f-129">Välj **Lägg till**, ange information om den nya funktionen och välj sedan **Skapa funktion**.</span><span class="sxs-lookup"><span data-stu-id="6893f-129">Select **Add**, enter information about the new feature, and then select **Create feature**.</span></span>
3. <span data-ttu-id="6893f-130">På fliken **Versioner**, välj funktionen och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="6893f-130">On the **Versions** tab, select the feature, and then select **Edit**.</span></span>
4. <span data-ttu-id="6893f-131">På fliken **Allmänt** i fältet **Konfigurationsversion**, välj den anpassade momskonfigurationen och versionen.</span><span class="sxs-lookup"><span data-stu-id="6893f-131">On the **General** tab, in the **Configuration version** field, select the customized tax configuration and version.</span></span>
5. <span data-ttu-id="6893f-132">I dialogrutan **Hantera kolumner**, markera rubrik- och radkolumnerna som du vill inkludera i din anpassade momsmått och välj sedan högerpil för att lägga till dem i listan **Valda kolumner**.</span><span class="sxs-lookup"><span data-stu-id="6893f-132">In the **Manage columns** dialog box, select the header and line columns that you want to include in your customized tax measure, and then select the right arrow button to add them to the **Selected columns** list.</span></span>
