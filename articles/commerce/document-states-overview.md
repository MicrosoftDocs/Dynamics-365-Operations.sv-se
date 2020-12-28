---
title: Dokumentera tillstånd och livscykel
description: I det här avsnittet beskrivs olika dokumentlägen för sidelement i Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
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
ms.openlocfilehash: 8aad7ef8425e46182c669686710dfc178abc418f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415837"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="4f136-103">Dokumentera tillstånd och livscykel</span><span class="sxs-lookup"><span data-stu-id="4f136-103">Document states and lifecycle</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4f136-104">I det här avsnittet beskrivs olika dokumentlägen för sidelement i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4f136-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="4f136-105">Dokumenttillståndbeskrivning</span><span class="sxs-lookup"><span data-stu-id="4f136-105">Document state descriptions</span></span>

<span data-ttu-id="4f136-106">I avsnittet [sidelement](page-elements-overview.md) visas olika dokumenttyper i innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="4f136-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="4f136-107">Dessa dokumenttyper kan ha flera lägen i redigeringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="4f136-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="4f136-108">Dokumenttillstånd bidrar till att förhindra datakonflikter och att använda versionskontroll.</span><span class="sxs-lookup"><span data-stu-id="4f136-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="4f136-109">De bestämmer vem som kan ändra dokumenten, när dokumenten kan ändras och när andra personer kan visa dem.</span><span class="sxs-lookup"><span data-stu-id="4f136-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="4f136-110">I följande tabell visas de möjliga dokumenttillstånden för sidelement i handel.</span><span class="sxs-lookup"><span data-stu-id="4f136-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="4f136-111">Dokumenttillstånd</span><span class="sxs-lookup"><span data-stu-id="4f136-111">Document state</span></span>      | <span data-ttu-id="4f136-112">Åtgärd för webbplatsskaparen</span><span class="sxs-lookup"><span data-stu-id="4f136-112">Site builder action</span></span>        | <span data-ttu-id="4f136-113">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4f136-113">Description</span></span>                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="4f136-114">Utcheckad</span><span class="sxs-lookup"><span data-stu-id="4f136-114">Checked out</span></span>         | <span data-ttu-id="4f136-115">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="4f136-115">Select **Edit**.</span></span>           | <span data-ttu-id="4f136-116">Det tillämpliga dokumentet är utcheckat till dig.</span><span class="sxs-lookup"><span data-stu-id="4f136-116">The applicable document is checked out to you.</span></span> <span data-ttu-id="4f136-117">När ett dokument är i det här tillståndet kan det inte ändras av andra autentiserade systemanvändare, och alla ändringar som du gör i dokumentet visas bara för dig.</span><span class="sxs-lookup"><span data-stu-id="4f136-117">While a document is in this state, it can't be changed by other authenticated system users, and any changes that you make to the document are visible only to you.</span></span> |
| <span data-ttu-id="4f136-118">Sparades</span><span class="sxs-lookup"><span data-stu-id="4f136-118">Saved</span></span>               | <span data-ttu-id="4f136-119">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4f136-119">Select **Save**.</span></span>           | <span data-ttu-id="4f136-120">Ändringar som har gjorts i ett utcheckat dokument sparas i databasen men dokumentet har inte checkats in eller publicerats.</span><span class="sxs-lookup"><span data-stu-id="4f136-120">Changes that have been made to a checked-out document are saved to the database, but the document isn't yet checked in or published.</span></span> <span data-ttu-id="4f136-121">De sparade ändringarna syns inte för andra autentiserade systemanvändare förrän författaren väljer **Avsluta redigering**.</span><span class="sxs-lookup"><span data-stu-id="4f136-121">The saved changes aren't visible to other authenticated system users until the author selects **Finish editing**.</span></span> <span data-ttu-id="4f136-122">De visas inte för externa användare förrän objektet har publicerats.</span><span class="sxs-lookup"><span data-stu-id="4f136-122">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="4f136-123">Ignorerade utcheckning</span><span class="sxs-lookup"><span data-stu-id="4f136-123">Discarded check out</span></span> | <span data-ttu-id="4f136-124">Välj **ignorera redigeringar**.</span><span class="sxs-lookup"><span data-stu-id="4f136-124">Select **Discard edits**.</span></span>  | <span data-ttu-id="4f136-125">Alla ändringar av det utcheckade dokumentet ignoreras och objektet återgår till den senast incheckade versionen.</span><span class="sxs-lookup"><span data-stu-id="4f136-125">All changes to the checked-out document are discarded, and the item reverts to the last version that was checked in.</span></span> |
| <span data-ttu-id="4f136-126">Incheckad</span><span class="sxs-lookup"><span data-stu-id="4f136-126">Checked in</span></span>          | <span data-ttu-id="4f136-127">Välj **Slutför redigering**.</span><span class="sxs-lookup"><span data-stu-id="4f136-127">Select **Finish editing**.</span></span> | <span data-ttu-id="4f136-128">Det redigerade dokumentet är incheckat.</span><span class="sxs-lookup"><span data-stu-id="4f136-128">The edited document is checked in.</span></span> <span data-ttu-id="4f136-129">Alla ändringar är synliga för andra autentiserade systemanvändare och dessa användare kan sedan redigera dokumentet.</span><span class="sxs-lookup"><span data-stu-id="4f136-129">All changes are visible to other authenticated system users, and those users can then edit the document.</span></span> <span data-ttu-id="4f136-130">Varje incheckning skapar en dokumentversionspost i historiken för artikeln.</span><span class="sxs-lookup"><span data-stu-id="4f136-130">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="4f136-131">Publicerat</span><span class="sxs-lookup"><span data-stu-id="4f136-131">Published</span></span>           | <span data-ttu-id="4f136-132">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="4f136-132">Select **Publish**.</span></span>        | <span data-ttu-id="4f136-133">Dokumentet publiceras och ändringarna överförs till den aktiva webbplatsen och blir synliga för externa användare.</span><span class="sxs-lookup"><span data-stu-id="4f136-133">The document is published, and the changes are pushed to your live site and become discoverable by external users.</span></span> <span data-ttu-id="4f136-134">Artiklar kan bara publiceras om de har checkats in först genom att du väljer **Slutför redigering**.</span><span class="sxs-lookup"><span data-stu-id="4f136-134">Items can be published only if they have first been checked in by selecting **Finish editing**.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="4f136-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4f136-135">Additional resources</span></span>

[<span data-ttu-id="4f136-136">Sätt att lägga till innehåll</span><span class="sxs-lookup"><span data-stu-id="4f136-136">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="4f136-137">Ordlista för sidmodell</span><span class="sxs-lookup"><span data-stu-id="4f136-137">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="4f136-138">Arbeta med publiceringsgrupper</span><span class="sxs-lookup"><span data-stu-id="4f136-138">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="4f136-139">Aktivera och använda delning av flera kanaler</span><span class="sxs-lookup"><span data-stu-id="4f136-139">Enable and use cross-channel sharing</span></span>](cross-channel-sharing.md)

[<span data-ttu-id="4f136-140">Arbeta med moduler</span><span class="sxs-lookup"><span data-stu-id="4f136-140">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="4f136-141">Arbeta med fragment</span><span class="sxs-lookup"><span data-stu-id="4f136-141">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="4f136-142">Översikt över mallar och layouter</span><span class="sxs-lookup"><span data-stu-id="4f136-142">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="4f136-143">Anpassa webbplatsnavigeringen</span><span class="sxs-lookup"><span data-stu-id="4f136-143">Customize site navigation</span></span>](customize-site-navigation.md)
