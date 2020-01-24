---
title: Dokumentera tillstånd och livscykel
description: I det här avsnittet beskrivs olika dokumentlägen för sidelement i Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: edb81efc45fc5e7eed32cb7d9b8fda5ade987dd4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914897"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="066d4-103">Dokumentera tillstånd och livscykel</span><span class="sxs-lookup"><span data-stu-id="066d4-103">Document states and lifecycle</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="066d4-104">I det här avsnittet beskrivs olika dokumentlägen för sidelement i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="066d4-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="066d4-105">Dokumenttillståndbeskrivning</span><span class="sxs-lookup"><span data-stu-id="066d4-105">Document state descriptions</span></span>

<span data-ttu-id="066d4-106">I avsnittet [sidelement](page-elements-overview.md) visas olika dokumenttyper i innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="066d4-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="066d4-107">Dessa dokumenttyper kan ha flera lägen i redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="066d4-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="066d4-108">Dokumenttillstånd bidrar till att förhindra datakonflikter och att använda versionskontroll.</span><span class="sxs-lookup"><span data-stu-id="066d4-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="066d4-109">De bestämmer vem som kan ändra dokumenten, när dokumenten kan ändras och när andra personer kan visa dem.</span><span class="sxs-lookup"><span data-stu-id="066d4-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="066d4-110">I följande tabell visas de möjliga dokumenttillstånden för sidelement i handel.</span><span class="sxs-lookup"><span data-stu-id="066d4-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="066d4-111">Dokumenttillstånd</span><span class="sxs-lookup"><span data-stu-id="066d4-111">Document state</span></span> | <span data-ttu-id="066d4-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="066d4-112">Description</span></span> |
|---|---|
| <span data-ttu-id="066d4-113">Utcheckad</span><span class="sxs-lookup"><span data-stu-id="066d4-113">Checked out</span></span> | <span data-ttu-id="066d4-114">När ett CMS-objekt är utcheckat till dig kan det inte redigeras av andra autentiserade systemanvändare.</span><span class="sxs-lookup"><span data-stu-id="066d4-114">When a CMS item is checked out to you, it can't be edited by any other authenticated system users.</span></span> <span data-ttu-id="066d4-115">Alla ändringar du gör i objektet är bara synliga för dig.</span><span class="sxs-lookup"><span data-stu-id="066d4-115">Any changes that you make to the item are visible only to you.</span></span> |
| <span data-ttu-id="066d4-116">Incheckad</span><span class="sxs-lookup"><span data-stu-id="066d4-116">Checked in</span></span> | <span data-ttu-id="066d4-117">När ett CMS-objekt checkas in, visas alla ändringar för andra autentiserade systemanvändare och dessa användare kan sedan checka ut objektet och redigera det.</span><span class="sxs-lookup"><span data-stu-id="066d4-117">When a CMS item is checked in, all changes are visible to other authenticated system users, and those users can then check out the item and edit it.</span></span> <span data-ttu-id="066d4-118">Varje incheckning skapar en dokumentversionspost i historiken för artikeln.</span><span class="sxs-lookup"><span data-stu-id="066d4-118">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="066d4-119">Publicerad</span><span class="sxs-lookup"><span data-stu-id="066d4-119">Published</span></span> | <span data-ttu-id="066d4-120">När ett CMS-objekt publiceras flyttas det till den aktiva platsen och kan upptäckas på Internet av icke-autentiserade externa användare.</span><span class="sxs-lookup"><span data-stu-id="066d4-120">When a CMS item is published, it's pushed to your live site and becomes discoverable on the internet by non-authenticated external users.</span></span> <span data-ttu-id="066d4-121">Artiklar kan bara publiceras om de har checkats in.</span><span class="sxs-lookup"><span data-stu-id="066d4-121">Items can be published only if they have been checked in.</span></span> |
| <span data-ttu-id="066d4-122">Sparade</span><span class="sxs-lookup"><span data-stu-id="066d4-122">Saved</span></span> | <span data-ttu-id="066d4-123">Ändringar som har gjorts i ett utcheckat CMS-objekt kan sparas till CMS-filen innan objektet checkas in eller publiceras.</span><span class="sxs-lookup"><span data-stu-id="066d4-123">Changes that have been made to a checked-out CMS item can be saved to the CMS before the item is checked in or published.</span></span> <span data-ttu-id="066d4-124">De sparade ändringarna syns inte för andra autentiserade systemanvändare förrän objektet checkas in.</span><span class="sxs-lookup"><span data-stu-id="066d4-124">These saved changes aren't visible to other authenticated system users until the item is checked in.</span></span> <span data-ttu-id="066d4-125">De visas inte för externa användare förrän objektet har publicerats.</span><span class="sxs-lookup"><span data-stu-id="066d4-125">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="066d4-126">Ignorerade utcheckning</span><span class="sxs-lookup"><span data-stu-id="066d4-126">Discarded check out</span></span> | <span data-ttu-id="066d4-127">När ett utcheckat CMS-objekt ignoreras tas alla sparade ändringar bort och objektet återgår till den senaste incheckade versionen.</span><span class="sxs-lookup"><span data-stu-id="066d4-127">When a checked-out CMS item is discarded, all saved changes are deleted, and the item reverts to the version that was most recently checked in.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="066d4-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="066d4-128">Additional resources</span></span>

[<span data-ttu-id="066d4-129">Sätt att lägga till innehåll</span><span class="sxs-lookup"><span data-stu-id="066d4-129">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="066d4-130">Ordlista för sidmodell</span><span class="sxs-lookup"><span data-stu-id="066d4-130">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="066d4-131">Arbeta med publiceringsgrupper</span><span class="sxs-lookup"><span data-stu-id="066d4-131">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="066d4-132">Arbeta med moduler</span><span class="sxs-lookup"><span data-stu-id="066d4-132">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="066d4-133">Arbeta med fragment</span><span class="sxs-lookup"><span data-stu-id="066d4-133">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="066d4-134">Översikt över mallar och layouter</span><span class="sxs-lookup"><span data-stu-id="066d4-134">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="066d4-135">Anpassa webbplatsnavigeringen</span><span class="sxs-lookup"><span data-stu-id="066d4-135">Customize site navigation</span></span>](customize-site-navigation.md)