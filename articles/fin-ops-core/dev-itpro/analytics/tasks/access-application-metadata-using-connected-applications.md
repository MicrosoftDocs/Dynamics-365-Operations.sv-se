---
title: Få åtkomst till programmets metadata med hjälp av anslutna program
description: Stegen i det här avsnittet beskriver hur en användare av Regulatory Configuration Service kan utforma en ny modellmappning för elektronisk rapportering genom att använda metadata.
author: NickSelin
manager: AnnBe
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 457d5760fb704b7a93ce16c081b7c5e6d0ff19c1
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093340"
---
# <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="2a2d3-103">Få åtkomst till programmets metadata med hjälp av anslutna program</span><span class="sxs-lookup"><span data-stu-id="2a2d3-103">Access application metadata by using connected applications</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2a2d3-104">I följande steg förklaras hur en användare av Regulatory configuration service (RCS) i rollen Systemadministratör eller Utvecklare av elektronisk rapportering kan utforma en ny modellmappning för elektronisk rapportering (ER) genom att använda metadata i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using metadata in Finance and Operations.</span></span> <span data-ttu-id="2a2d3-105">Programdata kan nås online genom att använda det RCS-anslutna programmet.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-105">Application metadata will be accessed online by using the RCS connected application.</span></span> <span data-ttu-id="2a2d3-106">Exempel på ER-modellmappning kommer att konfigureras för åtkomst till utländska handelstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-106">Sample ER model mapping will be configured to access foreign trade transactions.</span></span> <span data-ttu-id="2a2d3-107">För att slutföra dessa steg i RCS måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="2a2d3-107">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="2a2d3-108">Om du inte har slutfört stegen i ämnet [Få åtkomst till programdata genom att använda ER-konfiguration](access-application-metadata-er-configuration.md), gå till [Exeempelsidan för Elektronisk rapportering](https://go.microsoft.com/fwlink/?linkid=862266) för att hämta och spara följande ER-konfigurationer: Utländsk handel metadata.xml; Utländsk handel model.xml; Utländsk handel mapping.xml och slutför sedan stegen i proceduren.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-108">If you have not completed the steps in the topic, [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md), go to the [Electronic reporting examples page](https://go.microsoft.com/fwlink/?linkid=862266) to download and save the following ER configurations: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, and then complete the steps in the procedure.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2a2d3-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="2a2d3-109">Prerequisites</span></span>
1. <span data-ttu-id="2a2d3-110">Gå till **Alla arbetsytor** > **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-110">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="2a2d3-111">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="2a2d3-112">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="2a2d3-112">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="get-required-er-configurations"></a><span data-ttu-id="2a2d3-113">Skapa nödvändiga ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="2a2d3-113">Get required ER configurations</span></span>
1. <span data-ttu-id="2a2d3-114">Klicka på **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-114">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="2a2d3-115">Om du redan har slutfört stegen i proceduren [Få åtkomst till programdata genom att använda ER-konfiguration](access-application-metadata-er-configuration.md) har du redan alla ER-konfigurationer (metadata för utländsk handel, modell- och mappningskonfiguration) i den aktuella RCS-instansresursen.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-115">If you already completed the steps in the [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md) procedure, you already have all necessary ER configurations (foreign trade metadata, model and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="2a2d3-116">Du kan hoppa över resten av stegen i den här underaktivitet.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-116">You can skip all the remaining steps of this sub-task.</span></span> 
3. <span data-ttu-id="2a2d3-117">Klicka på **Byt**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-117">Click **Exchange**.</span></span> 
4. <span data-ttu-id="2a2d3-118">Klicka på **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-118">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="2a2d3-119">Klicka på **Bläddra** och välj filen **Utländsk handel metadata.xml**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-119">Click **Browse** and select the **Foreign trade metadata.xml** file.</span></span> 
6. <span data-ttu-id="2a2d3-120">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-120">Click **OK**.</span></span> 
7. <span data-ttu-id="2a2d3-121">Klicka på **Byt**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-121">Click **Exchange**.</span></span> 
8. <span data-ttu-id="2a2d3-122">Klicka på **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-122">Click **Load from XML file**.</span></span> 
9. <span data-ttu-id="2a2d3-123">Klicka på **Bläddra** och välj filen **Utländsk handel model.xml**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-123">Click **Browse** and select the **Foreign trade model.xml** file.</span></span> 
10. <span data-ttu-id="2a2d3-124">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-124">Click **OK**.</span></span> 
11. <span data-ttu-id="2a2d3-125">Klicka på **Byt**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-125">Click **Exchange**.</span></span> 
12. <span data-ttu-id="2a2d3-126">Klicka på **Läs in från XML-fil**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-126">Click **Load from XML file**.</span></span> 
13. <span data-ttu-id="2a2d3-127">Klicka på **Bläddra** och välj filen **Utländsk handel mapping.xml**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-127">Click **Browse** and select the **Foreign trade mapping.xml** file.</span></span> 
14. <span data-ttu-id="2a2d3-128">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-128">Click **OK**.</span></span> 

## <a name="register-a-connected-application"></a><span data-ttu-id="2a2d3-129">Registrera kopplat program</span><span class="sxs-lookup"><span data-stu-id="2a2d3-129">Register a connected application</span></span>
1. <span data-ttu-id="2a2d3-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-130">Close the page.</span></span> 
2. <span data-ttu-id="2a2d3-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-131">Close the page.</span></span> 
3. <span data-ttu-id="2a2d3-132">Gå till **Alla arbetsytor** > **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-132">Go to **All workspaces** > **Electronic reporting**.</span></span> 
4. <span data-ttu-id="2a2d3-133">Klicka på **anslutna program**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-133">Click **Connected applications**.</span></span> 
5. <span data-ttu-id="2a2d3-134">Kontrollera att det konfigurerade programmet är Azure-baserat och tillgängligt för den aktuella RCS-användaren.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-134">Make sure that the configured application is Azure based and accessible for the current RCS user.</span></span> <span data-ttu-id="2a2d3-135">Det krävs också att den aktuella RCS-användaren har åtkomst till det valda programmet och har registrerats som en användare av det här programmet som spelar en roll som ger dem behörighet att komma åt programmets metadata.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-135">It is also required that the current RCS user has access to the selected application and has been registered as a user of this application playing a role giving them privileges to access application's metadata.</span></span> 
6. <span data-ttu-id="2a2d3-136">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-136">Click **New**.</span></span> 
7. <span data-ttu-id="2a2d3-137">I fältet **Namn** ange MyConnectedApp.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-137">In the **Name** field, type 'MyConnectedApp'.</span></span> 
8. <span data-ttu-id="2a2d3-138">I fältet **program**, skriv https:// mycompany.operations.dynamics.com'.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-138">In the **Application** field, type 'https:// mycompany.operations.dynamics.com'.</span></span> 
9. <span data-ttu-id="2a2d3-139">I fältet **klientinnehavare** skriver du "mycompany.onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="2a2d3-139">In the **Tenant** field, type 'mycompany.onmicrosoft.com'.</span></span> 
10. <span data-ttu-id="2a2d3-140">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-140">Click **Save**.</span></span> 
11. <span data-ttu-id="2a2d3-141">När du kontrollerar anslutningen till ett konfigurerat program klickar du på sidan **Anslut till fjärrprogram**, klicka på länken **Klicka här för att ansluta till valt fjärrprogram**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-141">When you check connection to configured application, on the **Connect to remote application** page click **Click here to connect to selected remote application** link.</span></span> 
12. <span data-ttu-id="2a2d3-142">Klicka **kontrollera anslutning**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-142">Click **Check connection**.</span></span> 
13. <span data-ttu-id="2a2d3-143">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-143">Click **Close**.</span></span> 
14. <span data-ttu-id="2a2d3-144">När anslutningsvalideringen är klar uppdateras informationen om version och klientorganisation för det konfigurerade programmet i det aktuella rutnätet.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-144">When the connection validation succeeded, version and tenant details will be updated for the configured application in the current grid.</span></span> 

## <a name="review-existing-model-mapping-configuration"></a><span data-ttu-id="2a2d3-145">Granska befintlig konfiguration för mappning</span><span class="sxs-lookup"><span data-stu-id="2a2d3-145">Review existing model mapping configuration</span></span>
1. <span data-ttu-id="2a2d3-146">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-146">Close the page.</span></span> 
2. <span data-ttu-id="2a2d3-147">Klicka på **Rapporteringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-147">Click **Reporting configurations**.</span></span> 
3. <span data-ttu-id="2a2d3-148">I trädet, expandera **Utländsk handelsmodell**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-148">In the tree, expand **Foreign trade model**.</span></span> 
4. <span data-ttu-id="2a2d3-149">I trädet väljer du **Utländsk handelsmodell\Utländsk handelsmappning**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-149">In the tree, select **Foreign trade model\Foreign trade mapping**.</span></span> 
5. <span data-ttu-id="2a2d3-150">Expandera avsnittet **Förutsättningar**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-150">Expand the **Prerequisites** section.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2a2d3-151">Denna mappning refererar till konfigurationen för metadata.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-151">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="2a2d3-152">Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-152">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

6. <span data-ttu-id="2a2d3-153">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-153">Click **Designer**.</span></span> 
7. <span data-ttu-id="2a2d3-154">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-154">Click **Designer**.</span></span> 
8. <span data-ttu-id="2a2d3-155">Välj **Dynamics 365 for Operations\Tabellregister** i trädet.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-155">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
9. <span data-ttu-id="2a2d3-156">Klicka på **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-156">Click **Add root**.</span></span> 
10. <span data-ttu-id="2a2d3-157">Ange eller välj ett värde i fältet **Register**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-157">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2a2d3-158">Denna mappning refererar till konfigurationen för metadata.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-158">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="2a2d3-159">Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-159">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

11. <span data-ttu-id="2a2d3-160">Klicka på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-160">Click **Cancel**.</span></span> 
12. <span data-ttu-id="2a2d3-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-161">Close the page.</span></span> 
13. <span data-ttu-id="2a2d3-162">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-162">Close the page.</span></span> 

## <a name="assign-connected-application-to-model-mapping"></a><span data-ttu-id="2a2d3-163">Tilldela kopplat program till modellmappning</span><span class="sxs-lookup"><span data-stu-id="2a2d3-163">Assign connected application to model mapping</span></span> 
1. <span data-ttu-id="2a2d3-164">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-164">Click **Edit**.</span></span> 
2. <span data-ttu-id="2a2d3-165">Välj **MyConnectedApp**-program.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-165">Select **MyConnectedApp** application.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2a2d3-166">För närvarande refererar denna mappning till metadata för det markerade anslutna programmet.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-166">Currently, this mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="2a2d3-167">När samma mappning refererar till metadatakonfigurationen och det anslutna programmet samtidigt, används metadata för det anslutna programmet.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-167">When the same mapping refers to metadata configuration and connected application at the same time, metadata of the connected application will be used.</span></span> 

3. <span data-ttu-id="2a2d3-168">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-168">Click **Designer**.</span></span> 
4. <span data-ttu-id="2a2d3-169">Klicka på **Designer**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-169">Click **Designer**.</span></span> 
5. <span data-ttu-id="2a2d3-170">Välj **Dynamics 365 for Operations\Tabellregister** i trädet.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
6. <span data-ttu-id="2a2d3-171">Klicka på **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-171">Click **Add root**.</span></span> 
7. <span data-ttu-id="2a2d3-172">Ange eller välj ett värde i fältet **Register**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-172">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2a2d3-173">Fler än två programtabeller erbjöds nu eftersom mappningen använder alla metadata för det anslutna program som har tilldelats för det.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-173">More than two application tables were offered now as this mapping uses all the metadata of the connected application that has been assigned for it.</span></span> 

8. <span data-ttu-id="2a2d3-174">Klicka på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-174">Click **Cancel**.</span></span> 
9. <span data-ttu-id="2a2d3-175">Klicka på **Validera.**</span><span class="sxs-lookup"><span data-stu-id="2a2d3-175">Click **Validate**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2a2d3-176">Vi har bundit element i datamodellen med objekt av datakällor som beskrivs genom att använda information om metadata för det anslutna program som har tilldelats den här mappningen.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-176">We successfully bound elements of data model with items of data sources that are described by using details of metadata of the connected application that has been assigned for this mapping.</span></span> 

10. <span data-ttu-id="2a2d3-177">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-177">Close the page.</span></span> 
11. <span data-ttu-id="2a2d3-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-178">Close the page.</span></span> 

<span data-ttu-id="2a2d3-179">När du behöver utvärdera den här modellmappningen med hjälp av metadata i ett annat versionsprogram, registrerar du ett annat anslutet program, tilldelar det till den här modellmappningen och validerar det mot nya metadata.</span><span class="sxs-lookup"><span data-stu-id="2a2d3-179">When you need to evaluate this model mapping by using metadata of a different version application, register another connected application, assign it to this model mapping and validate it against new metadata.</span></span>
