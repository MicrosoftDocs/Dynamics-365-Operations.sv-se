---
title: Aktivera Broadbean-integrering i Microsoft Dynamics 365 Talent - Attract
description: I det här avsnittet beskriver hur du konfigurerar Microsoft Dynamics 365 Talent - Attract för att publicera jobb på externa jobbtavlor som t.ex. Broadbean.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 808f91fb4b68ba9b5cee54d86423d23232df23a4
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008603"
---
# <a name="enable-broadbean-integration"></a><span data-ttu-id="d3d04-103">Aktivera Broadbean-integration</span><span class="sxs-lookup"><span data-stu-id="d3d04-103">Enable Broadbean integration</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d3d04-104">Du vill få dina lediga befattningar framför så många kvalificerade kandidater som möjligt.</span><span class="sxs-lookup"><span data-stu-id="d3d04-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="d3d04-105">Rekryteringswebbplatser som Broadbean hjälper dig att uppnå det här målet.</span><span class="sxs-lookup"><span data-stu-id="d3d04-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="d3d04-106">Microsoft Dynamics 365 Talent: Attract låter dig nu publicera jobb på Broadbean och Microsoft tillhandahåller ständigt nya erbjudanden inom detta område.</span><span class="sxs-lookup"><span data-stu-id="d3d04-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

> [!NOTE]
> - <span data-ttu-id="d3d04-107">Om du vill skicka jobb till externa platser måste du ha [tillägget för omfattande anställning](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="d3d04-107">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="d3d04-108">Om du vill bokföra jobb på Broadbean via Attract måste du ha ett Broadbean-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="d3d04-108">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="d3d04-109">Den här funktionen är för närvarande i förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="d3d04-109">This feature is currently in preview.</span></span> <span data-ttu-id="d3d04-110">Om du vill prova den måste du [aktivera den i Attract administrationsinställningar](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="d3d04-110">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

## <a name="configure-broadbean-integration"></a><span data-ttu-id="d3d04-111">Konfigurera Broadbean-integration</span><span class="sxs-lookup"><span data-stu-id="d3d04-111">Configure Broadbean integration</span></span>

1. <span data-ttu-id="d3d04-112">Logga in på Attract som en administratör.</span><span class="sxs-lookup"><span data-stu-id="d3d04-112">Sign in to Attract as an admin.</span></span>

2. <span data-ttu-id="d3d04-113">Välj knappen **inställningar** (växelsymbol) i det övre högra hörnet på sidan och välj sedan **administratörscenter**.</span><span class="sxs-lookup"><span data-stu-id="d3d04-113">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>

3. <span data-ttu-id="d3d04-114">Kontakta Broadbean och skriv sedan in informationen i fälten **Användarnamn**, **klient-ID** och **krypteringstoken**.</span><span class="sxs-lookup"><span data-stu-id="d3d04-114">Contact Broadbean, and enter your information in the **Username**, **Client ID**, and **Encryption Token** fields.</span></span>

4. <span data-ttu-id="d3d04-115">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d3d04-115">Select **Save**.</span></span>

> [!WARNING]
> <span data-ttu-id="d3d04-116">Inloggningsinformationen för Broadbean är känslig och konfidentiell.</span><span class="sxs-lookup"><span data-stu-id="d3d04-116">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="d3d04-117">Därför ska den sparas och delas ansvarsfullt.</span><span class="sxs-lookup"><span data-stu-id="d3d04-117">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="d3d04-118">Alla som har en administratörsroll i Attract kan visa denna inloggningsinformation.</span><span class="sxs-lookup"><span data-stu-id="d3d04-118">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="d3d04-119">Microsoft och Attract är inte involverade i att skapa och underhålla dessa värden.</span><span class="sxs-lookup"><span data-stu-id="d3d04-119">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="d3d04-120">Det är ditt ansvar att hålla dem uppdaterade i Attract och arbeta med Broadbean för att åtgärda problem som rör dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d3d04-120">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>
