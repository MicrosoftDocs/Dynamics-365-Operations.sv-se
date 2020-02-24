---
title: Hantera funktioner
description: Det här avsnittet beskriver hur en administratör kan aktivera funktionen förhandsgranska i Microsoft Dynamics 365 Talent och visar funktionerna som är aktiverade för förhandsgranskning.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.1.0, Talent
ms.openlocfilehash: d818e9e04ce88e5ab285ef8176334809447fb477
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006441"
---
# <a name="manage-features"></a><span data-ttu-id="0a5c3-103">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="0a5c3-103">Manage features</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0a5c3-104">Som en del av vår kontinuerliga distribution av HR-hanteringsfunktioner (HCM) för Microsoft Dynamics 365 Human Resources, vill vi att kunder får nya funktioner så snart som möjligt.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-104">As part of our continuous rollout of human capital management (HCM) capabilities for Microsoft Dynamics 365 Human Resources, we want to let customers experience new features as soon as possible.</span></span> <span data-ttu-id="0a5c3-105">Administratörer kan se och använda funktioner för förhandsgranskning i datormiljön.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-105">Administrators can see and use preview features in their environments.</span></span> <span data-ttu-id="0a5c3-106">Dessa funktioner kan snart allmänt tillgänglig och har genomgått omfattande testning.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-106">These features are almost ready for general availability and have gone through extensive testing.</span></span> <span data-ttu-id="0a5c3-107">Vi söker bara en slutlig runda av feedback från kunder och validering innan vi gör dem allmänt tillgångliga.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-107">We're just looking for a final round of customer feedback and validation before we release them for general availability.</span></span>

<span data-ttu-id="0a5c3-108">Det här avsnittet beskriver hur du kan aktivera funktionen Förhandsgranska och visar funktionerna som är aktiverade för förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-108">This topic describes how you can enable preview features, and it lists the features that are currently available for preview.</span></span> <span data-ttu-id="0a5c3-109">Den här listan uppdateras funktioner släpps till normala tillgänglighet och nya funktioner som ges ut om du vill förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-109">This list will be updated as features are released to general availability and as new features are released to preview.</span></span> <span data-ttu-id="0a5c3-110">Ingen anmälan görs när nya funktioner publiceras för att förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-110">No notification is given when new features are released to preview.</span></span> <span data-ttu-id="0a5c3-111">Användare börjar bara se funktionerna.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-111">Users will just start to see the features.</span></span> <span data-ttu-id="0a5c3-112">Mer information om nya funktioner i Talent, se [Nyheter och ändringar in Dynamics 365 Talent](./whats-new.md) och [Viktig information om Dynamics 365 och Power Platform](https://docs.microsoft.com/business-applications-release-notes).</span><span class="sxs-lookup"><span data-stu-id="0a5c3-112">For more information about new features in Talent, see [What's new or changed in Dynamics 365 Talent](./whats-new.md) and [Dynamics 365 and Power Platform Release Notes](https://docs.microsoft.com/business-applications-release-notes).</span></span>

## <a name="enable-or-disable-preview-features"></a><span data-ttu-id="0a5c3-113">Aktivera eller inaktivera funktioner för förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="0a5c3-113">Enable or disable preview features</span></span>

<span data-ttu-id="0a5c3-114">För att du ska kunna använda funktionerna för förhandsgranskning måste du först aktivera dem i miljön.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-114">To access preview features, you must first enable them in your environment.</span></span> <span data-ttu-id="0a5c3-115">Aktivera eller inaktivera funktioner för förhandsgranskning är miljöspecifika.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-115">Enabling or disabling preview features is environment-specific.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a5c3-116">När du aktiverar inställningen **förhandsgranskningsfunktioner** kan du aktivera förhandsgranskning för alla användare i organisationen i denna miljö.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-116">When you turn on the **Preview Features** setting, you enable preview features for all users in your organization who are in that environment.</span></span> <span data-ttu-id="0a5c3-117">När du inaktiverar inställningen, inaktiveras förhandsgranskningsfunktioner och gör dem otillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-117">When you turn off the setting, you disable preview features and make them inaccessible to your users.</span></span> <span data-ttu-id="0a5c3-118">Förhandsgranskningsfunktioner har begränsad funktionalitet i Talent.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-118">Preview features have limited support in Talent.</span></span> <span data-ttu-id="0a5c3-119">De använder färre sekretess- och säkerhetsfunktioner och de ingår inte i Talent servicenivåavtal (SLA).</span><span class="sxs-lookup"><span data-stu-id="0a5c3-119">They might use fewer privacy and security measures, and they aren't included in the Talent service level agreement (SLA).</span></span> <span data-ttu-id="0a5c3-120">Du bör inte använda funktioner för förhandsgranskning för att behandla personuppgifter (d.v.s. all information som kan identifiera dig) eller bearbeta andra data som omfattas av lagar och andra efterföljandekrav.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-120">You should not use preview features to process personal data (that is, any information that could identify you), or to process other data that is subject to legal or regulatory compliance requirements.</span></span>

### <a name="attract"></a><span data-ttu-id="0a5c3-121">Attract</span><span class="sxs-lookup"><span data-stu-id="0a5c3-121">Attract</span></span>

1. <span data-ttu-id="0a5c3-122">Logga in på Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-122">Sign in to Microsoft Dynamics 365 Talent: Attract.</span></span>
2. <span data-ttu-id="0a5c3-123">I menyn **inställningar** (växel-symbol) i det övre högra hörnet väljer du **administrationscenter**.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-123">On the **Setup** menu (the gear symbol) in the upper-right corner, select **Admin center**.</span></span>
3. <span data-ttu-id="0a5c3-124">På fliken **Funktionshantering** väljer du alternativet bredvid **Förhandsgranskningsfunktioner** så att det blir blått och visar **På**.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-124">On the **Feature management** tab, select the option next to **Preview features** so that it turns blue and says **On**.</span></span>

    ![Aktivera förhandsfunktioner i Attract](./media/attract-enable-preview-features.png)

4. <span data-ttu-id="0a5c3-126">Välj eller avbryt valet av enskilda förhandsgranskningsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-126">Select or cancel the selection of individual preview features.</span></span> <span data-ttu-id="0a5c3-127">Om du inte gör någonting aktiveras alla tillgängliga funktioner för förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-127">If you do nothing, all available preview features are enabled.</span></span>
5. <span data-ttu-id="0a5c3-128">Uppdatera webbläsaren för att starta och se de nya funktionerna.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-128">Refresh your browser to start to see the new features.</span></span> <span data-ttu-id="0a5c3-129">Användare som redan har loggat in ser funktionerna nästa gång de loggar in och de kan uppdatera webbläsaren om du vill se funktionerna direkt.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-129">Any users who are already signed in will see the features the next time they sign in, or they can refresh their browser to see the features immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="0a5c3-130">Vissa förhandsgranskningsfunktioner kan kräva ytterligare konfiguration.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-130">Some preview features might require additional configuration.</span></span> <span data-ttu-id="0a5c3-131">Slutför inställningarna genom att följa länkarna bredvid förhandsgranskningsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-131">Follow the links next to the preview feature to complete the setup for it.</span></span>

## <a name="feedback"></a><span data-ttu-id="0a5c3-132">Feedback</span><span class="sxs-lookup"><span data-stu-id="0a5c3-132">Feedback</span></span>

<span data-ttu-id="0a5c3-133">Vi vill gärna höra om din erfarenhet av dessa förhandsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-133">We want to hear from you about your experience with any of these preview features.</span></span> <span data-ttu-id="0a5c3-134">Vi rekommenderar att du regelbundet publicerar feedback på följande webbplatser när du använder dessa eller andra funktioner.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-134">We encourage you to regularly post your feedback on the following sites as you use these or any other features:</span></span>

- <span data-ttu-id="0a5c3-135">[Gemenskap](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – webbplatsen är ett utmärkt verktyg där användare kan diskutera fall, ställa frågor och få hjälp från andra användare.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-135">[Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – This site is a great resource where users can discuss use cases, ask questions, and get community help.</span></span>
- <span data-ttu-id="0a5c3-136">Meddela oss om funktioner som du vill ska visas i produkten och även de ändringar som du tycker att vi ska göra av befintliga funktioner.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-136">Let us know about features that you want to see in the product, or let us know about any changes you think we should make to existing features.</span></span> <span data-ttu-id="0a5c3-137">Föreslå produktidéer på följande webbplatser:</span><span class="sxs-lookup"><span data-stu-id="0a5c3-137">Suggest product ideas on the following sites:</span></span>

    - [<span data-ttu-id="0a5c3-138">Attract idéer</span><span class="sxs-lookup"><span data-stu-id="0a5c3-138">Attract ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [<span data-ttu-id="0a5c3-139">Onboard idéer</span><span class="sxs-lookup"><span data-stu-id="0a5c3-139">Onboard ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

<span data-ttu-id="0a5c3-140">Se till att inte inkludera personuppgifter (all information som kan identifiera dig) i feedback eller produktomdömen.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-140">Make sure that you don't include personal data (any information that could identify you) in your feedback or product review submissions.</span></span> <span data-ttu-id="0a5c3-141">Insamlad information kan analyseras ytterligare och den används inte för att besvara frågor under tillämplig sekretesslagstiftning.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-141">Collected information might be analyzed further and isn't used to answer requests under applicable privacy laws.</span></span> <span data-ttu-id="0a5c3-142">Personuppgifter som samlas in separat under programmen som ingår i den [sekretesspolicyn för Microsoft ](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="0a5c3-142">Personal data that is collected separately under these programs is subject to the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span>

> [!TIP]
> <span data-ttu-id="0a5c3-143">Sätt ett bokmärke i detta ämne och gå tillbaka ofta för att hålla dig uppdaterad om nya funktioner för förhandsgranskning som vi släpper.</span><span class="sxs-lookup"><span data-stu-id="0a5c3-143">Bookmark this topic, and check back often to stay up to date about new preview features as we release them.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a5c3-144">Se även</span><span class="sxs-lookup"><span data-stu-id="0a5c3-144">See also</span></span>

- [<span data-ttu-id="0a5c3-145">Prova eller köp Talent-appar</span><span class="sxs-lookup"><span data-stu-id="0a5c3-145">Try or buy Talent apps</span></span>](https://dynamics.microsoft.com/talent/overview/)
- [<span data-ttu-id="0a5c3-146">Nyheter och ändringar i Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="0a5c3-146">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="0a5c3-147">Utgivningsplaner</span><span class="sxs-lookup"><span data-stu-id="0a5c3-147">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="0a5c3-148">Få support för Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="0a5c3-148">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
