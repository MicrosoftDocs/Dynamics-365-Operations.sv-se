---
title: Företagskoncept i Dataverse
description: I det här avsnittet beskrivs integreringen av företagsdata mellan Finance and Operations och Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/04/2020
ms.topic: article
ms.prod: ''
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
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 189d1b8a68f8457d32d656fefeb6cc2a332a3b22
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560259"
---
# <a name="company-concept-in-dataverse"></a><span data-ttu-id="3ea9c-103">Företagskoncept i Dataverse</span><span class="sxs-lookup"><span data-stu-id="3ea9c-103">Company concept in Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


<span data-ttu-id="3ea9c-104">I Finance and Operations, är begreppet av ett *företag* både en laglig konstruktion och en affärskonstruktion.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-104">In Finance and Operations, the concept of a *company* is both a legal construct and a business construct.</span></span> <span data-ttu-id="3ea9c-105">Det är också en säkerhets- och synlighetsgräns för data.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-105">It's also a security and visibility boundary for data.</span></span> <span data-ttu-id="3ea9c-106">Användare arbetar alltid inom ramen för ett enda företag, och de flesta av uppgifterna är sorterade efter företag.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-106">Users always work in the context of a single company, and most of the data is striped by company.</span></span>

<span data-ttu-id="3ea9c-107">Dataverse har inte ett likvärdigt koncept.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-107">Dataverse doesn't have an equivalent concept.</span></span> <span data-ttu-id="3ea9c-108">Det närmaste konceptet är *affärsenhet*, som i första hand är en säkerhets- och synlighetsgräns för användardata.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-108">The closest concept is *business unit*, which is primarily a security and visibility boundary for user data.</span></span> <span data-ttu-id="3ea9c-109">Det här konceptet har inte samma juridiska eller affärsmässiga betydelse som företagskonceptet.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-109">This concept doesn't have the same legal or business implications as the company concept.</span></span>

<span data-ttu-id="3ea9c-110">Eftersom affärsenhet och företag inte är likvärdiga begrepp, är det inte möjligt att tvinga en en-till-en-mappning (1:1) mellan dem i syfte integrera Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-110">Because business unit and company aren't equivalent concepts, it isn't possible to force a one-to-one (1:1) mapping between them for the purpose of Dataverse integration.</span></span> <span data-ttu-id="3ea9c-111">Men eftersom användare måste som standard kunna se samma rader i appen och Dataverse har Microsoft infört en ny tabell i Dataverse som heter CDM\_Företag.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-111">However, because users must, by default, be able to see the same rows in the application and Dataverse, Microsoft has introduced a new table in Dataverse that is named cdm\_Company.</span></span> <span data-ttu-id="3ea9c-112">Den här tabellen motsvarar företagstabellen i appen.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-112">This table is equivalent to the Company table in the application.</span></span> <span data-ttu-id="3ea9c-113">För att garantera att synligheten för rader är likvärdig mellan appen och färdiga Dataverse rekommenderar vi följande inställningar för data i Dataverse:</span><span class="sxs-lookup"><span data-stu-id="3ea9c-113">To help guarantee that visibility of rows is equivalent between the application and Dataverse out of the box, we recommend the following setup for data in Dataverse:</span></span>

+ <span data-ttu-id="3ea9c-114">För varje Finance and Operations-företagsrad som är aktiverad för dubbelriktad skrivning skapas en associerad cdm\_Företag-rad.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-114">For each Finance and Operations Company row that is enabled for dual-write, an associated cdm\_Company row is created.</span></span>
+ <span data-ttu-id="3ea9c-115">När en cdm\_Företag-rad skapas och aktiveras för dubbelriktad skrivning skapas en standardaffärsenhet som har samma namn.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-115">When a cdm\_Company row is created and enabled for dual-write, a default business unit is created that has the same name.</span></span> <span data-ttu-id="3ea9c-116">Även om ett standardteam skapas automatiskt för den affärsenheten används inte affärsenheten.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-116">Although a default team is automatically created for that business unit, the business unit isn't used.</span></span>
+ <span data-ttu-id="3ea9c-117">Ett separat ägarteam skapas med samma namn.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-117">A separate owner team is created that has the same name.</span></span> <span data-ttu-id="3ea9c-118">Det är också förknippat med affärsenheten.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-118">It's also associated with the business unit.</span></span>
+ <span data-ttu-id="3ea9c-119">Som standard anges ägaren av en rad som skapas och dubbelriktad skrivning till Dataverse anges till teamet "DW ägare" som är länkat till den associerade affärsenheten.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-119">By default, the owner of any row that is created and dual-written to Dataverse is set to the "DW Owner" team that is linked to the associated business unit.</span></span>

<span data-ttu-id="3ea9c-120">Följande illustration visar ett exempel på den här datainställningen i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-120">The following illustration shows an example of this data setup in Dataverse.</span></span>

![Inställning av data i Dataverse](media/dual-write-company-1.png)

<span data-ttu-id="3ea9c-122">På grund av den här konfigurationen kommer alla rader som är relaterade till USMF-företaget att ägas av ett team som är länkat till USMF-affärsenheten i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-122">Because of this configuration, any row that is related to the USMF company will be owned by a team that is linked to the USMF business unit in Dataverse.</span></span> <span data-ttu-id="3ea9c-123">Därför kan alla användare som har åtkomst till den affärsenheten via en säkerhetsroll som är inställd på synlighet på affärsenhetsnivå nu se dessa rader.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-123">Therefore, any user who has access to that business unit through a security role that is set to business unit–level visibility can now see those rows.</span></span> <span data-ttu-id="3ea9c-124">I följande exempel visas hur team kan användas för att ge rätt åtkomst till dessa rader.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-124">The following example shows how teams can be used to provide the correct access to those rows.</span></span>

+ <span data-ttu-id="3ea9c-125">Rollen "Säljchef" tilldelas medlemmar i teamet "USMF försäljning".</span><span class="sxs-lookup"><span data-stu-id="3ea9c-125">The "Sales Manager" role is assigned to members of the "USMF Sales" team.</span></span>
+ <span data-ttu-id="3ea9c-126">Användare som har rollen "Säljchef" kan komma åt alla rader i konton som är medlemmar i samma affärsenhet som de är medlemmar i.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-126">Users who have the "Sales Manager" role can access any account rows that are members of the same business unit that they are members of.</span></span>
+ <span data-ttu-id="3ea9c-127">"USMF försäljning"-teamet är länkat till den USMF-affärsenhet som nämndes tidigare.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-127">The "USMF Sales" team is linked to the USMF business unit that was mentioned earlier.</span></span>
+ <span data-ttu-id="3ea9c-128">Medlemmar i teamet "USMF försäljning" kan därför se alla konton som ägs av "USMF DW"-användaren, som skulle ha kommit från USMF-företagstabellen i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-128">Therefore, members of the "USMF Sales" team can see any account that is owned by the "USMF DW" user, which would have come from the USMF Company table in Finance and Operations.</span></span>

![Så här kan du använda team](media/dual-write-company-2.png)

<span data-ttu-id="3ea9c-130">Som föregående illustration visar är denna 1:1-mappning mellan affärsenhet, företag och team bara en utgångspunkt.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-130">As the preceding illustration shows, this 1:1 mapping between business unit, company, and team is just a starting point.</span></span> <span data-ttu-id="3ea9c-131">I det här exemplet skapas en ny affärsenhet "Europa" manuellt i Dataverse som överordnad för både DEMF och ESMF.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-131">In this example, a new "Europe" business unit is manually created in Dataverse as the parent for both DEMF and ESMF.</span></span> <span data-ttu-id="3ea9c-132">Denna nya rotaffärsenhet är inte kopplad till dubbelriktadskrivning.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-132">This new root business unit is unrelated to dual-write.</span></span> <span data-ttu-id="3ea9c-133">Den kan dock användas för att ge medlemmar i "EUR försäljnings"-teamet tillgång till kontodata i både DEMF och ESMF genom att ange datasynlighet till **överordnad/underordnad BU** i den associerade säkerhetsrollen.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-133">However, it can be used to give members of the "EUR Sales" team access to account data in both DEMF and ESMF by setting the data visibility to **Parent/Child BU** in the associated security role.</span></span>

<span data-ttu-id="3ea9c-134">Ett sista avsnitt att diskutera är hur dubbelriktadskrivning avgör vilket ägarteam det ska tilldela rader till.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-134">A final topic to discuss is how dual-write determines which owner team it should assign rows to.</span></span> <span data-ttu-id="3ea9c-135">Det här beteendet styrs av kolumnen **Standardägargrupp** i cdm\_Företag-raden.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-135">This behavior is controlled by the **Default owning team** column on the cdm\_Company row.</span></span> <span data-ttu-id="3ea9c-136">När encdm\_Företag-rad är aktiverad för dubbelriktad skrivning skapar ett plugin-program automatiskt den associerade affärsenheten och ägarteamet (om det inte redan finns) och ställer in kolumnen **Standardägargrupp**.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-136">When a cdm\_Company row is enabled for dual-write, a plug-in automatically creates the associated business unit and owner team (if it doesn't already exist), and sets the **Default owning team** column.</span></span> <span data-ttu-id="3ea9c-137">Administratören kan ändra det här kolumnen till ett annat värde.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-137">The admin can change this column to a different value.</span></span> <span data-ttu-id="3ea9c-138">Men administratören kan inte rensa kolumnen så länge tabellen är aktiverad för dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-138">However, the admin can't clear the column as long as the table is enabled for dual-write.</span></span>

> [!div class="mx-imgBorder"]
<span data-ttu-id="3ea9c-139">![Kolumn för standardägargrupp](media/dual-write-default-owning-team.jpg)</span><span class="sxs-lookup"><span data-stu-id="3ea9c-139">![Default owning team column](media/dual-write-default-owning-team.jpg)</span></span>

## <a name="company-striping-and-bootstrapping"></a><span data-ttu-id="3ea9c-140">Företagsstrimling och initiering</span><span class="sxs-lookup"><span data-stu-id="3ea9c-140">Company striping and bootstrapping</span></span>

<span data-ttu-id="3ea9c-141">Dataverse-integrering ger företagsparitet genom att använda en företagsidentifierare för strimla data.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-141">Dataverse integration brings company parity by using a company identifier to stripe data.</span></span> <span data-ttu-id="3ea9c-142">Som framgår av följande illustration utökas alla företagsspecifika tabeller så att de har en många-till-en-relation (N:1) med cdm\_Företag-tabellen.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-142">As the following illustration shows, all company-specific tables are extended so that they have a many-to-one (N:1) relationship with the cdm\_Company table.</span></span>

> [!div class="mx-imgBorder"]
<span data-ttu-id="3ea9c-143">![N:1-relation mellan en företagsspecifik tabell och tabellen cdm_Company](media/dual-write-bootstrapping.png)</span><span class="sxs-lookup"><span data-stu-id="3ea9c-143">![N:1 relationship between a company-specific table and the cdm_Company table](media/dual-write-bootstrapping.png)</span></span>

+ <span data-ttu-id="3ea9c-144">För rader blir värdet skrivskyddat när ett företag har lagts till och sparats.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-144">For rows, after a company is added and saved, the value becomes read-only.</span></span> <span data-ttu-id="3ea9c-145">Därför bör användare se till att de väljer rätt företag.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-145">Therefore, users should make sure that they select the correct company.</span></span>
+ <span data-ttu-id="3ea9c-146">Endast rader som har företagsdata är kvalificerade för dubbelriktad skrivning mellan appen och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-146">Only rows that have company data are eligible for dual-write between the application and Dataverse.</span></span>
+ <span data-ttu-id="3ea9c-147">För befintliga Dataverse-data kommer en administratörsledd initieringsupplevelse snart att vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-147">For existing Dataverse data, an admin-led bootstrapping experience will soon be available.</span></span>


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a><span data-ttu-id="3ea9c-148">Fyll i företagets namn automatiskt i kundengagemangsappar</span><span class="sxs-lookup"><span data-stu-id="3ea9c-148">Autopopulate company name in customer engagement apps</span></span>

<span data-ttu-id="3ea9c-149">Det finns flera sätt att fylla i företagsnamnet automatiskt i kundengagemangsappen.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-149">There are several ways to auto-populate the company name in customer engagement apps.</span></span>

+ <span data-ttu-id="3ea9c-150">Om du är systemadministratör kan du ställa in standardföretaget genom att navigera till **Avancerade inställningar > System > Säkerhet > Användare**.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-150">If you are a system administrator, you can set the default company by navigating to **Advanced Settings > System > Security > Users**.</span></span> <span data-ttu-id="3ea9c-151">Öppna formuläret **användare** och i avsnittet **organisationsinformation** i värdet **företag till standard på formulär**.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-151">Open the **User** form, and in the **Organization Information** section, set the **Company to default on Forms** value.</span></span>

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Ange standardföretag i avsnittet organisationsinformation.":::

+ <span data-ttu-id="3ea9c-153">Om du har **Skriv** åtkomst till tabellen **SystemUser** på nivån **affärsenhet** kan du ändra standardföretaget i valfritt formulär genom att välja ett företag i listrutan **företag**.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-153">If you have **Write** access to the **SystemUser** table for the **Business Unit** level, then you can change the default company on any form by selecting a company from the **Company** drop-down menu.</span></span>

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="Ändra företagsnamnet på ett nytt konto.":::

+ <span data-ttu-id="3ea9c-155">Om du har **Skriv**-åtkomst till data i fler än ett företag kan du ändra standardföretaget genom att välja en rad som tillhör ett annat företag.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-155">If you have **Write** access to data in more than one company, then you can change the default company by choosing a row that belongs to different company.</span></span>

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="När du väljer en rad ändras standardföretaget.":::

+ <span data-ttu-id="3ea9c-157">Om du är systemets konfigurator eller administratör och vill fylla i företagsdata automatiskt i ett anpassat formulär, kan du använda [formulärhändelser](https://docs.microsoft.com/powerapps/developer/model-driven-apps/clientapi/events-forms-grids).</span><span class="sxs-lookup"><span data-stu-id="3ea9c-157">If you are a system configurator or administrator, and you want to auto-populate company data on a custom form, then you can use [form events](https://docs.microsoft.com/powerapps/developer/model-driven-apps/clientapi/events-forms-grids).</span></span> <span data-ttu-id="3ea9c-158">Lägg till en JavaScript-referens till **msdyn_/DefaultCompany.js** och använd följande händelser.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-158">Add a JavaScript reference to **msdyn_/DefaultCompany.js** and use the following events.</span></span> <span data-ttu-id="3ea9c-159">Du kan t. ex. använda ett formulär som är utanför rutan, till exempel formuläret **konto**.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-159">You can use any out-of-the-box form, for example, the **Account** form.</span></span>

    + <span data-ttu-id="3ea9c-160">**OnLoad**-händelse för formuläret: Ställ in kolumnen **defaultCompany**.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-160">**OnLoad** event for the form: Set the **defaultCompany** column.</span></span>
    + <span data-ttu-id="3ea9c-161">**OnChange**-händelse för kolumnen **företag**: Ställ in kolumnen **updateDefaultCompany**.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-161">**OnChange** event for the **Company** column: Set the **updateDefaultCompany** column.</span></span>

## <a name="apply-filtering-based-on-the-company-context"></a><span data-ttu-id="3ea9c-162">Använd filtrering baserat på företagets kontext</span><span class="sxs-lookup"><span data-stu-id="3ea9c-162">Apply filtering based on the company context</span></span>

<span data-ttu-id="3ea9c-163">Om du vill använda filtrering baserat på företagets kontext i dina anpassade formulär eller anpassade uppslagskolumner som lagts till i standardformulären öppnar du formuläret och använder avsnittet **filtrering av relaterade poster** för att använda företagsfiltret.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-163">To apply filtering based on the company context on your custom forms or on custom lookup columns added to the standard forms, open the form and use the **Related Records Filtering** section to apply the company filter.</span></span> <span data-ttu-id="3ea9c-164">Du måste ställa in detta för varje uppslagskolumn som kräver filtrering baserat på det underliggande företaget för en viss rad.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-164">You must set this for each lookup column that requires filtering based on the underlying company on a given row.</span></span> <span data-ttu-id="3ea9c-165">Inställningen visas för **kontot** i följande bild.</span><span class="sxs-lookup"><span data-stu-id="3ea9c-165">The setting is shown for **Account** in the following illustration.</span></span>

:::image type="content" source="media/apply-company-context.png" alt-text="Använd företagets kontext":::



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]