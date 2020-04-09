---
title: Felsöka problem under första installationen
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som kan uppstå under den första installationen av integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: e20c9c5e1250c8e65b5642a7c45d7ae859315697
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172678"
---
# <a name="troubleshoot-issues-during-initial-setup"></a><span data-ttu-id="976cc-103">Felsöka problem under första installationen</span><span class="sxs-lookup"><span data-stu-id="976cc-103">Troubleshoot issues during initial setup</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="976cc-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="976cc-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="976cc-105">Särskilt innehåller det information som kan hjälpa dig att åtgärda problem som kan uppstå under den första installationen av integrering av dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="976cc-105">Specifically, it provides information that can help you fix issues that might occur during the initial setup of dual-write integration.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="976cc-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="976cc-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="976cc-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="976cc-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-link-a-finance-and-operations-app-to-common-data-service"></a><span data-ttu-id="976cc-108">Du kan inte länka en Finance and Operations-app till Common Data Service</span><span class="sxs-lookup"><span data-stu-id="976cc-108">You can't link a Finance and Operations app to Common Data Service</span></span>

<span data-ttu-id="976cc-109">**Obligatoriska autentiseringsuppgifter för att konfigurera dubbelriktad skrivning:** Azure AD-klientadministratör</span><span class="sxs-lookup"><span data-stu-id="976cc-109">**Required credentials to set up dual-write:** Azure AD tenant admin</span></span>

<span data-ttu-id="976cc-110">Fel på sidan **Konfigurera länk till Common Data Service** orsakas vanligtvis av ofullständiga installations- eller behörighetsproblem.</span><span class="sxs-lookup"><span data-stu-id="976cc-110">Errors on the **Setup link to Common Data Service** page are usually caused by incomplete setup or permissions issues.</span></span> <span data-ttu-id="976cc-111">Kontrollera att hela hälsokontrollen passerar **Konfigurera länk till Common Data Service** som visas i följande illustration.</span><span class="sxs-lookup"><span data-stu-id="976cc-111">Make sure that the whole health check passes on the **Setup link to Common Data Service** page, as shown in the following illustration.</span></span> <span data-ttu-id="976cc-112">Du kan inte länka dubbelriktad skrivning om inte hela hälsokontrollen passerar.</span><span class="sxs-lookup"><span data-stu-id="976cc-112">You can't link dual-write unless the whole health check passes.</span></span>

![Lyckad hälsokontroll](media/health_check.png)

<span data-ttu-id="976cc-114">Du måste ha Azure AD autentiseringsuppgifter för klientadministratör för att länka Finance and Operations och Common Data Service-miljöer.</span><span class="sxs-lookup"><span data-stu-id="976cc-114">You must have Azure AD tenant admin credentials to link the Finance and Operations and Common Data Service environments.</span></span> <span data-ttu-id="976cc-115">När du har länkat miljöerna kan användarna logga in med hjälp av sina kontouppgifter och uppdatera en befintlig entitetskarta.</span><span class="sxs-lookup"><span data-stu-id="976cc-115">After you link the environments, users can sign in by using their account credentials and update an existing entity map.</span></span>

## <a name="error-when-you-open-the-link-to-common-data-service-page"></a><span data-ttu-id="976cc-116">Fel när du öppnar sidan länka till Common Data Service</span><span class="sxs-lookup"><span data-stu-id="976cc-116">Error when you open the Link to Common Data Service page</span></span>

<span data-ttu-id="976cc-117">**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Azure AD klientadministratör</span><span class="sxs-lookup"><span data-stu-id="976cc-117">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="976cc-118">Du kan få följande felmeddelande när du öppnar sidan **Länka till Common Data Service** i en Finance and Operations-app:</span><span class="sxs-lookup"><span data-stu-id="976cc-118">You might receive the following error message when you open the **Link to Common Data Service** page in a Finance and Operations app:</span></span>

<span data-ttu-id="976cc-119">*Svarsstatuskoden anger inte lyckad: 404 (hittades inte).*</span><span class="sxs-lookup"><span data-stu-id="976cc-119">*Response status code does not indicate success: 404 (Not Found).*</span></span>

<span data-ttu-id="976cc-120">Det här felet uppstår när medgivandesteget inte har slutförts.</span><span class="sxs-lookup"><span data-stu-id="976cc-120">This error occurs when the consent step hasn't been completed.</span></span> <span data-ttu-id="976cc-121">För att bekräfta om godkännandesteget är slutfört, logga in på portal.Azure.com med hjälp av Azure AD klientadministratörskontot och se om tredje partens app som har ID **33976c19-1db5-4c02-810e-c243db79efde** visas i listan Azure AD **företagsappar**.</span><span class="sxs-lookup"><span data-stu-id="976cc-121">To validate whether the consent step has been completed, sign in to portal.Azure.com by using the Azure AD tenant admin account, and see whether the third-party app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** appears in the Azure AD **Enterprise applications** list.</span></span> <span data-ttu-id="976cc-122">Om den inte gör det måste du ge appmedgivande.</span><span class="sxs-lookup"><span data-stu-id="976cc-122">If it doesn't, you must provide app consent.</span></span>

<span data-ttu-id="976cc-123">Följ dessa steg för att ge appen samtycke.</span><span class="sxs-lookup"><span data-stu-id="976cc-123">To provide app consent, follow these steps.</span></span>

1. <span data-ttu-id="976cc-124">Öppna följande URL med hjälp av administratörsuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="976cc-124">Open the following URL by using your admin credentials.</span></span> <span data-ttu-id="976cc-125">Du bör uppmanas att ge samtycke.</span><span class="sxs-lookup"><span data-stu-id="976cc-125">You should be prompted for consent.</span></span>

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. <span data-ttu-id="976cc-126">Välj **Acceptera** för att ange att du ger ditt samtycke till att installera appen som har ID **33976c19-1db5-4c02-810e-c243db79efde** i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="976cc-126">Select **Accept** to indicate that you're giving your consent to install the app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** in your tenant.</span></span>

    > [!TIP]
    > <span data-ttu-id="976cc-127">Den här appen krävs för att länka Common Data Service och Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="976cc-127">This app is required to link Common Data Service and Finance and Operations apps.</span></span> <span data-ttu-id="976cc-128">Om du har problem med det här steget öppnar du webbläsaren i inkognitoläge (i Google Chrome) eller InPrivate-läge (i Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="976cc-128">If you have trouble with this step, open your browser in incognito mode (in Google Chrome) or InPrivate mode (in Microsoft Edge).</span></span>

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a><span data-ttu-id="976cc-129">Kontrollera att företagsdata och team med dubbelriktad skrivning är korrekt konfigurerade när du länkar</span><span class="sxs-lookup"><span data-stu-id="976cc-129">Verify that company data and dual-write teams are set up correctly during linking</span></span>

<span data-ttu-id="976cc-130">För att säkerställa att dubbelriktad skrivning fungerar korrekt skapas de företag som du väljer under konfigurationen i Common Data Service-miljön.</span><span class="sxs-lookup"><span data-stu-id="976cc-130">To ensure that dual-write works correctly, the companies that you select during configuration are created in the Common Data Service environment.</span></span> <span data-ttu-id="976cc-131">Som standard är dessa företag skrivskyddade och egenskapen **IsDualWriteEnable** är inställd på **Sant**.</span><span class="sxs-lookup"><span data-stu-id="976cc-131">By default, these companies are read-only, and the **IsDualWriteEnable** property is set to **True**.</span></span> <span data-ttu-id="976cc-132">Dessutom skapas standardägaren och teamet för den ägande affärsenheten och teamet och inkluderar företagsnamnet.</span><span class="sxs-lookup"><span data-stu-id="976cc-132">In addition, the default owning business unit owner and team are created and include the company name.</span></span> <span data-ttu-id="976cc-133">Innan du aktiverar kartorna kontrollerar du att standardteamets ägare har angetts.</span><span class="sxs-lookup"><span data-stu-id="976cc-133">Before you enable the maps, verify that the default team owner is specified.</span></span> <span data-ttu-id="976cc-134">För att hitta entiteten **företag (CDM\_företag)** följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="976cc-134">To find the **Companies (CDM\_Company)** entity, follow these steps.</span></span>

1. <span data-ttu-id="976cc-135">I den modellstyrda appen i Dynamics 365 väljer du filtret i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="976cc-135">In the model-driven app in Dynamics 365, select the filter in the upper-right corner.</span></span>
2. <span data-ttu-id="976cc-136">Välj **Företag** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="976cc-136">In the drop-down list, select **Company**.</span></span>
3. <span data-ttu-id="976cc-137">Välj **Kör** om du vill visa resultatet.</span><span class="sxs-lookup"><span data-stu-id="976cc-137">Select **Run** to see the results.</span></span>
4. <span data-ttu-id="976cc-138">Välj det företag som länkades när du konfigurerade dubbelskrivning.</span><span class="sxs-lookup"><span data-stu-id="976cc-138">Select the company that was linked when you configured dual-write.</span></span>
5. <span data-ttu-id="976cc-139">Kontrollera att fältet **standardägargrupp** har ett värde.</span><span class="sxs-lookup"><span data-stu-id="976cc-139">Verify that the **Default owning team** field has a value.</span></span> <span data-ttu-id="976cc-140">I bilden nedan är fältet **standardägargrupp** anges till **USMF dubbelriktad skrivning**.</span><span class="sxs-lookup"><span data-stu-id="976cc-140">In the following illustration, the **Default owning team** field is set to **USMF Dual Write**.</span></span>

    ![Verifiera standardägargruppen](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-entities-or-companies-that-can-be-linked-for-dual-write"></a><span data-ttu-id="976cc-142">Hitta gränsen för antalet juridiska personer eller företag som kan länkas för dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="976cc-142">Find the limit on the number of legal entities or companies that can be linked for dual-write</span></span>

<span data-ttu-id="976cc-143">Följande felmeddelande kan visas när du försöker att aktivera kartor:</span><span class="sxs-lookup"><span data-stu-id="976cc-143">You might receive the following error message when you try to enable maps:</span></span>

<span data-ttu-id="976cc-144">*Del i dubbelriktad skrivning - registrering av plugin-program misslyckades: \[(Det gick inte att skaffa karta över partitioner för projekt-DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Felet överskrider högsta antal tillåtna partitioner för mappning av DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], ett eller flera fel uppstod.*</span><span class="sxs-lookup"><span data-stu-id="976cc-144">*Dual write failure - Plugin registration failed: \[(Unable to get partition map for project DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Exceeds the maximum partitions allowed for mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], One or more errors occurred.*</span></span>

<span data-ttu-id="976cc-145">Den aktuella gränsen när du länkar miljöer är ungefär 40 juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="976cc-145">The current limit when you link the environments is approximately 40 legal entities.</span></span> <span data-ttu-id="976cc-146">Det här felet uppstår om du försöker aktivera mappningar och mer än 40 juridiska personer är länkade mellan miljöer.</span><span class="sxs-lookup"><span data-stu-id="976cc-146">This error occurs if you try to enable maps, and more than 40 legal entities are linked between the environments.</span></span>
