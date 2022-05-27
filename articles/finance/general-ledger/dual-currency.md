---
title: Dubbel valuta
description: Det här avsnittet innehåller information om dubbel valuta där rapporteringsvalutan används som en andra redovisningsvaluta för Microsoft Dynamics 365 Finance.
author: kweekley
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, Ledger, AssetTransReportingCurrencyAmountsWizard,BankAccountTransReportingCurrencyAmountsWizard, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 04738d2fe88fef5c0e96a39febfec86fab3bee7d
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713597"
---
# <a name="dual-currency"></a>Dubbel valuta

[!include [banner](../includes/banner.md)]

Funktion som infördes i Microsoft Dynamics 365 for Finance and Operations version 8.1 (oktober 2018) gör det möjligt att återanvända rapporteringsvalutan och använda den som en andra redovisningsvaluta. Den här funktionen kallas ibland för *dubbel valuta*. Ändringarna för dubbel valuta kan inte inaktiveras via en konfigurationsnyckel eller parameter. Eftersom rapporteringsvalutan används som en andra redovisningsvaluta, har sättet att beräkna rapporteringsvaluta i bokföringslogiken ändrats.

Dessutom har flera moduler förbättrats för att spåra, rapportera och använda rapporteringsvaluta i olika processer. Modulerna som påverkas är:

- Redovisning 
- Ekonomisk rapportering 
- Leverantörsreskontra
- Kundreskontra 
- Kassa- och bankhantering 
- Anläggningstillgångar 
- Konsolideringar

Efter en uppgradering måste du utföra specifika steg för kassa- och bankhantering och anläggningstillgångar. Därför bör du se till att läsa och förstå relevanta sektioner i det här avsnittet.

## <a name="posting-process"></a>Bokföringsprocess

Bokföringslogiken har ändrats för alla transaktioner som genererar en redovisningspost i redovisningen. Nedan visas hur rapporteringsvaluta tidigare beräknades:

Transaktionsvalutabelopp \> Redovisningsvalutabelopp \> Rapporteringsvalutabelopp

Exempelvis registreras en transaktion i valutan kanadensiska dollar (CAD). CAD-beloppet översätts till redovisningsvalutan som är amerikanska dollar (USD). USD-beloppet översätts sedan till rapporteringsvalutan som är euro (EUR). Därför måste valutakurserna finnas mellan CAD och USD och mellan USD och EUR.

Den nya beräkningen är:

Transaktionsvalutabelopp \> Redovisningsvalutabelopp

Transaktionsvalutabelopp \> Rapporteringsvalutabelopp

På grund a denna ändring måste valutakurserna nu finnas mellan CAD och USD och mellan CAD och EUR.

## <a name="reports-and-inquiries"></a>Rapporter och förfrågningar

Olika rapporter och förfrågningarna visar nu både rapporteringsvalutabeloppen och redovisningsvalutabeloppen. Alla rapporter och begäran har inte uppdaterats. Till exempel har rapporter som visar belopp i transaktionsvalutan inte ändrats.

Ändringarna följer ett av två mönster:

- Om rapporten eller begäran har tillräckligt med utrymme för att visa belopp i både redovisningsvalutan och rapporteringsvalutan, lades rapporteringsvalutabeloppen till.
- Då rapporten eller begäran inte har tillräckligt med utrymme för att visa belopp i båda valutor, lades ett alternativ till så att användarna kan välja vilken valuta som ska visas.

För olika rapporter och förfrågningarna lades även logik till för att ignorera rapporteringsvalutabeloppen om rapporteringsvalutan är samma som redovisningsvalutan eller om rapporteringsvaluta inte definierades i redovisningen för den juridiska personen.

## <a name="financial-journals"></a>Redovisningsjournaler

De ekonomiska journalerna, till exempel redovisningsjournal och leverantörsfakturajournal har uppdaterats så att de innehåller ytterligare information om rapporteringsvalutan. Totalbelopp för verifikationen och journalen visas nu i rapporteringsvalutan. Dessutom visas nu information om rapporteringsvalutans valutakurs på fliken **Allmänt** på journalraderna. Därför kan du åsidosätta den rapporteringsvalutans valutakurs när du registrerar transaktioner.

## <a name="vendor-invoices-sales-orders-and-sales-agreements"></a>Leverantörsfakturor, försäljningsorder och försäljningsavtal
Leverantörsfakturor, försäljningsorder och försäljningsavtal har uppdaterats så att de inkluderar en fast valutakurs för rapporteringsvalutan. Du kan definiera en fast valutakurs för både redovisningsvalutan och rapporteringsvalutan när transaktionsvalutan är olika. När redovisningsvalutan och rapporteringsvalutan är desamma, behålls den fasta valutakursen med redovisningsvalutans fasta tariff som rapport valutans fasta tariff. Den fasta valutakursen för rapporterings valutan kan inte ändras för den här konfigurationen. När bokföringsvalutan och rapporteringsvalutan skiljer sig från kan en fast valutakurs definieras för både bokföringsvaluta och rapporteringsvaluta under transaktionspost. Om rapporteringsvalutan inte har definierats i redovisningen aktiveras inte fältet **Rapporteringsvaluta fast valutakurs** och inget rapporteringsvalutabelopp beräknas.

## <a name="module-changes"></a>Moduländringar

Följande moduler använder rapporteringsvaluta som en andra redovisningsvaluta:

- [Redovisning](#general-ledger)
- [Ekonomisk rapportering](#financial-reporting)
- [Leverantörsreskontra](#accounts-payable-and-accounts-receivable)
- [Kundreskontra](#accounts-payable-and-accounts-receivable)
- [Kassa- och bankhantering](#cash-and-bank-management)
- [Anläggningstillgångar](#fixed-assets)
- [Konsolideringar](#consolidations)

### <a name="general-ledger"></a>Redovisning

Om en rapportvaluta har definierats i redovisningen, kommer redovisningen redan att spåra rapporteringsbeloppen i varje redovisningstransaktion. Dessa belopp konverteras nu från transaktionsvalutabelopp.

Följande ytterligare ändringar har gjorts i modulen **redovisning**:

- En separat valutakurstyp för rapporteringsvalutan kan definieras i redovisningen. Om organisationen inte kan använda en annan valutakurstyp lämnar du fältet för valutakurstypen för rapporteringsvalutan tomt. Alternativt kan du välja samma valutakurstyp som används för redovisningsvalutan. Om du lämnar fältet tomt används valutakurstypen för redovisningsvalutan.
- En ny journal, justeringsjournal för rapporteringsvaluta, möjliggör att justeringar kan bokföras till redovisningskontona endast i rapportvalutan. Denna journal tillåter bokföring endast på redovisningskonton. Den stöder inte koncernintern och valutan måste vara rapporteringsvaluta för den juridiska personen när journalen bokförs. När journalen bokförs är transaktionsvaluta- och redovisningsvalutabeloppen 0 (noll) och rapporteringsvalutabeloppet bokförs med det belopp som registreras på transaktionen. Eftersom sättet som rapporteringsvalutan används i modulerna **Leverantörsreskontra**, **Kundreskontra** och **Anläggningstillgångar** har ändrats, kan den här journalen användas för justeringar efter en uppgradering. För exempel som visar hur du kan använda den här journalen, se avsnitten för dessa moduler.
- Processen för periodallokering har uppdaterats så att den fördelar beloppen i transaktions-, redovisnings- och rapporteringsvalutor. Tidigare fördelades beloppen i transaktions- och redovisningsvalutor och sedan konverterades redovisningsvalutabeloppet till rapporteringsvalutan. Beteendet kan orsaka att ett saldo finns kvar på redovisningskontot i rapporteringsvalutan. Nu när beloppen beräknas och används i redovisningsposten sker ingen konvertering.
- Processen för omvärdering i utländsk valuta har redan omvärderat belopp i rapporteringsvalutan. Men rapporteringsvalutabeloppet beräknas nu med hjälp transaktionsvalutabeloppet, enligt beskrivningen i avsnittet [bokföringsprocess](#posting-process) tidigare i det här avsnittet.
- Många rapporter och förfrågningarna i redovisningen hade redan rapporteringsvalutan, men några hade den inte. Ett exempel är listsida **råbalans**. Den här sidan innehåller kolumner för både redovisningsvalutan och rapporteringsvaluta nu. Observera att kolumnerna för rapporteringsvalutan döljs om redovisningsvalutan och rapporteringsvalutan stämmer överens eller om ingen rapporteringsvaluta har definierats i redovisningen.

### <a name="financial-reporting"></a>Ekonomisk rapportering

En förbättring av modulen **ekonomisk rapportering** låter dig lägga till ett rapporteringsvalutabelopp på ett bokslut på två sätt. Du kan rapportera direkt på rapporteringsvalutabeloppet som bokförs i redovisningen (nya funktioner) på kolumndefinitionen. Alternativt kan fortsätta du att konvertera belopp från redovisningsvalutan till rapporteringsvaluta (befintliga funktioner).

Den här ändringen ingår i inställningen **valutavisning** i kolumndefinitionen. Om du väljer **Rapporteringsvaluta från redovisningen** kommer beloppen i kolumnen inte att konverteras. De rapporteras i stället direkt från redovisningen. Om du vill att kolumnen ska visa konverterade belopp väljer du alternativet **Konvertera till XXXX** där *XXXX* är rapporteringsvalutan som kolumnen ska visa. I det här fallet ska redovisningsvalutabeloppet konverteras till den valda valutan genom att använda den befintliga valutafunktionen.

### <a name="accounts-payable-and-accounts-receivable"></a>Leverantörsreskontra och Kundreskontra

Modulerna **Leverantörsreskontra** och **Kundreskontra** har redan spårat rapporteringsvalutabelopp. Beloppen visas eller används emellertid inte för olika processer. Följande ändringar gjordes:

- Rapporteringsvalutabelopp visas nu på transaktioner för både kunder och leverantörer. Rapporteringsvalutabelopp visas också för det öppna saldot för varje transaktion.
- Föråldringsprocessen har uppdaterats så att företaget kan visa föråldringsgrupper i antingen redovisningsvalutan eller rapporteringsvalutan.
- Olika förfrågningar och rapporter har uppdaterats så att de visar rapporteringsvalutabelopp. Exempel omfattar rapporterna **Avstämning kund mot huvudbok** och **Avstämning från leverantör till huvudbok**.
- Processen för omvärdering i utländsk valuta har redan omvärderat belopp i rapporteringsvalutan. Men rapporteringsvalutabeloppet beräknas nu med hjälp transaktionsvalutabeloppet, enligt beskrivningen i avsnittet [bokföringsprocess](#posting-process).
- **Uppgradera beaktanden:** Före en uppgradering beräknas rapporteringsvalutorna för dokument (fakturor, betalningar osv.) via bokföringsvalutan. Exempelvis en faktura bokförs innan en organisation uppgraderas och fakturan betalas inte. Under uppgraderingen ändras inte fakturans redovisningspost. Efter uppgraderingen gäller emellertid ändringarna för dubbel valuta. Därför när en betalning görs för fakturan, beräknas betalningens valutarapporteringsbelopp nu via transaktionsvalutabeloppet. När betalningen och fakturan kvittas, kan en viss skillnad beräknas i beloppen för realiserad vinst/förlust, eftersom rapporteringsvalutabeloppet nu beräknas på olika sätt. Om skillnaden som beräknas anses som betydande, kan den nya rapporteringsvalutans justeringsjournal användas till att endast justera saldot för realiserad vinst/förlust och huvudbokskonton Leverantörsreskontra/Kundreskontra i rapporteringsvalutan.

### <a name="cash-and-bank-management"></a>Kassa- och bankhantering

Tidigare spårade inte modulen **kontant- och bankhantering** alla belopp i rapporteringsvaluta för transaktioner som bokfördes mot varje bankkonto. Efter en uppgradering spåras rapporteringsvalutabelopp automatiskt för alla nya transaktioner som bokförs. Rapporteringsvalutabelopp måste emellertid läggas till tidigare bokförda transaktioner i redovisningen.

- **Uppgradera beaktanden:** eftersom bankkontotransaktioner inte tidigare spårade rapporteringsvalutabelopp i redovisningen har en guide lagts till så att du kan lägga till rapporteringsvalutabelopp till bankkontotransaktioner. Den här guiden bokför **inte** till redovisningen igen. I stället tar den rapporteringsvalutabelopp från redovisningen och uppdaterar dem i redovisningstabellen.

    - För att starta guiden väljer du **kontant- och bankhantering** \> **inställningar** \> **Lägg till rapporteringsvalutabelopp till bankkontotransaktioner**.
    - Guiden visar transaktioner för alla bankkonton i det aktuella företaget som har ett rapporteringsvalutabeloppet på 0 (noll). Endast transaktioner som bokfördes före uppgraderingen inkluderas.
    - För varje bankkontotransaktion söker guiden motsvarande redovisningsposter i redovisningen och registrerar ett standardbelopp för rapporteringsvaluta. Även om beloppen kan redigeras, rekommenderar vi att du **inte** redigerar dem. Annars kan du inte stämma av bankkontosaldona i huvudboken. Den enda gång du bör redigera ett belopp är om rapporteringsvalutabeloppet inte finns i redovisningen. I sådana fall visar denna guide ett belopp på 0 (noll) för rapporteringsvalutan.
    - Om du väljer **Avbryt** i guiden kommer bankkontotransaktioner och eventuella ändringar i rapporteringsbelopp att sparas tills nästa gång du kör guiden. Emellertid uppdateras inte rapporteringsvalutabelopp på bankkontotransaktionerna. Denna uppdatering sker bara när du markerar **Slutför** i guiden. Du kan köra guiden flera gånger. Därför måste du korrigera eventuella fel rapporteringsvalutabelopp om du gör ett misstag.

- Inga processer i Kassa- och bankhantering har ändrats, men olika rapporter och förfrågningarna har uppdaterats så att de visar rapporteringsvalutabelopp. Rapporter med kassaflödekassaflödesprognoser är ett undantag. De har inte uppdaterats att inkludera rapporteringsvalutabelopp.

### <a name="fixed-assets"></a>Anläggningstillgångar

Tidigare spårade inte modulen **Anläggningstillgångar** alla belopp i rapporteringsvaluta för transaktioner som bokfördes mot varje förteckning över anläggningstillgångar. Efter en uppgradering spåras rapporteringsvalutabelopp automatiskt för alla nya transaktioner som bokförs. Rapporteringsvalutabelopp måste emellertid läggas till tidigare bokförda transaktioner i redovisningen.

Dessutom har större ändringar gjorts i avskrivningsprocessen. Ändringarna kräver åtgärder från användaren efter en uppgradering. Det är viktigt att du läser och förstår följande ändringar även om du ännu inte använder anläggningstillgångar.

- Hur avskrivningsprocessen bestämmer rapporteringsvalutan har ändrats. Följande scenario jämför hur tidigare avskrivning bestämde rapporteringsvalutabeloppet och hur det avgör rapporteringsvalutabeloppet nu.



    **Avskrivningsscenario**

    En tillgång har anskaffats och bokförts med följande belopp. Observera att rapporteringsvalutabeloppet bokförs i redovisningen, men lagras inte i tabellerna redovisningsjournaler för anläggningstillgångar.

    | transaktionstyp | Transaktionsbelopp | Valutakurs | Belopp i redovisningsvaluta | Valutakurs | Rapporteringsvalutabelopp |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Anskaffning      | 1 000 000 DKK      | 2,0           | 500 000 USD                | 2,5           | 200 000 EUR               |

    **Tidigare avskrivning för rapporteringsvalutan**

    Avskrivningsförslaget utförs vid årets slut och beräknar följande värden.

    | transaktionstyp | Transaktionsbelopp | Valutakurs | Belopp i redovisningsvaluta | Valutakurs | Rapporteringsvalutabelopp |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Avskrivning     | 50 000 USD         | 1.0           | 50 000 USD                 | 2,6           | 19 230,77 EUR             |

    När avskrivningsförslaget körs beräknas redovisningsvalutabeloppet med avskrivningsmetoden. Det konverterar sedan detta belopp till rapporteringsvalutan med den aktuella valutakursen mellan USD och EUR. Denna konvertering orsakar problem, eftersom tillgången inte skrivs av helt i rapporteringsvalutan när spotkurs används.

    **Ny avskrivning per enhet i rapporteringsvaluta**

    Avskrivningsprocessen har ändrats så att rapporteringsvalutabeloppet också beräknas med hjälp av avskrivningsmetod. Här följer resultatet när avskrivningen körs på tillgången.

    | transaktionstyp | Transaktionsbelopp | Valutakurs | Belopp i redovisningsvaluta | Valutakurs                                                       | Rapporteringsvalutabelopp |
    |------------------|--------------------|---------------|----------------------------|---------------------------------------------------------------------|---------------------------|
    | Avskrivning     | 50 000 USD         | 1.0           | 50 000 USD                 | 2,5<blockquote>[!NOTE] Även om den här valutakursen visas används den inte för att konvertera till rapporteringsvalutan.</blockquote> | 20 000 EUR                |

    När avskrivningsförslaget körs beräknar den både redovisningsvalutabeloppet och rapporteringsvalutabeloppet med avskrivningsmetoden. Beloppen används sedan i redovisningsposten i redovisningen. Ingen konvertering görs för att fastställa rapporteringsvalutabeloppet.

- **Uppgradera beaktanden:** eftersom transaktioner för förteckning över anläggningstillgångar inte tidigare spårade rapporteringsvalutabelopp i redovisningen har en guide lagts till så att du kan lägga till rapporteringsvalutabelopp till transaktioner för förteckning över anläggningstillgångar. Den här guiden bokför **inte** till redovisningen igen. Eftersom det sätt som avskrivningsförslaget beräknar rapporteringsvalutabelopp har ändrats **måste** guiden köras och slutföras för varje företag innan en organisation kan ange några avskrivningstransaktioner.

    - Om du vill starta guiden väljer du **anläggningstillgångar** \> **inställningar** \> **Lägg till redovisningsvalutabelopp för anläggningstillgångsförteckningar**.
    - Guiden visar transaktioner för alla anläggningstillgångsförteckningar i det aktuella företaget som har ett rapporteringsvalutabeloppet på 0 (noll). Endast transaktioner som bokfördes före uppgraderingen inkluderas.
    - Guiden drar **inte** rapporteringsvalutabelopp från redovisningen. Som beskrevs i det förra fallet använde rapporteringsvalutabelopp som ursprungligen bokfördes i redovisningen spotkurs felaktigt. Dessa belopp skulle inte visas i anläggningstillgångens redovisningsjournal, eftersom nästa avskrivningsberäkning kommer att använda de felaktiga beloppen. I stället hittar guiden valutakursen vid tidpunkten för den första anskaffningen. Sedan används den valutakursen för att rekommendera rapporteringsvalutabelopp som ska bokföras i redovisningsjournalen. Till exempel, här är vad guiden kan visa för det föregående scenariot.

        | Anläggningstillgång | Bok      | transaktionstyp | Transaktionsdatum | Valuta | Belopp i transaktionsvaluta | Tid  | Valutakurs | Rapporteringsvalutabelopp |
        |-------------|-----------|------------------|------------------|----------|--------------------------------|---------|-----------|---------------------------|
        | BUIL-00001  | 200\_SLLT | Anskaffning      | 6/3/2016         | DKK      | 1 000 000                      | 500,000 | 2.5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Avskrivning     | 6/3/2016         | USD      | 50,000                         | 50,000  | 2.5       |  25,000                   |
        | BUIL-00001  | 200\_SLLT | Avskrivning     | 6/3/2016         | USD      | 50,000                         | 50,000  | 2.5       |  25,000                   |
        | BUIL-00001  | 200\_SLLT | Avskrivning     | 6/3/2016         | USD      | 50,000                         | 50,000  | 2.5       |  25,000                   |

    - Många kunder spårade derass transaktionsdetaljer för tillgångar i arbetsböcker. Den här informationen innefattar valutakurser och belopp. Om du har denna data i en arbetsbok kan du skapa en anpassad valutakurstyp och uppdatera den med aktuella valutakurser från arbetsboken. Den här typen av valutakurser används sedan för att ange en standardvalutakurs på anskaffningsdatum och beräkna rapporteringsvalutabeloppen. Om en valutakurstyp inte är vald, använder guiden valutakursen som definierades i huvudboken.
    - Valutakursen och rapporteringsvalutabeloppen kan inte ändras. Om valutakursen ändras beräknas rapporteringsvalutabeloppet om med den nya kursen.
    - Om du väljer **Avbryt** i guiden kommer transaktioner för förteckning över anläggningstillgångar och eventuella ändringar i valutakursen eller rapporteringsbelopp att sparas tills nästa gång du kör guiden. Emellertid uppdateras inte rapporteringsvalutabelopp på transaktioner för förteckning över anläggningstillgångar. Denna uppdatering sker bara när du markerar **Slutför** i guiden. Du kan köra guiden flera gånger. Därför måste du korrigera eventuella fel rapporteringsvalutabelopp om du gör ett misstag.
    - När rapporteringsvalutabeloppen uppdateras helt i redovisningsjournalen **måste** du ange alternativet **Har du uppdaterat alla rapporteringsvalutabelopp i transaktionerna för förteckning över anläggningstillgångar?** till **Ja** och markera **Slutför**. Avskrivningsberäkningar kan inte slutföras förrän du har ställt in **Har du uppdaterat alla rapporteringsvalutabelopp i transaktioner för förteckning över anläggningstillgångar?** till **Ja**. När detta alternativ är inställt på **Ja** är guiden inte längre tillgänglig.
    - Efter att transaktionerna för anläggningstillgångar i redovisningsjournalen har uppdaterats med rapporteringsvalutabelopp matchar beloppen inte de belopp som ursprungligen bokfördes i redovisningsjournalen. Emellertid kan justeringsjournalen för rapporteringsvaluta användas för att uppdatera saldon på avskrivningskontona i redovisningen så att de motsvarar de belopp som ursprungligen bokfördes.
    - En ny enhet **Rapporteringsvalutabelopp för tillgångstransaktion** har lagts till i arbetsytan **Datahantering** som låter dig exportera data från guiden. Du kan sedan använda informationen för att fastställa saldot i anläggningstillgångens redovisningsjournal för avskrivningstransaktionerna. Det saldot kan sedan användas för att fastställa beloppet för rapporteringsvalutajusteringen i redovisningen.

- **Uppgradera övervägan:** nya inställningsfält har lagts till anläggningstillgångar och används i avskrivningsberäkningen. Du kan behöva uppdatera dessa fält innan nästa avskrivningsberäkning.

    - I förteckningen över anläggningstillgångar (**anläggningstillgångar** \> **böcker**) har snabbfliken **allmänna** ett fält för **Anskaffningspris i rapporteringsvaluta**.
    - I förteckningen över anläggningstillgångar (**anläggningstillgångar** \> **böcker**) har snabbfliken **Avskrivning** ett fält för **Förväntat skrotvärde i rapporteringsvaluta**.
    - I anläggningstillgångens parametrar (**anläggningstillgångar** \> **inställningar** \> **parametrar för anläggningstillgångar**), på snabbfliken **allmänna** finns fältet **Lägsta avskrivningsbelopp i rapporteringsvaluta**.
    - I räkenskapsböcker (**anläggningstillgångar** \> **inställningar** \> **räkenskapsböcker**) på snabbfliken **allmänna** finns två nya fält: **Avrunda avskrivning i rapporteringsvaluta** och **Lämna bokfört nettovärde i rapporteringsvaluta**.

- Eftersom avskrivningsförslaget nu beräknar beloppen i både redovisningsvalutan och rapporteringsvaluta har journalen för anläggningstillgångar uppdaterats så att den visar avskrivningsbeloppen i rapporteringsvalutan. För avskrivningstransaktioner är transaktionsvalutan alltid bokföringsvaluta. Därför kan dessa värden fortsätta att visas i kolumnerna **debet** och **kredit**. Två nya kolumner **debet i rapporteringsvaluta** och **kredit i rapporteringsvaluta**, har lagts till i rutnätet.

    - De nya fälten är endast tillgängliga när transaktionstypen är en av de fyra avskrivningstyperna: **Avskrivning**, **Avskrivningsjustering**, **Extraordinär avskrivning**, eller **Särskild avskrivning**.
    - Om transaktionstypen för avskrivning anges i journalen för anläggningstillgångar visas rapporteringsvalutabeloppen i de nya kolumnerna. Dessa belopp kan ändras.
    - Om redovisningsvalutan och rapporteringsvalutan i redovisningen överensstämmer kommer beloppen att synkroniseras. Om du ändrar beloppet **kredit** kommer **kredit i rapporteringsvaluta** att ändras automatiskt så att den matchar.
    - Om alla andra transaktionstyper anges i journalen för anläggningstillgångar kommer beloppen **debet i rapporteringsvaluta** och **kredit i rapporteringsvaluta** aldrig att visas varken före eller efter bokföring. Redovisningsvaluta och rapporteringsvalutabelopp finns kvar i verifikationen som bokförs till redovisningen.
    
### <a name="consolidations"></a>Konsolideringar
    
Funktioner som introducerades i Dynamics 365 Finance version 10.0.5 (oktober 2019) aktiverar funktionalitet via funktionshantering för förbättrad flexibilitet för konsolidering och dubbel valuta. Om du vill aktivera den här funktionen går du till arbetsytan **Funktionshantering** och väljer **Aktivera funktionen dubbel valuta i funktioner för dubbla valutor redovisningskonsolidering**.

I redovisningskonsolidering har ett nytt alternativ lagts till för att konsolidera redovisnings- eller rapportvalutabeloppen från källföretagen. Om redovisnings- eller rapporteringsvalutan är samma som redovisnings- eller rapporteringsvalutan i konsolideringsföretaget kopieras beloppen direkt i stället för översatt.

-  Du kan nu välja om redovisningsvalutan eller rapportvalutan från källföretaget ska användas som transaktionsvaluta i konsolideringsföretaget.

- Redovisnings- eller rapportvalutabeloppen från källföretaget kopieras direkt till redovisnings- eller rapporteringsvalutabeloppen i konsolideringsföretaget om någon av valutorna är samma. Redovisnings- och rapportvalutabeloppen i konsolideringsföretaget beräknas med valutakursen om ingen av valutorna är samma.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
