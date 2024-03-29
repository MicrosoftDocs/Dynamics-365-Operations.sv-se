---
title: Ställ in inkasseringar
description: Denna artikel förklarar hur du ställer in samlingsfunktionen.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustCollectionsActivitiesListPage
audience: Application User
ms.reviewer: kfend
ms.custom: 14031
ms.assetid: dcc6da2f-9af5-4f1d-abaa-b72967b66979
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 49f47c48158f833f3d2cc0cad851860e995d3886
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870348"
---
# <a name="set-up-collections"></a>Ställ in inkasseringar

[!include [banner](../includes/banner.md)]

Denna artikel förklarar hur du ställer in samlingsfunktionen. Du måste slutföra vissa inställningssteg när du använder inkassofunktionen. Det finns också några valfria funktioner, inklusive kundpooler och inkassoteam. 

- Definitioner för åldersfördelningsperiod
- Ögonblicksbilder av åldersfördelningen
- Journalnamn
- Orsakskod för avskrivningstransaktioner
- Inkassohandläggare
- Avskrivningskonto
- NSF-information (otillräckliga medel)
- Outlook-inställningar för de som använder sidan **Inkasso**
- E-postadresser

Dessa punkter beskrivs mer detaljerat under resten av den här artikeln. 

## <a name="set-up-aging-period-definitions"></a>Ställ in definitioner för åldersfördelningsperioder

Konfigurera en definition för åldersfördelningsperioder. En definition av åldersfördelningsperioder definierar kolumnerna som visas på listsidorna **Åldersfördelade saldon**, **Inkassoaktiviteter** och **Kravärenden**. Den anger även perioderna som visas på sidan **Inkasso**. Om en kundpool har ställts in, används åldersfördelningsperioddefinitionen för poolen. Om inga pooler har ställts in används den förvalda definitionen av åldersfördelningsperioder som angetts på sidan **Parametrar för kundreskontra**. Om ingen förvald definition av åldersfördelningsperioder har angetts används den första definitionen av åldersfördelningsperioder på sidan **Definitioner för åldersfördelningsperiod**.

## <a name="create-an-aging-snapshot"></a>Skapa en ögonblicksbild av åldersfördelning
Skapa ögonblicksbild av åldersfördelningposter för alla kunder eller för kunderna i en kundpool. Information om ögonblicksbilden av åldersfördelning visas på listsidan **Åldersfördelade saldon** och på sidan **Inkasso**. Du måste skapa en ögonblicksbild av åldersfördelning, innan du kan använda listsidan. Listsidan visar bara information för kunder som en ögonblicksbild av åldersfördelning har skapats för.

## <a name="optional-set-up-customer-pools"></a>Valfritt: Ställ in kundpooler
Du kan ställa in kundpooler som representerar kundgrupper. Du kan använda kundpooler som filter för kundinformationen som visas på listsidor av typen **Inkasso**, på sidan **Inkasso** eller när du skapar ögonblicksbilder av åldersfördelning.

## <a name="optional-create-a-collections-team"></a>Du kan även: Skapa en samlingsteam
Om flera personer i din organisation gör samlingsarbete kan du ställa in en samlingsteam. Du kan välja teamet på sidan **Parametrar för kundreskontra**. Om du inte skapar ett inkassoteam skapas ett team automatiskt när du ställer in inkassohandläggare på sidan **Inkassohandläggare**.

## <a name="set-up-a-collections-case-category"></a>Ställa in en samlingsfallkategori
Om du vill ordna inkassoarbetet genom att använda fall kan du ställa in en fallkategori med kategoritypen för **Inkasso**. Detta krävs endast om du vill använda inkassofunktionen på sidan **Inkasso**.

## <a name="set-up-journal-names-settlement-writeoff-and-nsf"></a>Ställa in journalnamn (kvittning, avskrivning och NSF)
Ställ in journalnamnen som används när transaktionerna bearbetas på sidan **Inkasso**. Detta omfattar att kvitta en transaktion, att skriva av en transaktion och att bearbeta en betalning med otillräckliga medel (NSF).

| Beskrivning | Journaltyp     |
|-------------|------------------|
| Bostadsområde  | Kundbetalning |
| Bortskrivning   | Dagligen            |
| NSF         | Kundbetalning |

## <a name="set-up-a-reason-code-for-writeoff-transactions"></a>Ställa in en orsakskod för avskrivningstransaktioner
Ställ in standardanledningskoden som används när transaktioner skrivs av på sidan **Inkasso**. Du kan ändra koden under avskrivningsprocessen.

## <a name="set-up-a-folder-for-email-attachments-and-create-email-templates"></a>Ställa in en mapp för e-postbilagor och skapa e-postmallar
Om du skickar e-postmeddelanden från sidan **Inkasso** som har Microsoft Excel-bilagor kan du skapa valfria e-postmallar för de meddelandena.

## <a name="set-up-accounts-receivable-parameters-for-collections"></a>Ställa in kundreskontraparametrar för samlingar
Ställ in parametrar för kundreskontra som visas på fliken **Inkasso**.

## <a name="optional-set-up-collections-agents"></a>Valfritt: Ställ in inkassohandläggare
Om flera personer i din organisation gör samlingsarbete kan du ställa in samlingsagenter. En inkassohandläggare är en arbetare som har ställts in som en användare på sidan **Användarrelationer**. Du kan tilldela kundpooler (kundfrågor) till inkassohandläggare för att hjälpa dem att ordna sitt arbete. Inkassohandläggarna läggs till i teamet som väljs på sidan **Parametrar för kundreskontra**. Om ett team inte har valts på sidan skapas ett nytt team med namnet **Inkasso** automatiskt och inkassohandläggarna läggs till i det teamet.

## <a name="set-up-a-writeoff-account"></a>Ställ in ett avskrivningkonto
Ställ in avskrivningskontot som används för redovisningsavskrivningsposten när en transaktion skrivs av. Det här kontot lagras i kundbokföringsprofilen.

## <a name="set-up-nsf-information-for-bank-accounts"></a>Ange NSF-information för bankkonton
Uppdatera bankkonton så att de har korrekt journal när NSF-betalningar identifieras på sidan **Inkasso**. På fliken **Valutaledning**, i fältet **NSF-betalningsjournal**, väljer du en betalningsjournal.

## <a name="set-up-outlook-settings-for-users-of-the-collections-page"></a>Ställa in Outlook-inställningar för användare av sidan Inkasso
Innan anställda kan skapa aktiviteter eller skicka e-postmeddelanden med hjälp av sidan **Inkasso** måste du verifiera att konfigurationsnyckeln **Microsoft Outlook-synkronisering** har valts och att Outlook-synkronisering har ställts in för dessa arbetare.

## <a name="set-up-email-and-addresses"></a>Ställa in e-post och adresser
Du kan använda e-post för att kommunicera med både kunder och säljare om inkassoproblem för att skicka e-postmeddelanden från sidan **Inkasso**. 

### <a name="set-up-email-and-address-settings-for-collections-customer-contacts"></a>Ställ in inställningar för e-post och adress frö samlingskundkontakter
Ställ in e-postadresser för kundkontakter om du vill skicka e-postmeddelanden till dessa kontakter från sidan **Inkasso** . Inkassokontakten används som standardkontakten på sidan **Inkasso**. Du kan ställa in en utdragadress för kunden om utdrag ska ha en annan adress än den primära adressen. 

På snabbfliken **Kredit och inkasso** för en kund, i fältet **Kontaktperson vid krav**, väljer du den person i kundorganisationen som arbetar med inkassohandläggaren. Den här personen används som standardkontakt på sidan **Inkasso** och e-postmeddelande skickas till personen. 

> [!NOTE] 
> Om en inkassokontakt inte angetts för en kund används den primära kontakten för kunden. Om en primär kontakt inte anges skickas e-postmeddelanden till den första adressen som är angiven på sidan **Kontakter**.

### <a name="set-up-email-settings-for-salespeople"></a>Ställ in e-postinställningar för försäljare
Ställ in e-postadresser för försäljare om du vill skicka e-postmeddelanden till försäljare från sidan **Inkasso**. Ställ in en e-postadress för var försäljare i varje provisionssäljgrupp. Försäljaren som har alternativet **Kontakt** valt är standardsäljaren som e-postmeddelanden skickas till. 

Om en säljare inte har angetts används den primära säljaren för kundorganisationen. Om en primär försäljare inte anges skickas e-postmeddelanden till den första försäljaren på sidan.


Mer information finns i följande avsnitt:

 - [Skapa in en kravbrevsserie](tasks/create-collection-letter-sequence.md)

 - [Bearbeta kravbrev](tasks/process-collection-letters.md)

 - [Granska inkasseringsinformation](tasks/review-collections-information.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
