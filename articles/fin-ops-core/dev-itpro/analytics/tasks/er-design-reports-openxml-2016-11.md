---
title: ER Skapa en konfiguration för rapportgenerering i OPENXML-format (november 2016)
description: I detta avsnitt beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en mall för att skapa elektroniska betalningsdokument i OPENXML-format.
author: NickSelin
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea5b17873dea4508230f39ffb41a50e2f427584f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142142"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER Skapa en konfiguration för rapportgenerering i OPENXML-format (november 2016)

[!include [banner](../../includes/banner.md)]

I detta avsnitt beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en mall för att skapa elektroniska betalningsdokument i OPENXML-format. Denna konfiguration kommer att användas för att bearbeta leverantörsbetalningar.

I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i GBSI-företag.

För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”. Du måste även ha en Excel-fil som ska importeras, när du skapar mallen. Den här filen kan nås från [Mall för betalningsrapport](https://go.microsoft.com/fwlink/?linkid=862266).


## <a name="upload-the-payments-data-model-configuration"></a>Överför konfigurationen för betalningdatamodellen
1. I navigeringsfönstret, gå till **Moduler > Organisationsadministration > Arbetsytor > Elektronisk rapportering**.
2. I listan väljer du konfigurationsleverantören för exempelföretaget Litware, Inc. Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren [Skapa en konfigurationsleverantör och välj den som aktiv](er-configuration-provider-mark-it-active-2016-11.md).
3. Ställ in **Ange aktiva**.
4. Välj **Databaser**. Välj en databas för resurstypen Verksamhetsresurs, om det är tillämpligt. Om detta är tillgängligt hoppar du över stegen om att skapa en ny databas.  
5. Välj **Lägg till** för att öppna dialogrutan.
6. I fältet **Typ av konfigurationsdatabas**, ange `Operations resourcesdd`.
7. Välj **Skapa databas**.
8. Välj **OK**.
9. Välj **Öppen**.
10. Välj **Betalningsmodell** i trädet.
11. Välj **Importera**. Importera den här datamodell. Den används som en datakälla i en ny formatkonfiguration. Hoppa över detta steg om den här konfigurationen redan har importerats.  
12. Välj **Ja**.
13. Stäng sidorna tills du kommer tillbaka till sidan Elektronisk rapportering.

## <a name="create-a-new-format-configuration"></a>Skapa en ny formatkonfiguration
1. Välj **rapporteringskonfigurationer**.
2. Välj **Betalningsmodell** i trädet.
3. Välj **Skapa konfiguration** om du vill öppna dialogrutan.
4. I fältet **Nytt** anger du `Format based on data model PaymentModel`. Skapa ett format som baseras på datamodellen PaymentModel.
5. I fältet **Namn** skriver du `Sample worksheet report`. Rapport över exempelkalkylblad  
6. I fältet **Beskrivning** skriver du `Sample worksheet report for vendors' payments`. Rapport över kalkylblad prov för leverantörers betalningar.  
7. I fältet **Definition av datamodell** ange eller välj ett värde. Välj definitionen **CustomerCreditTransferInitiation**.  
8. Välj **Skapa konfiguration**.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Designa ett nytt dokument i OPENXML-kalkylbladformat
1. Välj **Betalningsmodell\rapport över exempelkalkylblad** i trädet.
2. Välj **Designer**.
3. Välj **Import** i åtgärdsfönstret.
4. Välj **Importera från Excel**.
5. Välj **bilagor**. Koppla det befintliga Excel-dokumentet som en mall.  
6. Välj **Ny**.
7. Välj **Fil**. Peka på den befintliga Excel-filen.  
8. Stäng sidan.
9. Ange eller välj ett värde i fältet **Mall**. Välj den bifogade Excel-filen som ska användas som en mall.  
10. Välj **OK**. Observera att ER-formatkomponenter har skapats i designformatet baserat på strukturen i det refererande MS Excel-dokumentet (namngivna intervall).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Skapa en ny datakälla för att beräkna summor per valutakoder
1. Välj fliken **Mappning**.
2. Välj **Lägg till rot** för att öppna dialogrutan.
3. Välj **Funktioner\gruppera efter** i trädet.
4. I fältet **Namn** skriver du `PaymentByCurrency`.
5. Välj **Redigera grupp efter**.
6. I trädet expanderar du **modell** och väljer **modell\Betalningar**.
7. Välj **Lägg till fält i**.
8. Välj **Vad ska grupperas**.
9. I trädet expanderar du **modell\Betalningar** och väljer **modell\Betalningar\Valuta**.
10. Välj **Lägg till fält i**.
11. Välj **Grupperade fält**.
12. Välj **modell\Betalningar\Instruerat belopp(InstructedAmount)** i trädet.
13. Välj **Lägg till fält i** och välj **Sammansättningsfält**.
14. Markera ett alternativ i fältet **Metod**. Välj den **sammansatta funktionen SUMMA**.  
15. I fältet **Namn** skriver du `TotalInstructuredAmount`.
16. Välj **Spara**.
17. Stäng sidan.
18. Välj **OK**.

## <a name="map-format-components-to-data-sources"></a>Mappa formatkomponenter till datakällor
1. Expandera **modell\Betalningar\Initierande part(InitiatingParty)\Namn** och **Excel\Rapporthuvud\Företagsnamn** i trädet.
2. Välj **bind**.
3. Välj **modell\Betalningar\Betalningsmottagare\Identifiering\Käll-ID(SourceID)** och **Excel\Betalningsrader\LevKontonamn** i trädet.
4. Välj **bind**.
5. Välj **modell\Betalningar\Betalningsmottagare\Namn** och **Excel\Betalningsrader\Leverantörsnamn** i trädet.
6. Välj **bind**.
7. Välj **modell\Betalningar\Betalningsmottagaragent(CreditorAgent)\Namn** och **Excel\Betalningsrader\Bank** i trädet.
8. Välj **bind**.
9. Välj **modell\Betalningar\Betalningsmottagaragent(CreditorAgent)\Organisationsnummer(RoutingNumber)** och **Excel\Betalningsrader\Orgnummer** i trädet.
10. Välj **bind**.
11. Välj **modell\Betalningar\Betalningsmottagares konto(CreditorAccount)\Identifiering\Nummer** och **Excel\Betalningsrader\Kontonummer** i trädet.
12. Välj **bind**.
13. Välj **modell\Betalningar\Instruerat belopp(InstructedAmount)** och **Excel\Betalningsrader\Debet**.
14. Välj **bind**.
15. Välj **modell\Betalningar\Valuta** och **Excel\Betalningsrader\Valuta** i trädet.
16. Välj **bind**.
17. Välj **BetalningEfterValuta\grupperat\Valuta** och **Excel\SammanfattningRader\SammafattningValuta** i trädet.
18. Välj **bind**.
19. Välj **BetalningEfterValuta\samlat\SummaInstrueratBelopp** och **Excel\SammanfattningRader\SammanfattningBelopp** i trädet
20. Välj **bind**.
21. Välj **BetalningEfterValuta** och **Excel\SammanfattningRader** i trädet.
22. Välj **bind**.
23. Välj **modell\Betalningar** och **Excel\Betalningsrader** i trädet.
24. Välj **bind**.
25. Välj **Spara** och stäng sedan sidan.

## <a name="use-the-created-configuration-for-payments-processing"></a>Använd den skapade konfigurationen för bearbetning av betalningar
1. Välj **Ändra status**.
2. Välj **Slutför**.
3. Välj **OK**.
4. I navigeringsfönstret, gå till **Moduler > Leverantörsreskontra > Betalningsinställning > Betalningsmetoder**.
5. Använd snabbfiltret för att filtrera på fältet **Betalningsmetod** med värdet **Elektroniskt**.
6. Välj **Redigera**.
7. Expandera avsnittet **Filformat**.
8. Välj **Ja** i fältet **Allmän elektronisk rapportering**.
9. Ange eller välj ett värde i fältet **Exportera formatkonfiguration**. Välj konfigurationen **Rapport över exempelkalkylblad**.  
10. Välj **Spara**.
11. Stäng sidan.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Använd den skapade konfigurationen för att testa bearbetning av betalningsjournaler
1. I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Betalningar > Betalningsjournal**.
2. Välj **Ny** för att skapa en ny betalningsjournal.
3. Skriv **VendPay** i fältet **Namn**.
4. Markera **rader**
5. Ange värdena `GB_SI_000001` i fältet **Konto**.
6. Ställ in **Debet** på `1000`.
7. Välj **Ny**.
8. Ange värdena `GB_SI_000005` i fältet **Konto**.
9. Ställ in **Debet** på `2000`.
10. Ange `EUR` i fältet **Valuta**.
11. Ange värdena `GBSI OPER` i fältet **Motkonto**.
12. Skriv `Electronic` i fältet **Betalningsmetod**.
13. Välj **Spara**.
14. Välj **Generera betalningar**.
15. Skriv `Electronic` i fältet **Betalningsmetod**.
16. Skriv `Payments` i fältet **Filnamn**.
17. Skriv `GBSI OPER` i fältet **Bankkonto**.
18. Välj **OK** och välj sedan **OK** igen. Granska det skapade kalkylbladet, inklusive information om betalningsrader samt summan för varje valutakod som används i detta betalningmeddelande.  

