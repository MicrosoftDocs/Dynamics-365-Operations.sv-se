---
title: Online ekonomisk konsolidering
description: Det här avsnittet beskriver online ekonomiska konsolideringar i redovisning.
author: aprilolson
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: d5848960ec5e30c1356a93ca4cb6545cec9e39de
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716731"
---
# <a name="online-financial-consolidations"></a>Online ekonomisk konsolidering

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver online ekonomiska konsolideringar i redovisning. Innan du läser det här avsnittet bör du läsa avsnittet [finansiell konsolidering och valutaomräkning – översikt](financial-consolidations-currency-translation.md).

När du har slutfört inställningarna kan du ange detaljerna för konsolideringen på sidan **konsolidera [Online]**. När du är klar kan du klicka på **OK** eller **Batch** för att bearbeta konsolideringen.

## <a name="criteria"></a>Kriterier
I fliken **kriterier** på sidan **konsolidera [Online]** kan du definiera kontona, perioder och vilken typ av data som ska konsolideras.

![Fliken Kriterier.](./media/criteria-consolidate-online.png "Fliken Kriterier")

Här följer en förklaring av de olika fälten på den här fliken:

- **Beskrivning** – ange en exakt beskrivning för den period som du konsoliderar.
- **Huvudkonto** – Använd fälten i det här avsnittet om du vill definiera huvudkontona som kommer att bearbetas.

    - **Från** och **Till** – Ange ett intervall med konton som ska bearbetas. Om du lämnar fälten tomma flyttas alla konton från alla företag till konsolideringsföretaget. Om du därför konsoliderar fyra företag och varje företag har olika kontoplaner skapas alla konton från alla fyra företag i det konsoliderade företaget.
    - **Använd konsolideringskonto** – om du ställer in detta alternativ till **Ja** blir fältet **Välj konsolideringskonto från** tillgängligt. I det här fältet väljer du om alla konton ska konsolideras till konsolideringskontot som har angetts på sidan **huvudkonton**, eller om du vill välja kontot från en av konsolideringskontogrupperna.
    - **Konsolideringskontogrupp** – Välj den grupp som ska användas för huvudkontomappningen för konsolideringen.

- **Konsolideringsperioden** – Använd fälten i det här avsnittet om du vill definiera konsolideringsperioden.

    - **Från** och **till** – Ange ett datumintervall för konsolideringen. Om du lämnar dessa fält tomma behandlas konsolideringen för alla perioder som definieras i företagets redovisningskalender. Vi rekommenderar inte att du lämnar dessa fält tomma.
    - **Inkludera faktiska belopp** – Ange det här alternativet till **Ja** för att konsolidera dina faktiska data.
    - **Inkludera budgetbelopp** – Ange det här alternativet till **Ja** för att konsolidera data från budgetregistret.
    - **Återskapa saldon under konsolideringen** – vi rekommenderar inte att du ställer in detta alternativ till **Ja**. Återskapa i stället saldon som separata batch-jobb.

- **Budgetmodeller** – om du har valt att konsolidera budgetdata och använder fälten i det här avsnittet för att definiera budgetmodellerna.

    - **Från** och **Till** – Ange intervallet för de modeller som ska användas.
    - **Budgetkurstyp** – Välj typ av budgetkurs som ska användas för valutaomräkning med budgeterade data.

## <a name="financial-dimensions"></a>Ekonomiska dimensioner
På fliken **ekonomiska dimensioner** definierar du de dimensioner som ska tas med i konsolideringsföretaget. För att välja en dimension anger du fältet **Specifikation** till **Dimension** och definierar sedan fältordningen för dimensionen i konsolideringsföretaget.

![Fliken Ekonomiska dimensioner.](./media/financial-dimensions-cons.png "Fliken Ekonomiska dimensioner")

Oavsett vilken ordning du definierar ska alltid **huvudkonto** vara det första segmentet.

## <a name="legal-entities"></a>Juridiska personer
På fliken **Juridiska personer** definierar du de förtag som ska tas med i konsolideringsföretaget. Du kan också ange ägarskapsprocent av dessa företag. Om du anger mindre än 100 procent ägarskap ska den angivna procentandelen sammanställas med konsolideringsföretaget. För eventuella översättningsskillnader används fältet **Kontotyp för konverteringsdifferenser** för att välja huvudkontot från inställningarna på sidan **Konton för automatiska transaktioner**.

![Fliken Juridiska personer.](./media/legal-entities-cons.png "Fliken Juridiska personer")

![Sidan Konton för automatiska transaktioner.](./media/accounts-for-automatic-cons.png "Sidan Konton för automatiska transaktioner")

## <a name="elimination"></a>Eliminering
På fliken **eliminering** finns det tre alternativ för att bearbeta elimineringar:

- Välj elimineringsregeln och sedan på fliken **Förslagsalternativ** väljer du **Enbart förslag**. Det här alternativet bearbetar elimineringen under konsolideringsprocessen, men bokför inte allt i ett enda steg. Du kan bokföra journalen senare.
- Välj elimineringsregeln och sedan på fliken **Förslagsalternativ** väljer du **Bokför bara**. Det här alternativet bearbetar elimineringen under konsolideringsprocessen och bokför inte allt i ett enda steg.
- Kör ett elimineringsförslag separat från konsolideringsprocessen genom att använda elimineringsjournalen.

![Fliken Eliminering.](./media/elimination-cons-onl.png "Fliken Eliminering")

Mer information om elimineringar finns i [Elimineringsregler](./elimination-rules.md).

## <a name="currency-translation"></a>Valutaregistrering
På fliken **valutaomräkning** definierar du juridisk person, konto och valutakurstyp och kurs. Det finns tre alternativ på fältet **Använd valutakurs från**:

- **Konsolideringsdatum** – datumet för konsolideringen ska användas för att få valutakursen. Kursen motsvarar punkttariff eller månadsslutets kurs. En förhandsgranskning av kursen visas, men du kan inte redigera den.
- **Transaktionsdatum** – datumet för varje transaktion som ska användas för att välja en valutakurs. Det här alternativet används oftast för anläggningstillgångar och kallas ofta historisk kurs. Du kan inte förhandsgranska kursen eftersom det kommer att vara många kurser för olika transaktioner i kontointervallet.
- **Användardefinierad kurs** – När du har valt detta alternativ kan du ange valutakursen som du vill använda. Det här alternativet kan vara användbart för genomsnittliga valutakurser, eller om du konsoliderar mot en fast valutakurs.

![Fliken Valutaregistrering.](./media/currency-translation-cons-online.png "Fliken Valutaregistrering")

## <a name="additional-resources"></a>Ytterligare resurser

Mer information om konsolidering och valutaöversättning finns i det överordnade avsnittet i det här avsnittet [Översikt över ekonomisk konsolidering och valutaomräkning](./financial-consolidations-currency-translation.md).

För information om scenarier där du kan skapa konsoliderade bokslut, se [skapa konsoliderade bokslut](./generating-consolidated-financial-statements.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
