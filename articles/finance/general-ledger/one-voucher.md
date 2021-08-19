---
title: En verifikation
description: En verifikation för redovisningsjournaler (allmän journal, journal för anläggningstillgångar, leverantörsbetalningsjournal och så vidare) låter dig ange flera redovisningsjournaltransaktioner i samband med en enda verifikation.
author: kweekley
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerParameters, AssetProposalDepreciation
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: 08ece85c773538283fa31ed72e8af61e2da03845fbaa4e6b0507a65626bce803
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720536"
---
# <a name="one-voucher"></a>En verifikation

[!include [banner](../includes/banner.md)]


## <a name="what-is-one-voucher"></a>Vad är en verifikation?

Den befintliga funktionaliteten för redovisningsjournaler (allmän journal, journal för anläggningstillgångar, leverantörsbetalningsjournal och så vidare) låter dig ange flera redovisningsjournaltransaktioner (kund, leverantör, anläggningstillgångar, projekt och bank) i samband med en enda verifikation. Microsoft hänvisar till den här funktionen som *En verifikation*. Du kan skapa en enda verifikation med en av följande metoder:

- Ställ in journalnamnet (**Redovisning** \> **Journalinställning** \> **Journalnamn**) så att fältet **Ny verifikation** anges till **Bara ett verifikationsnummer**. Varje rad som du lägger till journalen finns nu på samma verifikation. Därför kan verifikationen anges som en verifikation med flera rader, som ett konto eller motkonto på samma rad, eller en kombination.

    [![Enstaka rad.](./media/same-line.png)](./media/same-line.png)

    > [!IMPORTANT]
    > Definitionen av En verifikation omfattar **inte** fall där journalnamn ställs in som **Bara ett verifikationsnummer**, men användaren anger sedan en verifikation som endast omfattar typer av redovisningskonton. I det här avsnittet betyder En verifikation en enda verifikation som innehåller mer än en leverantör, kund, bank, anläggningstillgångar eller projekt.

- Ange en verifikation med flera rader om det inte finns något motkonto.

    [![Verifikation med flera rader.](./media/Multi-line.png)](./media/Multi-line.png)

- Ange en verifikation där både kontot och motkontot innehåller redovisningsjournal som kontotyp, till exempel **leverantör**/**leverantör**, **kund**/**kund**, **leverantör**/**kund** eller **Bank**/**Bank**.

    [![Verifikation för redovisning.](./media/subledger.png)](./media/subledger.png)

## <a name="issues-with-one-voucher"></a>Problem med en verifikation

Funktionen för en verifikation orsakar problem vid kvittning, beräkning av skatt, återföring av transaktion, avstämning av en redovisningsjournal i redovisningen, ekonomisk rapportering och mycket mer. (Exempelvis finns mer information om problem som kan uppstå under betalningen i [En verifikation med flera kund- eller leverantörsposter](../accounts-payable/single-voucher-multiple-customer-vendor-records.md).) För att fungera och rapportera korrekt kräver dessa processer och rapporter transaktionsdetaljer. Även om vissa fall ändå fungerar korrekt, baserat på organisationens konfiguration, finns ofta problem när flera transaktioner registreras i en verifikation.

Du bokför t.ex. följande verifikation med flera rader.

[![Exempel på en flerradsverifikation.](./media/example.png)](./media/example.png)

Sedan skapar du rapporten **Utgifter per leverantör** i arbetsytan **Ekonomiska insikter**. På den här rapporten grupperas utgiftskontosaldon under leverantörsgrupp och sedan leverantör. När du genererar rapporten kan systemet inte avgöra vilka leverantörsgrupper/leverantörer som påförde kostnaden på 250,00. Eftersom transaktionsdetaljer saknas, antar systemet att hela utgiften på 250,00 uppstod av den första leverantören som finns i verifikationen. Därför visas utgiften på 250,00 som inkluderades i saldot för huvudkonto 600120 under den leverantörsgruppen/leverantören. Det är emellertid troligt att den första leverantören i verifikationen inte är rätt leverantör. Därför är rapporten antagligen felaktig.

[![Utgifter per leverantörsrapport.](./media/expenses.png)](./media/expenses.png)

## <a name="the-future-of-one-voucher"></a>Framtiden för en verifikation

På grund av de problem som kan uppstå när En verifikation används, kommer denna funktion slutligen att avskaffas. Eftersom det finns funktionsluckor som är beroende av den här funktionen kan avskaffandet emellertid inte ske överallt samtidigt. I stället används följande schema:

- **Version våren 2018** – Denna funktion inaktiverades som standard via parametern **Tillåt flera transaktioner i en verifikation** på fliken **Allmänt** på sidan **Redovisningsparametrar**. Du kan emellertid återaktivera funktionen om din organisation har ett scenario som faller inom en av funktionsluckorna som nämns senare i detta ämne.

    - Om ditt affärsscenario inte kräver En verifikation rekommenderar vi att du låter funktionen vara inaktiverad. Microsoft åtgärdar inte ”buggar” i områden som identifierades senare i detta ämne om du använder den fastän en annan lösning finns.
    - Vi rekommenderar att du slutar använda En verifikation för integrering, såvida du inte behöver funktionen för en av de dokumenterade funktionsluckorna.

- **Senare versioner** – Ett flertal affärsbehov kan uppfyllas genom att använda En verifikation. Microsoft måste se till att alla identifierade affärsbehov fortfarande kan uppfyllas i systemet efter att funktionen har avskaffats. Därför måste nya funktioner troligen läggas till för att fylla i funktionella luckor. Microsoft kan inte skapa en specifik lösning eftersom varje funktionslucka är unik och måste utvärderas utifrån verksamhetens krav. Vissa funktionella luckor kommer troligen att ersättas med funktioner som hjälper till att uppfylla särskilda affärsbehov. Andra luckor kan emellertid fyllas genom att man fortsätter att tillåta bokföring i en journal - som när En verifikation används - men förbättrar systemet så att detta kan spåra mer detaljerat efter behov.

När alla funktionella luckor har fyllts i meddelar Microsoft att funktionen kommer att avskaffas. Avskaffandet kommer dock inte att gälla under minst ett år efter det beskedet. Även om Microsoft inte kan ge en uppskattning av när funktionen En verifikation kommer att avskaffas, kommer det troligen att infalla minst två år innan avskrivningen sker. Microsofts policy är att ha minst 12 månaders marginal mellan meddelande av funktionsavskaffning och det faktiska avskaffandet, detta så att kunder och oberoende programvaruleverantörer har tid att reagera på ändringen. En organisation kanske t. ex. behöver uppdatera sina affärsprocesser, entiteter och integrationer.

Avskaffandet av En verifikation är en viktig ändring som kommuniceras allmänt. Som en del av kommunikationen uppdaterar Microsoft detta avsnitt, lägger upp ett bloggpost på Microsoft Dynamics 365 Finance-bloggen, uppdaterar avsnittet "Borttagna eller avskaffade funktioner", kommunicerar ändringen via lämpligt Microsoft-konto, och så vidare.

## <a name="why-use-one-voucher"></a>Varför använda en verifikation?

Utifrån samtal med våra kunder har Microsoft samlat följande lista med scenarier där kunder använder funktionen för en verifikation eller skälen till varför de använder den. Vissa av dessa affärsbehov kan uppfyllas via en verifikation. I många fall kan dock alternativ uppfylla samma affärskrav.

### <a name="scenarios-that-require-one-voucher"></a>Scenarier som kräver en verifikation

Följande scenarier kan endast uppnås genom att använda funktionen för en verifikation. Om din organisation har något av dessa scenarier, måste du aktivera flera transaktioner som ska registreras på en verifikation genom att ändra inställningen av parametern **tillåta flera transaktioner i en verifikation** på sidan **allmänna redovisningsparametrar**. Dessa funktionella luckor fylls med andra funktioner i senare versioner.

> [!Note]
> [I följande scenarier måste fältet **Tillåt flera transaktioner inom en verifikation** anges till Ja på snabbfliken **Allmänt** på sidan **Allmänna huvudboksparametrar**.]

### <a name="post-vendor-or-customer-payments-in-summary-form-to-a-bank-account"></a>Bokför kund- eller leverantörsbetalningar i sammanfattningsformulär till ett bankkonto

**Scenario** En organisation kommunicerar en lista med leverantörer och belopp till dess bank och banken använder den här listan för att betala leverantörerna på organisationens vägnar. Banken skickar summan av betalningarna som ett enda uttag på bankkontot.

Sammanfattning av leverantörsbetalningar stöds endast genom en verifikation. Varje leverantör anges som en separat rad för att underhålla informationen i redovisningsjournal för leverantörsreskontra. Det summerade beloppet för alla betalningar förskjuts dock till en enda linje för bankkontot. Därför visas uttaget som ett enda summerat belopp i bankredovisningen.

**Scenario** En organisation sätter in kundbetalningar, eller banken sätter in kundbetalningar på organisationens vägnar och insättningen visas som en klumpsumma på bankkontot.

Sammanfattning av kundbetalningar stöds vanligtvis genom funktionen för insättning. Om du använder ”bryggning” på betalsättet stöds det här scenariot endast via en verifikation. Kundbetalningarna anges på samma sätt som beskrivs för sammanfattning av leverantörsbetalning.

### <a name="mechanism-to-group-transactions-from-a-business-event"></a>Metod för att gruppera transaktioner från en affärshändelse

**Scenario** En organisation har en enda affärshändelse som utlöser flera transaktioner. Ekonomiavdelningen vill emellertid visa redovisningsposterna tillsammans för bättre granskning.

Om en organisation måste visa redovisningsposter från en affärshändelse tillsammans måste den använda en verifikation. 

### <a name="country-specific-features"></a>Landsspecifika funktioner

**Scenario** Funktionen för SAD (Single Administrative Document) för Polen kräver att en enda verifikation används. Tills ett grupperingsalternativ är tillgängligt för den här funktionen måste du fortsätta att använda funktionen för en verifikation. Det kan finnas ytterligare landsspecifika funktioner som kräver funktionen för en verifikation.

### <a name="customer-prepayment-payment-journal-that-has-taxes-on-multiple-lines"></a>Betalningsjournal för förskottsbetalning som har skatter på flera "rader"”

I det här scenariot är kunder i en verifikation samma kund eftersom transaktionen simulerar raderna i en kundorder. Förskottsbetalningen måste anges i en verifikation eftersom skatteberäkningen måste göras på "raderna" för en betalning som kunden har gjort.

### <a name="customer-reimbursement"></a>Kundåterbetalning

**Scenario** En kund gör en förskottsbetalning för en order och raderna på ordern har olika skatter som måste bokföras för förskottsbetalningen. Kundens förskottsbetalning är en transaktion som simulerar raderna på ordern, så att lämplig skatt kan registreras för beloppet på varje rad.

Om återbetalning av periodisk uppgift körs i kundreskontramodulen, skapas en transaktion för att flytta saldot från en kund till en leverantör. I det här scenariot måste en verifikation användas för att återbetala kunden.

### <a name="fixed-asset-maintenance-catch-up-depreciation-split-asset-calculate-depreciation-on-disposal"></a>Underhåll av anläggningstillgångar: Catch-up-avskrivning, dela tillgång, beräkna avskrivning vid avyttring
Följande transaktioner för anläggningstillgångar kan också skapa flera transaktioner inom en verifikation:

- Ett ytterligare förvärv görs på en tillgång och "catch-up”-avskrivning beräknas.
- En tillgång delas upp.
- En parameter för att beräkna avskrivning vid avyttring aktiveras och sedan avyttras tillgången.
- En tillgångs servicedatum infaller före anskaffningsdatumet. Dörför bokförs en avskrivningsjustering.

> [!Note]
> När du registrerar transaktioner ska du se till att alla transaktionerna gäller för samma anläggningstillgång. Verifikationen bokförs inte om den innehåller fler än en anläggningstillgång, även om fältet **Ny verifikation** anges till bara Ett verifikationsnummer på sidan **Journalnamn** i redovisningen. Om du inkluderar fler än en anläggningstillgång i verifikationen kan meddelandet **Den kan bara finnas en transaktion för anläggningstillgång per verifikation** och du kan inte bokföra verifikationen.  

### <a name="bills-of-exchange-and-promissory-notes"></a> Växlar och skuldsedlar
Växlar och skuldsedlar kräver att en verifikation används eftersom transaktionerna flyttar Kundreskontra/Leverantörsreskontra från ett redovisningskonto till ett annat baserat på betalningens status.

## <a name="scenarios-that-dont-require-one-voucher"></a>Scenarier som inte kräver en verifikation

Följande scenarier kan utföras på annat sätt och bör inte använda funktionen för en verifikation.

### <a name="post-customer-payments-in-summary-form-to-the-bank-account"></a>Bokför kundbetalningar i sammanfattningsformulär till bankkontot

En organisation sätter in kundbetalningar, eller banken sätter in kundbetalningar på organisationens vägnar och insättningen visas som en klumpsumma på bankkontot.

Sammanfattning av kundbetalningar stöds genom insättningsfunktionen när bryggning inte används på betalsättet.

### <a name="netting"></a>Netting

I nettning kvittas saldon för en leverantör och kund mot varandra eftersom leverantören och kunden är samma part. Denna metod minimerar utbyte av pengar mellan företaget och kund-/leverantörsparten.

Nettning kan åstadkommas genom att ange ökningen och minskningen i separata verifikationer och bokföra förskjutningen till ett clearingredovisningskonto.

### <a name="post-in-summary-to-the-general-ledger"></a>Bokföra i sammanfattning i redovisningen

Organisationer vill ofta bokföra i redovisningen i sammanfattningsform för att minimera mängden data. Organisationer kräver dock fortfarande att transaktionsdetaljerna behålls. När bokföringen görs i sammanfattningsform genom en verifikation är transaktionsdetaljerna inte kända och kan inte behållas.

- Eftersom transaktionsdetaljer för närvarande inte kan behållas, rekommenderar vi att organisationen **inte** använder en verifikation för att bokföra i sammanfattningsform.
- När stöd för en verifikation tas bort kan källdokument och redovisningsramar implementeras i journalerna. Dessa ramar kommer sedan att underhålla transaktionsdetaljerna och ge stöd för sammanfattning till redovisningen.


### <a name="settle-multiple-unposted-payments-to-the-same-invoice"></a>Kvitta flera ej bokförda betalningar till samma faktura

Det här scenariot finns vanligtvis i organisationer där användare kan använda flera betalsätt för inköp. I det här scenariot måste organisationen kunna registrera flera ej bokförda betalningar och kvitta dem mot den valda kundfakturan.

En ny funktion lades till i Microsoft Dynamics 365 for Operations version 1611 (november 2016) som tillåter flera ej bokförda betalningar att kvittas mot en enda faktura. +Flera kundbetalningar måste inte längre tas upp i en enda verifikation.

### <a name="import-bank-statement-transactions"></a>Importera transaktioner för bankutdrag

Banker betalar och tar ofta emot betalningar för organisationens räkning och dessa transaktioner bokförs i Finance via en fil som tas emot från banken. Organisationer vill ofta gruppera dessa transaktioner genom att använda bankutdragsnumret i filen. Eftersom varje transaktion visas i detalj på kontoutdraget från banken, krävs ingen sammanfattning i bankredovisningen.

Transaktioner kan grupperas genom att använda andra fält i journal, t.ex. själva journalbatchnumret eller verifikationsnumret.


### <a name="transfer-balances"></a>Överför saldo

En organisation kan behöva överföra ett saldo från en leverantör till en annan leverantör, antingen på grund av fel eller för att en annan leverantör har tagit över ansvaret för skulden. Överföringar av denna typ inträffar även för kontotyper såsom **Kund** och **Bank**.

Saldoöverföringar från ett konto (leverantör, kund, bank och så vidare) till ett annat konto bör göras via separata verifikationer och förskjutningen kan bokföras till clearingredovisningskonto.

### <a name="enter-beginning-balances"></a>Ange ingående saldon.

Organisationer anger ofta ingående saldon för redovisningsjournalkonton (leverantörer, kunder, anläggningstillgångar och så vidare) som en verifikationstransaktion. Ingående saldon för varje redovisningskonto kan anges som separata verifikationer och förskjutningen kan bokföras till clearingredovisningskonto.

### <a name="correct-the-accounting-entry-of-a-posted-customer-or-vendor-document"></a>Korrigera redovisningsposten för ett bokfört kund- eller leverantörsdokument

En organisation kan behöva korrigera redovisningskonto för Kundreskontra eller Leverantörsreskontra för en redovisningspost för en bokförd faktura, men den fakturan kan inte återföras eller korrigeras genom en annan metod.

Om en korrigering måste göras för redovisningskonto för Kundreskontra eller Leverantörsreskontra måste en justering göras direkt på redovisningskontot. Justeringen kan inte göras efter bokföringen via leverantören eller kunden. Den här metoden kräver att justeringen görs under en ”nedtid”, så att redovisningskontot tillfälligt kan tillåta manuell inmatning.

### <a name="the-system-allows-it"></a>”Det är möjligt i systemet”

Organisationer använder ofta funktionen för en verifikation för att systemet låter dem använda det, utan att förstå följderna.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]