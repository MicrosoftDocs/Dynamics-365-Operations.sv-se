---
title: Felsöka problem relaterade till lösningsmedvetenhet
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som är relaterade till lösningsmedvetenhet.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 7f1a6e424996201ecae1b624c13cfc573745dc0a
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997288"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="a55f8-103">Felsöka problem relaterade till lösningsmedvetenhet</span><span class="sxs-lookup"><span data-stu-id="a55f8-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="a55f8-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a55f8-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="a55f8-105">Det här avsnittet innehåller specifikt information som kan hjälpa dig att åtgärda problem som är relaterade till lösningsmedvetenhet.</span><span class="sxs-lookup"><span data-stu-id="a55f8-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a55f8-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="a55f8-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="a55f8-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="a55f8-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="a55f8-108">Fel på sidan dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="a55f8-108">Error on the Dual-write page</span></span>

<span data-ttu-id="a55f8-109">På sidan **dubbelriktad skrivning** kan du få ett felmeddelande som liknar följande exempel:</span><span class="sxs-lookup"><span data-stu-id="a55f8-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="a55f8-110">*Entiteten med namnet 'msdyn\_dualwriteentitymap' with namemapping='Logical' hittades inte i MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="a55f8-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="a55f8-111">Lös problemet genom att kontrollera att kärnlösningen för dubbelriktad skrivning är installerad i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a55f8-111">To fix the issue, make sure that the dual-write core solution is installed in Common Data Service.</span></span> <span data-ttu-id="a55f8-112">Kärnlösningen för dubbelriktad skrivning är en förutsättning för lösningsmedvetenhet.</span><span class="sxs-lookup"><span data-stu-id="a55f8-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>
