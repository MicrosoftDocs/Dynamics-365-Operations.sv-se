---
title: ER-målstyp för e-post
description: Det här ämnet ger information om hur du konfigurerar en e-postdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 086114d6a8d425ca01521d9607e4a70ec5aa766b
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020006"
---
# <span data-ttu-id="08f7f-103"><a name="EmailDestinationType">E-postmål</a></span><span class="sxs-lookup"><span data-stu-id="08f7f-103"><a name="EmailDestinationType">Email destination</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08f7f-104">Du kan konfigurera en e-postdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.</span><span class="sxs-lookup"><span data-stu-id="08f7f-104">You can configure an email destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="08f7f-105">Baserat på destinationsinställningen lagras ett levererat dokument som en bilaga till ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="08f7f-105">Based on the destination setting, a generated document is delivered as an attachment of an electronic mail.</span></span>

<span data-ttu-id="08f7f-106">Ställ in **Aktiverad** till **Ja** för att skicka en utdatafil via e-post.</span><span class="sxs-lookup"><span data-stu-id="08f7f-106">Set **Enabled** to **Yes** to send an output file by email.</span></span> <span data-ttu-id="08f7f-107">När det här alternativet är aktiverat kan du ange e-postmottagare samt redigera e-postmeddelandets ämne och brödtext.</span><span class="sxs-lookup"><span data-stu-id="08f7f-107">After this option is enabled, you can specify the email recipients and edit the subject and body of the email message.</span></span> <span data-ttu-id="08f7f-108">Du kan skapa konstanta texter mailets rubrik och brödtext, eller använda ER-[formler](er-formula-language.md) för att skapa e-posttexter dynamiskt.</span><span class="sxs-lookup"><span data-stu-id="08f7f-108">You can set up constant texts for the email subject and body, or you can use ER [formulas](er-formula-language.md) to dynamically create email texts.</span></span> 

<span data-ttu-id="08f7f-109">Du kan konfigurera e-postadresser för ER på två sätt.</span><span class="sxs-lookup"><span data-stu-id="08f7f-109">You can configure email addresses for ER in two ways.</span></span> <span data-ttu-id="08f7f-110">Konfigurationen kan slutföras på samma sätt som funktionen utskriftshanterings slutför den, eller så kan du lösa en e-postadress genom att använda en direkt referens till ER-konfigurationen via en formel.</span><span class="sxs-lookup"><span data-stu-id="08f7f-110">The configuration can be completed in the same way that the Print management feature completes it, or you can resolve an email address by using a direct reference to the ER configuration through a formula.</span></span>

<span data-ttu-id="08f7f-111">[![Aktivera e-postmål](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span><span class="sxs-lookup"><span data-stu-id="08f7f-111">[![Enable email destination](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span></span>

## <a name="email-address-types"></a><span data-ttu-id="08f7f-112">E-postadresstyper</span><span class="sxs-lookup"><span data-stu-id="08f7f-112">Email address types</span></span>

<span data-ttu-id="08f7f-113">När du klickar på **Redigera** för fältet **Till** eller **Cc**, visas dialogrutan **E-posta**.</span><span class="sxs-lookup"><span data-stu-id="08f7f-113">When you select **Edit** in the **To** or **Cc** fields, the **Email to** dialog box appears.</span></span> <span data-ttu-id="08f7f-114">Du kan sedan välja vilken typ av e-postadress som ska användas.</span><span class="sxs-lookup"><span data-stu-id="08f7f-114">You can then select the type of email address to use.</span></span> <span data-ttu-id="08f7f-115">E-posttyperna **Konfigurations-e-postmeddelande** och **Utskriftshantering** stöds för närvarande.</span><span class="sxs-lookup"><span data-stu-id="08f7f-115">The **Configuration email** and **Print Management** email types are currently supported.</span></span>

<span data-ttu-id="08f7f-116">[![Välj typ av e-post](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span><span class="sxs-lookup"><span data-stu-id="08f7f-116">[![Select email type](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span></span>

### <a name="print-management"></a><span data-ttu-id="08f7f-117">Utskriftshantering</span><span class="sxs-lookup"><span data-stu-id="08f7f-117">Print management</span></span>

<span data-ttu-id="08f7f-118">Om du väljer typen **Utskriftshantering för e-postmeddelanden** kan du ange fasta e-postadresser i fältet **Till**.</span><span class="sxs-lookup"><span data-stu-id="08f7f-118">If you select the **Print Management** email type, you can enter fixed email addresses in the **To** field.</span></span> 

<span data-ttu-id="08f7f-119">[![Konfigurera fasta e-postadresser](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span><span class="sxs-lookup"><span data-stu-id="08f7f-119">[![Configure fixed email addresses](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span></span>

<span data-ttu-id="08f7f-120">Du måste välja källtyp för e-postmeddelanden till en filmål om du vill använda e-postadresser som inte är fasta.</span><span class="sxs-lookup"><span data-stu-id="08f7f-120">To use email addresses that aren't fixed, you must select the email source type for a file destination.</span></span> <span data-ttu-id="08f7f-121">Följande värden kan användas: **Kund**, **Leverantör**, **Potentiell kund**, **Kontakt**, **Konkurrent**, **Arbetare**, **Sökande**, **Potentiell leverantör** samt **Otillåten leverantör**.</span><span class="sxs-lookup"><span data-stu-id="08f7f-121">The following values are supported: **Customer**, **Vendor**, **Prospect**, **Contact**, **Competitor**, **Worker**, **Applicant**, **Prospective vendor**, and **Disallowed vendor**.</span></span> <span data-ttu-id="08f7f-122">När du har valt en e-posttyp klickar du på knappen bredvid fältet **Källkonto för e-post** för att öppna formuläret **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="08f7f-122">After you select an email source type, use the button next to the **Email source account** field to open the **Formula designer** form.</span></span> <span data-ttu-id="08f7f-123">Du kan använda det här formuläret för att bifoga en formel som returneras vid körningen **partskonto** för den valda källtypen från det bearbetade dokumentet till e-postmålet.</span><span class="sxs-lookup"><span data-stu-id="08f7f-123">You can use this form to attach a formula that returns at runtime, the **party account** of the selected source type from the processed document to the email destination.</span></span>

<span data-ttu-id="08f7f-124">[![Konfigurera källkonto för e-post](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span><span class="sxs-lookup"><span data-stu-id="08f7f-124">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span></span>

<span data-ttu-id="08f7f-125">Formlerna är specifika för ER-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="08f7f-125">Formulas are specific to the ER configuration.</span></span> <span data-ttu-id="08f7f-126">Ange en dokumentspecifik referens till en kund- eller leverantörsparttyp i fältet **Formel**.</span><span class="sxs-lookup"><span data-stu-id="08f7f-126">In the **Formula** field, enter a document-specific reference to a customer or vendor party type.</span></span> <span data-ttu-id="08f7f-127">I stället för skriva in datakällanoden kan du hitta den som representerar kund- eller leverantörskontot och klicka på **Lägg till datakälla** om du vill uppdatera formeln.</span><span class="sxs-lookup"><span data-stu-id="08f7f-127">Instead of typing, you can find the data source node that represents the customer or vendor account, and then select **Add data source** to update the formula.</span></span> <span data-ttu-id="08f7f-128">Exempel: Om du använder konfigurationen **ISO 20022 för kreditöverföring** är noden som representerar ett leverantörskonto `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span><span class="sxs-lookup"><span data-stu-id="08f7f-128">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents a vendor account is `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span></span>

<span data-ttu-id="08f7f-129">Om du anger ett strängvärde, t.ex. `"DE-001"` och sparar en formel, skickas ett e-postmeddelande till leverantörens kontaktperson **DE-001**.</span><span class="sxs-lookup"><span data-stu-id="08f7f-129">If you enter a string value, such as `"DE-001"`, and save a formula, an email will be sent to the contact person of the vendor, **DE-001**.</span></span>


<span data-ttu-id="08f7f-130">[![Sidan ER-formeldesigner](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span><span class="sxs-lookup"><span data-stu-id="08f7f-130">[![ER formula designer page](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span></span>

<span data-ttu-id="08f7f-131">[![Konfigurera källkonto för e-post](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span><span class="sxs-lookup"><span data-stu-id="08f7f-131">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span></span>



### <a name="configuration-email"></a><span data-ttu-id="08f7f-132">Konfigurations-e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="08f7f-132">Configuration email</span></span>

<span data-ttu-id="08f7f-133">Använd den här typen av e-post om den konfiguration som du använder har en nod i datakällorna som representerar en **e-postadress**.</span><span class="sxs-lookup"><span data-stu-id="08f7f-133">Use this email type if the configuration that you use has a node in the data sources that returns an **email address**.</span></span> <span data-ttu-id="08f7f-134">Du kan använda datakällor och funktioner i formeldesignern för att få en korrekt formaterad e-postadress.</span><span class="sxs-lookup"><span data-stu-id="08f7f-134">You can use data sources and functions in the formula designer to get a correctly formatted email address.</span></span> <span data-ttu-id="08f7f-135">Exempel: Om du använder konfigurationen **ISO 20022 kreditöverföring** är noden som representerar en e-postadress för leverantörens kontaktperson `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span><span class="sxs-lookup"><span data-stu-id="08f7f-135">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents an email address of a vendor's contact person is `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span></span>

<span data-ttu-id="08f7f-136">[![Konfigurera målkonto för e-post](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span><span class="sxs-lookup"><span data-stu-id="08f7f-136">[![Configure email address source](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="08f7f-137">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="08f7f-137">Additional resources</span></span>

- [<span data-ttu-id="08f7f-138">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="08f7f-138">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="08f7f-139">Destinationer för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="08f7f-139">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="08f7f-140">Formeldesigner i elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="08f7f-140">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
