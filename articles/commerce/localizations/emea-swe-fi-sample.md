---
title: Exempel på integration av kontrollenhet för Sverige
description: I det här avsnittet finns en översikt över exemplet på räkenskapsintegration för Sverige.
author: sepism
manager: annbe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Sweden
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 41333f8c0ec77a591d372c5b0654585d05872a5c
ms.sourcegitcommit: fa5c45f7842c4d20c994ac1655e2fbf2a1cf14a9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/28/2020
ms.locfileid: "3734899"
---
# <a name="control-unit-integration-sample-for-sweden"></a><span data-ttu-id="90e98-103">Exempel på integration av kontrollenhet för Sverige</span><span class="sxs-lookup"><span data-stu-id="90e98-103">Control unit integration sample for Sweden</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="90e98-104">Den här exempelfunktionen räkenskapsintegrering ersätter det tidigare [exemplet för POS-integrering med styrenheter för Sverige](retail-sdk-control-unit-sample.md).</span><span class="sxs-lookup"><span data-stu-id="90e98-104">This sample fiscal integration functionality replaces the earlier [Sample for POS integration with control units for Sweden](retail-sdk-control-unit-sample.md).</span></span> <span data-ttu-id="90e98-105">Det tidigare exemplet utnyttjar inte [ramverket för räkenskapsintegration](./fiscal-integration-for-retail-channel.md) och blir föråldrat i senare uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="90e98-105">The earlier sample doesn't take advantage of the [fiscal integration framework](./fiscal-integration-for-retail-channel.md) and will become obsolete in later updates.</span></span> <span data-ttu-id="90e98-106">Information om hur du migrerar från det tidigare exemplet till det aktuella exemplet finns i avsnittet [migrera från det tidigare integrationsexemplet](#migrating-from-the-earlier-integration-sample).</span><span class="sxs-lookup"><span data-stu-id="90e98-106">For information about how to migrate from the earlier sample to the current sample, see the [Migrating from the earlier integration sample](#migrating-from-the-earlier-integration-sample) section.</span></span>

## <a name="introduction"></a><span data-ttu-id="90e98-107">Introduktion</span><span class="sxs-lookup"><span data-stu-id="90e98-107">Introduction</span></span>

<span data-ttu-id="90e98-108">Commerce-funktionen för Sverige inkluderar ett exempel för att integrera kassa med Sverige-specifika kvittoskrivarenhet som kallas *kontrollenheter*.</span><span class="sxs-lookup"><span data-stu-id="90e98-108">The Commerce functionality for Sweden includes a sample integration of the point of sale (POS) with Sweden-specific fiscal devices that are known as *control units*.</span></span> <span data-ttu-id="90e98-109">Det här exemplet utökar [funktionen räkenskapsintegrering](fiscal-integration-for-retail-channel.md).</span><span class="sxs-lookup"><span data-stu-id="90e98-109">This sample extends the [fiscal integration functionality](fiscal-integration-for-retail-channel.md).</span></span> <span data-ttu-id="90e98-110">Det antas att en enhet är fysiskt ansluten till maskinvarustationerna som kassan är kopplad till.</span><span class="sxs-lookup"><span data-stu-id="90e98-110">It's assumed that a control unit is physically connected to a Hardware station that the POS is paired with.</span></span> <span data-ttu-id="90e98-111">Som exempel använder det här exemplet programmeringsgränssnittet (API) för [Cleancash-typen A](https://www.retailinnovation.se/produkter)-styrenhet av Retail innovation HTT AB.</span><span class="sxs-lookup"><span data-stu-id="90e98-111">As an example, this sample uses the application programming interface (API) of the [CleanCash Type A](https://www.retailinnovation.se/produkter) control unit by Retail Innovation HTT AB.</span></span> <span data-ttu-id="90e98-112">Version 1.1.4 av CleanCash-API används.</span><span class="sxs-lookup"><span data-stu-id="90e98-112">Version 1.1.4 of the CleanCash API is used.</span></span>

<span data-ttu-id="90e98-113">Exemplet tillhandahålls i form av källkod och är en del av Retail Software Development Kit (SDK).</span><span class="sxs-lookup"><span data-stu-id="90e98-113">The sample is provided in the form of source code and is part of the Retail software development kit (SDK).</span></span>

<span data-ttu-id="90e98-114">Microsoft släpper inte någon maskinvara, programvara eller dokumentation från Retail innovation HTT AB.</span><span class="sxs-lookup"><span data-stu-id="90e98-114">Microsoft doesn't release any hardware, software, or documentation from Retail Innovation HTT AB.</span></span> <span data-ttu-id="90e98-115">För information om hur du får kontrollenheten och använder den, kontakta [Retail Innovation HTT AB](https://www.retailinnovation.se/).</span><span class="sxs-lookup"><span data-stu-id="90e98-115">For information about how to get the control unit and operate it, contact [Retail Innovation HTT AB](https://www.retailinnovation.se/).</span></span>

## <a name="scenarios"></a><span data-ttu-id="90e98-116">Scenarier</span><span class="sxs-lookup"><span data-stu-id="90e98-116">Scenarios</span></span>

<span data-ttu-id="90e98-117">Kontrollenhetens integrering av prov för Sverige omfattar följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="90e98-117">The control unit integration sample for Sweden includes the following capabilities:</span></span>

- <span data-ttu-id="90e98-118">Försäljning, returer och kvittokopior registreras automatiskt i en kontrollenhet som är ansluten till maskinvarustationen som är kopplad till kassan.</span><span class="sxs-lookup"><span data-stu-id="90e98-118">Sales, returns, and receipt copies are automatically registered in a control unit that is connected to the Hardware station that is paired with the POS.</span></span>
- <span data-ttu-id="90e98-119">Kontrollkoden och tillverkningsnumret för kontrollenheten för en registrerad transaktion fångas in från kontrollenheten och sparas i transaktionen.</span><span class="sxs-lookup"><span data-stu-id="90e98-119">The control code and the manufacturing number of the control unit for a registered transaction are captured from the control unit and saved in the transaction.</span></span> <span data-ttu-id="90e98-120">Dessa data kallas också ett *räkenskapssvar*.</span><span class="sxs-lookup"><span data-stu-id="90e98-120">This data is also referred to as a *fiscal response*.</span></span> <span data-ttu-id="90e98-121">Det skattemässiga svaret kan visas på sidan **butikstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="90e98-121">The fiscal response can be viewed on the **Store transactions** page.</span></span>
- <span data-ttu-id="90e98-122">Anpassade fält för kontrollkoden och tillverkningsnumret för kontrollenheten kan läggas till en kvittolayout.</span><span class="sxs-lookup"><span data-stu-id="90e98-122">Custom fields for the control code and the manufacturing number of the control unit can be added to a receipt layout.</span></span> <span data-ttu-id="90e98-123">På så sätt kan du skriva ut räkenskapsårets svar för en transaktion på en inleverans.</span><span class="sxs-lookup"><span data-stu-id="90e98-123">In that way, you can print the fiscal response for a transaction on a receipt.</span></span>
- <span data-ttu-id="90e98-124">Räkenskapssvar för en transaktion visas på kanalrapporten **elektronisk journal (Sverige)**.</span><span class="sxs-lookup"><span data-stu-id="90e98-124">The fiscal response for a transaction is shown on the **Electronic journal (Sweden)** channel report.</span></span>
- <span data-ttu-id="90e98-125">Det finns flera alternativ för felhantering.</span><span class="sxs-lookup"><span data-stu-id="90e98-125">Several error handling options are available.</span></span> <span data-ttu-id="90e98-126">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="90e98-126">Here are some examples:</span></span>

    - <span data-ttu-id="90e98-127">Försök med räkenskapsregistrering om ett nytt försök är möjligt.</span><span class="sxs-lookup"><span data-stu-id="90e98-127">Retry fiscal registration, if a retry is possible.</span></span> <span data-ttu-id="90e98-128">Du kan försöka registrera räkenskapsregistrering om till exempel styrenheten inte är ansluten, inte är redo eller inte svarar.</span><span class="sxs-lookup"><span data-stu-id="90e98-128">You can retry fiscal registration if, for example, the control unit isn't connected, isn't ready, or isn't responding.</span></span>
    - <span data-ttu-id="90e98-129">Senarelägg räkenskapsregistrering.</span><span class="sxs-lookup"><span data-stu-id="90e98-129">Postpone fiscal registration.</span></span>
    - <span data-ttu-id="90e98-130">Hoppa över räkenskapsregistrering eller markera transaktionen som registrerad och inkludera informationskoder för att fånga orsaken till felet och ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="90e98-130">Skip fiscal registration, or mark the transaction as registered, and include info codes to capture the reason for the failure and additional information.</span></span>
    - <span data-ttu-id="90e98-131">Kontrollera tillgängligheten för kontrollenheten innan en ny försäljningstransaktion öppnas eller en försäljningstransaktion slutförs.</span><span class="sxs-lookup"><span data-stu-id="90e98-131">Verify the availability of the control unit before a new sales transaction is opened or a sales transaction is finalized.</span></span>

### <a name="default-data-mapping"></a><span data-ttu-id="90e98-132">Standarddatamappning</span><span class="sxs-lookup"><span data-stu-id="90e98-132">Default data mapping</span></span>

<span data-ttu-id="90e98-133">Följande standarddatamappning ingår i konfigurationen av leverantören av skattedokument som distribueras som en del av exemplet på räkenskapsintegration.</span><span class="sxs-lookup"><span data-stu-id="90e98-133">The following default data mapping is included in the fiscal document provider configuration that is distributed as a part of the fiscal integration sample.</span></span>

<span data-ttu-id="90e98-134">**Kodmappning för mervärdesskatt (VAT)** anger enhetsspecifika koder för mervärdesskatt (VAT) till motsvarande momskoder.</span><span class="sxs-lookup"><span data-stu-id="90e98-134">**Value-added tax (VAT) code mapping** sets device-specific value-added tax (VAT) codes to corresponding sales tax codes.</span></span> <span data-ttu-id="90e98-135">Kodmappning av mervärdesskatt bör ha följande format:</span><span class="sxs-lookup"><span data-stu-id="90e98-135">VAT code mapping should have the following format:</span></span>

<span data-ttu-id="90e98-136">*1 : kod1 ; 2 : kod2*</span><span class="sxs-lookup"><span data-stu-id="90e98-136">*1 : code1 ; 2 : code2*</span></span>

<span data-ttu-id="90e98-137">Här följer en förklaring av detta format:</span><span class="sxs-lookup"><span data-stu-id="90e98-137">Here is an explanation of this format:</span></span>

- <span data-ttu-id="90e98-138">*1* och *2* är enhetsspecifika momskoder.</span><span class="sxs-lookup"><span data-stu-id="90e98-138">*1* and *2* are device-specific VAT codes.</span></span>
- <span data-ttu-id="90e98-139">Ett semikolon (;) används som avgränsare.</span><span class="sxs-lookup"><span data-stu-id="90e98-139">A semicolon (;) is used as a separator.</span></span>
- <span data-ttu-id="90e98-140">*kod1* och *kod2* är momskoder som har konfigurerat i Administration.</span><span class="sxs-lookup"><span data-stu-id="90e98-140">*code1* and *code2* are sales tax codes that are configured in Headquarters.</span></span>

<span data-ttu-id="90e98-141">Styrenheter stöder upp till fyra olika momskoder.</span><span class="sxs-lookup"><span data-stu-id="90e98-141">Control units support up to four different VAT codes.</span></span> <span data-ttu-id="90e98-142">Därför kan momskodmappningen ställas in på det sätt som visas här:</span><span class="sxs-lookup"><span data-stu-id="90e98-142">Therefore, the VAT code mapping might be set up as shown here:</span></span>

<span data-ttu-id="90e98-143">*1 : kod1 ; 2 : kod2 ; 3 : kod3 ; 4 : kod4*</span><span class="sxs-lookup"><span data-stu-id="90e98-143">*1 : code1 ; 2 : code2 ; 3 : code3 ; 4 : code4*</span></span>

> [!NOTE]
> <span data-ttu-id="90e98-144">Flera momskoder kan mappas till samma enhetsspecifika momskod.</span><span class="sxs-lookup"><span data-stu-id="90e98-144">Multiple sales tax codes can be mapped to the same device-specific VAT code.</span></span>

### <a name="limitations-of-the-sample"></a><span data-ttu-id="90e98-145">Begränsningar i provet</span><span class="sxs-lookup"><span data-stu-id="90e98-145">Limitations of the sample</span></span>

<span data-ttu-id="90e98-146">Styrenhetens integrationsprov för Sverige stöder för närvarande inte orderscenarier.</span><span class="sxs-lookup"><span data-stu-id="90e98-146">The control unit integration sample for Sweden doesn't currently support customer order scenarios.</span></span>

## <a name="setting-up-the-integration-with-control-units"></a><span data-ttu-id="90e98-147">Ställa in integrationen med styrenheter</span><span class="sxs-lookup"><span data-stu-id="90e98-147">Setting up the integration with control units</span></span>

<span data-ttu-id="90e98-148">Mer information om de inställningar som krävs för Sverige finns i [ställa in Handel för Sverige](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).</span><span class="sxs-lookup"><span data-stu-id="90e98-148">For more information about the setup that is required for Sweden, see [Setting up Commerce for Sweden](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).</span></span>

### <a name="configuring-swedenspecific-receipts"></a><span data-ttu-id="90e98-149">Konfigurera Sverige – specifika kvitton</span><span class="sxs-lookup"><span data-stu-id="90e98-149">Configuring Sweden–specific receipts</span></span>

#### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a><span data-ttu-id="90e98-150">Konfigurera anpassade fält så att de kan användas i kvittoformat för försäljningskvitton</span><span class="sxs-lookup"><span data-stu-id="90e98-150">Configure custom fields so that they can be used in receipt formats for sales receipts</span></span>

<span data-ttu-id="90e98-151">Du kan konfigurera språktext och anpassade fält som används i kassakvittoformat.</span><span class="sxs-lookup"><span data-stu-id="90e98-151">You can configure the language text and custom fields that are used in POS receipt formats.</span></span> <span data-ttu-id="90e98-152">Standardföretaget för den användare som skapar kvittoinställningen bör vara samma juridiska person där språktextinställningarna skapas.</span><span class="sxs-lookup"><span data-stu-id="90e98-152">The default company of the user who creates the receipt setup should be the same legal entity where the language text setup is created.</span></span> <span data-ttu-id="90e98-153">Du kan också skapa samma språktexter i både användarens standardföretag och den juridiska personen i butiken som installationen har skapats för.</span><span class="sxs-lookup"><span data-stu-id="90e98-153">Alternatively, the same language texts should be created in both the user's default company and the legal entity of the store that the setup is created for.</span></span>

<span data-ttu-id="90e98-154">På sidan **Språktext** kan du lägga till följande poster för etiketterna för de anpassade fälten för kvittolayout.</span><span class="sxs-lookup"><span data-stu-id="90e98-154">On the **Language text** page, add the following records for the labels of the custom fields for receipt layouts.</span></span> <span data-ttu-id="90e98-155">Observera att värdena **Språk-ID**, **Text-ID** och **Text** som visas i tabellen bara är exempel.</span><span class="sxs-lookup"><span data-stu-id="90e98-155">Note that the **Language ID**, **Text ID**, and **Text** values that are shown in the table are just examples.</span></span> <span data-ttu-id="90e98-156">Du kan ändra dem för att uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="90e98-156">You can change them to meet your requirements.</span></span> <span data-ttu-id="90e98-157">Värdena för **text-ID** som du använder måste dock vara unika och de måste vara lika med eller större än 900001.</span><span class="sxs-lookup"><span data-stu-id="90e98-157">However, the **Text ID** values that you use must be unique, and they must be equal to or greater than 900001.</span></span>

<span data-ttu-id="90e98-158">Lägg till följande kassaetiketter i avsnittet **kassa** på sidan **språktext**.</span><span class="sxs-lookup"><span data-stu-id="90e98-158">Add the following POS labels in the **POS** section of the **Language text** page.</span></span>

| <span data-ttu-id="90e98-159">Språk-ID</span><span class="sxs-lookup"><span data-stu-id="90e98-159">Language ID</span></span> | <span data-ttu-id="90e98-160">Text-ID</span><span class="sxs-lookup"><span data-stu-id="90e98-160">Text ID</span></span> | <span data-ttu-id="90e98-161">Text</span><span class="sxs-lookup"><span data-stu-id="90e98-161">Text</span></span>                  |
|-------------|---------|-----------------------|
| <span data-ttu-id="90e98-162">en-US</span><span class="sxs-lookup"><span data-stu-id="90e98-162">en-US</span></span>       | <span data-ttu-id="90e98-163">900001</span><span class="sxs-lookup"><span data-stu-id="90e98-163">900001</span></span>  | <span data-ttu-id="90e98-164">Registrera kontrollkod</span><span class="sxs-lookup"><span data-stu-id="90e98-164">Register control code</span></span> |
| <span data-ttu-id="90e98-165">en-US</span><span class="sxs-lookup"><span data-stu-id="90e98-165">en-US</span></span>       | <span data-ttu-id="90e98-166">900002</span><span class="sxs-lookup"><span data-stu-id="90e98-166">900002</span></span>  | <span data-ttu-id="90e98-167">Registrera enhet</span><span class="sxs-lookup"><span data-stu-id="90e98-167">Register device</span></span>       |

<span data-ttu-id="90e98-168">På sidan **Anpassade fält** kan du lägga till följande poster för anpassade fält för kvittolayouter.</span><span class="sxs-lookup"><span data-stu-id="90e98-168">On the **Custom fields** page, add the following records for the custom fields for receipt layouts.</span></span> <span data-ttu-id="90e98-169">Observera att värdena **Text-ID för rubrik** måste motsvara de värden för **Text-ID** som du angav på sidan **språktext**.</span><span class="sxs-lookup"><span data-stu-id="90e98-169">Note that **Caption text ID** values must correspond to the **Text ID** values that you specified on the **Language text** page.</span></span>

| <span data-ttu-id="90e98-170">Namn</span><span class="sxs-lookup"><span data-stu-id="90e98-170">Name</span></span>                         | <span data-ttu-id="90e98-171">Typ</span><span class="sxs-lookup"><span data-stu-id="90e98-171">Type</span></span>    | <span data-ttu-id="90e98-172">Text-ID för rubrik</span><span class="sxs-lookup"><span data-stu-id="90e98-172">Caption text ID</span></span> |
|------------------------------|---------|-----------------|
| <span data-ttu-id="90e98-173">SE_FISCALREGISTERCONTROLCODE</span><span class="sxs-lookup"><span data-stu-id="90e98-173">SE_FISCALREGISTERCONTROLCODE</span></span> | <span data-ttu-id="90e98-174">Inleverans</span><span class="sxs-lookup"><span data-stu-id="90e98-174">Receipt</span></span> | <span data-ttu-id="90e98-175">900001</span><span class="sxs-lookup"><span data-stu-id="90e98-175">900001</span></span>          |
| <span data-ttu-id="90e98-176">SE_FISCALREGISTERID</span><span class="sxs-lookup"><span data-stu-id="90e98-176">SE_FISCALREGISTERID</span></span>          | <span data-ttu-id="90e98-177">Inleverans</span><span class="sxs-lookup"><span data-stu-id="90e98-177">Receipt</span></span> | <span data-ttu-id="90e98-178">900002</span><span class="sxs-lookup"><span data-stu-id="90e98-178">900002</span></span>          |

#### <a name="configure-receipt-formats"></a><span data-ttu-id="90e98-179">Konfigurera kvittoformat</span><span class="sxs-lookup"><span data-stu-id="90e98-179">Configure receipt formats</span></span>

<span data-ttu-id="90e98-180">För varje kvittoformat som krävs, ändra värdet för fältet **Utskriftssätt** till **Skriv alltid ut**.</span><span class="sxs-lookup"><span data-stu-id="90e98-180">For every receipt format that is required, change the value of the **Print behavior** field to **Always print**.</span></span>

<span data-ttu-id="90e98-181">I Layoutdesigner för kvitto, lägg till följande anpassade fält i avsnittet **Sidfot**.</span><span class="sxs-lookup"><span data-stu-id="90e98-181">In the Receipt format designer, add the following custom fields to the **Footer** section.</span></span> <span data-ttu-id="90e98-182">Observera att fältnamn motsvarar de språktexter som du definierade i föregående avsnitt i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="90e98-182">Note that field names correspond to the language texts that you defined in the previous section of this topic.</span></span>

- <span data-ttu-id="90e98-183">**Registrera kontrollkod** – det här fältet skriver ut kontrollkoden.</span><span class="sxs-lookup"><span data-stu-id="90e98-183">**Register control code** – This field prints the control code.</span></span>
- <span data-ttu-id="90e98-184">**Registrera enhet** – i det här fältet skrivs kontrollenhetens tillverkningsnummer ut.</span><span class="sxs-lookup"><span data-stu-id="90e98-184">**Register device** – This field prints the manufacturing number of the control unit.</span></span>

<span data-ttu-id="90e98-185">Mer information om hur du arbetar med kvittoformat finns i [Kvittomallar och utskrift](../receipt-templates-printing.md).</span><span class="sxs-lookup"><span data-stu-id="90e98-185">For more information about how to work with receipt formats, see [Receipt templates and printing](../receipt-templates-printing.md).</span></span>

### <a name="configure-fiscal-integration"></a><span data-ttu-id="90e98-186">Konfigurera räkenskapsintegration</span><span class="sxs-lookup"><span data-stu-id="90e98-186">Configure fiscal integration</span></span>

<span data-ttu-id="90e98-187">Slutför konfigurationsstegen för räkenskapsintegration som beskrivs i [ställa in räkenskapsintegration för Commerce-kanaler](setting-up-fiscal-integration-for-retail-channel.md):</span><span class="sxs-lookup"><span data-stu-id="90e98-187">Complete the fiscal integration setup steps that are described in [Set up the fiscal integration for Commerce channels](setting-up-fiscal-integration-for-retail-channel.md):</span></span>

- <span data-ttu-id="90e98-188">[Ställa in process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).</span><span class="sxs-lookup"><span data-stu-id="90e98-188">[Set up a fiscal registration process](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).</span></span> <span data-ttu-id="90e98-189">Var noga med att notera inställningarna för den process för räkenskapsregistrering som är [specifika för det här kontrollenhetens integrering av prov](#set-up-the-registration-process).</span><span class="sxs-lookup"><span data-stu-id="90e98-189">Be sure to note the settings for the fiscal registration process that are [specific to this control unit integration sample](#set-up-the-registration-process).</span></span>
- <span data-ttu-id="90e98-190">[Ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).</span><span class="sxs-lookup"><span data-stu-id="90e98-190">[Set error handling settings](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).</span></span>
- <span data-ttu-id="90e98-191">[Aktivera manuell körning av uppskjutna räkenskapsregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).</span><span class="sxs-lookup"><span data-stu-id="90e98-191">[Enable manual execution of postponed fiscal registration](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).</span></span>

## <a name="deployment-guidelines-for-cash-registers-for-sweden"></a><span data-ttu-id="90e98-192">Riktlinjer för distribution av kassaapparater för Sverige</span><span class="sxs-lookup"><span data-stu-id="90e98-192">Deployment guidelines for cash registers for Sweden</span></span>

<span data-ttu-id="90e98-193">Det här avsnittet fungerar som en distributionsguide som visar hur du aktiverar lokalisering av Microsoft Dynamics 365 Commerce för Sverige.</span><span class="sxs-lookup"><span data-stu-id="90e98-193">This topic serves as a deployment guide that shows how to enable the localization of Microsoft Dynamics 365 Commerce for Sweden.</span></span> <span data-ttu-id="90e98-194">Lokaliseringen är en del av Retail SDK.</span><span class="sxs-lookup"><span data-stu-id="90e98-194">The localization is part of the Retail SDK.</span></span> <span data-ttu-id="90e98-195">Information om hur du installerar och använder Retail SDK finns i [dokumentation för Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md).</span><span class="sxs-lookup"><span data-stu-id="90e98-195">For information about how to install and use the Retail SDK, see the [Retail SDK documentation](../dev-itpro/retail-sdk/retail-sdk-overview.md).</span></span>

<span data-ttu-id="90e98-196">Det här exemplet består av tillägg för Commerce Runtime (CRT), kassa och Hardware Station.</span><span class="sxs-lookup"><span data-stu-id="90e98-196">This sample consists of extensions for the Commerce runtime (CRT), POS, and Hardware station.</span></span> <span data-ttu-id="90e98-197">Om du vill köra det här exemplet måste du ändra och bygga CRT och Hardware Station-projekt.</span><span class="sxs-lookup"><span data-stu-id="90e98-197">To run this sample, you must modify and build the CRT and Hardware station projects.</span></span> <span data-ttu-id="90e98-198">Vi rekommenderar att du använder en icke-modifierad Retail SDK för att göra de ändringar som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="90e98-198">We recommend that you use an unmodified Retail SDK to make the changes that are described in this topic.</span></span> <span data-ttu-id="90e98-199">Vi rekommenderar också att du använder ett källkontrollsystem, till exempel Microsoft Azure DevOps, där inga filer har ändrats ännu.</span><span class="sxs-lookup"><span data-stu-id="90e98-199">We also recommend that you use a source control system, such as Microsoft Azure DevOps, where no files have been changed yet.</span></span>

<span data-ttu-id="90e98-200">Följ dessa steg för att konfigurera en utvecklingsmiljö så att du kan testa och utöka exemplet.</span><span class="sxs-lookup"><span data-stu-id="90e98-200">Follow these steps to configure a development environment so that you can test and extend the sample.</span></span> <span data-ttu-id="90e98-201">Du måste också slutföra alla nödvändiga inställningsuppgifter som beskrivs i avsnittet [ställa in integrationen med kontrollenheter](#setting-up-the-integration-with-control-units).</span><span class="sxs-lookup"><span data-stu-id="90e98-201">You must also complete all the required setup tasks that are described in the [Setting up the integration with control units](#setting-up-the-integration-with-control-units) section.</span></span>

### <a name="enable-crt-extensions"></a><span data-ttu-id="90e98-202">Aktivera CRT-tillägg</span><span class="sxs-lookup"><span data-stu-id="90e98-202">Enable CRT extensions</span></span>

<span data-ttu-id="90e98-203">CRT tilläggskomponenter inkluderas i CRT-exemplen.</span><span class="sxs-lookup"><span data-stu-id="90e98-203">The CRT extension components are included in the CRT samples.</span></span> <span data-ttu-id="90e98-204">För att slutföra följande procedurer, öppna CRT-lösningen, **CommerceRuntimeSamples.sln**, under **RetailSdk\\SampleExtensions\\CommerceRuntime**.</span><span class="sxs-lookup"><span data-stu-id="90e98-204">To complete the following procedures, open the CRT solution, **CommerceRuntimeSamples.sln**, under **RetailSdk\\SampleExtensions\\CommerceRuntime**.</span></span>

#### <a name="documentprovidercleancashsample-component"></a><span data-ttu-id="90e98-205">DocumentProvider. CleanCashSample-komponent</span><span class="sxs-lookup"><span data-stu-id="90e98-205">DocumentProvider.CleanCashSample component</span></span>

1. <span data-ttu-id="90e98-206">Leta upp projektet **Runtime.Extensions.DocumentProvider.CleanCashSample** och skapa det.</span><span class="sxs-lookup"><span data-stu-id="90e98-206">Find the **Runtime.Extensions.DocumentProvider.CleanCashSample** project, and build it.</span></span>
2. <span data-ttu-id="90e98-207">I mappen **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.</span><span class="sxs-lookup"><span data-stu-id="90e98-207">In the **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** folder, find the **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll** assembly file.</span></span>
3. <span data-ttu-id="90e98-208">Kopiera sammansättningsfilen till CRT-tilläggsmappen:</span><span class="sxs-lookup"><span data-stu-id="90e98-208">Copy the assembly file to the CRT extensions folder:</span></span>

    - <span data-ttu-id="90e98-209">**Commerce Scale Unit:** kopiera sammansättningen till mappen **\\bin\\ext** under Microsoft Internet Information Services (IIS) Commerce Scale Unit-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="90e98-209">**Commerce Scale Unit:** Copy the assembly to the **\\bin\\ext** folder under the Microsoft Internet Information Services (IIS) Commerce Scale Unit site location.</span></span>
    - <span data-ttu-id="90e98-210">**Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.</span><span class="sxs-lookup"><span data-stu-id="90e98-210">**Local CRT on Modern POS:** Copy the assembly to the **\\ext** folder under the local CRT client broker location.</span></span>

4. <span data-ttu-id="90e98-211">Hitta konfigurationsfilen för tillägget för CRT:</span><span class="sxs-lookup"><span data-stu-id="90e98-211">Find the extension configuration file for CRT:</span></span>

    - <span data-ttu-id="90e98-212">**Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="90e98-212">**Commerce Scale Unit:** The file is named **commerceruntime.ext.config**, and it's in the **bin\\ext** folder under the IIS Commerce Scale Unit site location.</span></span>
    - <span data-ttu-id="90e98-213">**Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.</span><span class="sxs-lookup"><span data-stu-id="90e98-213">**Local CRT on Modern POS:** The file is named **CommerceRuntime.MPOSOffline.Ext.config**, and it's under the local CRT client broker location.</span></span>

5. <span data-ttu-id="90e98-214">Registrera CRT-ändringen i konfigurationsfilen för tillägget.</span><span class="sxs-lookup"><span data-stu-id="90e98-214">Register the CRT change in the extension configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="update-the-extension-configuration-file"></a><span data-ttu-id="90e98-215">Uppdatera konfigurationsfilen för tillägget</span><span class="sxs-lookup"><span data-stu-id="90e98-215">Update the extension configuration file</span></span>

1. <span data-ttu-id="90e98-216">Hitta konfigurationsfilen för tillägget för CRT:</span><span class="sxs-lookup"><span data-stu-id="90e98-216">Find the extension configuration file for CRT:</span></span>

    - <span data-ttu-id="90e98-217">**Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="90e98-217">**Commerce Scale Unit:** The file is named **commerceruntime.ext.config**, and it's in the **bin\\ext** folder under the IIS Commerce Scale Unit site location.</span></span>
    - <span data-ttu-id="90e98-218">**Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.</span><span class="sxs-lookup"><span data-stu-id="90e98-218">**Local CRT on Modern POS:** The file is named **CommerceRuntime.MPOSOffline.Ext.config**, and it's under the local CRT client broker location.</span></span>

2. <span data-ttu-id="90e98-219">Registrera CRT-ändringen i konfigurationsfilen för tillägget.</span><span class="sxs-lookup"><span data-stu-id="90e98-219">Register the CRT change in the extension configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a><span data-ttu-id="90e98-220">Aktivera tilläggen för Hardware Station</span><span class="sxs-lookup"><span data-stu-id="90e98-220">Enable Hardware station extensions</span></span>

<span data-ttu-id="90e98-221">Tilläggskomponenterna för Hardware Station ingår i Hardware Station exemplen.</span><span class="sxs-lookup"><span data-stu-id="90e98-221">The Hardware station extension components are included in the Hardware station samples.</span></span> <span data-ttu-id="90e98-222">För att slutföra följande procedurer, öppna lösningen **HardwareStationSamples.sln.sln**, under **RetailSdk\\SampleExtensions\\HardwareStation**.</span><span class="sxs-lookup"><span data-stu-id="90e98-222">To complete the following procedures, open the solution, **HardwareStationSamples.sln.sln**, under **RetailSdk\\SampleExtensions\\HardwareStation**.</span></span>

#### <a name="cleancash-component"></a><span data-ttu-id="90e98-223">CleanCash-komponent</span><span class="sxs-lookup"><span data-stu-id="90e98-223">CleanCash component</span></span>

1. <span data-ttu-id="90e98-224">Leta upp projektet **HardwareStation.Extension.CleanCashSample** och skapa det.</span><span class="sxs-lookup"><span data-stu-id="90e98-224">Find the **HardwareStation.Extension.CleanCashSample** project, and build it.</span></span>
2. <span data-ttu-id="90e98-225">I mappen **Extension.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.HardwareStation.CleanCashSample.dll**.</span><span class="sxs-lookup"><span data-stu-id="90e98-225">In the **Extension.CleanCashSample\\bin\\Debug** folder, find the **Contoso.Commerce.HardwareStation.CleanCashSample.dll** assembly file.</span></span>
3. <span data-ttu-id="90e98-226">Kopiera sammansättningsfilen till Hardware Station-tilläggsmappen:</span><span class="sxs-lookup"><span data-stu-id="90e98-226">Copy the assembly file to the Hardware station extensions folder:</span></span>

    - <span data-ttu-id="90e98-227">**Delad Hardware Station** : kopiera filen till **binge**-mappen under IIS Hardware Station webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="90e98-227">**Shared hardware station:** Copy the file to the **bin** folder under the IIS Hardware station site location.</span></span>
    - <span data-ttu-id="90e98-228">**Dedikerad Hardware Station på Modern POS** : kopiera filen till platsen för Modern POS Client Broker.</span><span class="sxs-lookup"><span data-stu-id="90e98-228">**Dedicated hardware station on Modern POS:** Copy the file to the Modern POS client broker location.</span></span>

4. <span data-ttu-id="90e98-229">Leta reda på tilläggskonfigurationsfilen för Hardware Station-tillägg.</span><span class="sxs-lookup"><span data-stu-id="90e98-229">Find the extension configuration file for the Hardware station's extensions.</span></span> <span data-ttu-id="90e98-230">Filen heter **HardwareStation.Extension.config**.</span><span class="sxs-lookup"><span data-stu-id="90e98-230">The file is named **HardwareStation.Extension.config**.</span></span>

    - <span data-ttu-id="90e98-231">**Delad Hardware Station** : filen är under IIS Hardware Station webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="90e98-231">**Shared hardware station:** The file is under the IIS Hardware station site location.</span></span>
    - <span data-ttu-id="90e98-232">**Dedikerad Hardware Station på Modern POS** : filen är under platsen för Modern POS Client Broker.</span><span class="sxs-lookup"><span data-stu-id="90e98-232">**Dedicated hardware station on Modern POS:** The file is under the Modern POS client broker location.</span></span>

5. <span data-ttu-id="90e98-233">Lägg till följande rad i avsnittet **sammansättning** i konfigurationsfilen.</span><span class="sxs-lookup"><span data-stu-id="90e98-233">Add the following line to the **composition** section of the configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
    ```

### <a name="enable-modern-pos-extension-components"></a><span data-ttu-id="90e98-234">Aktivera tilläggskomponenter för Modern POS</span><span class="sxs-lookup"><span data-stu-id="90e98-234">Enable Modern POS extension components</span></span>

1. <span data-ttu-id="90e98-235">Öppna lösningen på **RetailSdk\\POS\\ModernPOS.sln** och se till att den kan kompileras utan fel.</span><span class="sxs-lookup"><span data-stu-id="90e98-235">Open the solution at **RetailSdk\\POS\\ModernPOS.sln**, and make sure that it can be compiled without errors.</span></span> <span data-ttu-id="90e98-236">Kontrollera dessutom att du kan köra Modern POS från Microsoft Visual Studio med hjälp av kommandot **kör**.</span><span class="sxs-lookup"><span data-stu-id="90e98-236">Additionally, make sure that you can run Modern POS from Microsoft Visual Studio by using the **Run** command.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90e98-237">Modern POS får inte anpassas.</span><span class="sxs-lookup"><span data-stu-id="90e98-237">Modern POS must not be customized.</span></span> <span data-ttu-id="90e98-238">Du måste aktivera User Account Control (UAC) och du måste avinstallera tidigare installerade instanser av Modern POS efter behov.</span><span class="sxs-lookup"><span data-stu-id="90e98-238">You must enable User Account Control (UAC), and you must uninstall previously installed instances of Modern POS as required.</span></span>

2. <span data-ttu-id="90e98-239">Aktivera tilläggen som måste läsas in genom att lägga till följande rader i filen **extensions.json**.</span><span class="sxs-lookup"><span data-stu-id="90e98-239">Enable the extensions that must be loaded by adding the following lines in the **extensions.json** file.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > <span data-ttu-id="90e98-240">Mer information och exempel som visar hur du inkluderar källkodsmappar och aktiverar tillägg som ska läsas in finns i instruktionerna i readme.md filen i projektet **Pos.Extensions**.</span><span class="sxs-lookup"><span data-stu-id="90e98-240">For more information, and for samples that show how to include source code folders and enable extensions to be loaded, see the instructions in the readme.md file in the **Pos.Extensions** project.</span></span>

3. <span data-ttu-id="90e98-241">Återskapa lösningen.</span><span class="sxs-lookup"><span data-stu-id="90e98-241">Rebuild the solution.</span></span>
4. <span data-ttu-id="90e98-242">Kör Modern POS i felsökaren och testa funktionen.</span><span class="sxs-lookup"><span data-stu-id="90e98-242">Run Modern POS in the debugger, and test the functionality.</span></span>

### <a name="enable-cloud-pos-extension-components"></a><span data-ttu-id="90e98-243">Aktivera tilläggskomponenter för Cloud POS</span><span class="sxs-lookup"><span data-stu-id="90e98-243">Enable Cloud POS extension components</span></span>

1. <span data-ttu-id="90e98-244">Öppna lösningen på **RetailSdk\\POS\\CloudPOS.sln** och se till att den kan kompileras utan fel.</span><span class="sxs-lookup"><span data-stu-id="90e98-244">Open the solution at **RetailSdk\\POS\\CloudPOS.sln**, and make sure that it can be compiled without errors.</span></span>
2. <span data-ttu-id="90e98-245">Aktivera tilläggen som måste läsas in genom att lägga till följande rader i filen **extensions.json**.</span><span class="sxs-lookup"><span data-stu-id="90e98-245">Enable the extensions that must be loaded by adding the following lines in the **extensions.json** file.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > <span data-ttu-id="90e98-246">Mer information och exempel som visar hur du inkluderar källkodsmappar och aktiverar tillägg som ska läsas in finns i instruktionerna i readme.md filen i projektet **Pos.Extensions**.</span><span class="sxs-lookup"><span data-stu-id="90e98-246">For more information, and for samples that show how to include source code folders and enable extensions to be loaded, see the instructions in the readme.md file in the **Pos.Extensions** project.</span></span>

3. <span data-ttu-id="90e98-247">Återskapa lösningen.</span><span class="sxs-lookup"><span data-stu-id="90e98-247">Rebuild the solution.</span></span>
4. <span data-ttu-id="90e98-248">Kör lösningen med hjälp av kommandot **kör** och följa stegen i handboken Retail SDK.</span><span class="sxs-lookup"><span data-stu-id="90e98-248">Run the solution by using the **Run** command and following the steps in the Retail SDK handbook.</span></span>

### <a name="set-up-the-registration-process"></a><span data-ttu-id="90e98-249">Ställa in registrationsprocessen</span><span class="sxs-lookup"><span data-stu-id="90e98-249">Set up the registration process</span></span>

<span data-ttu-id="90e98-250">Om du vill aktivera registreringsprocessen, följ dessa steg för att ställa in Administration.</span><span class="sxs-lookup"><span data-stu-id="90e98-250">To enable the registration process, follow these steps to set up Headquarters.</span></span> <span data-ttu-id="90e98-251">Mer information finns [Ställ in en räkenskapsregistreringsprocess](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).</span><span class="sxs-lookup"><span data-stu-id="90e98-251">For more details, see [Set up a fiscal registration process](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).</span></span>

1. <span data-ttu-id="90e98-252">Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Delade parametrar**.</span><span class="sxs-lookup"><span data-stu-id="90e98-252">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Shared parameters**.</span></span> <span data-ttu-id="90e98-253">På fliken **allmänt** anger du alternativet **Aktivera räkenskapsintegration** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="90e98-253">On the **General** tab, set the **Enable fiscal integration** option to **Yes**.</span></span>
2. <span data-ttu-id="90e98-254">Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Räkenskapskopplingar** och läs in kopplingskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="90e98-254">Go to **Retail and Commerce \> Channel setup \> Fiscal integration \> Fiscal connectors**, and load the connector configuration.</span></span> <span data-ttu-id="90e98-255">Filens plats är **RetailSdk\\SampleExtensions\\HardwareStation\\Extension.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml**.</span><span class="sxs-lookup"><span data-stu-id="90e98-255">The file location is **RetailSdk\\SampleExtensions\\HardwareStation\\Extension.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml**.</span></span>
3. <span data-ttu-id="90e98-256">Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Leverantörer av skattedokument** och läs in konfigurationens dokumentleverantör.</span><span class="sxs-lookup"><span data-stu-id="90e98-256">Go to **Retail and Commerce \> Channel setup \> Fiscal integration \> Fiscal document providers**, and load the document provider configuration.</span></span> <span data-ttu-id="90e98-257">Filens plats är **RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml**.</span><span class="sxs-lookup"><span data-stu-id="90e98-257">The file location is **RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml**.</span></span>
4. <span data-ttu-id="90e98-258">Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Funktionsprofiler för koppling**.</span><span class="sxs-lookup"><span data-stu-id="90e98-258">Go to **Retail and Commerce \> Channel setup \> Fiscal integration \> Connector functional profiles**.</span></span> <span data-ttu-id="90e98-259">Skapa en ny funktionsprofil för koppling och välj dokumentleverantören och kopplingen som du laddade tidigare.</span><span class="sxs-lookup"><span data-stu-id="90e98-259">Create a new connector functional profile, and select the document provider and the connector that you loaded earlier.</span></span> <span data-ttu-id="90e98-260">Uppdatera datamappningsinställningarna efter behov.</span><span class="sxs-lookup"><span data-stu-id="90e98-260">Update the data mapping settings as required.</span></span>
5. <span data-ttu-id="90e98-261">Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Tekniska profiler för koppling**.</span><span class="sxs-lookup"><span data-stu-id="90e98-261">Go to **Retail and Commerce \> Channel setup \> Fiscal integration \> Connector technical profiles**.</span></span> <span data-ttu-id="90e98-262">Skapa en ny teknisk profil för koppling och välj kopplingen som du laddade tidigare.</span><span class="sxs-lookup"><span data-stu-id="90e98-262">Create a new connector technical profile, and select the connector that you loaded earlier.</span></span> <span data-ttu-id="90e98-263">Uppdatera kopplingsinställningarna efter behov.</span><span class="sxs-lookup"><span data-stu-id="90e98-263">Update the connection settings as required.</span></span>
6. <span data-ttu-id="90e98-264">Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Grupper för skattekoppling**.</span><span class="sxs-lookup"><span data-stu-id="90e98-264">Go to **Retail and Commerce \> Channel setup \> Fiscal integration \> Fiscal connector groups**.</span></span> <span data-ttu-id="90e98-265">Skapa en ny grupp för räkenskapskoppling för den funktionsprofil för koppling som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="90e98-265">Create a new fiscal connector group for the connector functional profile that you created earlier.</span></span>
7. <span data-ttu-id="90e98-266">Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Processer för räkenskapsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="90e98-266">Go to **Retail and Commerce \> Channel setup \> Fiscal integration \> Fiscal registration processes**.</span></span> <span data-ttu-id="90e98-267">Skapa en ny räkenskapsregistrering, skapa ett steg för räkenskapsregistrering och välj den grupp för räkenskapskoppling som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="90e98-267">Create a new fiscal registration process, create a fiscal registration process step, and select the fiscal connector group that you created earlier.</span></span>
8. <span data-ttu-id="90e98-268">Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="90e98-268">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Functionality profiles**.</span></span> <span data-ttu-id="90e98-269">Välj en funktionsprofil som är kopplad till butiken där registreringsprocessen ska aktiveras.</span><span class="sxs-lookup"><span data-stu-id="90e98-269">Select a functionality profile that is linked to the store where the registration process should be activated.</span></span> <span data-ttu-id="90e98-270">På snabbfliken **Process för räkenskapsregistrering**, välj räkenskapsregistreringsprocessen som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="90e98-270">On the **Fiscal registration process** FastTab, select the fiscal registration process that you created earlier.</span></span>
9. <span data-ttu-id="90e98-271">Gåt ill **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassaprofiler \> Maskinvaruprofiler**.</span><span class="sxs-lookup"><span data-stu-id="90e98-271">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Hardware profiles**.</span></span> <span data-ttu-id="90e98-272">Välj en maskinvaruprofil som är länkad till den Hardware Station som styrenheten ska anslutas till.</span><span class="sxs-lookup"><span data-stu-id="90e98-272">Select a hardware profile that is linked to the Hardware station that the control unit will be connected to.</span></span> <span data-ttu-id="90e98-273">På snabbfliken **Kringutrustning för räkenskaper**, välj teknisk profil för koppling som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="90e98-273">On the **Fiscal peripherals** FastTab, select the connector technical profile that you created earlier.</span></span>
10. <span data-ttu-id="90e98-274">Öppna distributionstidsplanen (**Retail och Commerce \> Retail och Commerce-IT \> Distributionsschema**) och välj jobb **1070** och **1090** för att överföra data till kanaldatabasen.</span><span class="sxs-lookup"><span data-stu-id="90e98-274">Open the distribution schedule (**Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**), and select jobs **1070** and **1090** to transfer data to the channel database.</span></span>

### <a name="production-environment"></a><span data-ttu-id="90e98-275">Produktionsmiljö</span><span class="sxs-lookup"><span data-stu-id="90e98-275">Production environment</span></span>

<span data-ttu-id="90e98-276">Föregående procedur aktiverar tilläggen som är komponenter i exemplet på skatteregistreringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="90e98-276">The previous procedure enables the extensions that are components of the fiscal registration service integration sample.</span></span> <span data-ttu-id="90e98-277">Förutom att slutföra proceduren måste du följa dessa steg för att skapa distribuerbara paket som innehåller Commerce-komponenter och för att tillämpa dessa paket i en produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="90e98-277">In addition to completing that procedure, you must follow these steps to create deployable packages that contain Commerce components, and to apply those packages in a production environment.</span></span>

1. <span data-ttu-id="90e98-278">Gör följande ändringar i paketkonfigurationsfilerna under mappen **RetailSdk\\Assets**:</span><span class="sxs-lookup"><span data-stu-id="90e98-278">Make the following changes in the package configuration files under the **RetailSdk\\Assets** folder:</span></span>

    - <span data-ttu-id="90e98-279">I konfigurationsfilerna **commerceruntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** lägger du till följande rader i avsnittet **komposition**.</span><span class="sxs-lookup"><span data-stu-id="90e98-279">In the **commerceruntime.ext.config** and **CommerceRuntime.MPOSOffline.Ext.config** configuration files, add the following lines to the **composition** section.</span></span>

        ``` xml 
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
        ```

    - <span data-ttu-id="90e98-280">I konfigurationsfilen **HardwareStation.Extension.config** lägg till följande rad i avsnittet **komposition**.</span><span class="sxs-lookup"><span data-stu-id="90e98-280">In the **HardwareStation.Extension.config** configuration file, add the following line to the **composition** section.</span></span>

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
        ```

2. <span data-ttu-id="90e98-281">Gör följande ändringar i konfigurationsfilerna för paketanpassning **Customization.settings** under **BuildTools**:</span><span class="sxs-lookup"><span data-stu-id="90e98-281">Make the following changes in the **Customization.settings** package customization configuration file under the **BuildTools** folder:</span></span>

    - <span data-ttu-id="90e98-282">Lägg till följande rader om du vill inkludera CRT-tilläggen i de distribuerbara paketen.</span><span class="sxs-lookup"><span data-stu-id="90e98-282">Add the following lines to include the CRT extensions in the deployable packages.</span></span>

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
        ```

    - <span data-ttu-id="90e98-283">Lägg till följande rad om du vill inkludera Hardware Station-tillägget i de distribuerbara paketen.</span><span class="sxs-lookup"><span data-stu-id="90e98-283">Add the following line to include the Hardware station extension in the deployable packages.</span></span>

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        ```

3. <span data-ttu-id="90e98-284">Aktivera kassatillägget genom att lägga till följande rader i filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.</span><span class="sxs-lookup"><span data-stu-id="90e98-284">Enable the POS extension by adding the following lines in the **extensions.json** file under the **RetailSDK\\POS\\Extensions** folder.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
            "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

4. <span data-ttu-id="90e98-285">Starta MSBuild-Kommandotolken för Visual Studio-verktyget och **kör MSBuild** under mappen Retail SDK för att skapa distribuerbara paket.</span><span class="sxs-lookup"><span data-stu-id="90e98-285">Start the MSBuild Command Prompt for Visual Studio utility, and run **msbuild** under the Retail SDK folder to create deployable packages.</span></span>
5. <span data-ttu-id="90e98-286">Tillämpa paketen via Microsoft Dynamics Lifecycle Services (LCS) eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="90e98-286">Apply the packages via Microsoft Dynamics Lifecycle Services (LCS) or manually.</span></span> <span data-ttu-id="90e98-287">Mer information finns i [skapa distribuerbara paket](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="90e98-287">For more information, see [Create deployable packages](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span></span>

## <a name="design-of-the-extensions"></a><span data-ttu-id="90e98-288">Design av tilläggen</span><span class="sxs-lookup"><span data-stu-id="90e98-288">Design of the extensions</span></span>

### <a name="crt-extension-design"></a><span data-ttu-id="90e98-289">CRT tilläggsdesign</span><span class="sxs-lookup"><span data-stu-id="90e98-289">CRT extension design</span></span>

<span data-ttu-id="90e98-290">Syftet med tillägget som är en skattedokument leverantör är att generera tjänstspecifika dokument och hantera svar från räkenskapsregistreringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="90e98-290">The purpose of the extension that is a fiscal document provider is to generate service-specific documents and handle responses from the fiscal registration service.</span></span>

<span data-ttu-id="90e98-291">CRT-tillägget är **Runtime.Extensions.DocumentProvider.CleanCashSample**.</span><span class="sxs-lookup"><span data-stu-id="90e98-291">The CRT extension is **Runtime.Extensions.DocumentProvider.CleanCashSample**.</span></span>

<span data-ttu-id="90e98-292">Mer information om design av lösningen av räkenskapsintegration finns i [Process för räkenskapsregistrering och exempel på räkenskapsintegration för kvittoskrivarenheter](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).</span><span class="sxs-lookup"><span data-stu-id="90e98-292">For more details about the design of the fiscal integration solution, see [Fiscal registration process and fiscal integration samples for fiscal devices](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).</span></span>

#### <a name="request-handler"></a><span data-ttu-id="90e98-293">Begärandehanterare</span><span class="sxs-lookup"><span data-stu-id="90e98-293">Request handler</span></span>
    
<span data-ttu-id="90e98-294">Det finns en enda **DocumentProviderCleanCash**-begärandehanterare för dokumentprovidern.</span><span class="sxs-lookup"><span data-stu-id="90e98-294">There is a single **DocumentProviderCleanCash** request handler for the document provider.</span></span> <span data-ttu-id="90e98-295">Den här hanteraren används för att generera skattedokument för räkenskapsregistreringstjänst.</span><span class="sxs-lookup"><span data-stu-id="90e98-295">This handler is used to generate fiscal documents for the fiscal registration service.</span></span>

<span data-ttu-id="90e98-296">Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**.</span><span class="sxs-lookup"><span data-stu-id="90e98-296">This handler is inherited from the **INamedRequestHandler** interface.</span></span> <span data-ttu-id="90e98-297">Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren.</span><span class="sxs-lookup"><span data-stu-id="90e98-297">The **HandlerName** method is responsible for returning the name of the handler.</span></span> <span data-ttu-id="90e98-298">Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Administration.</span><span class="sxs-lookup"><span data-stu-id="90e98-298">The handler name should match the connector document provider name that is specified in Headquarters.</span></span>

<span data-ttu-id="90e98-299">Kopplingen stöder följande begäranden:</span><span class="sxs-lookup"><span data-stu-id="90e98-299">The connector supports the following requests:</span></span>

- <span data-ttu-id="90e98-300">**GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas.</span><span class="sxs-lookup"><span data-stu-id="90e98-300">**GetFiscalDocumentDocumentProviderRequest** – This request contains information about what document should be generated.</span></span> <span data-ttu-id="90e98-301">Den returnerar ett tjänstspecifikt dokument som ska registreras i räkenskapsregistreringstjänst.</span><span class="sxs-lookup"><span data-stu-id="90e98-301">It returns a service-specific document that should be registered in the fiscal registration service.</span></span>
- <span data-ttu-id="90e98-302">**GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på.</span><span class="sxs-lookup"><span data-stu-id="90e98-302">**GetSupportedRegistrableEventsDocumentProviderRequest** – This request returns the list of events to subscribe to.</span></span> <span data-ttu-id="90e98-303">För närvarande stöds försäljningshändelser och granskningshändelser.</span><span class="sxs-lookup"><span data-stu-id="90e98-303">Currently, sales events and audit events are supported.</span></span>

#### <a name="configuration"></a><span data-ttu-id="90e98-304">Inställningar</span><span class="sxs-lookup"><span data-stu-id="90e98-304">Configuration</span></span>

<span data-ttu-id="90e98-305">Konfigurationsfilen **DocumentProviderFiscalCleanCashSample** finns i mappen **konfiguration** för tilläggsprojektet.</span><span class="sxs-lookup"><span data-stu-id="90e98-305">The **DocumentProviderFiscalCleanCashSample** configuration file is in the **Configuration** folder of the extension project.</span></span> <span data-ttu-id="90e98-306">Syftet med den här filen är att aktivera inställningar för dokumentprovidern som ska konfigureras från Administration.</span><span class="sxs-lookup"><span data-stu-id="90e98-306">The purpose of this file is to enable settings for the document provider to be configured from Headquarters.</span></span> <span data-ttu-id="90e98-307">Filformatet justeras med kraven för konfiguration av räkenskapsintegration.</span><span class="sxs-lookup"><span data-stu-id="90e98-307">The file format is aligned with the requirements for fiscal integration configuration.</span></span> <span data-ttu-id="90e98-308">Följande inställningar är tillagda:</span><span class="sxs-lookup"><span data-stu-id="90e98-308">The following settings are added:</span></span>

- <span data-ttu-id="90e98-309">Mappning av momskoder</span><span class="sxs-lookup"><span data-stu-id="90e98-309">VAT codes mapping</span></span>

### <a name="hardware-station-extension-design"></a><span data-ttu-id="90e98-310">Tilläggsdesign för Hardware Station</span><span class="sxs-lookup"><span data-stu-id="90e98-310">Hardware station extension design</span></span>

<span data-ttu-id="90e98-311">Syftet med tillägget som är en räkenskapskoppling är att kommunicera med räkenskapsregistreringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="90e98-311">The purpose of the extension that is a fiscal connector is to communicate with the fiscal registration service.</span></span>

<span data-ttu-id="90e98-312">Hardware Station-tillägget **HardwareStation.Extension.CleanCashSample**.</span><span class="sxs-lookup"><span data-stu-id="90e98-312">The Hardware station extension is **HardwareStation.Extension.CleanCashSample**.</span></span> <span data-ttu-id="90e98-313">Den använder HTTP-protokollet för att skicka dokument som CRT-tillägget genererar till räkenskapsregistreringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="90e98-313">It uses the HTTP protocol to submit documents that the CRT extension generates to the fiscal registration service.</span></span> <span data-ttu-id="90e98-314">Den hanterar också svar som tas emot från räkenskapsregistreringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="90e98-314">It also handles the responses that are received from the fiscal registration service.</span></span>

#### <a name="request-handler"></a><span data-ttu-id="90e98-315">Begärandehanterare</span><span class="sxs-lookup"><span data-stu-id="90e98-315">Request handler</span></span>

<span data-ttu-id="90e98-316">**Cleancashhandler** begäranhanteraren är startpunkten för hantering av begäranden till räkenskapsregistreringstjänst.</span><span class="sxs-lookup"><span data-stu-id="90e98-316">The **CleanCashHandler** request handler is the entry point for handling requests to the fiscal registration service.</span></span>

<span data-ttu-id="90e98-317">Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**.</span><span class="sxs-lookup"><span data-stu-id="90e98-317">The handler is inherited from the **INamedRequestHandler** interface.</span></span> <span data-ttu-id="90e98-318">Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren.</span><span class="sxs-lookup"><span data-stu-id="90e98-318">The **HandlerName** method is responsible for returning the name of the handler.</span></span> <span data-ttu-id="90e98-319">Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Administration.</span><span class="sxs-lookup"><span data-stu-id="90e98-319">The handler name should match the fiscal connector name that is specified in Headquarters.</span></span>

<span data-ttu-id="90e98-320">Kopplingen stöder följande begäranden:</span><span class="sxs-lookup"><span data-stu-id="90e98-320">The connector supports the following requests:</span></span>

- <span data-ttu-id="90e98-321">**SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till räkenskapsregistreringstjänsten och returnerar ett svar från den.</span><span class="sxs-lookup"><span data-stu-id="90e98-321">**SubmitDocumentFiscalDeviceRequest** – This request sends documents to the fiscal registration service and returns a response from it.</span></span>
- <span data-ttu-id="90e98-322">**IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av tjänsten för räkenskapsregistrering.</span><span class="sxs-lookup"><span data-stu-id="90e98-322">**IsReadyFiscalDeviceRequest** – This request is used for a health check of the fiscal registration service.</span></span>
- <span data-ttu-id="90e98-323">**InitializeFiscalDeviceRequest** – den här begäran används för initiera tjänsten för räkenskapsregistrering.</span><span class="sxs-lookup"><span data-stu-id="90e98-323">**InitializeFiscalDeviceRequest** – This request is used to initialize the fiscal registration service.</span></span>

#### <a name="configuration"></a><span data-ttu-id="90e98-324">Inställningar</span><span class="sxs-lookup"><span data-stu-id="90e98-324">Configuration</span></span>

<span data-ttu-id="90e98-325">Konfigurationsfilen finns i mappen **konfiguration** för tilläggsprojektet.</span><span class="sxs-lookup"><span data-stu-id="90e98-325">The configuration file is in the **Configuration** folder of the extension project.</span></span> <span data-ttu-id="90e98-326">Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Administration.</span><span class="sxs-lookup"><span data-stu-id="90e98-326">The purpose of the file is to enable settings for the fiscal connector to be configured from Headquarters.</span></span> <span data-ttu-id="90e98-327">Filformatet justeras med kraven för konfiguration av räkenskapsintegration.</span><span class="sxs-lookup"><span data-stu-id="90e98-327">The file format is aligned with the requirements for fiscal integration configuration.</span></span> <span data-ttu-id="90e98-328">Följande inställningar är tillagda:</span><span class="sxs-lookup"><span data-stu-id="90e98-328">The following settings are added:</span></span>

- <span data-ttu-id="90e98-329">**Anslutningssträng** – inställningarna för kontrollenhetens anslutning.</span><span class="sxs-lookup"><span data-stu-id="90e98-329">**Connections string** – The control unit connection settings.</span></span>
- <span data-ttu-id="90e98-330">**Tidsgräns** – hur länge, i millisekunder, som drivrutinen väntar på ett svar från räkenskapsregistreringstjänst.</span><span class="sxs-lookup"><span data-stu-id="90e98-330">**Timeout** – The amount of time, in milliseconds, that the driver will wait for a response from the fiscal registration service.</span></span>

## <a name="migrating-from-the-earlier-integration-sample"></a><span data-ttu-id="90e98-331">Migrera från det tidigare integrationsprovet</span><span class="sxs-lookup"><span data-stu-id="90e98-331">Migrating from the earlier integration sample</span></span>

<span data-ttu-id="90e98-332">Om du använder det tidigare [exemplet för POS-integrering med styrenheter för Sverige](retail-sdk-control-unit-sample.md), kan du behöva migrera från den till det aktuella integrationsexemplet.</span><span class="sxs-lookup"><span data-stu-id="90e98-332">If you're using the earlier [Sample for POS integration with control units for Sweden](retail-sdk-control-unit-sample.md), you might have to migrate from it to the current integration sample.</span></span> <span data-ttu-id="90e98-333">För att kunna utnyttja förändringen och få snabba uppdateringar av funktionerna för Sverige i framtiden kan du behöva uppgradera, göra mindre kod- och konfigurationsjusteringar i tilläggen som du har skapat och återskapa dina lösningar.</span><span class="sxs-lookup"><span data-stu-id="90e98-333">To uptake the change and receive timely updates for the features for Sweden in the future, you might have to upgrade, make minor code and configuration adjustments in the extensions that you built, and rebuild your solutions.</span></span> <span data-ttu-id="90e98-334">Inga större ändringar krävs i den tilläggslogik som du skapade.</span><span class="sxs-lookup"><span data-stu-id="90e98-334">No major changes are required in the extension logic that you created.</span></span> <span data-ttu-id="90e98-335">Det tidigare integrationsprovet och anpassningarna kommer att fortsätta att fungera om inga ändringar görs från din sida.</span><span class="sxs-lookup"><span data-stu-id="90e98-335">The earlier integration sample and your customizations will continue to work if no changes are made from your side.</span></span> <span data-ttu-id="90e98-336">Därför kan du planera, förbereda för och göra upptaget för din miljö.</span><span class="sxs-lookup"><span data-stu-id="90e98-336">Therefore, you can plan, prepare for, and do the uptake for your environment.</span></span>

### <a name="migration-process"></a><span data-ttu-id="90e98-337">Migreringsprocess</span><span class="sxs-lookup"><span data-stu-id="90e98-337">Migration process</span></span>

<span data-ttu-id="90e98-338">Migreringen från det tidigare integrationsprovet till det aktuella styrenhetens integrationsprov bör baseras på konceptet med en gradvis uppdatering.</span><span class="sxs-lookup"><span data-stu-id="90e98-338">The migration from the earlier integration sample to the current control unit integration sample should be based on the concept of a gradual update.</span></span> <span data-ttu-id="90e98-339">Med andra ord bör alla Administration och Commerce Scale Unit-komponenter redan uppdateras innan du börjar uppdatera POS och komponenter för Hardware Station.</span><span class="sxs-lookup"><span data-stu-id="90e98-339">In other words, all Headquarters and Commerce Scale Unit components should already be updated before you start to update the POS and Hardware station components.</span></span>

<span data-ttu-id="90e98-340">För att förhindra en situation där en händelse eller transaktion undertecknas två gånger (det vill säga den är undertecknad av både den tidigare tillägget och den nuvarande tillägget), eller där den inte kan undertecknas på grund av den saknade konfigurationen, rekommenderar vi att du stänger av alla POS- och Hardware Station-enheter som använder det tidigare exemplet och uppdaterar dem samtidigt.</span><span class="sxs-lookup"><span data-stu-id="90e98-340">To help prevent a situation where an event or transaction is signed twice (that is, it's signed by both the earlier extension and the current extension), or where it can't be signed because of the missing configuration, we recommend that you turn off all POS and Hardware station devices that use the earlier sample, and then update them simultaneously.</span></span> <span data-ttu-id="90e98-341">Den här samtidiga uppdateringen kan göras, till exempel i butik för butik genom att uppdatera butikens funktionsprofil och Hardware Station maskinvaruprofil.</span><span class="sxs-lookup"><span data-stu-id="90e98-341">This simultaneous update can be done, for example, on a store-by-store basis by updating the store's functionality profile and the Hardware station's hardware profile.</span></span>

<span data-ttu-id="90e98-342">Migreringsprocessen bör bestå av följande steg.</span><span class="sxs-lookup"><span data-stu-id="90e98-342">The migration process should consist of the following steps.</span></span>

1. <span data-ttu-id="90e98-343">Uppdatera Administration-komponenterna.</span><span class="sxs-lookup"><span data-stu-id="90e98-343">Update the Headquarters components.</span></span>
1. <span data-ttu-id="90e98-344">Uppdatera Commerce Scale Unit-komponenterna och aktivera tilläggen för det aktuella exemplet.</span><span class="sxs-lookup"><span data-stu-id="90e98-344">Update the Commerce Scale Unit components, and enable the extensions of the current sample.</span></span>
1. <span data-ttu-id="90e98-345">Kontrollera att alla offlinetransaktioner synkroniseras från MPOS-enheter som har aktiverats offline.</span><span class="sxs-lookup"><span data-stu-id="90e98-345">Make sure that all offline transactions are synced from offline-enabled MPOS devices.</span></span>
1. <span data-ttu-id="90e98-346">Stäng av alla enheter som använder komponenterna i det tidigare exemplet.</span><span class="sxs-lookup"><span data-stu-id="90e98-346">Turn off all devices that use the components of the earlier sample.</span></span>
1. <span data-ttu-id="90e98-347">Slutföra alla inställningsuppgifter som beskrivs i avsnittet [ställa in integrationen med kontrollenheter](#setting-up-the-integration-with-control-units).</span><span class="sxs-lookup"><span data-stu-id="90e98-347">Complete the setup tasks that are described in the [Setting up the integration with control units](#setting-up-the-integration-with-control-units) section.</span></span>
1. <span data-ttu-id="90e98-348">Uppdatera komponenterna för POS och Hardware Station, inaktivera tilläggen som är delar av det tidigare exemplet och aktivera tilläggen för det aktuella exemplet.</span><span class="sxs-lookup"><span data-stu-id="90e98-348">Update the POS and Hardware station components, disable the extensions that are parts of the earlier sample, and enable the extensions of the current sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90e98-349">Beroende på typ av miljö kan du hitta mer tekniska detaljer om migreringsprocessen i antingen avsnittet [Migration i en utvecklingsmiljö](#migration-in-a-development-environment) avsnittet [Migration i en produktionsmiljö](#migration-in-a-production-environment).</span><span class="sxs-lookup"><span data-stu-id="90e98-349">Depending on the type of environment, you can find more technical details about the migration process in either the [Migration in a development environment](#migration-in-a-development-environment) section or the [Migration in a production environment](#migration-in-a-production-environment) section.</span></span>

### <a name="migration-in-a-development-environment"></a><span data-ttu-id="90e98-350">Migrering i en utvecklingsmiljö</span><span class="sxs-lookup"><span data-stu-id="90e98-350">Migration in a development environment</span></span>

#### <a name="update-crt"></a><span data-ttu-id="90e98-351">Uppdatera CRT</span><span class="sxs-lookup"><span data-stu-id="90e98-351">Update CRT</span></span>

1. <span data-ttu-id="90e98-352">Leta upp projektet **Runtime.Extensions.DocumentProvider.CleanCashSample** och skapa det.</span><span class="sxs-lookup"><span data-stu-id="90e98-352">Find the **Runtime.Extensions.DocumentProvider.CleanCashSample** project, and build it.</span></span>
2. <span data-ttu-id="90e98-353">I mappen **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.</span><span class="sxs-lookup"><span data-stu-id="90e98-353">In the **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** folder, find the **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll** assembly file.</span></span>
3. <span data-ttu-id="90e98-354">Kopiera sammansättningsfilen till CRT-tilläggsmappen:</span><span class="sxs-lookup"><span data-stu-id="90e98-354">Copy the assembly file to the CRT extensions folder:</span></span>

    - <span data-ttu-id="90e98-355">**Commerce Scale Unit:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Commerce Scale Unit-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="90e98-355">**Commerce Scale Unit:** Copy the assembly to the **\\bin\\ext** folder under the IIS Commerce Scale Unit site location.</span></span>
    - <span data-ttu-id="90e98-356">**Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.</span><span class="sxs-lookup"><span data-stu-id="90e98-356">**Local CRT on Modern POS:** Copy the assembly to the **\\ext** folder under the local CRT client broker location.</span></span>

4. <span data-ttu-id="90e98-357">Hitta konfigurationsfilen för tillägget för CRT:</span><span class="sxs-lookup"><span data-stu-id="90e98-357">Find the extension configuration file for CRT:</span></span>

    - <span data-ttu-id="90e98-358">**Commerce Scale Unit:** Filen kallas **CommerceRuntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="90e98-358">**Commerce Scale Unit:** The file is named **CommerceRuntime.ext.config**, and it's in the **bin\\ext** folder under the IIS Commerce Scale Unit site location.</span></span>
    - <span data-ttu-id="90e98-359">**Lokal CRT på Modern POS:** Filen heter **CommerceRuntime.MPOSOffline.Ext.config** och den är i mappar **bin\\ext** under den lokala platsen för CRT-klienten Broker.</span><span class="sxs-lookup"><span data-stu-id="90e98-359">**Local CRT on Modern POS:** The file is named **CommerceRuntime.MPOSOffline.Ext.config**, and it's in the **bin\\ext** folder under the local CRT client broker location.</span></span>

    > [!WARNING]
    > <span data-ttu-id="90e98-360">Redigera **inte** filerna CommerceRuntime.config och CommerceRuntime.MPOSOffline.config files.</span><span class="sxs-lookup"><span data-stu-id="90e98-360">Do **not** edit the CommerceRuntime.config and CommerceRuntime.MPOSOffline.config files.</span></span> <span data-ttu-id="90e98-361">Dessa filer är inte avsedda för några anpassningar.</span><span class="sxs-lookup"><span data-stu-id="90e98-361">These files aren't intended for any customizations.</span></span>

5. <span data-ttu-id="90e98-362">Hitta och ta bort det tidigare CRT-tillägget från konfigurationsfilen för tillägget.</span><span class="sxs-lookup"><span data-stu-id="90e98-362">Find and remove the earlier CRT extension from the extension configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > <span data-ttu-id="90e98-363">Slutför inte det här steget förrän du uppdaterar alla kassaenheter som fungerar med den här CRT-instansen.</span><span class="sxs-lookup"><span data-stu-id="90e98-363">Don't complete this step until you update all POS devices that work with this CRT instance.</span></span>

6. <span data-ttu-id="90e98-364">Registrera de aktuella exempel CRT-tilläggen i konfigurationsfilen för tillägget genom att lägga till följande rader.</span><span class="sxs-lookup"><span data-stu-id="90e98-364">Register the current sample CRT extensions in the extension configuration file by adding the following lines.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

#### <a name="update-hardware-station"></a><span data-ttu-id="90e98-365">Uppdatera Hardware Station</span><span class="sxs-lookup"><span data-stu-id="90e98-365">Update Hardware station</span></span>

1. <span data-ttu-id="90e98-366">Leta upp projektet **HardwareStation.Extension.CleanCashSample** och skapa det.</span><span class="sxs-lookup"><span data-stu-id="90e98-366">Find the **HardwareStation.Extension.CleanCashSample** project, and build it.</span></span>
2. <span data-ttu-id="90e98-367">I mappen **Extension.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.HardwareStation.CleanCashSample.dll**.</span><span class="sxs-lookup"><span data-stu-id="90e98-367">In the **Extension.CleanCashSample\\bin\\Debug** folder, find the **Contoso.Commerce.HardwareStation.CleanCashSample.dll** assembly file.</span></span>
3. <span data-ttu-id="90e98-368">Kopiera sammansättningsfilen till Hardware Station-tilläggsmappen:</span><span class="sxs-lookup"><span data-stu-id="90e98-368">Copy the assembly file to the Hardware station extensions folder:</span></span>

    - <span data-ttu-id="90e98-369">**Delad Hardware Station** : kopiera filen till **binge**-mappen under IIS Hardware Station webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="90e98-369">**Shared hardware station:** Copy the file to the **bin** folder under the IIS Hardware station site location.</span></span>
    - <span data-ttu-id="90e98-370">**Dedikerad Hardware Station på Modern POS** : kopiera filen till platsen för Modern POS Client Broker.</span><span class="sxs-lookup"><span data-stu-id="90e98-370">**Dedicated hardware station on Modern POS:** Copy the file to the Modern POS client broker location.</span></span>

4. <span data-ttu-id="90e98-371">Hitta **HardwareStation.Extension.config** tilläggskonfigurationsfilen:</span><span class="sxs-lookup"><span data-stu-id="90e98-371">Find the **HardwareStation.Extension.config** extension configuration file:</span></span>

    - <span data-ttu-id="90e98-372">**Fjärrstyrd Hardware Station** : filen är under IIS Hardware Station webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="90e98-372">**Remote Hardware station:** The file is under the IIS Hardware station site location.</span></span>
    - <span data-ttu-id="90e98-373">**Lokal Hardware Station på Modern POS** : filen är under platsen för Modern POS Client Broker.</span><span class="sxs-lookup"><span data-stu-id="90e98-373">**Local Hardware station on Modern POS:** The file is under the Modern POS client broker location.</span></span>

    > [!WARNING]
    > <span data-ttu-id="90e98-374">Redigera **inte** filerna CommerceRuntime.config och CommerceRuntime.MPOSOffline.config files.</span><span class="sxs-lookup"><span data-stu-id="90e98-374">Do **not** edit the CommerceRuntime.config and CommerceRuntime.MPOSOffline.config files.</span></span> <span data-ttu-id="90e98-375">Dessa filer är inte avsedda för några anpassningar.</span><span class="sxs-lookup"><span data-stu-id="90e98-375">These files aren't intended for any customizations.</span></span>

5. <span data-ttu-id="90e98-376">Hitta och ta bort det tidigare Hardware Station-tillägget från konfigurationsfilen för tillägget.</span><span class="sxs-lookup"><span data-stu-id="90e98-376">Find and remove the earlier Hardware station extension from the extension configuration file.</span></span>

    # <a name="retail-73-and-earlier"></a>[<span data-ttu-id="90e98-377">Retail 7.3 och tidigare</span><span class="sxs-lookup"><span data-stu-id="90e98-377">Retail 7.3 and earlier</span></span>](#tab/retail-7-3)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[<span data-ttu-id="90e98-378">Retail 7.3.1 och senare</span><span class="sxs-lookup"><span data-stu-id="90e98-378">Retail 7.3.1 and later</span></span>](#tab/retail-7-3-1)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[<span data-ttu-id="90e98-379">Retail 10.0 och senare</span><span class="sxs-lookup"><span data-stu-id="90e98-379">Retail 10.0 and later</span></span>](#tab/retail-10-0)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

6. <span data-ttu-id="90e98-380">Lägg till följande rad i avsnittet **sammansättning** i tilläggets konfigurationsfil.</span><span class="sxs-lookup"><span data-stu-id="90e98-380">Add the following line to the **composition** section of the extension configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
    ```

#### <a name="update-modern-pos"></a><span data-ttu-id="90e98-381">Uppdatera Modern POS</span><span class="sxs-lookup"><span data-stu-id="90e98-381">Update Modern POS</span></span>

1. <span data-ttu-id="90e98-382">Öppna lösningen på **RetailSdk\\POS\\CloudPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="90e98-382">Open the solution at **RetailSdk\\POS\\CloudPOS.sln**.</span></span>
2. <span data-ttu-id="90e98-383">Inaktivera det tidigare kassatillägget genom att ta bort följande rader filen **extensions.json**.</span><span class="sxs-lookup"><span data-stu-id="90e98-383">Disable the earlier POS extension by removing the following lines from the **extensions.json** file.</span></span>

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. <span data-ttu-id="90e98-384">Aktivera det aktuella tillägget för kassatillägget genom att lägga till följande rader i filen **extensions.json**.</span><span class="sxs-lookup"><span data-stu-id="90e98-384">Enable the current sample POS extension by adding the following lines in the **extensions.json** file.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a><span data-ttu-id="90e98-385">Uppdatera Cloud POS</span><span class="sxs-lookup"><span data-stu-id="90e98-385">Update Cloud POS</span></span>

1. <span data-ttu-id="90e98-386">Öppna lösningen på **RetailSdk\\POS\\ModernPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="90e98-386">Open the solution at **RetailSdk\\POS\\ModernPOS.sln**.</span></span>
2. <span data-ttu-id="90e98-387">Inaktivera det tidigare kassatillägget genom att ta bort följande rader filen **extensions.json**.</span><span class="sxs-lookup"><span data-stu-id="90e98-387">Disable the earlier POS extension by removing the following lines from the **extensions.json** file.</span></span>

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. <span data-ttu-id="90e98-388">Aktivera det aktuella tillägget för kassatillägget genom att lägga till följande rader i filen **extensions.json**.</span><span class="sxs-lookup"><span data-stu-id="90e98-388">Enable the current sample POS extension by adding the following lines in the **extensions.json** file.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

### <a name="migration-in-a-production-environment"></a><span data-ttu-id="90e98-389">Migrering i en produktionsmiljö</span><span class="sxs-lookup"><span data-stu-id="90e98-389">Migration in a production environment</span></span>

#### <a name="update-crt"></a><span data-ttu-id="90e98-390">Uppdatera CRT</span><span class="sxs-lookup"><span data-stu-id="90e98-390">Update CRT</span></span>

1. <span data-ttu-id="90e98-391">Ta bort tidigare CRT-tillägg från konfigurationsfilerna **CommerceRuntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** under mappen **RetailSdk\\Assets**.</span><span class="sxs-lookup"><span data-stu-id="90e98-391">Remove the earlier CRT extension from the **CommerceRuntime.ext.config** and **CommerceRuntime.MPOSOffline.Ext.config** configuration files under the **RetailSdk\\Assets** folder.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > <span data-ttu-id="90e98-392">Slutför inte det här steget förrän du uppdaterar alla kassaenheter som fungerar med den här CRT-instansen.</span><span class="sxs-lookup"><span data-stu-id="90e98-392">Don't complete this step until you update all POS devices that work with this CRT instance.</span></span>

2. <span data-ttu-id="90e98-393">Aktivera det aktuella exempel CRT-tillägg genom att göra följande ändringar i **CommerceRuntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** konfigurationsfilerna under mappen **RetailSdk\\Assets**.</span><span class="sxs-lookup"><span data-stu-id="90e98-393">Enable the current sample CRT extensions by making the following changes in the **CommerceRuntime.ext.config** and **CommerceRuntime.MPOSOffline.Ext.config** configuration files under the **RetailSdk\\Assets** folder.</span></span>

    ``` xml 
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

3. <span data-ttu-id="90e98-394">I konfigurationsfilen för paketanpassning **Customization.settings** under mappen **BuildTools** lägger du till följande rader för att inkludera det aktuella exempeltillägget CRT i i distribuerbara paket.</span><span class="sxs-lookup"><span data-stu-id="90e98-394">In the **Customization.settings** package customization configuration file under the **BuildTools** folder, add the following lines to include the current sample CRT extension in deployable packages.</span></span>

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
    ```

#### <a name="update-hardware-station"></a><span data-ttu-id="90e98-395">Uppdatera Hardware Station</span><span class="sxs-lookup"><span data-stu-id="90e98-395">Update Hardware station</span></span>

1. <span data-ttu-id="90e98-396">Ta bort det tidigare Hardware Station-tillägget genom att modifiera konfigurationsfilen **HardwareStation.Extension.config**.</span><span class="sxs-lookup"><span data-stu-id="90e98-396">Remove the earlier Hardware station extension by modifying the **HardwareStation.Extension.config** configuration file.</span></span>

    # <a name="retail-73-and-earlier"></a>[<span data-ttu-id="90e98-397">Retail 7.3 och tidigare</span><span class="sxs-lookup"><span data-stu-id="90e98-397">Retail 7.3 and earlier</span></span>](#tab/retail-7-3)

    <span data-ttu-id="90e98-398">Ta bort följande avsnitt från konfigurationsfiler **HardwareStation.Shared.config** och **HardwareStation.Dedicated.config**.</span><span class="sxs-lookup"><span data-stu-id="90e98-398">Remove the following section from the **HardwareStation.Shared.config** and **HardwareStation.Dedicated.config** configuration files.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[<span data-ttu-id="90e98-399">Retail 7.3.1 och senare</span><span class="sxs-lookup"><span data-stu-id="90e98-399">Retail 7.3.1 and later</span></span>](#tab/retail-7-3-1)

    <span data-ttu-id="90e98-400">Ta bort följande avsnitt från konfigurationsfilen **HardwareStation.Extension.config**.</span><span class="sxs-lookup"><span data-stu-id="90e98-400">Remove the following section from the **HardwareStation.Extension.config** configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[<span data-ttu-id="90e98-401">Retail 10.0 och senare</span><span class="sxs-lookup"><span data-stu-id="90e98-401">Retail 10.0 and later</span></span>](#tab/retail-10-0)

    <span data-ttu-id="90e98-402">Ta bort följande avsnitt från konfigurationsfilen **HardwareStation.Extension.config**.</span><span class="sxs-lookup"><span data-stu-id="90e98-402">Remove the following section from the **HardwareStation.Extension.config** configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

2. <span data-ttu-id="90e98-403">Aktivera det aktuella exemplet på Hardware Station-tillägget genom att lägga till följande rad i avsnittet **komposition** i konfigurationsfil **HardwareStation.Extension.config**.</span><span class="sxs-lookup"><span data-stu-id="90e98-403">Enable the current sample Hardware station extension by adding the following line to the **composition** section in the **HardwareStation.Extension.config** configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

3. <span data-ttu-id="90e98-404">Gör följande ändringar i konfigurationsfilerna för paketanpassning **Customization.settings** under **BuildTools**:</span><span class="sxs-lookup"><span data-stu-id="90e98-404">Make the following changes in the **Customization.settings** package customization configuration file under the **BuildTools** folder:</span></span>

    - <span data-ttu-id="90e98-405">Ta bort följande rader för att utesluta den tidigare Hardware Station-tillägget från distribuerbara paket.</span><span class="sxs-lookup"><span data-stu-id="90e98-405">Remove the following lines to exclude the earlier Hardware station extension from deployable packages.</span></span>

        ``` xml 
        <ISV_CommerceRuntime_CustomizableFileInclude="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - <span data-ttu-id="90e98-406">Lägg till följande rad om du vill inkludera det aktuella exemplet Hardware Station-tillägget i de distribuerbara paketen.</span><span class="sxs-lookup"><span data-stu-id="90e98-406">Add the following line to include the current sample Hardware station extension in deployable packages.</span></span>

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        ```

#### <a name="update-modern-pos"></a><span data-ttu-id="90e98-407">Uppdatera Modern POS</span><span class="sxs-lookup"><span data-stu-id="90e98-407">Update Modern POS</span></span>

1. <span data-ttu-id="90e98-408">Öppna lösningen på **RetailSdk\\POS\\CloudPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="90e98-408">Open the solution at **RetailSdk\\POS\\CloudPOS.sln**.</span></span>
2. <span data-ttu-id="90e98-409">Inaktivera det tidigare kassatillägget:</span><span class="sxs-lookup"><span data-stu-id="90e98-409">Disable the earlier POS extension:</span></span>

    - <span data-ttu-id="90e98-410">I filen **tsconfig.json**, lägg till mappen **FiscalRegisterSample** i undantagslistan.</span><span class="sxs-lookup"><span data-stu-id="90e98-410">In the **tsconfig.json** file, add the **FiscalRegisterSample** folder to the exclude list.</span></span>
    - <span data-ttu-id="90e98-411">Ta bort de tidigare raderna från filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.</span><span class="sxs-lookup"><span data-stu-id="90e98-411">Remove the following lines from the **extensions.json** file under the **RetailSDK\\POS\\Extensions** folder.</span></span>

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. <span data-ttu-id="90e98-412">Aktivera det aktuella exemplet för kassatillägget genom att lägga till följande rader i filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.</span><span class="sxs-lookup"><span data-stu-id="90e98-412">Enable the current sample POS extension by adding the following lines in the **extensions.json** file under the **RetailSDK\\POS\\Extensions** folder.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a><span data-ttu-id="90e98-413">Uppdatera Cloud POS</span><span class="sxs-lookup"><span data-stu-id="90e98-413">Update Cloud POS</span></span>

1. <span data-ttu-id="90e98-414">Öppna lösningen på **RetailSdk\\POS\\ModernPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="90e98-414">Open the solution at **RetailSdk\\POS\\ModernPOS.sln**.</span></span>
2. <span data-ttu-id="90e98-415">Inaktivera det tidigare kassatillägget:</span><span class="sxs-lookup"><span data-stu-id="90e98-415">Disable the earlier POS extension:</span></span>

    - <span data-ttu-id="90e98-416">I filen **tsconfig.json**, lägg till mappen **FiscalRegisterSample** i undantagslistan.</span><span class="sxs-lookup"><span data-stu-id="90e98-416">In the **tsconfig.json** file, add the **FiscalRegisterSample** folder to the exclude list.</span></span>
    - <span data-ttu-id="90e98-417">Ta bort de tidigare raderna från filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.</span><span class="sxs-lookup"><span data-stu-id="90e98-417">Remove the following lines from the **extensions.json** file under the **RetailSDK\\POS\\Extensions** folder.</span></span>

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

4. <span data-ttu-id="90e98-418">Aktivera det aktuella exemplet för kassatillägget genom att lägga till följande rader i filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.</span><span class="sxs-lookup"><span data-stu-id="90e98-418">Enable the current sample POS extension by adding the following lines in the **extensions.json** file under the **RetailSDK\\POS\\Extensions** folder.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="create-deployable-packages"></a><span data-ttu-id="90e98-419">Skapa driftfärdiga paket</span><span class="sxs-lookup"><span data-stu-id="90e98-419">Create deployable packages</span></span>

<span data-ttu-id="90e98-420">Kör **msbuild** för hela Retail SDK för att skapa distribuerbara paket.</span><span class="sxs-lookup"><span data-stu-id="90e98-420">Run **msbuild** for the whole Retail SDK to create deployable packages.</span></span> <span data-ttu-id="90e98-421">Tillämpa paketen via LCS eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="90e98-421">Apply the packages via LCS or manually.</span></span> <span data-ttu-id="90e98-422">Mer information finns i [Retail SDK-paket](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="90e98-422">For more information, see [Retail SDK packaging](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span></span>
