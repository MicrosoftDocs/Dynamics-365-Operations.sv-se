---
title: Skapa juridiska personer
description: I det här avsnittet beskrivs hur du skapar juridiska personer i Microsoft Dynamics 365 Commerce, som måste skapas och konfigureras innan kanaler skapas.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 225fd6a07fee29414ac30a4602b4dfccdc4d742b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800625"
---
# <a name="create-legal-entities"></a><span data-ttu-id="fe068-103">Skapa juridiska personer</span><span class="sxs-lookup"><span data-stu-id="fe068-103">Create legal entities</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe068-104">I det här avsnittet beskrivs hur du skapar juridiska personer i Microsoft Dynamics 365 Commerce, som måste skapas och konfigureras innan kanaler skapas.</span><span class="sxs-lookup"><span data-stu-id="fe068-104">This topic describes how to create legal entities in Microsoft Dynamics 365 Commerce, which must be created and configured before creating channels.</span></span>

<span data-ttu-id="fe068-105">En juridisk person är en organisation som har en registrerad eller lagstiftad juridisk struktur.</span><span class="sxs-lookup"><span data-stu-id="fe068-105">A legal entity is an organization that has a registered or legislated legal structure.</span></span> <span data-ttu-id="fe068-106">Juridiska personer kan ingå juridiska kontrakt och måste förbereda utdrag som rapporterar deras resultat.</span><span class="sxs-lookup"><span data-stu-id="fe068-106">Legal entities can enter into legal contracts and are required to prepare statements that report on their performance.</span></span>

<span data-ttu-id="fe068-107">Ett företag är en sorts juridisk person.</span><span class="sxs-lookup"><span data-stu-id="fe068-107">A company is a type of legal entity.</span></span> <span data-ttu-id="fe068-108">För närvarande är företag den enda typ av juridisk person som du kan skapa, och varje juridisk person associeras med ett företags-ID.</span><span class="sxs-lookup"><span data-stu-id="fe068-108">Currently, companies are the only kind of legal entity that you can create, and every legal entity is associated with a company ID.</span></span> <span data-ttu-id="fe068-109">Denna koppling finns eftersom vissa funktionella områden i programmet använder ett företags-ID eller *DataAreaId*, i deras datamodeller.</span><span class="sxs-lookup"><span data-stu-id="fe068-109">This association exists because some functional areas in the program use a company ID, or *DataAreaId*, in their data models.</span></span> <span data-ttu-id="fe068-110">I dessa funktionella områden används företag som en gräns för datasäkerhet.</span><span class="sxs-lookup"><span data-stu-id="fe068-110">In these functional areas, companies are used as a boundary for data security.</span></span> <span data-ttu-id="fe068-111">Användarna kan endast komma åt data för de företag som de är inloggade på.</span><span class="sxs-lookup"><span data-stu-id="fe068-111">Users can access data only for the company that they are currently logged on to.</span></span> 

<span data-ttu-id="fe068-112">När du skapar en kanal måste du ange vilken juridisk person som kanalen tillhör.</span><span class="sxs-lookup"><span data-stu-id="fe068-112">When creating a channel, you must specify which legal entity that channel belongs to.</span></span>

## <a name="create-a-new-legal-entity"></a><span data-ttu-id="fe068-113">Skapa ny juridisk person</span><span class="sxs-lookup"><span data-stu-id="fe068-113">Create a new legal entity</span></span>

<span data-ttu-id="fe068-114">Om du vill skapa en ny juridisk enhet i Dynamics 365 Commerce, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="fe068-114">To create a new legal entity in Dynamics 365 Commerce, follow these steps.</span></span>

1. <span data-ttu-id="fe068-115">I navigeringsfönstret, gå till **Moduler \> Administrationsinställning \> Juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="fe068-115">In the navigation pane, go to  **Modules \> Headquarters setup \> Legal entities**.</span></span>
1. <span data-ttu-id="fe068-116">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fe068-116">On the action pane, select **New**.</span></span> <span data-ttu-id="fe068-117">Fönstret **Ny juridisk person** visas till höger.</span><span class="sxs-lookup"><span data-stu-id="fe068-117">The **New legal entity** pane appears on the right.</span></span>
1. <span data-ttu-id="fe068-118">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="fe068-118">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="fe068-119">I fältet **Företag** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="fe068-119">In the **Company** field, enter a value.</span></span>
1. <span data-ttu-id="fe068-120">Ange eller välj ett värde i fältet **Land/region**.</span><span class="sxs-lookup"><span data-stu-id="fe068-120">In the **Country/region** field, enter or select a value.</span></span>
1. <span data-ttu-id="fe068-121">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe068-121">Select **OK**.</span></span> 

   ![Skapa en juridisk person](media/legal-entities.png)

1. <span data-ttu-id="fe068-123">I avsnittet **allmän** ge följande information om juridiska personen:</span><span class="sxs-lookup"><span data-stu-id="fe068-123">In the **General** section, provide the following general information about the legal entity:</span></span> 
   1. <span data-ttu-id="fe068-124">Ange ett söknamn, om ett söknamn krävs.</span><span class="sxs-lookup"><span data-stu-id="fe068-124">Enter a search name, if a search name is required.</span></span> <span data-ttu-id="fe068-125">En söknamn är ett alternativt namn som kan användas för att söka efter den här juridisk person.</span><span class="sxs-lookup"><span data-stu-id="fe068-125">A search name is an alternate name that can be used to search for this legal entity.</span></span> 
   1. <span data-ttu-id="fe068-126">Markera om den här juridisk person används som ett konsolideringsföretag.</span><span class="sxs-lookup"><span data-stu-id="fe068-126">Select whether this legal entity is being used as a consolidation company.</span></span>
   1. <span data-ttu-id="fe068-127">Markera om den här juridisk person används som ett elimineringsföretag.</span><span class="sxs-lookup"><span data-stu-id="fe068-127">Select whether this legal entity is being used as an elimination company.</span></span> 
   1. <span data-ttu-id="fe068-128">Välj **systemspråk** för entiteten.</span><span class="sxs-lookup"><span data-stu-id="fe068-128">Select the **default language** for the entity.</span></span> 
   1. <span data-ttu-id="fe068-129">Välj **tidszon** för entiteten.</span><span class="sxs-lookup"><span data-stu-id="fe068-129">Select the **time zone** for the entity.</span></span>
1. <span data-ttu-id="fe068-130">I avsnittet **Adresser**, klicka på **Redigera** för att ange adressinformation, till exempel gatunamn och nummer, postnummer och ort.</span><span class="sxs-lookup"><span data-stu-id="fe068-130">In the **Addresses** section, select **Edit** to enter address information, such as the street name and number, postal code, and city.</span></span>
1. <span data-ttu-id="fe068-131">Ange information om metoder för kommunikationen till exempel e-postadresser, telefonnummer, webbadress, i avsnittet **Kontaktinformation**.</span><span class="sxs-lookup"><span data-stu-id="fe068-131">In the **Contact information** section, enter information about methods of communication, such as email addresses, URLs, and telephone numbers.</span></span>
1. <span data-ttu-id="fe068-132">Ange registreringsnumren som används för lagstadgad rapportering i avsnittet **Rapportering enligt lag**.</span><span class="sxs-lookup"><span data-stu-id="fe068-132">In the **Statutory reporting** section, enter the registration numbers that are used for statutory reporting.</span></span>
1. <span data-ttu-id="fe068-133">I avsnittet **Registreringsnummer**, ange vilken information som krävs av den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="fe068-133">In the **Registration numbers** section, enter any information required by the legal entity.</span></span>
1. <span data-ttu-id="fe068-134">Ange bankkonton och organisationsnummer för juridiska personen i avsnittet **Bankkontoinformation**.</span><span class="sxs-lookup"><span data-stu-id="fe068-134">In the **Bank account information** section, enter bank accounts and routing numbers for the legal entity.</span></span>
1. <span data-ttu-id="fe068-135">Ange leveransinformation för juridiska personen i avsnittet **Utrikeshandel- och logistik**.</span><span class="sxs-lookup"><span data-stu-id="fe068-135">In the **Foreign trade and logistics** section, enter shipping information for the legal entity.</span></span>
1. <span data-ttu-id="fe068-136">I avsnittet **Nummerserie**, kan du visa de nummerserier som är kopplade till juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="fe068-136">In the **Number sequences** section, you can view the number sequences that are associated with the legal entity.</span></span> <span data-ttu-id="fe068-137">Detta kommer att vara tomt att börja med.</span><span class="sxs-lookup"><span data-stu-id="fe068-137">This will be empty to start with.</span></span>
1. <span data-ttu-id="fe068-138">I avsnittet **Instrumentpanelsbild** kan du visa eller ändra logotyp- och/eller instrumentpanelbilden som associeras med juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="fe068-138">In the **Dashboard image** section, view or change the logo and dashboard image associated with the legal entity.</span></span>
1. <span data-ttu-id="fe068-139">Ange registreringsnumren som används för att rapportera till skattemyndigheten i avsnittet **Momsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="fe068-139">In the **Tax registration** section, enter the registration numbers that are used to report to tax authorities.</span></span>
1. <span data-ttu-id="fe068-140">Ange 1099-information för juridiska personen i avsnittet **Skatt 1099**.</span><span class="sxs-lookup"><span data-stu-id="fe068-140">In the **Tax 1099** section, enter 1099 information for the legal entity.</span></span>
1. <span data-ttu-id="fe068-141">I avsnittet **Momsinformation** ange den juridiska enhetens momsinformation.</span><span class="sxs-lookup"><span data-stu-id="fe068-141">In the **Tax invormation** section, enter tax information for the legal entity.</span></span>
1. <span data-ttu-id="fe068-142">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fe068-142">Select **Save**.</span></span>

<span data-ttu-id="fe068-143">I bilden nedan visas ett detaljer för exempel på en juridisk enhet.</span><span class="sxs-lookup"><span data-stu-id="fe068-143">The following image shows details of an example legal entity.</span></span>

![Allmänt avsnitt om juridisk person](media/legal-entities-general.png)
   
## <a name="additional-resources"></a><span data-ttu-id="fe068-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fe068-145">Additional resources</span></span>

[<span data-ttu-id="fe068-146">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="fe068-146">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="fe068-147">Planera en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="fe068-147">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="fe068-148">Organisationshierarkier</span><span class="sxs-lookup"><span data-stu-id="fe068-148">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="fe068-149">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="fe068-149">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="fe068-150">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="fe068-150">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
