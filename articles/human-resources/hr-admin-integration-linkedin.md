---
title: Integration med LinkedIn Talent Hub
description: Det här avsnittet beskriver hur du ställer in integreringen mellan Microsoft Dynamics 365 Human Resources och LinkedIn Talent Hub.
author: jaredha
manager: tfehr
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6f70e3a6ccf9770c75334d355db5e9df9ee912dd
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527895"
---
# <a name="integrate-with-linkedin-talent-hub"></a><span data-ttu-id="b8756-103">Integration med LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="b8756-103">Integrate with LinkedIn Talent Hub</span></span>

[!include [banner](includes/preview-feature.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b8756-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) är en plattform för sökningsspårningssystem (ATS).</span><span class="sxs-lookup"><span data-stu-id="b8756-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) is an applicant tracking system (ATS) platform.</span></span> <span data-ttu-id="b8756-105">Med den kan du anskaffa, hantera och anställa medarbetare på samma ställe.</span><span class="sxs-lookup"><span data-stu-id="b8756-105">It lets you source, manage, and hire employees all in one place.</span></span> <span data-ttu-id="b8756-106">Genom att integrera Microsoft Dynamics 365 Human Resources med LinkedIn Talent Hub kan du enkelt skapa medarbetarposter i Human Resources för de sökande som har anställts för en befattning.</span><span class="sxs-lookup"><span data-stu-id="b8756-106">By integrating Microsoft Dynamics 365 Human Resources with LinkedIn Talent Hub, you can easily create employee records in Human Resources for applicants who have been hired for a position.</span></span>

## <a name="setup"></a><span data-ttu-id="b8756-107">Ställ in</span><span class="sxs-lookup"><span data-stu-id="b8756-107">Setup</span></span>

<span data-ttu-id="b8756-108">En systemadministratör måste slutföra installationsåtgärderna för att kunna integrera med LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="b8756-108">A system administrator must complete setup tasks to enable integration with LinkedIn Talent Hub.</span></span> <span data-ttu-id="b8756-109">Först i Power Apps-miljön måste du ställa in en användar- och säkerhetsroll för att ge LinkedIn Talent Hub rätt behörighet att skriva data till Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b8756-109">First, in the Power Apps environment, you must set up a user and security role to grant LinkedIn Talent Hub the appropriate permissions to write data into Human Resources.</span></span>

### <a name="link-your-environment-to-linkedin-talent-hub"></a><span data-ttu-id="b8756-110">Länka din miljö till LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="b8756-110">Link your environment to LinkedIn Talent Hub</span></span>

1. <span data-ttu-id="b8756-111">Öppna [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span><span class="sxs-lookup"><span data-stu-id="b8756-111">Open [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span></span>

2. <span data-ttu-id="b8756-112">På listmenyn för användare väljer du **produktinställningar**.</span><span class="sxs-lookup"><span data-stu-id="b8756-112">On the user drop-down menu, select **Product Settings**.</span></span>

3. <span data-ttu-id="b8756-113">I det vänstra navigeringsfönstret i avsnittet **Avancerat** välj **Integreringar**.</span><span class="sxs-lookup"><span data-stu-id="b8756-113">In the left navigation pane, in the **Advanced** section, select **Integrations**.</span></span>

4. <span data-ttu-id="b8756-114">Välj **auktorisera** för Microsoft Dynamics 365 Human Resources-integrationen.</span><span class="sxs-lookup"><span data-stu-id="b8756-114">Select **Authorize** for the Microsoft Dynamics 365 Human Resources integration.</span></span>

5. <span data-ttu-id="b8756-115">På sidan **Dynamics 365 Human Resources**, välj den miljö du vill länka LinkedIn Talent Hub till och välj sedan **Länka**.</span><span class="sxs-lookup"><span data-stu-id="b8756-115">On the **Dynamics 365 Human Resources** page, select the environment to link LinkedIn Talent Hub to, and then select **Link**.</span></span>

    ![LinkedIn Talent Hub registrering](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > <span data-ttu-id="b8756-117">Du kan bara länka till miljöer där ditt användarkonto har administratörsåtkomst till både Human Resources-miljön och den associerade Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="b8756-117">You can link only to environments where your user account has administrator access to both the Human Resources environment and the associated Power Apps environment.</span></span> <span data-ttu-id="b8756-118">Om det inte finns några miljöer på sidan Human Resources-länkar ser du till att du har licensierade Human Resources-miljöer på klientorganisationen och att användaren som du har loggat in på länksidan som har administratörsbehörighet för både Human Resources-miljön och Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="b8756-118">If no environments are listed on the Human Resources link page, make sure that you have licensed Human Resources environments on the tenant, and that the user that you signed in to the link page as has administrator permissions to both the Human Resources environment and the Power Apps environment.</span></span>

### <a name="create-a-power-apps-security-role"></a><span data-ttu-id="b8756-119">Skapa en Power Apps säkerhetsroll</span><span class="sxs-lookup"><span data-stu-id="b8756-119">Create a Power Apps security role</span></span>

1. <span data-ttu-id="b8756-120">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b8756-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="b8756-121">I listan **miljöer** väljer du den miljö som är kopplad till Human Resources-miljön som du vill länka din instans av LinkedIn Talent Hub till.</span><span class="sxs-lookup"><span data-stu-id="b8756-121">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="b8756-122">Välj **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="b8756-122">Select **Settings**.</span></span>

4. <span data-ttu-id="b8756-123">Expandera noden **användare + behörigheter** och välj sedan **säkerhetsroller**.</span><span class="sxs-lookup"><span data-stu-id="b8756-123">Expand the **Users + Permissions** node, and select **Security Roles**.</span></span>

5. <span data-ttu-id="b8756-124">På sidan **säkerhetsroller** i verktygsfältet, välj **Ny roll**.</span><span class="sxs-lookup"><span data-stu-id="b8756-124">On the **Security Roles** page, on the toolbar, select **New role**.</span></span>

6. <span data-ttu-id="b8756-125">På fliken **Detaljer** anger du ett namn på rollen, t.ex. **LinkedIn Talent Hub HRIS-integration**.</span><span class="sxs-lookup"><span data-stu-id="b8756-125">On the **Details** tab, enter a name for the role, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>

7. <span data-ttu-id="b8756-126">På fliken **Anpassning** väljer du behörighet **Läs** på organisationsnivå för följande entiteter:</span><span class="sxs-lookup"><span data-stu-id="b8756-126">On the **Customization** tab, select organization-level **Read** permission for the following entities:</span></span>

    - <span data-ttu-id="b8756-127">Enhet</span><span class="sxs-lookup"><span data-stu-id="b8756-127">Entity</span></span>
    - <span data-ttu-id="b8756-128">Fält</span><span class="sxs-lookup"><span data-stu-id="b8756-128">Field</span></span>
    - <span data-ttu-id="b8756-129">Förhållande</span><span class="sxs-lookup"><span data-stu-id="b8756-129">Relationship</span></span>

8. <span data-ttu-id="b8756-130">Spara och stäng säkerhetsrollen.</span><span class="sxs-lookup"><span data-stu-id="b8756-130">Save and close the security role.</span></span>

### <a name="create-a-power-apps-application-user"></a><span data-ttu-id="b8756-131">Skapa en Power Apps appanvändare</span><span class="sxs-lookup"><span data-stu-id="b8756-131">Create a Power Apps application user</span></span>

<span data-ttu-id="b8756-132">En program användare måste skapas för LinkedIn Talent Hub för att bevilja behörighet till adaptern att skriva kandidatposter till Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="b8756-132">An application user must be created for the LinkedIn Talent Hub adapter to grant permissions to the adapter to write candidate records into the Power Apps environment.</span></span>

1. <span data-ttu-id="b8756-133">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b8756-133">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="b8756-134">I listan **miljöer** väljer du den miljö som är kopplad till Human Resources-miljön som du vill länka din instans av LinkedIn Talent Hub till.</span><span class="sxs-lookup"><span data-stu-id="b8756-134">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="b8756-135">Välj **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="b8756-135">Select **Settings**.</span></span>

4. <span data-ttu-id="b8756-136">Expandera noden **användare + behörigheter** och välj sedan **användare**.</span><span class="sxs-lookup"><span data-stu-id="b8756-136">Expand the **Users + Permissions** node, and select **Users**.</span></span>

5. <span data-ttu-id="b8756-137">Välj **Hantera användare i Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="b8756-137">Select **Manage users in Dynamics 365**.</span></span>

6. <span data-ttu-id="b8756-138">Använd den nedrullningsbara menyn ovanför listan för att ändra visningen av vyn standardinställda **användare** för **appanvändare**.</span><span class="sxs-lookup"><span data-stu-id="b8756-138">Use the drop-down menu above the list to change the view from the default **Enabled Users** view to **Application Users**.</span></span>

    ![Vyn appanvändare](./media/hr-admin-integration-power-apps-application-users.jpg)

7. <span data-ttu-id="b8756-140">I verktygsfältet klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="b8756-140">On the toolbar, select **New**.</span></span>

8. <span data-ttu-id="b8756-141">Gå till sidan **Ny användare** och följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="b8756-141">On the **New user** page, follow these steps:</span></span>

    1. <span data-ttu-id="b8756-142">Ändra värdet för fältet **Användartyp** till **Appanvändare**.</span><span class="sxs-lookup"><span data-stu-id="b8756-142">Change the value of the **User type** field to **Application User**.</span></span>
    2. <span data-ttu-id="b8756-143">Ange fältet **användarnamn** till **Dynamics365 HR LinkedIn HRIS-integration**.</span><span class="sxs-lookup"><span data-stu-id="b8756-143">Set the **User Name** field to **Dynamics365 HR LinkedIn HRIS Integration**.</span></span>
    3. <span data-ttu-id="b8756-144">Ange fältet **App-ID** till **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="b8756-144">Set the **Application ID** field to **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    4. <span data-ttu-id="b8756-145">Ange valfritt värde i fälten **Förnamn**, **Efternamn** och **Primär e-post**.</span><span class="sxs-lookup"><span data-stu-id="b8756-145">Enter any value in the **First Name**, **Last Name**, and **Primary Email** fields.</span></span>
    5. <span data-ttu-id="b8756-146">I verktygsfältet, välj **Spara \& Stäng**.</span><span class="sxs-lookup"><span data-stu-id="b8756-146">On the toolbar, select **Save \& Close**.</span></span>

### <a name="assign-a-security-role-to-the-new-user"></a><span data-ttu-id="b8756-147">Tilldela den nya användaren en säkerhetsroll</span><span class="sxs-lookup"><span data-stu-id="b8756-147">Assign a security role to the new user</span></span>

<span data-ttu-id="b8756-148">När du har sparat och stängt den nya appanvändaren i föregående avsnitt, kommer du tillbaka till sidan **användarlista**.</span><span class="sxs-lookup"><span data-stu-id="b8756-148">After you save and close the new application user in the previous section, you're returned to the **Users list** page.</span></span>

1. <span data-ttu-id="b8756-149">På sidan **Användarlista** ändra vyn till **appanvändare**.</span><span class="sxs-lookup"><span data-stu-id="b8756-149">On the **Users list** page, change the view to **Application Users**.</span></span>

2. <span data-ttu-id="b8756-150">Välj den appanvändare som du skapade i det föregående avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b8756-150">Select the application user that you created in the previous section.</span></span>

3. <span data-ttu-id="b8756-151">Välj **hantera roller** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="b8756-151">On the toolbar, select **Manage Roles**.</span></span>

4. <span data-ttu-id="b8756-152">Välj den säkerhetsroll som du skapade tidigare för integrationen.</span><span class="sxs-lookup"><span data-stu-id="b8756-152">Select the security role that you created earlier for the integration.</span></span>

5. <span data-ttu-id="b8756-153">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8756-153">Select **OK**.</span></span>

### <a name="add-an-azure-active-directory-app-in-human-resources"></a><span data-ttu-id="b8756-154">Lägg till en Azure Active Directory-app i Human Resources</span><span class="sxs-lookup"><span data-stu-id="b8756-154">Add an Azure Active Directory app in Human Resources</span></span>

1. <span data-ttu-id="b8756-155">I Dynamics 365 Human Resources, öppna sidan **Azure Active Directory-appar**.</span><span class="sxs-lookup"><span data-stu-id="b8756-155">In Dynamics 365 Human Resources, open the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="b8756-156">Lägg till en ny post till listan och ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="b8756-156">Add a new record to the list, and set the following fields:</span></span>

    - <span data-ttu-id="b8756-157">**Klient-ID**: ange **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="b8756-157">**Client ID**: Enter **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    - <span data-ttu-id="b8756-158">**Namn**: Ange namnet på den Power Apps säkerhetsroll som du skapade tidigare, t.ex. **LinkedIn Talent Hub HRIS-integration**.</span><span class="sxs-lookup"><span data-stu-id="b8756-158">**Name**: Enter the name of the Power Apps security role that you created earlier, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>
    - <span data-ttu-id="b8756-159">**Användar-ID**: Välj en användare som har behörighet att skriva data i personalhantering.</span><span class="sxs-lookup"><span data-stu-id="b8756-159">**User ID**: Select a user who has permissions to write data in Personnel Management.</span></span>

### <a name="create-the-entity-in-common-data-service"></a><span data-ttu-id="b8756-160">Skapa entiteten i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b8756-160">Create the entity in Common Data Service</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8756-161">Integrationen med LinkedIn Talent Hub beror på virtuella enheter i Common Data Service för Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b8756-161">The integration with LinkedIn Talent Hub depends on virtual entities in Common Data Service for Human Resources.</span></span> <span data-ttu-id="b8756-162">Som en förutsättning för det här steget i konfigurationen måste du konfigurera virtuella enheter.</span><span class="sxs-lookup"><span data-stu-id="b8756-162">As a prerequisite for this step in the setup, you must configure virtual entities.</span></span> <span data-ttu-id="b8756-163">Mer information om hur du konfigurerar virtuella entiteter finns i [Konfigurera Common Data Service virtuella enheter](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="b8756-163">For information about how to configure virtual entities, see [Configure Common Data Service virtual entities](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

1. <span data-ttu-id="b8756-164">I Human Resources, öppna sidan **Common Data Service (CDS) integration**.</span><span class="sxs-lookup"><span data-stu-id="b8756-164">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="b8756-165">Välj fliken **virtuella entiteter**.</span><span class="sxs-lookup"><span data-stu-id="b8756-165">Select the **Virtual entities** tab.</span></span>

3. <span data-ttu-id="b8756-166">Filtrera enhetslistan efter enhetsetikett för att hitta **LinkedIn-exporterad kandidat**.</span><span class="sxs-lookup"><span data-stu-id="b8756-166">Filter the entity list by entity label to find **LinkedIn exported candidate**.</span></span>

4. <span data-ttu-id="b8756-167">Välj den entiteten och välj sedan **generera/uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="b8756-167">Select the entity, and then select **Generate/refresh**.</span></span>

## <a name="exporting-candidate-records"></a><span data-ttu-id="b8756-168">Exportera kandidatposter</span><span class="sxs-lookup"><span data-stu-id="b8756-168">Exporting candidate records</span></span>

<span data-ttu-id="b8756-169">När installationen är klar kan rekryterare och HR-personal använda funktionen **Exportera till HRIS** i LinkedIn Talent Hub för att exportera anställda kandidatposter från LinkedIn Talent Hub till Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b8756-169">After the setup is completed, recruiters and Human resources (HR) professionals can use the **Export to HRIS** function in LinkedIn Talent Hub to export hired candidate records from LinkedIn Talent Hub to Human Resources.</span></span>

### <a name="export-records-from-linkedin-talent-hub"></a><span data-ttu-id="b8756-170">Exportera poster från LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="b8756-170">Export records from LinkedIn Talent Hub</span></span>

<span data-ttu-id="b8756-171">När en kandidat har gått igenom rekryteringsprocessen och har anställts kan du exportera kandidatposten från LinkedIn Talent Hub till Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b8756-171">After a candidate has moved through the recruiting process and has been hired, you can export the candidate record from LinkedIn Talent Hub to Human Resources.</span></span>

1. <span data-ttu-id="b8756-172">På LinkedIn Talent Hub öppnar du projektet som du har anställt den nya medarbetaren för.</span><span class="sxs-lookup"><span data-stu-id="b8756-172">In LinkedIn Talent Hub, open the project that you hired the new employee for.</span></span>

2. <span data-ttu-id="b8756-173">Välj en kandidatpost.</span><span class="sxs-lookup"><span data-stu-id="b8756-173">Select a candidate record.</span></span>

3. <span data-ttu-id="b8756-174">Välj **Ändra fas** och välj sedan **Anställd**.</span><span class="sxs-lookup"><span data-stu-id="b8756-174">Select **Change stage**, and then select **Hired**.</span></span>

4. <span data-ttu-id="b8756-175">På ellips-menyn (**...**) för kandidaten väljer du **Exportera till HRIS**.</span><span class="sxs-lookup"><span data-stu-id="b8756-175">On the ellipsis menu (**...**) for the candidate, select **Export to HRIS**.</span></span>

5. <span data-ttu-id="b8756-176">I fönstret **Exportera till HRIS** ange informationen som måste exporteras:</span><span class="sxs-lookup"><span data-stu-id="b8756-176">In the **Export to HRIS** pane, enter the information that must be exported:</span></span>

    - <span data-ttu-id="b8756-177">I fältet **HRIS-leverantör** väljer du **Microsoft Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="b8756-177">In the **HRIS provider** field, select **Microsoft Dynamics 365 Human Resources**.</span></span>
    - <span data-ttu-id="b8756-178">I fältet **startdatum** välj ett värde för den nya anställda.</span><span class="sxs-lookup"><span data-stu-id="b8756-178">In the **Start date** field, select a value for the new employee.</span></span>
    - <span data-ttu-id="b8756-179">I fältet **jobbtitel**, ange en jobbtitel för den nya medarbetarens jobb.</span><span class="sxs-lookup"><span data-stu-id="b8756-179">In the **Job title** field, enter a job title for the new employee's job.</span></span>
    - <span data-ttu-id="b8756-180">I fältet **plats** anger du den plats där medarbetaren ska baseras.</span><span class="sxs-lookup"><span data-stu-id="b8756-180">In the **Location** field, enter the location where the employee will be based.</span></span>
    - <span data-ttu-id="b8756-181">Ange eller verifiera medarbetarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="b8756-181">Enter or verify the employee's email address.</span></span>

![Exportera till HRIS-fönstret på LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a><span data-ttu-id="b8756-183">Slutföra registrering i Human Resources</span><span class="sxs-lookup"><span data-stu-id="b8756-183">Complete onboarding in Human Resources</span></span>

<span data-ttu-id="b8756-184">Kandidatposter som exporteras från LinkedIn Talent Hub till Human Resources visas i avsnittet **kandidater att anställa** på sidan **personalhantering**.</span><span class="sxs-lookup"><span data-stu-id="b8756-184">Candidate records that are exported from LinkedIn Talent Hub to Human Resources appear in the **Candidates to hire** section of the **Personnel management** page.</span></span>

1. <span data-ttu-id="b8756-185">I Personal, öppna listsidan **personalhantering**.</span><span class="sxs-lookup"><span data-stu-id="b8756-185">In Human Resources, open the **Personnel management** page.</span></span>

2. <span data-ttu-id="b8756-186">I avsnittet **kandidater att anställa** väljer du **anställa** för den valda kandidaten.</span><span class="sxs-lookup"><span data-stu-id="b8756-186">In the **Candidates to hire** section, select **Hire** for the selected candidate.</span></span>

3. <span data-ttu-id="b8756-187">I dialogrutan **Anställ ny medarbetare** granskar du posten och lägger till nödvändig information.</span><span class="sxs-lookup"><span data-stu-id="b8756-187">In the **Hire new worker** dialog box, review the record, and add any required information.</span></span> <span data-ttu-id="b8756-188">Du kan också välja positionsnumret som kandidaten har anställts för.</span><span class="sxs-lookup"><span data-stu-id="b8756-188">You can also select the position number that the candidate has been hired for.</span></span>

<span data-ttu-id="b8756-189">När den information som krävs har angetts kan du fortsätta med dina standardprocesser för att skapa medarbetarposter och registrera medarbetare.</span><span class="sxs-lookup"><span data-stu-id="b8756-189">After the required information has been entered, you can continue with your standard processes for creating employee records and onboarding employees.</span></span>

<span data-ttu-id="b8756-190">Följande information importeras och inkluderas i den nya medarbetarposten:</span><span class="sxs-lookup"><span data-stu-id="b8756-190">The following details are imported and included on the new employee record:</span></span>

- <span data-ttu-id="b8756-191">Förnamn</span><span class="sxs-lookup"><span data-stu-id="b8756-191">First name</span></span>
- <span data-ttu-id="b8756-192">Efternamn</span><span class="sxs-lookup"><span data-stu-id="b8756-192">Last name</span></span>
- <span data-ttu-id="b8756-193">Startdatum för anställning</span><span class="sxs-lookup"><span data-stu-id="b8756-193">Employment start date</span></span>
- <span data-ttu-id="b8756-194">E-postadress</span><span class="sxs-lookup"><span data-stu-id="b8756-194">Email address</span></span>
- <span data-ttu-id="b8756-195">Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="b8756-195">Phone number</span></span>

## <a name="see-also"></a><span data-ttu-id="b8756-196">Se även</span><span class="sxs-lookup"><span data-stu-id="b8756-196">See also</span></span>

[<span data-ttu-id="b8756-197">Konfigurera Common Data Service virtuella enheter</span><span class="sxs-lookup"><span data-stu-id="b8756-197">Configure Common Data Service virtual entities</span></span>](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="b8756-198">Vad är Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="b8756-198">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
