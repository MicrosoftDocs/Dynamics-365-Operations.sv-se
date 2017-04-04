---
title: "Ställa in importprocessen för avancerad bankavstämning"
description: "Med hjälp av funktionen Avancerad bankavstämning kan du importera elektroniska bankutdrag och stämma av dem automatiskt mot transaktioner i Microsoft Dynamics 365 for Operations. Den här artikeln innehåller en beskrivning av hur du ställer in importfunktionen för bankutdrag."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eab840b2974f4e9e8cf542c146482ba8e4239079
ms.openlocfilehash: acf7bacf6e95725024ff0a542a059349593d01a0
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Ställa in importprocessen för avancerad bankavstämning

Med hjälp av funktionen Avancerad bankavstämning kan du importera elektroniska bankutdrag och stämma av dem automatiskt mot transaktioner i Microsoft Dynamics 365 for Operations. Den här artikeln innehåller en beskrivning av hur du ställer in importfunktionen för bankutdrag. 

Inställningen för import av bankutdrag varierar beroende på formatet på det elektroniska bankutdraget. Microsoft Dynamics 365 för operationer som stöder tre bankutdragsformat vid leverans: ISO20022, MT940 och BAI2.

## <a name="sample-files"></a>Exempelfiler
Du måste ha filerna som översätter elektroniska bankutdraget från det ursprungliga formatet till ett format som kan använda Dynamics 365 för åtgärder för alla tre format. Du kan hitta nödvändiga resursfiler under noden **Resurser** i programutforskaren i Microsoft Visual Studio. När du har hittat filerna kan du kopiera dem till en enstaka känd plats, så att du enklare kan överföra dem under inställningsprocessen.

| Resursnamn                                           | Filnamn                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_till\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_till\_avstämning\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_till\_sammansatta\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_till\_avstämning\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_till\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_till\_avstämning\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exempel på bankutdragsformat och tekniska layouter
Nedan visas exempel på avancerad avstämning importen layout tekniska definitioner och tre relaterade bankutdragsfiler exempel: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  

| Teknisk layoutdefinition                             | Bankutdragsexempelfil          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |

 

## <a name="set-up-the-import-of-iso20022-bank-statements"></a>Ställa in import av ISO20022-bankutdrag
Först måste du definiera bankutdragets formatbearbetningsgrupp för ISO20022-bankutdrag med hjälp av ramverket för datatabellen.

1.  Gå till **arbetsytor**&gt;**datahantering**.
2.  Click **Import**.
3.  Ange ett namn på formatet såsom **ISO20022**.
4.  Ställ in fältet **Källdataformat ** på **XML-element**.
5.  Ställ in fältet **Enhetsnamn** på **Bankutdrag**.
6.  Om du vill hämta importfilerna klickar du på **Överför** och bläddrar till filen **SampleBankCompositeEntity.xml** som du sparade tidigare och markerar den.
7.  När bankutdragsenheten överförs och mappningen är slutförd ska du klicka på åtgärden **Visa mappning** för enheten.
8.  Bankutdragsenheten är en sammansatt enhet som består av fyra separata enheter. Markera **BankStatementDocumentEntity** i listan och klicka sedan på åtgärden **Visa mappning**.
9.  På fliken **Transformationer**, klicka på **Ny**.
10. För löpnummer 1 klickar du på **Överför fil** och väljer filen **ISO20022XML-to-Reconciliation.xslt** som du sparade tidigare. **Anmärkning:** Dynamics 365 för operationer transformeringsfiler har tagits fram för standardformat. Eftersom banker ofta avviker från det här formatet, kan du behöva uppdatera transformeringsfilen mappa till din bankutdragsformat. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. Click **New**.
12. För löpnummer 2 klickar du på **Överför fil** och väljer filen **BankReconciliation-to-Composite.xslt** som du sparade tidigare.
13. Klicka på **Tillämpa transformeringar**.

När formatbearbetningsgruppen har ställts in är nästa steg att definiera formatregler för ISO20022-bankutdrag.

1.  Gå till **kontanter och bankhantering**&gt;**inställningar**&gt;**avancerad avstämning bank inställningar**&gt;**bankutdragsformat**.
2.  Click **New**.
3.  Ange ett utdragsformat såsom **ISO20022**.
4.  Ange ett namn på formatet.
5.  Ställ in fältet **Bearbetninggrupp** till den grupp som du definierade tidigare, till exempel **ISO20022**.
6.  Markera kryssrutan **XML-fil**.

Det sista steget är att aktivera Avancerad bankavstämning och att ställa in utdragsformatet på bankkontot.

1.  Gå till **kontanter och bankhantering**&gt;**bankkonton**.
2.  Välj bankkonto och öppna det för att visa detaljerna.
3.  På fliken **Avstämning**, ställ in alternativet **Avancerad bankavstämning** på **Ja**.
4.  Ställ in fältet **Utdragsformat** på det format som du skapade tidigare, till exempel **ISO20022**.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>Ställa in import av MT940-bankutdrag
Först måste du definiera bankutdragets formatbearbetningsgrupp för MT940-bankutdrag med hjälp av ramverket för datatabellen.

1.  Gå till **arbetsytor**&gt;**datahantering**.
2.  Click **Import**.
3.  Ange ett namn på formatet såsom **MT940**.
4.  Ställ in fältet **Källdataformat ** på **XML-element**.
5.  Ställ in fältet **Enhetsnamn** på **Bankutdrag**.
6.  Om du vill hämta importfilerna klickar du på **Överför** och bläddrar sedan till filen **SampleBankCompositeEntity.xml** som du sparade tidigare och markerar den.
7.  När bankutdragsenheten överförs och mappningen är slutförd ska du klicka på åtgärden **Visa mappning** för enheten.
8.  Bankutdragsenheten är en sammansatt enhet som består av fyra separata enheter. Markera **BankStatementDocumentEntity** i listan och klicka sedan på åtgärden **Visa mappning**.
9.  På fliken **Transformationer**, klicka på **Ny**.
10. För löpnummer 1 klickar du på **Överför fil** och väljer filen **MT940TXT-to-MT940XML.xslt** som du sparade tidigare.
11. Klicka på **Ny**.
12. För löpnummer 2 klickar du på **Överför fil** och väljer filen **MT940XML-to-Reconciliation.xslt** som du sparade tidigare. **Anmärkning:** Dynamics 365 för operationer transformeringsfiler har tagits fram för standardformat. Eftersom banker ofta avviker från det här formatet, kan du behöva uppdatera transformeringsfilen mappa till din bankutdragsformat. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. Click **New**.
14. För löpnummer 3 klickar du på **Överför fil** och väljer filen **BankReconciliation-to-Composite.xslt** som du sparade tidigare.
15. Klicka på **Tillämpa transformeringar**.

När formatbearbetningsgruppen har ställts in är nästa steg att definiera formatregler för MT940-bankutdrag.

1.  Gå till **kontanter och bankhantering**&gt;**inställningar**&gt;**avancerad avstämning bank inställningar**&gt;**bankutdragsformat**.
2.  Click **New**.
3.  Ange ett utdragsformat såsom **MT940**.
4.  Ange ett namn på formatet.
5.  Ställ in fältet **Bearbetningsgrupp** till den grupp som du definierade tidigare, till exempel **MT940**.
6.  Ställ in fältet **Filtyp** på **txt**.

Det sista steget är att aktivera Avancerad bankavstämning och att ställa in utdragsformatet på bankkontot.

1.  Gå till **kontanter och bankhantering**&gt;**bankkonton**.
2.  Välj bankkonto och öppna det för att visa detaljerna.
3.  På fliken **Avstämning**, ställ in alternativet **Avancerad bankavstämning** på **Ja**.
4.  När du uppmanas att bekräfta ditt val och aktivera Avancerad bankavstämning klickar du på **OK**.
5.  Ställ in fältet **Utdragsformat** på det format som du skapade tidigare, till exempel **MT940**.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>Ställa in import av BAI2-bankutdrag
Först måste du definiera bankutdragets formatbearbetningsgrupp för BAI2-bankutdrag med hjälp av ramverket för datatabellen.

1.  Gå till **arbetsytor**&gt;**datahantering**.
2.  Click **Import**.
3.  Ange ett namn på formatet såsom **BAI2**.
4.  Ställ in fältet **Källdataformat ** på **XML-element**.
5.  Ställ in fältet **Enhetsnamn** på **Bankutdrag**.
6.  Om du vill hämta importfilerna klickar du på **Överför** och bläddrar sedan till filen **SampleBankCompositeEntity.xml** som du sparade tidigare och markerar den.
7.  När bankutdragsenheten överförs och mappningen är slutförd ska du klicka på åtgärden **Visa mappning** för enheten.
8.  Bankutdragsenheten är en sammansatt enhet som består av fyra separata enheter. Markera **BankStatementDocumentEntity** i listan och klicka sedan på åtgärden **Visa mappning**.
9.  På fliken **Transformationer**, klicka på **Ny**.
10. För löpnummer 1 klickar du på **Överför fil** och väljer filen **BAI2CSV-to-BAI2XML.xslt** som du sparade tidigare.
11. Klicka på **Ny**.
12. För löpnummer 2 klickar du på **Överför fil** och väljer filen **BAI2XML-to-Reconciliation.xslt** som du sparade tidigare. **Anmärkning:** Dynamics 365 för operationer transformeringsfiler har tagits fram för standardformat. Eftersom banker ofta avviker från det här formatet, och du kan behöva uppdatera transformeringsfilen mappa till din bankutdragsformat. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. Click **New**.
14. För löpnummer 3 klickar du på **Överför fil** och väljer filen **BankReconciliation-to-Composite.xslt** som du sparade tidigare.
15. Klicka på **Tillämpa transformeringar**.

När formatbearbetningsgruppen har ställts in är nästa steg att definiera formatregler för BAI2-bankutdrag.

1.  Gå till **kontanter och bankhantering**&gt;**inställningar**&gt;**avancerad avstämning bank inställningar**&gt;**bankutdragsformat**.
2.  Click **New**.
3.  Ange ett utdragsformat såsom **BAI2**.
4.  Ange ett namn på formatet.
5.  Ställ in fältet **Bearbetningsgrupp** till den grupp som du definierade tidigare, till exempel **BAI2**.
6.  Ställ in fältet **Filtyp** på **txt**.

Det sista steget är att aktivera Avancerad bankavstämning och att ställa in utdragsformatet på bankkontot.

1.  Gå till **kontanter och bankhantering**&gt;**bankkonton**.
2.  Välj bankkonto och öppna det för att visa detaljerna.
3.  På fliken **Avstämning**, ställ in alternativet **Avancerad bankavstämning** på **Ja**.
4.  När du uppmanas att bekräfta ditt val och aktivera Avancerad bankavstämning klickar du på **OK**.
5.  Ställ in fältet **Utdragsformat** på det format som du skapade tidigare, till exempel **BAI2**.

## <a name="test-the-bank-statement-import"></a>Testa import av bankutdrag
Det sista steget är att kontrollera att du kan importera bankutdraget.

1.  Gå till **kontanter och bankhantering**&gt;**bankkonton**.
2.  Välj bankkontot som funktionen Avancerad bankavstämning är aktiverad för.
3.  På fliken **Stäm av** klickar du på **Bankutdrag**.
4.  På sidan **Bankutdrag** klickar du på **Importera utdrag**.
5.  Ställ in fältet **Bankkonto** till det valda bankkontot. Fältet **Utdragsformat** ställs in automatiskt, baserat på inställningen för bankkontot.
6.  Klicka på **Bläddra** och välj din elektroniska bankutdragsfil.
7.  Klicka på **Skicka**.
8.  Klicka på **OK**.

Om importen lyckades visas ett meddelande om att utdraget har importerats. Om importen misslyckades kan du söka efter jobbet på arbetsytan **Datahantering** i avsnittet **Jobbhistorik**. Klicka på **Körningsinformation** så att jobbet öppnar sidan **Körningssammanfattning** och klicka sedan på **Visa körningslogg** för att visa importfel.

