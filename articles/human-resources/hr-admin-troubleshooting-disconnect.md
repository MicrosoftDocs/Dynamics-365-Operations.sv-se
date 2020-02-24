---
title: Klienten kopplas från
description: Det här avsnittet beskriver vad du gör om kunden kopplas från sin miljö och inte vet varför.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.article: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 73f0c31d5153a82651ed77aa37bc10966ce7c9b1
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010570"
---
# <a name="client-disconnects"></a><span data-ttu-id="f8a76-103">Klienten kopplas från</span><span class="sxs-lookup"><span data-stu-id="f8a76-103">Client disconnects</span></span>

<span data-ttu-id="f8a76-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="f8a76-104">**Environment details**</span></span> 

<span data-ttu-id="f8a76-105">Detta problem kan inträffa i alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="f8a76-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="f8a76-106">**Symptom**</span><span class="sxs-lookup"><span data-stu-id="f8a76-106">**Symptom**</span></span> 

<span data-ttu-id="f8a76-107">Kunden kopplas från sin miljö och inte vet varför.</span><span class="sxs-lookup"><span data-stu-id="f8a76-107">The customer is disconnected from his or her environment and doesn't know why.</span></span> <span data-ttu-id="f8a76-108">Kunden får ett av följande felmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="f8a76-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="f8a76-109">Anslutningen har kopplats från.</span><span class="sxs-lookup"><span data-stu-id="f8a76-109">We've lost your connection.</span></span> <span data-ttu-id="f8a76-110">Klicka på Stäng om du vill fortsätta arbeta.</span><span class="sxs-lookup"><span data-stu-id="f8a76-110">Click Close to continue working.</span></span>
- <span data-ttu-id="f8a76-111">Det verkar som att du tappat anslutningen till nätverket. Klicka på Försök igen.</span><span class="sxs-lookup"><span data-stu-id="f8a76-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="f8a76-112">**Röd flagga**</span><span class="sxs-lookup"><span data-stu-id="f8a76-112">**Red flag**</span></span>

<span data-ttu-id="f8a76-113">Det här problemet uppstår ofta när användare befinner sig i implementeringssteget, jämför information mellan produktions- och testmiljöer och har glömt att de flyttar mellan sessioner.</span><span class="sxs-lookup"><span data-stu-id="f8a76-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="f8a76-114">Om en användare befinner sig i det här steget kommer de sannolikt uppleva detta problem.</span><span class="sxs-lookup"><span data-stu-id="f8a76-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="f8a76-115">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="f8a76-115">**Issue**</span></span> 

<span data-ttu-id="f8a76-116">**Webbläsartyper:** Google Chrome, Internet Explorer och Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f8a76-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="f8a76-117">Microsoft Dynamics 365 Human Resources kopplar från användare när två olika sessioner öppnas samtidigt för samma användare och samma webbläsartyp.</span><span class="sxs-lookup"><span data-stu-id="f8a76-117">Microsoft Dynamics 365 Human Resources disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="f8a76-118">(T.ex. användare A visar både miljö 1 och miljö 2 i Chrome.) Det spelar ingen roll om användarna öppnar olika webbläsarfönster eller olika flikar.</span><span class="sxs-lookup"><span data-stu-id="f8a76-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="f8a76-119">Om samma användarautentisering används för att logga in på både miljö 1 och miljö 2 samtidigt och i samma webbläsartyp, kopplar Personal från en av sessionerna.</span><span class="sxs-lookup"><span data-stu-id="f8a76-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Human Resources disconnects one of the sessions.</span></span>

<span data-ttu-id="f8a76-120">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="f8a76-120">**Solution**</span></span>

<span data-ttu-id="f8a76-121">Kontrollera att endast en miljö är öppen i taget för en viss webbläsartyp.</span><span class="sxs-lookup"><span data-stu-id="f8a76-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="f8a76-122">Användare kan öppna flera sessioner till samma miljö (det vill säga flera flikar i samma webbläsare).</span><span class="sxs-lookup"><span data-stu-id="f8a76-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="f8a76-123">Användare som vill hoppa mellan två miljöer samtidigt ska öppna varje miljö i olika webbläsartyper.</span><span class="sxs-lookup"><span data-stu-id="f8a76-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="f8a76-124">(T.ex. användare A kan visa miljö 1 i Chrome och miljö 2 i Microsoft Edge.)</span><span class="sxs-lookup"><span data-stu-id="f8a76-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>
