---
title: Dynamics 365 Commerce och Microsoft Teams-integrering, översikt
description: Det här ämnet innehåller en översikt över Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3b7872757815d4eec0393e8b1c8c6ff5467e9473
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842744"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a><span data-ttu-id="9d22a-103">Dynamics 365 Commerce och Microsoft Teams-integrering, översikt</span><span class="sxs-lookup"><span data-stu-id="9d22a-103">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="9d22a-104">Det här ämnet innehåller en översikt över Microsoft Dynamics 365 Commerce och Microsoft Teams-integration.</span><span class="sxs-lookup"><span data-stu-id="9d22a-104">This topic presents an overview of Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="9d22a-105">Dynamics 365 Commerce integrerar med Teams för att hjälpa kunder och deras medarbetare att förbättra produktiviteten genom att synkronisera uppgiftshantering mellan de två programmen.</span><span class="sxs-lookup"><span data-stu-id="9d22a-105">Dynamics 365 Commerce is integrating with Teams to help customers and their employees improve productivity by synchronizing task management between the two applications.</span></span> <span data-ttu-id="9d22a-106">Den sömlösa uppgiftshantering som Commerce and Teams-integrationen tillhandahåller, gör att butikschefer och medarbetare kan skapa uppgiftslistor, tilldela uppgifter till flera butiker och spåra status för uppgifter mellan butiker, från antingen programmet eller program.</span><span class="sxs-lookup"><span data-stu-id="9d22a-106">The seamless task management that Commerce and Teams integration provides lets store managers and employees create task lists, assign tasks to multiple stores, and track the status of tasks across stores, from either application.</span></span>

<span data-ttu-id="9d22a-107">Commerce and Teams-integration är tillgänglig i Commerce version 10.0.18 som finns tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9d22a-107">Commerce and Teams integration is available as of the Commerce version 10.0.18 release.</span></span>

## <a name="key-features"></a><span data-ttu-id="9d22a-108">Nyckelfunktioner</span><span class="sxs-lookup"><span data-stu-id="9d22a-108">Key features</span></span>

<span data-ttu-id="9d22a-109">Här är några av de nyckelfunktioner som finns i Commerce och Microsoft Teams-integration:</span><span class="sxs-lookup"><span data-stu-id="9d22a-109">Here are some of the key features that the Commerce and Microsoft Teams integration provides:</span></span>

- <span data-ttu-id="9d22a-110">Etablera Teams genom att dra nytta av väldefinierad information från Commerce, till exempel organisationsstrukturen och information om butiker, arbetare, behörigheter och affärssammanhang.</span><span class="sxs-lookup"><span data-stu-id="9d22a-110">Provision Teams by taking advantage of well-defined information from Commerce, such as the organizational structure and information about stores, workers, permissions, and business context.</span></span>
- <span data-ttu-id="9d22a-111">Synkronisera enkelt pågående ändringar (till exempel tillägg av nya butiker eller anställning av nya medarbetare) mellan Commerce och Teams, men behåll Commerce som huvudkälla för organisationsstrukturdata.</span><span class="sxs-lookup"><span data-stu-id="9d22a-111">Easily synchronize ongoing changes (for example, the addition of new stores or hiring of new employees) between Commerce and Teams, but keep Commerce as the master source of organizational structure data.</span></span>
- <span data-ttu-id="9d22a-112">Integrera uppgiftshantering mellan Commerce och Teams om du vill hjälpa butiksarbetare, butikschefer, regionala chefer och kommunikationschefer att hantera uppgiftshantering från antingen program.</span><span class="sxs-lookup"><span data-stu-id="9d22a-112">Integrate task management between Commerce and Teams to help store workers, store managers, regional managers, and communications managers handle task management from either application.</span></span>

## <a name="prerequisites-for-using-integration-features"></a><span data-ttu-id="9d22a-113">Förutsättningar för användning av integrationsfunktioner</span><span class="sxs-lookup"><span data-stu-id="9d22a-113">Prerequisites for using integration features</span></span>

<span data-ttu-id="9d22a-114">Följande förutsättningar måste uppfyllas innan du kan börja använda Microsoft Teams integrationsfunktionerna:</span><span class="sxs-lookup"><span data-stu-id="9d22a-114">The following prerequisites must be in place before you can start to use Microsoft Teams integration features:</span></span>

- <span data-ttu-id="9d22a-115">Microsoft 365 Business Standard-licens (denna licens inkluderar Teams.)</span><span class="sxs-lookup"><span data-stu-id="9d22a-115">Microsoft 365 Business Standard License (This license includes Teams.)</span></span>
- <span data-ttu-id="9d22a-116">Azure Active Directory ( Azure AD) konton för alla butikschefer och medarbetare</span><span class="sxs-lookup"><span data-stu-id="9d22a-116">Azure Active Directory (Azure AD) accounts for all store managers and workers</span></span>
- <span data-ttu-id="9d22a-117">Kassasystem som är konfigurerade med Azure AD-autentisering</span><span class="sxs-lookup"><span data-stu-id="9d22a-117">Point of sale (POS) systems that are configured with Azure AD authentication</span></span>

## <a name="conceptual-architecture"></a><span data-ttu-id="9d22a-118">Konceptuell arkitektur</span><span class="sxs-lookup"><span data-stu-id="9d22a-118">Conceptual architecture</span></span>

<span data-ttu-id="9d22a-119">följande bild visas den konceptuella arkitekturen för Dynamics 365 Commerce och Microsoft Teams-integration, med en San Francisco-butik som exempel.</span><span class="sxs-lookup"><span data-stu-id="9d22a-119">The following illustration shows the conceptual architecture of Dynamics 365 Commerce and Microsoft Teams integration, using a San Francisco store as an example.</span></span> <span data-ttu-id="9d22a-120">Både Teams och kassaprogrammet Commerce använder Microsoft Planner som en databas så att uppgifter som publiceras från Teams visas i kassaprogrammet och ad hoc-uppgifter som skapas av butikschefer i kassaprogrammet visas i Teams, vilket leder till en sömlös uppgiftshanteringserfarenhet mellan programmen.</span><span class="sxs-lookup"><span data-stu-id="9d22a-120">Both Teams and the Commerce POS application use Microsoft Planner as a repository so that tasks published from Teams appear in the POS application and ad hoc tasks created by store managers in the POS application appear in Teams, resulting in a seamless task management experience between the applications.</span></span>    

![Arkitektur för Commerce och Teams-integration](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a><span data-ttu-id="9d22a-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9d22a-122">Additional resources</span></span>

[<span data-ttu-id="9d22a-123">Aktivera Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="9d22a-123">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="9d22a-124">Provision Microsoft Teams från Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9d22a-124">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="9d22a-125">Synkronisera uppgiftshantering mellan Microsoft Teams och Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="9d22a-125">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="9d22a-126">Hantera användarroller i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d22a-126">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="9d22a-127">Mappa butiker och team om det finns befintliga team i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d22a-127">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="9d22a-128">Vanliga frågor och svar om Dynamics 365 Commerce och Microsoft Teams-integration</span><span class="sxs-lookup"><span data-stu-id="9d22a-128">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
