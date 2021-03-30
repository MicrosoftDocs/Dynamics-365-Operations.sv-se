---
title: Skapa ER-konfigurationer i RCS och överföra dem till den globala databasen
description: Det här förklarar hur du skapar en elektronisk rapporteringskonfiguration (ER) i Microsoft Regulatory Configuration Services (RCS) och laddar upp den till den globala databasen.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: f45749e1bf26eb6f19f326ba8bd15c08436943ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218816"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a><span data-ttu-id="87434-103">Skapa ER-konfigurationer i RCS och överför dem till den globala databasen</span><span class="sxs-lookup"><span data-stu-id="87434-103">Create ER configurations in Regulatory Configuration Services (RCS) and upload them to the Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87434-104">Du kan använda Microsoft RCS (Regulatoryr Configuration Services) för att utforma konfigurationer för elektronisk rapportering (ER) och sedan publicera dem så att de kan användas i din organisation.</span><span class="sxs-lookup"><span data-stu-id="87434-104">You can use Microsoft Regulatory Configuration Services (RCS) to design Electronic reporting (ER) configurations and publish them so that they can be used in your organization.</span></span>

<span data-ttu-id="87434-105">Följande procedurer förklarar hur en användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en härledd version av en ER-konfiguration som har konfigurerats i en RCS-instans och sedan överföra den härledda konfigurationen till den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="87434-105">The following procedures explain how a user in the System Administrator or Electronic Reporting Developer role can create a derived version of an ER configuration that has been configured in an RCS instance, and then upload the derived configuration to the Global repository.</span></span> 

<span data-ttu-id="87434-106">Innan du kan slutföra dessa procedurer måste du först uppfylla följande förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="87434-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="87434-107">Öppna en RCS-instans.</span><span class="sxs-lookup"><span data-stu-id="87434-107">Access an RCS instance.</span></span>
- <span data-ttu-id="87434-108">Skapa en aktiv konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="87434-108">Create an active configuration provider.</span></span> <span data-ttu-id="87434-109">Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="87434-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="87434-110">Du måste också säkerställa att en RCS-miljö har etablerats för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="87434-110">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="87434-111">I en Finance and Operations-app går du till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="87434-111">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="87434-112">Om ingen RCS-miljö har etablerats för ditt företag väljer du **Regulatory services – extern konfiguration** och följer sedan instruktionerna för att etablera en.</span><span class="sxs-lookup"><span data-stu-id="87434-112">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="87434-113">Om en RCS-miljö redan har etablerats för ditt företag kan du använda sidans URL för att komma åt den genom att välja alternativet för inloggning.</span><span class="sxs-lookup"><span data-stu-id="87434-113">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a><span data-ttu-id="87434-114">Skapa en härledd version av en konfiguration i RCS</span><span class="sxs-lookup"><span data-stu-id="87434-114">Create a derived version of a configuration in RCS</span></span>

1. <span data-ttu-id="87434-115">I arbetsytan **Elektronisk rapportering** bekräftar du att du har en aktiv konfigurationsleverantör för din organisation.</span><span class="sxs-lookup"><span data-stu-id="87434-115">In the **Electronic reporting** workspace, verify that you have an active configuration provider for your organization.</span></span> 
2. <span data-ttu-id="87434-116">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="87434-116">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="87434-117">Välj den konfiguration som du vill härleda en ny version från.</span><span class="sxs-lookup"><span data-stu-id="87434-117">Select the configuration that you want to derive a new version from.</span></span> <span data-ttu-id="87434-118">Du kan använda filterfältet ovanför trädet för att begränsa sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="87434-118">You can use the filter field above the tree to narrow your search.</span></span>
4. <span data-ttu-id="87434-119">Välj **Skapa konfiguration** \> **Härled från namn**.</span><span class="sxs-lookup"><span data-stu-id="87434-119">Select **Create configuration** \> **Derive from Name**.</span></span>
5. <span data-ttu-id="87434-120">Ange ett namn och en beskrivning och välj sedan **Skapa konfiguration** för att skapa en ny härledd version.</span><span class="sxs-lookup"><span data-stu-id="87434-120">Enter a name and description, and then select **Create configuration** to create a new derived version.</span></span>
6. <span data-ttu-id="87434-121">Välj den nya härledda konfigurationen, lägg till en beskrivning av versionen och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="87434-121">Select the newly derived configuration, add a description of the version, and then select **OK**.</span></span> <span data-ttu-id="87434-122">Status för konfigurationen ändras till **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="87434-122">The status of the configuration to is changed to **Completed**.</span></span>

![Ny konfigurationsversion i RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> <span data-ttu-id="87434-124">När konfigurationsstatusen ändras kan du få ett meddelande om valideringsfel som berör de anslutna programmen.</span><span class="sxs-lookup"><span data-stu-id="87434-124">When the configuration status is changed, you might receive a validation error message that is related to the connected applications.</span></span> <span data-ttu-id="87434-125">Om du vill inaktivera valideringen grå du till åtgärdsfönstret i fliken **Konfigurationer**, väljer **Användarparametrar** och anger sedan alternativet **Hoppa över validering vid statusändring och ombasering av konfigurationsstatus** som **Ja**</span><span class="sxs-lookup"><span data-stu-id="87434-125">To turn off the validation, on the Action Pane on the **Configurations** tab, select **User parameters**, and then set the **Skip validation at configuration's status change and rebase** option to **Yes**</span></span> 

## <a name="upload-a-configuration-to-the-global-repository"></a><span data-ttu-id="87434-126">Överför en konfiguration till den globala databasen</span><span class="sxs-lookup"><span data-stu-id="87434-126">Upload a configuration to the Global repository</span></span>

<span data-ttu-id="87434-127">Om du vill dela en ny eller härledd konfiguration med din organisation kan du överföra den till den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="87434-127">To share a new or derived configuration with your organization, you can upload it to the Global repository.</span></span>

1. <span data-ttu-id="87434-128">Markera den slutförda versionen av konfigurationen och välj sedan **Överför till databas**.</span><span class="sxs-lookup"><span data-stu-id="87434-128">Select the completed version of the configuration, and then select **Upload into repository**.</span></span>
2. <span data-ttu-id="87434-129">Markera alternativet **Global (Microsoft)** och välj sedan **Överför**.</span><span class="sxs-lookup"><span data-stu-id="87434-129">Select the **Global (Microsoft)** option, and then select **Upload**.</span></span>

    ![Alternativ för databasöverföring](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. <span data-ttu-id="87434-131">Markera **Ja** i bekräftelserutan som visas.</span><span class="sxs-lookup"><span data-stu-id="87434-131">In the confirmation message box, select **Yes**.</span></span> 
4. <span data-ttu-id="87434-132">Uppdatera beskrivningen av versionen efter behov och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="87434-132">Update the description of the version as required, and then select **OK**.</span></span> 

<span data-ttu-id="87434-133">Konfigurationens status uppdateras till **Delas**, och konfigurationen överförs till den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="87434-133">The status of the configuration is updated to **Share**, and the configuration is uploaded to the Global repository.</span></span> <span data-ttu-id="87434-134">Därifrån kan du arbeta med den på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="87434-134">From there, you can work with it in the following ways:</span></span>

- <span data-ttu-id="87434-135">Importera den till din Dynamics 365-instans.</span><span class="sxs-lookup"><span data-stu-id="87434-135">Import it into your Dynamics 365 instance.</span></span> <span data-ttu-id="87434-136">Mer information finns i [Importera konfigurationer för elektronisk rapportering (ER) från RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="87434-136">For more information, see [(ER) Import configurations from RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span></span>
- <span data-ttu-id="87434-137">För att dela den med en tredje part eller en extern organisation, se [RCS Dela konfigurationer för elektronisk rapportering (ER) med externa organisationer](rcs-global-repo-share-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="87434-137">Share it with a third party or an external organization, see [RCS Share Electronic reporting (ER) configurations with external organizations](rcs-global-repo-share-configuration.md)</span></span>

    ![Härledd Intrastat contoso-konfigurationsversion i den globala databasen](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a><span data-ttu-id="87434-139">Radera en konfiguration från den globala databasen</span><span class="sxs-lookup"><span data-stu-id="87434-139">Delete a configuration from the Global repository</span></span>
<span data-ttu-id="87434-140">Gör på följande sätt för att ta bort en konfiguration som din organisation har skapat.</span><span class="sxs-lookup"><span data-stu-id="87434-140">Complete the following steps to delete a configuration that your organization has created.</span></span>

1. <span data-ttu-id="87434-141">I arbetsytan **Elektronisk rapportering** verifierar du att din konfigurationsleverantör är **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="87434-141">In the **Electronic reporting** workspace, verify that your configuration provider is **Active**.</span></span> <span data-ttu-id="87434-142">Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="87434-142">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
2. <span data-ttu-id="87434-143">Välj **databas** i den aktiva konfigurationsleverantören.</span><span class="sxs-lookup"><span data-stu-id="87434-143">On your active configuration provider, select **repository**.</span></span>
3. <span data-ttu-id="87434-144">Välj typ av databas **Global** och sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="87434-144">Select the repository type **Global**, and select **Open**.</span></span>
4. <span data-ttu-id="87434-145">På snabbfliken **Filter** hittar du den konfiguration som du vill radera med hjälp av funktionen **Filter**.</span><span class="sxs-lookup"><span data-stu-id="87434-145">On the **Filter** FastTab, find the configuration that you want to delete by using the **Filter** functionality.</span></span>
5. <span data-ttu-id="87434-146">På snabbfliken **Version** välj den version av konfigurationen som du vill ta bort och välj sedan **Ta bort**:</span><span class="sxs-lookup"><span data-stu-id="87434-146">On the **Version** FastTab, select the version of the configuration that you want to delete, and then select **Delete**:</span></span>

    ![Radera en konfiguration från den globala databasen](media/RCS_Delete_from_GlobalRepo.JPG)

6. <span data-ttu-id="87434-148">Markera **Ja** i bekräftelserutan som visas.</span><span class="sxs-lookup"><span data-stu-id="87434-148">In the confirmation message box, select **Yes**.</span></span>

    ![Ta bort bekräftelsemeddelande för konfigurationsversion](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
<span data-ttu-id="87434-150">Konfigurationsversionen tas bort och bekräftelsemeddelandet visas.</span><span class="sxs-lookup"><span data-stu-id="87434-150">The configuration version is deleted, and confirmation message is shown.</span></span> 

> [!NOTE]
> <span data-ttu-id="87434-151">Konfigurationer kan bara tas bort av den konfigurationsprovider som skapade dem.</span><span class="sxs-lookup"><span data-stu-id="87434-151">Configurations can only be deleted by the Configuration provider that created them.</span></span> <span data-ttu-id="87434-152">Om konfigurationen har delats med en annan organisation måste konfigurationen delas ut innan du kan ta bort den.</span><span class="sxs-lookup"><span data-stu-id="87434-152">If the configuration has been shared with another organization, the configuration will need to be unshared before you delete it.</span></span>
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]