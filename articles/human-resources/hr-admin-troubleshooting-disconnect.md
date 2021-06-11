---
title: Klienten kopplas från
description: Det här avsnittet beskriver vad du gör om kunden kopplas från miljön och inte vet varför.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fcb7e5e3230aee9f6c04e4854c8eea836ae14c7f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053429"
---
# <a name="client-disconnects"></a><span data-ttu-id="3f671-103">Klienten kopplas från</span><span class="sxs-lookup"><span data-stu-id="3f671-103">Client disconnects</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3f671-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="3f671-104">**Environment details**</span></span> 

<span data-ttu-id="3f671-105">Detta problem kan inträffa i alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="3f671-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="3f671-106">**Symptom**</span><span class="sxs-lookup"><span data-stu-id="3f671-106">**Symptom**</span></span> 

<span data-ttu-id="3f671-107">Kunden kopplas från miljön och vet inte varför.</span><span class="sxs-lookup"><span data-stu-id="3f671-107">The customer is disconnected from the environment and doesn't know why.</span></span> <span data-ttu-id="3f671-108">Kunden får ett av följande felmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="3f671-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="3f671-109">Anslutningen har kopplats från.</span><span class="sxs-lookup"><span data-stu-id="3f671-109">We've lost your connection.</span></span> <span data-ttu-id="3f671-110">Klicka på Stäng om du vill fortsätta arbeta.</span><span class="sxs-lookup"><span data-stu-id="3f671-110">Click Close to continue working.</span></span>
- <span data-ttu-id="3f671-111">Det verkar som att du tappat anslutningen till nätverket. Klicka på Försök igen.</span><span class="sxs-lookup"><span data-stu-id="3f671-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="3f671-112">**Röd flagga**</span><span class="sxs-lookup"><span data-stu-id="3f671-112">**Red flag**</span></span>

<span data-ttu-id="3f671-113">Det här problemet uppstår ofta när användare befinner sig i implementeringssteget, jämför information mellan produktions- och testmiljöer och har glömt att de flyttar mellan sessioner.</span><span class="sxs-lookup"><span data-stu-id="3f671-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="3f671-114">Om en användare befinner sig i det här steget kommer de sannolikt uppleva detta problem.</span><span class="sxs-lookup"><span data-stu-id="3f671-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="3f671-115">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="3f671-115">**Issue**</span></span> 

<span data-ttu-id="3f671-116">**Webbläsartyper:** Google Chrome, Internet Explorer och Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3f671-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="3f671-117">Microsoft Dynamics 365 Human Resources kopplar från användare när två olika sessioner öppnas samtidigt för samma användare och samma webbläsartyp.</span><span class="sxs-lookup"><span data-stu-id="3f671-117">Microsoft Dynamics 365 Human Resources disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="3f671-118">(T.ex. användare A visar både miljö 1 och miljö 2 i Chrome.) Det spelar ingen roll om användarna öppnar olika webbläsarfönster eller olika flikar.</span><span class="sxs-lookup"><span data-stu-id="3f671-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="3f671-119">Om samma användarautentisering används för att logga in på både miljö 1 och miljö 2 samtidigt och i samma webbläsartyp, kopplar Personal från en av sessionerna.</span><span class="sxs-lookup"><span data-stu-id="3f671-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Human Resources disconnects one of the sessions.</span></span>

<span data-ttu-id="3f671-120">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="3f671-120">**Solution**</span></span>

<span data-ttu-id="3f671-121">Kontrollera att endast en miljö är öppen i taget för en viss webbläsartyp.</span><span class="sxs-lookup"><span data-stu-id="3f671-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="3f671-122">Användare kan öppna flera sessioner till samma miljö (det vill säga flera flikar i samma webbläsare).</span><span class="sxs-lookup"><span data-stu-id="3f671-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="3f671-123">Användare som vill hoppa mellan två miljöer samtidigt ska öppna varje miljö i olika webbläsartyper.</span><span class="sxs-lookup"><span data-stu-id="3f671-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="3f671-124">(T.ex. användare A kan visa miljö 1 i Chrome och miljö 2 i Microsoft Edge.)</span><span class="sxs-lookup"><span data-stu-id="3f671-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]