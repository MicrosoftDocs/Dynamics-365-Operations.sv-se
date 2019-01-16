---
title: "Skapa och arbeta med anpassade fält"
description: "Det här avsnittet visar hur Microsoft Dynamics 365 for Finance and Operations tillåter vissa användare att skapa egna fält för att anpassa programmet så att det passar verksamheten."
author: jasongre
manager: AnnBe
ms.date: 07/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: 3ee5334c87b2b0acae2afa6882feca63e3b9cc8e
ms.openlocfilehash: 18402579789c17de7b46dd7a013b3b6327ea5d4f
ms.contentlocale: sv-se
ms.lasthandoff: 12/18/2018

---

# <a name="create-and-work-with-custom-fields"></a><span data-ttu-id="b5a3e-103">Skapa och arbeta med anpassade fält</span><span class="sxs-lookup"><span data-stu-id="b5a3e-103">Create and work with custom fields</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5a3e-104">Trots att Microsoft Dynamics 365 for Finance and Operations ger en omfattande uppsättning av färdiga fält för hantering av en mängd olika affärsprocesser, kan ibland företag ha behov av att söka ytterligare information i systemet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-104">While Microsoft Dynamics 365 for Finance and Operations provides an extensive set of fields out-of-the-box for managing a broad range of business processes, sometimes there is a need for a company to track additional information in the system.</span></span> <span data-ttu-id="b5a3e-105">För att tillgodose detta behov tillåter Finance and Operations dig att skapa egna fält för att anpassa programmet så att det passar ditt företag, förutsatt att du har behörighet till funktionen.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-105">To accommodate this need, Finance and Operations allows you to create custom fields to tailor the application to fit your business, provided you have permissions to the feature.</span></span>

<span data-ttu-id="b5a3e-106">Möjligheten att lägga till egna fält finns i plattformsuppdatering 13 och senare.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-106">The ability to add custom fields is available in platform update 13 and later.</span></span>

<span data-ttu-id="b5a3e-107">Det här videoklippet visar hur enkelt det är att lägga till ett anpassat fält i en sida: [Lägga till anpassade fält i Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=gWSGZI9Vtnc).</span><span class="sxs-lookup"><span data-stu-id="b5a3e-107">This video shows how easy it is to add a custom field to a page: [Adding custom fields in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=gWSGZI9Vtnc).</span></span>

## <a name="creating-custom-fields"></a><span data-ttu-id="b5a3e-108">Skapa anpassade fält</span><span class="sxs-lookup"><span data-stu-id="b5a3e-108">Creating custom fields</span></span>

<span data-ttu-id="b5a3e-109">När du har identifierat ytterligare information som du vill spåra i programmet skapar du anpassade fält i lämplig tabell och visar det nya fältet på en sida.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-109">After you've identified additional information that you would like to track in the application, you can create the custom field on the appropriate table and expose that new field on a page.</span></span>

<span data-ttu-id="b5a3e-110">Följande steg beskriver processen för att skapa ett anpassat fält och placera fältet i ett formulär.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-110">The following steps describe the process for creating a custom field and placing that field on a form.</span></span>

1. <span data-ttu-id="b5a3e-111">Navigera till det formulär där det nya fältet behövs.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-111">Navigate to the form where the new field is needed.</span></span>
2. <span data-ttu-id="b5a3e-112">Eftersom slutmålet är att tillhandahålla anpassade fält i ett formulär, finns startpunkten för att skapa anpassade fält i anpassningserfarenheten.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-112">Because the end goal is to expose the custom field on a form, the entry point for creating custom fields exists inside the personalization experience.</span></span> <span data-ttu-id="b5a3e-113">Öppna verktygsfältet för att anpassa genom att välja **alternativ**, och sedan **anpassa formuläret**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-113">Open the personalization toolbar by selecting **Options**, and then **Personalize this form**.</span></span>
3. <span data-ttu-id="b5a3e-114">Klicka på **infoga** och **fält**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-114">Click **Insert** and then **Field**.</span></span>
4. <span data-ttu-id="b5a3e-115">Välj det område på formuläret där du vill visa det nya fältet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-115">Select the region of the form where you want to expose the new field.</span></span> <span data-ttu-id="b5a3e-116">När du valt område visar dialogrutan **Infoga fält** en lista över befintliga fält som kan infogas i det markerade området på formuläret.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-116">After selection, the **Insert fields** dialog box will display a list of existing fields that can be inserted into the selected region of the form.</span></span>
5. <span data-ttu-id="b5a3e-117">Kontrollera att det fält du är intresserad av inte redan finns i listan.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-117">Ensure that the field you are interested in does not already exist in the list.</span></span> <span data-ttu-id="b5a3e-118">Om det gör det markerar du bara fältet i listan och klickar på **infoga**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-118">If it does, you can simply select that field in the list and click **Insert**.</span></span>
6. <span data-ttu-id="b5a3e-119">Klicka på knappen **Skapa nytt fält** ovanför listan för att initiera processen att skapa ett anpassat fält.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-119">Click the **Create new field** button above the list to initiate the process of creating a custom field.</span></span> <span data-ttu-id="b5a3e-120">Då öppnas dialogrutan **Skapa nytt fält**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-120">This will open the **Create new field** dialog box.</span></span>

    <span data-ttu-id="b5a3e-121">Om du inte ser knappen **Skapa nytt fält** har du inte behörighet att använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-121">If you do not see the **Create new field** button, you do not have the necessary permissions to use this feature.</span></span>

7. <span data-ttu-id="b5a3e-122">Ange följande information i dialogrutan **Skapa nytt fält**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-122">In the **Create new field** dialog box, enter the following information.</span></span>

    1. <span data-ttu-id="b5a3e-123">Markera databastabellen där fältet ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-123">Select the database table where this field should be added.</span></span> <span data-ttu-id="b5a3e-124">Observera att bara de tabeller som har stöd för anpassade fält visas i rullgardinsmenyn.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-124">Note that only tables that support custom fields will appear in the drop-down list.</span></span> <span data-ttu-id="b5a3e-125">Se avsnittet nedan för teknisk information om tabeller som stöds.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-125">See the section below for technical details on supported tables.</span></span>
    2. <span data-ttu-id="b5a3e-126">Välj datatyp för det nya fältet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-126">Select the data type for the new field.</span></span> <span data-ttu-id="b5a3e-127">Tillgängliga datatyper är kryssruta, datum, datum/tid, decimal, nummer, plocklista och text.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-127">The available data types are checkbox, date, date time, decimal, number, picklist, and text.</span></span>

        - <span data-ttu-id="b5a3e-128">Om du väljer datatypen text kan du också ange maxlängden för den text som kan skrivas in i fältet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-128">If you choose the text data type, you can also specify the maximum length of the text that can be entered in this field.</span></span>
        - <span data-ttu-id="b5a3e-129">Om du väljer datatypen plocklista kan du också välja en uppsättning giltiga värden för fältet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-129">If you choose the picklist data type, you can also select the set of valid values for the field.</span></span>

    3. <span data-ttu-id="b5a3e-130">Ange namn, etikett och hjälptext för fältet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-130">Provide a name, label, and help text for the field.</span></span> <span data-ttu-id="b5a3e-131">Namnet motsvarar det fysiska fältnamnet i databasen, där etikett och hjälptext används för att representera fältet i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-131">The name corresponds to the physical field name in the database, whereas the label and help text are the text used to represent this field in the user interface.</span></span>

8. <span data-ttu-id="b5a3e-132">Om detta är det enda fält du måste skapa för det här formuläret klickar du på **spara**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-132">If this is the only field that you need to create for this form, click **Save**.</span></span> <span data-ttu-id="b5a3e-133">Om du behöver skapa ytterligare fält klickar du på **spara och skapa ny** och går tillbaka till steg 7.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-133">If you need to create additional fields, click **Save and new** and go back to step 7.</span></span> <span data-ttu-id="b5a3e-134">Observera att det finns en gräns på **20 anpassade fält per tabell**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-134">Note that there is currently a limit of **20 custom fields per table**.</span></span>
9. <span data-ttu-id="b5a3e-135">När du lämnar dialogrutan **Skapa nytt fält** kommer du automatiskt tillbaka till dialogrutan **Infoga fält**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-135">Leaving the **Create new field** dialog box will return you to the **Insert fields** dialog box.</span></span> <span data-ttu-id="b5a3e-136">Fält som nyss lagts till markeras automatiskt i listan över fält som ska infogas i formuläret.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-136">Any custom fields that were just added will be automatically marked in the field list to be inserted into the form.</span></span>
10. <span data-ttu-id="b5a3e-137">Klicka på **infoga** för att infoga markerade fält i det utvalda området på formuläret.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-137">Click **Insert** to insert the marked fields into the selected region of the form.</span></span>
11. <span data-ttu-id="b5a3e-138">**Valfritt:** Aktivera läget **flytta** från verktygsfältet för anpassning för att flytta de nya fälten till önskad plats i det markerade området.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-138">**Optional:** Enable **Move** mode from the personalization toolbar to move the new fields to their desired location in the selected region.</span></span> <span data-ttu-id="b5a3e-139">Se [anpassa användarupplevelsen](personalize-user-experience.md) för mer information om hur du använder olika funktioner för anpassning om du vill optimera ett formulär för din personliga användning.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-139">See [Personalize the user experience](personalize-user-experience.md) for more information about how to use the various personalization capabilities to optimize a form for your personal usage.</span></span>

## <a name="sharing-custom-fields-with-other-users"></a><span data-ttu-id="b5a3e-140">Dela anpassade fält med andra användare</span><span class="sxs-lookup"><span data-stu-id="b5a3e-140">Sharing custom fields with other users</span></span>

<span data-ttu-id="b5a3e-141">När du har skapat ett anpassat fält och det visas i ett formulär, vill du kanske tillhandahålla denna uppdaterade sida som innehåller det nya fältet för andra användare i systemet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-141">After you have created a custom field and exposed it on a form, you might want to provide this updated page view that includes the new field to other users in the system.</span></span> <span data-ttu-id="b5a3e-142">Det kan du göra på två olika sätt genom att använda funktionerna för anpassning av produkten:</span><span class="sxs-lookup"><span data-stu-id="b5a3e-142">This can be accomplished in two different ways using the personalization capabilities of the product:</span></span>

- <span data-ttu-id="b5a3e-143">Det rekommenderade flödet är via den systemadministratör som kan skicka en anpassning till alla användare eller en grupp användare.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-143">The recommended route is through the system administrator, who can push a personalization to all users or a subset of users.</span></span> <span data-ttu-id="b5a3e-144">Mer information i [Anpassa användarupplevelsen](personalize-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="b5a3e-144">See [Personalize the user experience](personalize-user-experience.md) for more details.</span></span>
- <span data-ttu-id="b5a3e-145">Du kan också exportera dina ändringar (kallas *anpassningar*), skicka dem till en eller flera användare och låta var och en av dessa användare importera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-145">Alternatively, you can export your changes (called *personalizations*), send them to one or more users, and have each of those users import your changes.</span></span> <span data-ttu-id="b5a3e-146">Alternativet **hantera** verktygsfältet för anpassning låter dig exportera och importera anpassningar.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-146">The **Manage** option on the personalization toolbar enables you to export and import personalizations.</span></span>

## <a name="managing-custom-fields"></a><span data-ttu-id="b5a3e-147">Hantera anpassade fält</span><span class="sxs-lookup"><span data-stu-id="b5a3e-147">Managing custom fields</span></span>

<span data-ttu-id="b5a3e-148">Hanteringen av anpassade fält i systemet kan utföras via sidan **anpassade fält** i modulen systemadministration.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-148">Management of all the custom fields in the system can be accomplished through the **Custom fields** page in the System administration module.</span></span> <span data-ttu-id="b5a3e-149">Den här sidan ger användare tillgång till många funktioner, inklusive:</span><span class="sxs-lookup"><span data-stu-id="b5a3e-149">This page allows users access to many capabilities, including:</span></span>

- <span data-ttu-id="b5a3e-150">Visa en lista över alla anpassade fält i systemet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-150">Viewing a list of all custom fields in the system.</span></span>
- <span data-ttu-id="b5a3e-151">Begränsad redigering av befintliga anpassade fält.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-151">Limited editing of existing custom fields.</span></span>
- <span data-ttu-id="b5a3e-152">Radera anpassade fält.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-152">Deleting custom fields.</span></span>
- <span data-ttu-id="b5a3e-153">Visa anpassade fält i datatabeller.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-153">Exposing custom fields on data entities.</span></span>
- <span data-ttu-id="b5a3e-154">Tillhandahålla översättningar av etiketter och hjälptexter till anpassade fält.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-154">Providing translations of custom field labels and help text.</span></span>

### <a name="viewing-all-custom-fields"></a><span data-ttu-id="b5a3e-155">Visa alla anpassade fält</span><span class="sxs-lookup"><span data-stu-id="b5a3e-155">Viewing all custom fields</span></span>

<span data-ttu-id="b5a3e-156">Sidan **anpassade fält** visar alla anpassade fält som har definierats i systemet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-156">The **Custom fields** page provides visibility to all the custom fields that have been defined in the system.</span></span> <span data-ttu-id="b5a3e-157">Välj den tabell som du är intresserad av och sidan uppdateras för att visa en lista över de anpassade fält som är kopplade till tabellen.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-157">Simply select the table that you are interested in, and the page will update to show a list of the custom fields associated with that table.</span></span> <span data-ttu-id="b5a3e-158">Genom att välj ett anpassat fält i listan kan du se alla detaljer om fältet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-158">Choosing a custom field from the list will allow you to view all the details about the field.</span></span>

### <a name="editing-custom-fields"></a><span data-ttu-id="b5a3e-159">Redigera anpassade fält</span><span class="sxs-lookup"><span data-stu-id="b5a3e-159">Editing custom fields</span></span>

<span data-ttu-id="b5a3e-160">När du har skapat ett anpassat fält kan bara vissa delar av information om det anpassade fältet ändras på sidan **anpassade fält**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-160">After a custom field has been created, only certain pieces of information about the custom field can be modified on the **Custom fields** page.</span></span>

<span data-ttu-id="b5a3e-161">Du *kan* ändra dessa attribut:</span><span class="sxs-lookup"><span data-stu-id="b5a3e-161">You *can* modify these attributes:</span></span>

- <span data-ttu-id="b5a3e-162">Etikett</span><span class="sxs-lookup"><span data-stu-id="b5a3e-162">Label</span></span>
- <span data-ttu-id="b5a3e-163">Hjälptext</span><span class="sxs-lookup"><span data-stu-id="b5a3e-163">Help text</span></span>
- <span data-ttu-id="b5a3e-164">Längden, på textfält</span><span class="sxs-lookup"><span data-stu-id="b5a3e-164">Length, for Text fields</span></span>

<span data-ttu-id="b5a3e-165">Du kan *inte* redigera följande attribut:</span><span class="sxs-lookup"><span data-stu-id="b5a3e-165">You *cannot* edit the following attributes:</span></span>

- <span data-ttu-id="b5a3e-166">Fältnamn</span><span class="sxs-lookup"><span data-stu-id="b5a3e-166">Field name</span></span>
- <span data-ttu-id="b5a3e-167">Datatyp</span><span class="sxs-lookup"><span data-stu-id="b5a3e-167">Data type</span></span>

<span data-ttu-id="b5a3e-168">För plocklista kan dessutom uppsättningen av giltiga värden för anpassade fält ordnas om och nya värden kan läggas till, befintliga värden för fältet plocklista kan dock inte tas bort.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-168">Additionally, for picklist fields, the set of valid values for the custom field can be reordered, and new values can be added; however, existing values for the picklist field cannot be removed.</span></span> <span data-ttu-id="b5a3e-169">Kom ihåg att klicka på **verkställ ändringarna** när du är klar med redigeringen av fält för en viss tabell för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-169">Remember to click **Apply changes** when you are done editing fields for a particular table so the changes are saved.</span></span>

### <a name="exposing-custom-fields-on-data-entities"></a><span data-ttu-id="b5a3e-170">Visa anpassade fält i datatabeller</span><span class="sxs-lookup"><span data-stu-id="b5a3e-170">Exposing custom fields on data entities</span></span>

<span data-ttu-id="b5a3e-171">Det kan också vara viktigt att visa anpassade fält i datatabeller.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-171">It may also be important to allow custom fields to be visible on data entities.</span></span> <span data-ttu-id="b5a3e-172">Datatabeller används i funktionen [Öppna i Office](../../dev-itpro/office-integration/office-integration.md) samt vid import och export av data.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-172">Data entities are utilized in the [Open in Office](../../dev-itpro/office-integration/office-integration.md) feature, as well as for data import/export scenarios.</span></span>

<span data-ttu-id="b5a3e-173">Gör så här om du vill visa ett anpassat fält i en datatabell:</span><span class="sxs-lookup"><span data-stu-id="b5a3e-173">Follow these steps to expose a custom field on a data entity:</span></span>

1. <span data-ttu-id="b5a3e-174">Välj anpassade fält i formuläret **anpassade fält**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-174">Select the custom field on the **Custom fields** form.</span></span>
2. <span data-ttu-id="b5a3e-175">Expandera avsnittet **enheter** för att visa uppsättningen av relevanta enheter.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-175">Expand the **Entities** section to view the set of relevant entities.</span></span>
3. <span data-ttu-id="b5a3e-176">Klicka på knappen för att **redigera**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-176">Click the **Edit** button.</span></span>
4. <span data-ttu-id="b5a3e-177">Ändra fältet **aktiverad** för varje enhet som ska visas i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-177">Modify the **Enabled** field to be selected for each entity that should expose this field.</span></span>
5. <span data-ttu-id="b5a3e-178">Spara ändringarna genom att klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-178">Click **Apply changes** to save your selections.</span></span>

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a><span data-ttu-id="b5a3e-179">Tillåra anpassade fält att visas på ett annat språk</span><span class="sxs-lookup"><span data-stu-id="b5a3e-179">Allowing custom fields to be displayed in other languages</span></span>

<span data-ttu-id="b5a3e-180">Eftersom anpassade fält kan behöva användas av användare på en mängd språk, måste sidan **anpassade fält** ge dig möjlighet att översätta etikett och hjälptext till andra språk.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-180">Because custom fields may need to be accessed by users in a variety of languages, the **Custom fields** page provides a mechanism to allow the label and help text for a custom field to be translated into other languages.</span></span>

<span data-ttu-id="b5a3e-181">Följande steg beskriver processen för översättning av anpassade fält till ett annat språk:</span><span class="sxs-lookup"><span data-stu-id="b5a3e-181">The following steps describe the process for translating custom fields in other languages:</span></span>

1. <span data-ttu-id="b5a3e-182">Välj det anpassade fältet på sidan **anpassade fält**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-182">Select the custom field on the **Custom fields** page.</span></span>
2. <span data-ttu-id="b5a3e-183">Välj knappen **Översättningar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-183">Select the **Translations** button in the Action Pane.</span></span> <span data-ttu-id="b5a3e-184">Då öppnas en rullgardinsmeny med befintliga transaktioner för det här fältet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-184">This will open a drop-down menu with existing translations for this field.</span></span>
3. <span data-ttu-id="b5a3e-185">Rullgardinsmenyn **språk** visar vilka språk som det redan finns översättningar för.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-185">The **Language** drop-down menu shows the set of languages for which translations have already been provided.</span></span>

    <span data-ttu-id="b5a3e-186">Om du vill redigera en befintlig översättning väljer du önskat språk på menyn och ändrar värdena etiketten och hjälptext.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-186">If you want to edit an existing translation, select the desired language from the menu and modify the values for the label and help text.</span></span>

    <span data-ttu-id="b5a3e-187">Annars klickar du på **lägga till språk** och välj språk i menyn. Översätt sedan etikett och hjälptext.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-187">Otherwise, click the **Add language** button, select the desired language from the menu, and then provide translated values for the label and help text.</span></span>

4. <span data-ttu-id="b5a3e-188">Klicka på **OK**, när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-188">Click **OK** when you are finished.</span></span>

### <a name="deleting-custom-fields"></a><span data-ttu-id="b5a3e-189">Radera anpassade fält</span><span class="sxs-lookup"><span data-stu-id="b5a3e-189">Deleting custom fields</span></span>

<span data-ttu-id="b5a3e-190">I sällsynta fall kanske du bestämmer att ett anpassat fält inte längre behövs.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-190">In some rare cases, you may decide that a custom field is no longer needed.</span></span> <span data-ttu-id="b5a3e-191">I dessa fall kan systemadministratören välja att ta bort fältet från sidan **anpassade fält**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-191">When this occurs, a system administrator can choose to delete the field from the **Custom fields** page.</span></span> <span data-ttu-id="b5a3e-192">Kontrollera att rätt fält är markerat, klicka du på **ta bort** och sedan på **ja** för att att bekräfta borttagningen och klicka slutligen på **verkställ ändringar**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-192">To do this, ensure the correct field is selected, click **Delete**, click **Yes** to confirm the deletion, and finally click **Apply changes**.</span></span>

> [!NOTE]
> <span data-ttu-id="b5a3e-193">Den här åtgärden kan inte ångras och innebär att data som hör till fältet tas bort permanent från databasen.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-193">This action cannot be undone, and will result in the data associated with the field being permanently deleted from the database.</span></span>

## <a name="appendix"></a><span data-ttu-id="b5a3e-194">Bilaga</span><span class="sxs-lookup"><span data-stu-id="b5a3e-194">Appendix</span></span>

### <a name="who-can-create-custom-fields"></a><span data-ttu-id="b5a3e-195">Vem kan skapa anpassade fält?</span><span class="sxs-lookup"><span data-stu-id="b5a3e-195">Who can create custom fields?</span></span>

<span data-ttu-id="b5a3e-196">För att skydda systemet kan, som standard, endast systemadministratörer skapa anpassade fält.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-196">As a safeguard to the system, only system administrators are able to create custom fields by default.</span></span> <span data-ttu-id="b5a3e-197">Men de privilegierade användare som organisationen anser nödvändiga kan få behörighet att skapa anpassade fält av en systemadministratör med hjälp av säkerhetsrollen **körning anpassning privilegierad användare**.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-197">However, those power users whom the organization deems necessary can be given rights to create custom fields by a system administrator using the **Runtime customization power user** security role.</span></span> <span data-ttu-id="b5a3e-198">Användare utan den här säkerhetsrollen kommer inte att kunna skapa anpassade fält, men kommer fortfarande att kunna se och använda anpassade fält som lagts till av andra användare i systemet.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-198">Users without this security role will not be able to create custom fields, but will still be able to see and interact with custom fields added by other users in the system.</span></span>

### <a name="what-tables-support-custom-fields"></a><span data-ttu-id="b5a3e-199">Vilka tabeller har stöd för anpassade fält?</span><span class="sxs-lookup"><span data-stu-id="b5a3e-199">What tables support custom fields?</span></span>

<span data-ttu-id="b5a3e-200">Av prestandaskäl och tekniska skäl kan för tillfället endast tabeller som uppfyller följande villkor tillåta att anpassade fält läggs till.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-200">For performance and technical reasons, only tables that meet the following conditions currently allow custom fields to be added.</span></span>

- <span data-ttu-id="b5a3e-201">Tabellen måste vara märkas som en av dessa grupper:</span><span class="sxs-lookup"><span data-stu-id="b5a3e-201">The table must be tagged as one of these groups:</span></span>

    - <span data-ttu-id="b5a3e-202">Grupp</span><span class="sxs-lookup"><span data-stu-id="b5a3e-202">Group</span></span>
    - <span data-ttu-id="b5a3e-203">WorksheetHeader</span><span class="sxs-lookup"><span data-stu-id="b5a3e-203">WorksheetHeader</span></span>
    - <span data-ttu-id="b5a3e-204">Rubrik</span><span class="sxs-lookup"><span data-stu-id="b5a3e-204">Main</span></span>
    - <span data-ttu-id="b5a3e-205">Diverse</span><span class="sxs-lookup"><span data-stu-id="b5a3e-205">Miscellaneous</span></span>
    - <span data-ttu-id="b5a3e-206">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5a3e-206">Parameter</span></span>
    - <span data-ttu-id="b5a3e-207">Referens</span><span class="sxs-lookup"><span data-stu-id="b5a3e-207">Reference</span></span>
    - <span data-ttu-id="b5a3e-208">TransactionHeader</span><span class="sxs-lookup"><span data-stu-id="b5a3e-208">TransactionHeader</span></span>

- <span data-ttu-id="b5a3e-209">Tabellen kan inte utöka en annan tabell.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-209">The table cannot extend another table.</span></span>
- <span data-ttu-id="b5a3e-210">Registret kan inte klassas som ett systemregister.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-210">The table cannot be marked as a system table.</span></span>
- <span data-ttu-id="b5a3e-211">Registret kan inte vara ett tillfälligt register.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-211">The table cannot be a temporary table.</span></span>

