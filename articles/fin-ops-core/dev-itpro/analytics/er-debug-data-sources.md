---
title: Felsöka datakällor i ett kört ER-format för analys av dataflöde och omvandling
description: I det här avsnittet beskrivs hur du kan felsöka datakällorna i ett exekverat ER-format för att bättre förstå det konfigurerade dataflödet och omvandlingen.
author: NickSelin
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: fe3e6a4223fc8b26e523a982a2e1752a34b370de
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753682"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a><span data-ttu-id="853fe-103">Felsöka datakällor i ett kört ER-format för analys av dataflöde och omvandling</span><span class="sxs-lookup"><span data-stu-id="853fe-103">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="853fe-104">När du [konfigurerar](tasks/er-format-configuration-2016-11.md) en elektronisk rapportlösning (ER) för att generera elektroniska dokument, definierar du den metod som används för att hämta data från programmet och anger den i genererad utdata.</span><span class="sxs-lookup"><span data-stu-id="853fe-104">When you [configure](tasks/er-format-configuration-2016-11.md) an Electronic reporting (ER) solution to generate outbound documents, you define the methods that are used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="853fe-105">För att du ska kunna göra livscykelsupport för ER-lösningen mer effektiv bör din lösning bestå av en ER [datamodell ](general-electronic-reporting.md#DataModelComponent)och dess [mappnings](general-electronic-reporting.md#ModelMappingComponent)-komponenter, och också ett återställnings[format ](general-electronic-reporting.md#FormatComponentOutbound) med dess mappningskomponenter så att modellmappningen är programspecifik, medan andra komponenter fortfarande är programagnostiska.</span><span class="sxs-lookup"><span data-stu-id="853fe-105">To make the life cycle support of the ER solution more efficient, your solution should consist of an ER [data model](general-electronic-reporting.md#DataModelComponent) and its [mapping](general-electronic-reporting.md#ModelMappingComponent) components, and also an ER [format](general-electronic-reporting.md#FormatComponentOutbound) and its mapping components, so that the model mapping is application-specific, whereas other components remain application-agnostic.</span></span> <span data-ttu-id="853fe-106">Därför kan flera ER-komponenter [påverka](general-electronic-reporting.md#FormatComponentOutbound) processen att ange data i den genererade utmatningen.</span><span class="sxs-lookup"><span data-stu-id="853fe-106">Therefore, several ER components might [affect](general-electronic-reporting.md#FormatComponentOutbound) the process of entering data in the generated output.</span></span>

<span data-ttu-id="853fe-107">Ibland ser data i den genererade utmatningen annorlunda ut än samma data i programdatabasen.</span><span class="sxs-lookup"><span data-stu-id="853fe-107">Sometimes, the data of the generated output looks different than the same data in the application database.</span></span> <span data-ttu-id="853fe-108">I dessa fall vill du ta reda på vilken ER-komponent som ansvarar för dataomvandlingen.</span><span class="sxs-lookup"><span data-stu-id="853fe-108">In these cases, you will want to determine which ER component is responsible for the data transformation.</span></span> <span data-ttu-id="853fe-109">Funktionen för felsökning av ER-datakällan minskar markant både tid och kostnad för undersökningen.</span><span class="sxs-lookup"><span data-stu-id="853fe-109">The ER data source debugger feature significantly reduces the time and cost that are involved in this investigation.</span></span> <span data-ttu-id="853fe-110">Du kan avbryta körningen av ett ER-format och öppna gränssnittet för datakällans felsökning.</span><span class="sxs-lookup"><span data-stu-id="853fe-110">You can interrupt the execution of an ER format and open the data source debugger interface.</span></span> <span data-ttu-id="853fe-111">Där kan du bläddra bland tillgängliga datakällor och välja en enskild datakälla att köra.</span><span class="sxs-lookup"><span data-stu-id="853fe-111">There, you can browse the available data sources and select an individual data source for execution.</span></span> <span data-ttu-id="853fe-112">Denna manuella körning simulerar körning av datakällan när ett ER-format körs på riktigt.</span><span class="sxs-lookup"><span data-stu-id="853fe-112">This manual execution simulates the execution of the data source during the real run of an ER format.</span></span> <span data-ttu-id="853fe-113">Resultatet visas på en sida där du kan analysera de data som har tagits emot.</span><span class="sxs-lookup"><span data-stu-id="853fe-113">The result is presented on a page where you can analyze the data that is received.</span></span>

<span data-ttu-id="853fe-114">Om du vill aktivera funktionen för felsökning av datakälla anger du alternativet **Aktivera datafelsökning vid formatkörning** till **Ja** i ER:s användarparametrar.</span><span class="sxs-lookup"><span data-stu-id="853fe-114">To turn on the data source debugging feature, set the **Enable data debugging at format run** option to **Yes** in the ER user parameters.</span></span> <span data-ttu-id="853fe-115">Du kan sedan starta felsökningen av datakällan när du kör ett ER-format för att generera utgående dokument.</span><span class="sxs-lookup"><span data-stu-id="853fe-115">You can then start data source debugging while you run an ER format to generate outbound documents.</span></span> <span data-ttu-id="853fe-116">Du kan också använda alternativet **Starta felsökning** om du vill initiera felsökning av datakällor för ett ER-format som har konfigurerats i [ER-åtgärdsdesigner](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span><span class="sxs-lookup"><span data-stu-id="853fe-116">You can also use the **Start debugging** option to initiate data source debugging for an ER format that is configured in the [ER Operation designer](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span></span>

<span data-ttu-id="853fe-117">Det här avsnittet innehåller riktlinjer för initiering av felsökning av datakällor för körda ER-format.</span><span class="sxs-lookup"><span data-stu-id="853fe-117">This topic provides guidelines for initiating data source debugging for executed ER formats.</span></span> <span data-ttu-id="853fe-118">Det förklarar hur informationen kan hjälpa dig att förstå dataflödet och dataomvandlingar.</span><span class="sxs-lookup"><span data-stu-id="853fe-118">It explains how the information can help you understand the data flow and data transformations.</span></span> <span data-ttu-id="853fe-119">I exemplen i det här avsnittet används affärsprocessen för bearbetning av leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="853fe-119">The examples in this topic use the business process for vendor payments processing.</span></span>

## <a name="limitations"></a><span data-ttu-id="853fe-120">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="853fe-120">Limitations</span></span>

<span data-ttu-id="853fe-121">Datakällans felsökare kan användas för att få åtkomst till datakällor som används i ER-format för att generera utgående dokument.</span><span class="sxs-lookup"><span data-stu-id="853fe-121">The data source debugger can be used to access the data of data sources that are used in ER formats that are run to generate outbound documents.</span></span> <span data-ttu-id="853fe-122">Den kan inte användas för att felsöka datakällor i ER-format som är utformade för att tolka inkommande dokument.</span><span class="sxs-lookup"><span data-stu-id="853fe-122">It can't be used to debug data sources of ER formats that are designed to parse inbound documents.</span></span>

<span data-ttu-id="853fe-123">Följande inställningar för ER-format är för närvarande inte tillgängliga för felsökning av datakällor:</span><span class="sxs-lookup"><span data-stu-id="853fe-123">The following settings of ER formats aren't currently accessible for data source debugging:</span></span>

- <span data-ttu-id="853fe-124">Formatomvandlingar</span><span class="sxs-lookup"><span data-stu-id="853fe-124">Format transformations</span></span>
- <span data-ttu-id="853fe-125">Formatera och mappa valideringsregler</span><span class="sxs-lookup"><span data-stu-id="853fe-125">Format and mapping validation rules</span></span>
- <span data-ttu-id="853fe-126">Aktivera uttryck</span><span class="sxs-lookup"><span data-stu-id="853fe-126">Enabling expressions</span></span>
- <span data-ttu-id="853fe-127">Information om datainsamling i minnet</span><span class="sxs-lookup"><span data-stu-id="853fe-127">Details of in-memory data collection</span></span>

## <a name="prerequisites"></a><span data-ttu-id="853fe-128">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="853fe-128">Prerequisites</span></span>

- <span data-ttu-id="853fe-129">Om du vill slutföra exemplen i det här avsnittet måste du ha tillgång till en av följande [roller](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="853fe-129">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="853fe-130">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="853fe-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="853fe-131">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="853fe-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="853fe-132">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="853fe-132">System administrator</span></span>

- <span data-ttu-id="853fe-133">Företaget måste vara inställt på **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="853fe-133">The company must be set to **DEMF**.</span></span>

- <span data-ttu-id="853fe-134">Följ instruktionerna i [Bilaga 1](#appendix1) i det här avsnittet för att hämta komponenterna för den Microsoft ER-lösning som krävs för att bearbeta leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="853fe-134">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the Microsoft ER solution that are required to process vendor payments.</span></span>
- <span data-ttu-id="853fe-135">Följ instruktionerna i [Bilaga 2](#appendix2) till det här avsnittet för att förbereda leverantörsreskontra för bearbetning av leverantörsbetalningar genom att använda den ER-lösning som du ska hämta.</span><span class="sxs-lookup"><span data-stu-id="853fe-135">Follow the steps in [Appendix 2](#appendix2) of this topic to prepare Accounts payable for vendor payment processing by using the ER solution that you will download.</span></span>

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a><span data-ttu-id="853fe-136">Bearbeta en leverantörsbetalning för att få en betalningsfil</span><span class="sxs-lookup"><span data-stu-id="853fe-136">Process a vendor payment to get a payment file</span></span>

1. <span data-ttu-id="853fe-137">Följ instruktionerna i [Bilaga 3](#appendix3) till det här avsnittet för att bearbeta leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="853fe-137">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>

    ![Bearbetning av leverantörsbetalningar pågår](./media/er-data-debugger-process-payment.png)

2. <span data-ttu-id="853fe-139">Hämta och spara zip-filen på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="853fe-139">Download and save the zip file to your local computer.</span></span>
3. <span data-ttu-id="853fe-140">Packa upp betalningsfilen **ISO20022 Credit transfer.xml** från zip-filen.</span><span class="sxs-lookup"><span data-stu-id="853fe-140">Extract the **ISO20022 Credit transfer.xml** payment file from the zip file.</span></span>
4. <span data-ttu-id="853fe-141">Öppna den extraherade betalningsfilen med hjälp av XML-granskaren.</span><span class="sxs-lookup"><span data-stu-id="853fe-141">Open the extracted payment file by using the XML file viewer.</span></span>

    <span data-ttu-id="853fe-142">I betalningsfilen finns IBAN-koden (International Bank Account Number) för leverantörens bankkonto utan blanksteg.</span><span class="sxs-lookup"><span data-stu-id="853fe-142">In the payment file, the International Bank Account Number (IBAN) code of the vendor bank account contains no spaces.</span></span> <span data-ttu-id="853fe-143">Därför skiljer det sig från värdet som [angavs](#enteredIBANcode) på sidan **Bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="853fe-143">Therefore, it differs from the value that was [entered](#enteredIBANcode) on the **Bank accounts** page.</span></span>

    ![IBAN-kod utan blanksteg](./media/er-data-debugger-payment-file.png)

    <span data-ttu-id="853fe-145">Du kan använda felsökaren för ER-datakälla om du vill veta vilken del av ER-lösningen som används för att ta bort blanksteg i IBAN-koden.</span><span class="sxs-lookup"><span data-stu-id="853fe-145">You can use the ER data source debugger to learn which component of the ER solution is used to truncate spaces in the IBAN code.</span></span>

## <a name="turn-on-data-source-debugging"></a><span data-ttu-id="853fe-146">Aktivera felsökning av datakälla</span><span class="sxs-lookup"><span data-stu-id="853fe-146">Turn on data source debugging</span></span>

1. <span data-ttu-id="853fe-147">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="853fe-147">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="853fe-148">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="853fe-148">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="853fe-149">Ställ in alternativet **Aktivera felsökning av data vid formatkörning** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="853fe-149">Set the **Enable data debugging at format run** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="853fe-150">Den här parametern är specifik för användaren och företaget.</span><span class="sxs-lookup"><span data-stu-id="853fe-150">This parameter is user-specific and company-specific.</span></span>

    ![Dialogruta Användarparametrar](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a><span data-ttu-id="853fe-152">Bearbeta en leverantörsbetalning för felsökning</span><span class="sxs-lookup"><span data-stu-id="853fe-152">Process a vendor payment for debugging</span></span>

1. <span data-ttu-id="853fe-153">Följ instruktionerna i [Bilaga 3](#appendix3) till det här avsnittet för att bearbeta leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="853fe-153">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>
2. <span data-ttu-id="853fe-154">I meddelanderutan väljer du **Ja** för att bekräfta att du vill avbryta bearbetning av leverantörsbetalningar och i stället starta felsökning av datakällor på sidan **Felsökning av datakällor**.</span><span class="sxs-lookup"><span data-stu-id="853fe-154">In the message box, select **Yes** to confirm that you want to interrupt vendor payment processing and instead start data source debugging on the **Debug Datasources** page.</span></span>

    ![Ruta för bekräftelsemeddelande](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a><span data-ttu-id="853fe-156">Felsökning av datakällor som används vid betalningsbearbetning</span><span class="sxs-lookup"><span data-stu-id="853fe-156">Debug data sources that are used in payment processing</span></span>

### <a name="debug-the-model-mapping"></a><span data-ttu-id="853fe-157">Felsöka modellmappningen</span><span class="sxs-lookup"><span data-stu-id="853fe-157">Debug the model mapping</span></span>

1. <span data-ttu-id="853fe-158">På sidan **Felsök datakällor**, i åtgärdsfönstret, väljer du **Modellmappning** för att starta felsökning från denna ER-komponent.</span><span class="sxs-lookup"><span data-stu-id="853fe-158">On the **Debug Datasources** page, on the Action Pane, select **Model mapping** to start to debug from this ER component.</span></span>
2. <span data-ttu-id="853fe-159">Markera datakällan **\$notSentTransactions** i fönstret med datakällor till vänster och välj sedan **Läs alla poster**.</span><span class="sxs-lookup"><span data-stu-id="853fe-159">In the data source pane on the left, select the **\$notSentTransactions** data source, and then select **Read all records**.</span></span>

    <span data-ttu-id="853fe-160">Du kan välja **Läs 1 post**, **Läs 10 poster**, **Läs 100 poster** eller **Läs alla poster** för att tvinga korrekt antal poster att läsas från den valda datakällan.</span><span class="sxs-lookup"><span data-stu-id="853fe-160">You can select **Read 1 record**, **Read 10 records**, **Read 100 records**, or **Read all records** to force the appropriate number of records to be read from the selected data source.</span></span> <span data-ttu-id="853fe-161">På så sätt kan du simulera åtkomst till datakällan från det pågående ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="853fe-161">In this way, you can simulate access to the data source from the running ER format.</span></span>

3. <span data-ttu-id="853fe-162">I datarutan till höger, välj **Expandera allt**.</span><span class="sxs-lookup"><span data-stu-id="853fe-162">In the data pane on the right, select **Expand all**.</span></span>

    <span data-ttu-id="853fe-163">Du ser att den valda datakällan för **postlistetypen** innehåller en enda post.</span><span class="sxs-lookup"><span data-stu-id="853fe-163">You can see that the selected data source of the **Record list** type contains a single record.</span></span>

4. <span data-ttu-id="853fe-164">Expandera datakällan **\$notSentTransactions** och välj den kapslade metoden **vendBankAccountInTransactionCompany()**.</span><span class="sxs-lookup"><span data-stu-id="853fe-164">Expand the **\$notSentTransactions** data source, and select the nested **vendBankAccountInTransactionCompany()** method.</span></span>
5. <span data-ttu-id="853fe-165">Expandera metoden **vendBankAccountInTransactionCompany()** och välj det kapslade fältet **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="853fe-165">Expand the **vendBankAccountInTransactionCompany()** method, and select the nested **IBAN** field.</span></span>
6. <span data-ttu-id="853fe-166">Välj **Hämta värde**.</span><span class="sxs-lookup"><span data-stu-id="853fe-166">Select **Get value**.</span></span>

    <span data-ttu-id="853fe-167">Du kan välja **Hämta värde** för att tvinga värdet i ett markerat fält i den valda datakällan att läsas.</span><span class="sxs-lookup"><span data-stu-id="853fe-167">You can select **Get value** to force the value of a selected field of the selected data source to be read.</span></span> <span data-ttu-id="853fe-168">På så sätt kan du simulera åtkomst till fältet i fråga från det pågående ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="853fe-168">In this way, you can simulate access to this field from the running ER format.</span></span>

7. <span data-ttu-id="853fe-169">Välj **Expandera alla**.</span><span class="sxs-lookup"><span data-stu-id="853fe-169">Select **Expand all**.</span></span>

    ![Värdet i IBAN-fältet i modellmappningen](./media/er-data-debugger-debugging-model-mapping.png)

    <span data-ttu-id="853fe-171">Som du ser är modellmappningen inte ansvarig för avkortningar, eftersom IBAN-koden som den returnerar för leverantörens bankkonto innehåller blanksteg.</span><span class="sxs-lookup"><span data-stu-id="853fe-171">As you can see, the model mapping isn't responsible for the truncated spaces, because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="853fe-172">Därför måste du fortsätta felsökningen av datakällan.</span><span class="sxs-lookup"><span data-stu-id="853fe-172">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format-mapping"></a><span data-ttu-id="853fe-173">Felsök formatmappningen</span><span class="sxs-lookup"><span data-stu-id="853fe-173">Debug the format mapping</span></span>

1. <span data-ttu-id="853fe-174">På sidan **Felsök datakällor** väljer du i åtgärdsfönstret **Formatmappning** för att fortsätta felsökning från denna ER-komponent.</span><span class="sxs-lookup"><span data-stu-id="853fe-174">On the **Debug Datasources** page, on the Action Pane, select **Format mapping** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="853fe-175">Välj datakällan **\$PaymentByDebtor** och välj sedan **Läs alla poster**.</span><span class="sxs-lookup"><span data-stu-id="853fe-175">Select the **\$PaymentByDebtor** data source, and then select **Read all records**.</span></span>
3. <span data-ttu-id="853fe-176">Expandera **\$PaymentByDebtor**.</span><span class="sxs-lookup"><span data-stu-id="853fe-176">Expand **\$PaymentByDebtor**.</span></span>
4. <span data-ttu-id="853fe-177">Expandera **\$PaymentByDebtor.Lines** och välj sedan **Läs alla poster**.</span><span class="sxs-lookup"><span data-stu-id="853fe-177">Expand **\$PaymentByDebtor.Lines**, and then select **Read all records**.</span></span>
5. <span data-ttu-id="853fe-178">Expandera **\$PaymentByDebtor.Lines.CreditorAccount**.</span><span class="sxs-lookup"><span data-stu-id="853fe-178">Expand **\$PaymentByDebtor.Lines.CreditorAccount**.</span></span>
6. <span data-ttu-id="853fe-179">Expandera **\$PaymentByDebtor.Lines.CreditorAccount.Identification** och välj sedan **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span><span class="sxs-lookup"><span data-stu-id="853fe-179">Expand **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, and then select **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span></span>
7. <span data-ttu-id="853fe-180">Välj **Hämta värde**.</span><span class="sxs-lookup"><span data-stu-id="853fe-180">Select **Get value**.</span></span>
8. <span data-ttu-id="853fe-181">Välj **Expandera alla**.</span><span class="sxs-lookup"><span data-stu-id="853fe-181">Select **Expand all**.</span></span>

    ![Värdet i IBAN-fältet i formatmappningen](./media/er-data-debugger-debugging-format-mapping.png)

    <span data-ttu-id="853fe-183">Som du ser är datakällorna för formatmappningen inte ansvariga för avkortningar, eftersom IBAN-koden som de returnerar för leverantörens bankkonto innehåller blanksteg.</span><span class="sxs-lookup"><span data-stu-id="853fe-183">As you can see, the data sources of the format mapping aren't responsible for the truncated spaces, because the IBAN code that they return for the vendor bank account includes spaces.</span></span> <span data-ttu-id="853fe-184">Därför måste du fortsätta felsökningen av datakällan.</span><span class="sxs-lookup"><span data-stu-id="853fe-184">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format"></a><span data-ttu-id="853fe-185">Felsök formatet</span><span class="sxs-lookup"><span data-stu-id="853fe-185">Debug the format</span></span>

1. <span data-ttu-id="853fe-186">På sidan **Felsök datakällor** väljer du **Format** i åtgärdsfönstret för att fortsätta felsökning från denna ER-komponent.</span><span class="sxs-lookup"><span data-stu-id="853fe-186">On the **Debug Datasources** page, on the Action Pane, select **Format** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="853fe-187">Expandera formatelementen för att välja **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** och välj sedan **Läs alla poster**.</span><span class="sxs-lookup"><span data-stu-id="853fe-187">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, and then select **Read all records**.</span></span>
3. <span data-ttu-id="853fe-188">Expandera formatelementen för att välja **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** och välj sedan **Läs alla poster**.</span><span class="sxs-lookup"><span data-stu-id="853fe-188">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, and then select **Read all records**.</span></span>
4. <span data-ttu-id="853fe-189">Expandera formatelementen för att välja **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** och välj sedan **Hämta värde**.</span><span class="sxs-lookup"><span data-stu-id="853fe-189">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, and then select **Get value**.</span></span>
5. <span data-ttu-id="853fe-190">Välj **Expandera alla**.</span><span class="sxs-lookup"><span data-stu-id="853fe-190">Select **Expand all**.</span></span>

    ![Värdet i IBAN-fältet i formatet](./media/er-data-debugger-debugging-format.png)

   <span data-ttu-id="853fe-192">Som du ser är formatbindningen inte ansvarig för avkortningar, eftersom IBAN-koden som den returnerar för leverantörens bankkonto innehåller blanksteg.</span><span class="sxs-lookup"><span data-stu-id="853fe-192">As you can see, the format binding isn't responsible for the truncated spaces because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="853fe-193">Därför konfigureras elementet **BankIBAN** att använda formatomvandling som avkortar blanksteg.</span><span class="sxs-lookup"><span data-stu-id="853fe-193">Therefore, the **BankIBAN** element is configured to use a format transformation that truncates spaces.</span></span>

6. <span data-ttu-id="853fe-194">Stäng felsökaren för datakälla.</span><span class="sxs-lookup"><span data-stu-id="853fe-194">Close the data source debugger.</span></span>

### <a name="review-the-format-transformations"></a><span data-ttu-id="853fe-195">Granska formatomvandlingarna</span><span class="sxs-lookup"><span data-stu-id="853fe-195">Review the format transformations</span></span>

1. <span data-ttu-id="853fe-196">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="853fe-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="853fe-197">På sidan **Konfigurationer** väljer du **Betalningsmodell** \> **ISO20022-kreditöverföring**.</span><span class="sxs-lookup"><span data-stu-id="853fe-197">On the **Configurations** page, select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="853fe-198">Välj **Designer** och expandera sedan elementen för att välja **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span><span class="sxs-lookup"><span data-stu-id="853fe-198">Select **Designer**, and then expand the elements to select **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span></span>

    ![BankIBAN-element på sidan Formatdesigner](./media/er-data-debugger-referred-transformation.png)

    <span data-ttu-id="853fe-200">Som du ser är elementet **BankIBAN** konfigurerat att använda **ta bort icke alfanumerisk** omvandling.</span><span class="sxs-lookup"><span data-stu-id="853fe-200">As you can see, the **BankIBAN** element is configured to use the **remove not alphanumeric** transformation.</span></span>

4. <span data-ttu-id="853fe-201">Välj fliken **Omvandlingar**.</span><span class="sxs-lookup"><span data-stu-id="853fe-201">Select the **Transformations** tab.</span></span>

    ![Fliken omvandlingar för BankIBAN-elementet](./media/er-data-debugger-transformation.png)

    <span data-ttu-id="853fe-203">Som du ser konfigureras omvandlingen **ta bort icke alfanumeriska** att använda ett uttryck som avkortar blanksteg från den angivna textsträngen.</span><span class="sxs-lookup"><span data-stu-id="853fe-203">As you can see, the **remove not alphanumeric** transformation is configured to use an expression that truncates spaces from the text string that is provided.</span></span>

## <a name="start-to-debug-in-the-operation-designer"></a><span data-ttu-id="853fe-204">Starta felsökning i åtgärdsdesigner</span><span class="sxs-lookup"><span data-stu-id="853fe-204">Start to debug in the Operation designer</span></span>

<span data-ttu-id="853fe-205">När du konfigurerar en utkastversion av ER-format som kan köras direkt från åtgärdsdesignern, kan du öppna felsökningen för datakälla genom att välja **Starta felsökning** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="853fe-205">When you configure a draft version of the ER format that can be run directly from the Operation designer, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Knappen Starta felsökning på sidan formatdesigner](./media/er-data-debugger-run-from-designer.png)

<span data-ttu-id="853fe-207">Formatmappning och formatkomponenter för ER-formatet som redigeras är tillgängliga för felsökning.</span><span class="sxs-lookup"><span data-stu-id="853fe-207">The format mapping and format components of the ER format that is being edited are available for debugging.</span></span>

## <a name="start-to-debug-in-the-model-mapping-designer"></a><span data-ttu-id="853fe-208">Starta felsökning i modellmappningsdesigner</span><span class="sxs-lookup"><span data-stu-id="853fe-208">Start to debug in the Model mapping designer</span></span>

<span data-ttu-id="853fe-209">När du konfigurerar en ER-modellmappning som kan köras från sidan **Modellmappning** kan du öppna felsökning för datakälla genom att välja **Starta felsökning** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="853fe-209">When you configure an ER model mapping that can be run from the **Model mapping** page, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Knappen Starta felsökning på sidan modellmappningsdesigner](./media/er-data-debugger-run-from-designer-mapping.png)

<span data-ttu-id="853fe-211">Modellmappningskomponenten i ER-mappningen som redigeras är tillgänglig för felsökning.</span><span class="sxs-lookup"><span data-stu-id="853fe-211">The model mapping component of the ER mapping that is being edited is available for debugging.</span></span>

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a><span data-ttu-id="853fe-212">Bilaga 1: Hämta en ER-lösning</span><span class="sxs-lookup"><span data-stu-id="853fe-212">Appendix 1: Get an ER solution</span></span>

### <a name="download-an-er-solution"></a><span data-ttu-id="853fe-213">Hämta en ER-lösning</span><span class="sxs-lookup"><span data-stu-id="853fe-213">Download an ER solution</span></span>

<span data-ttu-id="853fe-214">Om du vill använda en ER-lösning för att generera en elektronisk betalningsfil för en leverantörsbetalning som bearbetas, kan du [hämta](download-electronic-reporting-configuration-lcs.md) ER-betalningsformatet **ISO20022-kreditöverföring** som finns i det delade resursbiblioteket i Microsoft Dynamics Lifecycle Services (LCS) eller i den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="853fe-214">If you want to use an ER solution to generate an electronic payment file for a vendor payment that is processed, you can [download](download-electronic-reporting-configuration-lcs.md) the **ISO20022 Credit transfer** ER payment format that is available from the Shared asset library in Microsoft Dynamics Lifecycle Services (LCS) or from the Global repository.</span></span>

![Importera ER-betalningsformatet på sidan konfigurationsdatabas](./media/er-data-debugger-import-from-repo.png)

<span data-ttu-id="853fe-216">Förutom det valda ER-formatet måste följande [konfigurationer](general-electronic-reporting.md#Configuration) automatiskt importeras till din Microsoft Dynamics 365 Finance-instans som del av ER-lösningen **ISO20022-kreditöverföring**:</span><span class="sxs-lookup"><span data-stu-id="853fe-216">In addition to the selected ER format, the following [configurations](general-electronic-reporting.md#Configuration) must be automatically imported into your Microsoft Dynamics 365 Finance instance as part of the **ISO20022 Credit transfer** ER solution:</span></span>

- <span data-ttu-id="853fe-217">**Betalningsmodell** [ER-datamodellkonfiguration](general-electronic-reporting.md#DataModelComponent)</span><span class="sxs-lookup"><span data-stu-id="853fe-217">**Payment model** [ER data model configuration](general-electronic-reporting.md#DataModelComponent)</span></span>
- <span data-ttu-id="853fe-218">**ISO20022-kreditöverföring** [ER-formatkonfiguration](general-electronic-reporting.md#FormatComponentOutbound)</span><span class="sxs-lookup"><span data-stu-id="853fe-218">**ISO20022 Credit transfer** [ER format configuration](general-electronic-reporting.md#FormatComponentOutbound)</span></span>
- <span data-ttu-id="853fe-219">**Betalningsmodellmappning 1611** [ER-modellmappningskonfiguration](general-electronic-reporting.md#ModelMappingComponent)</span><span class="sxs-lookup"><span data-stu-id="853fe-219">**Payment model mapping 1611** [ER model mapping configuration](general-electronic-reporting.md#ModelMappingComponent)</span></span>
- <span data-ttu-id="853fe-220">**Betalningsmodellmappning till destination ISO20022** ER-modellmappningskonfiguration</span><span class="sxs-lookup"><span data-stu-id="853fe-220">**Payment model mapping to destination ISO20022** ER model mapping configuration</span></span>

<span data-ttu-id="853fe-221">Du hittar dessa konfigurationer på sidan **Konfigurationer** i ER-ramverket (**Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**).</span><span class="sxs-lookup"><span data-stu-id="853fe-221">You can find these configurations on the **Configurations** page of the ER framework (**Organization administration** \> **Electronic reporting** \> **Configurations**).</span></span>

![Importerade konfigurationer på sidan Konfigurationer](./media/er-data-debugger-configurations.png)

<span data-ttu-id="853fe-223">Om några av de tidigare listade konfigurationerna saknas i konfigurationsträdet måste du hämta dem manuellt från LCS delade resursbibliotek på samma sätt som du har hämtat ER-betalningsformatet **ISO20022 kreditöverföring**.</span><span class="sxs-lookup"><span data-stu-id="853fe-223">If any of the previously listed configurations are missing in the configuration tree, you must manually download them from the LCS Shared asset library in the same way that you downloaded the **ISO20022 Credit transfer** ER payment format.</span></span>

### <a name="analyze-the-downloaded-er-solution"></a><span data-ttu-id="853fe-224">Analysera den hämtade ER-lösningen</span><span class="sxs-lookup"><span data-stu-id="853fe-224">Analyze the downloaded ER solution</span></span>

#### <a name="review-the-model-mapping"></a><span data-ttu-id="853fe-225">Granska modellmappningen</span><span class="sxs-lookup"><span data-stu-id="853fe-225">Review the model mapping</span></span>

1. <span data-ttu-id="853fe-226">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="853fe-226">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="853fe-227">Välj **Betalningsmodell** \> **Betalningsmodellmappning 1611**.</span><span class="sxs-lookup"><span data-stu-id="853fe-227">Select **Payment model** \> **Payment model mapping 1611**.</span></span>
3. <span data-ttu-id="853fe-228">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="853fe-228">Select **Designer**.</span></span>
4. <span data-ttu-id="853fe-229">Välj mappningsposten **Betalningsmodellmappning ISO20022 CT**.</span><span class="sxs-lookup"><span data-stu-id="853fe-229">Select the **Payment model mapping ISO20022 CT** mapping record.</span></span>
5. <span data-ttu-id="853fe-230">Välj **Designer** och granska sedan modellmappningen som öppnas.</span><span class="sxs-lookup"><span data-stu-id="853fe-230">Select **Designer**, and then review the model mapping that is opened.</span></span>

    <span data-ttu-id="853fe-231">Observera att fältet **Betalningar** i datamodellen är knutet till datakällan **\$notSentTransactions** som returnerar listan med leverantörsbetalningsrader som bearbetas.</span><span class="sxs-lookup"><span data-stu-id="853fe-231">Notice that the **Payments** field of the data model is bound to the **\$notSentTransactions** data source that returns the list of vendor payment lines that are being processed.</span></span>

    ![Fältet Betalningar på sidan modellmappningsdesigner](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a><span data-ttu-id="853fe-233">Granska formatmappningen</span><span class="sxs-lookup"><span data-stu-id="853fe-233">Review the format mapping</span></span>

1. <span data-ttu-id="853fe-234">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="853fe-234">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="853fe-235">Välj **Betalningsmodell** \> **ISO20022 kreditöverföring**.</span><span class="sxs-lookup"><span data-stu-id="853fe-235">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="853fe-236">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="853fe-236">Select **Designer**.</span></span>
4. <span data-ttu-id="853fe-237">På fliken **Mappning** granskar du formatmappningen som öppnas.</span><span class="sxs-lookup"><span data-stu-id="853fe-237">On the **Mapping** tab, review the format mapping that is opened.</span></span>

    <span data-ttu-id="853fe-238">Observera att elementet **Dokument** \> **CstmrCdtTrfInitn** \> **PmtInf** i **ISO20022CTReports** \> **XMLHeader**-filen är knutet till datakällan **\$PaymentByDebtor** som är konfigurerad för att gruppera poster i datamodellens fält **Betalningar**.</span><span class="sxs-lookup"><span data-stu-id="853fe-238">Notice that the **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** element of the **ISO20022CTReports** \> **XMLHeader** file is bound to the **\$PaymentByDebtor** data source that is configured to group records of the data model's **Payments** field.</span></span>

    ![PmtInf-element på sidan Formatdesigner](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a><span data-ttu-id="853fe-240">Granska formatet</span><span class="sxs-lookup"><span data-stu-id="853fe-240">Review the format</span></span>

1. <span data-ttu-id="853fe-241">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="853fe-241">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="853fe-242">Välj **Betalningsmodell** \> **ISO20022 kreditöverföring**.</span><span class="sxs-lookup"><span data-stu-id="853fe-242">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="853fe-243">Välj **Designer** och granska sedan formatet som öppnas.</span><span class="sxs-lookup"><span data-stu-id="853fe-243">Select **Designer**, and then review the format that is opened.</span></span>

    <span data-ttu-id="853fe-244">Observera att formatelementet under **Dokument** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAccts** \> **ID** \> **IBAN** \> **BankIBAN** har konfigurerats för att ange IBAN-kod för leverantörens konto i betalningsfilen.</span><span class="sxs-lookup"><span data-stu-id="853fe-244">Notice that the format element under **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** is configured to enter the IBAN code of the vendor account in the payment file.</span></span>

    ![BankIBAN-element på sidan Formatdesigner](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a><span data-ttu-id="853fe-246">Bilaga 2: Konfigurera leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="853fe-246">Appendix 2: Configure Accounts payable</span></span>

### <a name="modify-a-vendor-property"></a><span data-ttu-id="853fe-247">Ändra en leverantörsegenskap</span><span class="sxs-lookup"><span data-stu-id="853fe-247">Modify a vendor property</span></span>

1. <span data-ttu-id="853fe-248">Gå till **Leverantörsreskontra** \> **Leverantörer** \> **Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="853fe-248">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="853fe-249">Välj leverantör **DE-01002** och sedan, i åtgärdsfönstret på fliken **Leverantör**, i gruppen **Ställ in** väljer du **Bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="853fe-249">Select vendor **DE-01002**, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="853fe-250">På snabbfliken **Identifiering**, i fältet **IBAN**, <a name="enteredIBANcode"></a>anger du **GB33 BUKB 2020 1555 5555 55**.</span><span class="sxs-lookup"><span data-stu-id="853fe-250">On the **Identification** FastTab, in the **IBAN** field, <a name="enteredIBANcode"></a>enter **GB33 BUKB 2020 1555 5555 55**.</span></span>
4. <span data-ttu-id="853fe-251">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="853fe-251">Select **Save**.</span></span>

![IBAN-fält inställt på sidan Leverantörsbankkonton](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a><span data-ttu-id="853fe-253">Skapa betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="853fe-253">Set up a method of payment</span></span>

1. <span data-ttu-id="853fe-254">Gå till **Leverantörsreskontra** \> **Betalningsinställning** \> **Betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="853fe-254">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="853fe-255">Välj betalningsmetod **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="853fe-255">Select the **SEPA CT** payment method.</span></span>
3. <span data-ttu-id="853fe-256">På snabbfliken **Filformat**, avsnittet **Filformat**, ställer du in alternativet **Allmänt elektroniskt exportformat** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="853fe-256">On the **File formats** FastTab, in the **File formats** section, set the **Generic electronic Export format** option to **Yes**.</span></span>
4. <span data-ttu-id="853fe-257">I fältet **Exportformatkonfiguration** väljer du ER-formatet **ISO20022 kredit överföring**.</span><span class="sxs-lookup"><span data-stu-id="853fe-257">In the **Export format configuration** field, select the **ISO20022 Credit transfer** ER format.</span></span>
5. <span data-ttu-id="853fe-258">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="853fe-258">Select **Save**.</span></span>

![Filformatinställningar på sidan Betalningsmetoder](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a><span data-ttu-id="853fe-260">Lägg till en leverantörsbetalning</span><span class="sxs-lookup"><span data-stu-id="853fe-260">Add a vendor payment</span></span>

1. <span data-ttu-id="853fe-261">Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="853fe-261">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="853fe-262">Lägg till en ny betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="853fe-262">Add a new payment journal.</span></span>
3. <span data-ttu-id="853fe-263">Välj **Rader** och lägg till en ny betalningsrad.</span><span class="sxs-lookup"><span data-stu-id="853fe-263">Select **Lines**, and add a new payment line.</span></span>
4. <span data-ttu-id="853fe-264">I fältet **Konto** väljer du leverantör **DE-01002**.</span><span class="sxs-lookup"><span data-stu-id="853fe-264">In the **Account** field, select vendor **DE-01002**.</span></span>
5. <span data-ttu-id="853fe-265">I fältet **Debit** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="853fe-265">In the **Debit** field, enter a value.</span></span>
6. <span data-ttu-id="853fe-266">I fältet **Betalningsmetod** väljer du **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="853fe-266">In the **Method of payment** field, select **SEPA CT**.</span></span>
7. <span data-ttu-id="853fe-267">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="853fe-267">Select **Save**.</span></span>

![Leverantörsbetalning har lagts till på sidan Leverantörsbetalningar](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a><span data-ttu-id="853fe-269">Bilaga 3: Bearbeta leverantörsbetalningstransaktioner</span><span class="sxs-lookup"><span data-stu-id="853fe-269">Appendix 3: Process a vendor payment</span></span>

1. <span data-ttu-id="853fe-270">Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="853fe-270">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="853fe-271">På sidan **Leverantörsbetalningsjournal** väljer du den betalningsjournal som du skapade tidigare och väljer sedan **Rader**.</span><span class="sxs-lookup"><span data-stu-id="853fe-271">On the **Vendor payment journal** page, select the payment journal that you previously created, and then select **Lines**.</span></span>
3. <span data-ttu-id="853fe-272">Markera betalningsraden och välj **Betalningsstatus** \> **Ingen**.</span><span class="sxs-lookup"><span data-stu-id="853fe-272">Select the payment line, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="853fe-273">Välj **Generera betalningar**.</span><span class="sxs-lookup"><span data-stu-id="853fe-273">Select **Generate payments**.</span></span>
5. <span data-ttu-id="853fe-274">I fältet **Betalningsmetod** väljer du **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="853fe-274">In the **Method of payment** field, select **SEPA CT**.</span></span>
6. <span data-ttu-id="853fe-275">I fältet **Bankkonto** väljer du **DEMF OPER**.</span><span class="sxs-lookup"><span data-stu-id="853fe-275">In the **Bank account** field, select **DEMF OPER**.</span></span>
7. <span data-ttu-id="853fe-276">I dialogrutan **Generera betalningar** väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="853fe-276">In the **Generate payments** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="853fe-277">I dialogrutan **Parametrar för elektronisk rapportering** väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="853fe-277">In the **Electronic report parameters** dialog box, select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]