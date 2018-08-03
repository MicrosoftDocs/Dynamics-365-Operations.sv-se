---
title: En verifikation
description: "En verifikation för redovisningsjournaler (allmän journal, journal för anläggningstillgångar, leverantörsbetalningsjournal och så vidare) låter dig ange flera redovisningsjournaltransaktioner i samband med en enda verifikation."
author: kweekley
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9f996131830f9bd4efd534143b3fb761c5ccc756
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="one-voucher"></a>En verifikation

[!include [banner](../includes/banner.md)]

> [!NOTE]
>  Den här funktionen blir tillgänglig i Dynamics 365 for Finance and Operations version 8.0, som kommer att vara tillgänglig i versionen som kommer våren 2018.   

<a name="what-is-one-voucher"></a>Vad är ”en verifikation”?
======================

Den befintliga funktionaliteten för redovisningsjournaler (allmän journal, journal för anläggningstillgångar, leverantörsbetalningsjournal och så vidare) låter dig ange flera redovisningsjournaltransaktioner i samband med en enda verifikation. Vi r
efererar till den här funktionen som ”en verifikation” Du kan skapa en verifikation med en av följande metoder:

-   Ställ in journalnamnet (**Redovisning**\>**Journalinställning**\>**Journalnamn**) så att fältet **Ny verifikation** anges till **Bara ett verifikationsnummer**. * Varje rad som du lägger till journalen finns nu på samma verifikation. Eftersom alla rader läggs till samma verifikation, kan verifikationen anges som en verifikation med flera rader, som ett konto eller motkonto på samma rad, eller en kombination.

[![Enstaka rad](./media/same-line.png)](./media/same-line.png)
 
> [!IMPORTANT] 
> *  Observera att definitionen av ”En verifikation" INTE innehåller journalnamn som är inställda som endast **Ett verifikationsnummer** och användaren anger sedan en verifikation som endast omfattar typer av redovisningskonton.  I det här dokumentet betyder "En verifikation" en verifikation som innehåller mer än en leverantör, kund, bank, anläggningstillgångar eller projekt. 

-   Ange en verifikation med flera rader om det inte finns något motkonto.

[![Verifikation med flera rader](./media/Multi-line.png)](./media/Multi-line.png)

-   Ange en verifikation där både kontot och motkontot innehåller redovisningsjournal som kontotyp, till exempel leverantör/leverantör, kund/kund, leverantör/kund eller bank/bank.

[![Redovisningsjournalverifikation](./media/subledger.png)](./media/subledger.png)

<a name="issues-with-one-voucher"></a>Problem med en verifikation
=======================

Funktionen för en verifikation orsakar problem vid kvittning, beräkning av moms, avstämning av en redovisningsjournal i redovisningen, ekonomisk rapportering och mycket mer. (Exempelvis finns mer information om problem som kan uppstå under betalningen i [En verifikation med flera kund- eller leverantörsposter](https://docs.microsoft.com/en-us/dynamics365/unified-operations/financials/accounts-payable/single-voucher-multiple-customer-vendor-records).) För att fungera och rapportera korrekt kräver dessa processer och rapporter transaktionsdetaljer. Även om vissa fall ändå fungerar korrekt, baserat på organisationens konfiguration, finns ofta problem när flera transaktioner registreras i en verifikation.

Du bokför t.ex. följande verifikation med flera rader.

[![Exempel](./media/example.png)](./media/example.png)

Sedan skapar du rapporten **Utgifter per leverantör** i arbetsytan **Ekonomiska insikter**. Rapporten grupperar utgiftskontosaldon under leverantörsgrupp och sedan leverantör. När du genererar rapporten kan systemet inte avgöra vilka leverantörsgrupper/leverantörer som påförde kostnaden på 250,00. Eftersom transaktionsdetaljer saknas, antar systemet att hela 250,00 uppstod av den första leverantören som finns i verifikationen. De 250,00 som inkluderades i saldot för huvudkonto 600120 visas sedan under den leverantörsgruppen/leverantören. Det är troligt att den första leverantören i verifikationen inte är rätt leverantören, så att rapporten blir fel.

[![Utgifter](./media/expenses.png)](./media/expenses.png)

<a name="the-future-of-one-voucher"></a>Framtiden för en verifikation
=========================

På grund av de problem som har angetts tidigare används inte längre funktionen för en verifikation. Men eftersom det finns funktionsluckor som är beroende av den här funktionen kan funktionen inte föråldras samtidigt. I stället använder vi följande schema: 

- **Version våren 2018** - Funktionen inaktiveras som standard via en parameter i redovisningen. Men kan du aktivera funktionen om ditt företag har ett scenario som faller inom luckorna för affärsscenario som nämns senare i detta avsnitt.

  -   Om en kund har ett affärsscenario som inte kräver en verifikation ska funktionen inte aktiveras. Vi åtgärdar inte ”fel” i områden som identifierades senare i det här avsnittet om den här funktionen används även om det finns en annan lösning.

  -   Sluta använda en verifikation för integrering i Microsoft Dynamics 365 Finance and Operations om funktionen krävs för en av de fungerande luckorna.

- **Höst 2018 och senare versioner** – De funktionella luckorna fylls. När funktionella luckor fylls inaktiveras funktionen med en verifikation permanent.

- > [!IMPORTANT]
  > Observera att alternativet **Bara ett verifikationsnummer** inte har tagits bort från journalnamnsinställningen.  Det här alternativet stöds fortfarande när verifikationen endast innehåller typer av redovisningskonton.  Kunder måste vara försiktiga när de använder den här inställningen eftersom verifikationen inte bokförs om de använder **Bara ett verifikationsnummer** utan att ange mer än en kund, leverantör, bank, anläggningstillgångar eller projekt.  Kunder kan fortfarande ange en blandning av typer av redovisningskontotyper för underordnad bok, såsom betalning inom en enda verifikation med kontotyperna för leverantör/bankkonto.  

<a name="why-use-one-voucher"></a>Varför använda en verifikation?
====================

Utifrån samtal med våra kunder har vi samlat följande lista med scenarier där kunder använder funktionen för en verifikation eller skälen till varför de använder den. Vissa av dessa affärsbehov kan uppfyllas via en verifikation. I många fall kan dock alternativ uppfylla samma affärskrav.

<a name="scenarios-that-require-one-voucher"></a>Scenarier som kräver en verifikation
----------------------------------

Följande scenarier kan endast uppnås genom att använda funktionen för en verifikation. Dessa funktionella luckor fylls med andra funktioner i Höst 2018 och senare versioner.

-   **Bokför kund- eller leverantörsbetalningar i sammanfattningsformulär till ett bankkonto**

    -   En organisation kommunicerar en lista med leverantörer och belopp till dess bank och banken använder den här listan för att betala leverantörerna på organisationens vägnar. Banken skickar summan av betalningarna som ett enda uttag på bankkontot.

>   Sammanfattning av leverantörsbetalningar stöds endast genom en verifikation. Varje leverantör anges som en separat rad för att behålla detaljerna i redovisning för leverantörsreskontra men det summerade beloppet för alla betalningar förskjuts till en enda rad för bankkontot. Därför visas uttaget som ett enda summerat belopp i bankredovisningen.

-   En organisation sätter in kundbetalningar, eller banken sätter in kundbetalningar på organisationens vägnar och insättningen visas som en klumpsumma på bankkontot.

>   Sammanfattning av kundbetalningar stöds vanligtvis genom funktionen för insättning. Om du använder ”bryggning” på betalningsmetoden stöds det här scenariot endast via en verifikation. Kundbetalningarna anges på samma sätt som beskrivs för sammanfattning av leverantörsbetalning.

-   **Metod för att gruppera transaktioner från en affärshändelse**

    -   En organisation har en enda affärshändelse som utlöser flera transaktioner. Ekonomiavdelningen vill emellertid visa redovisningsposterna tillsammans för bättre granskning.

>   Om en organisation måste visa redovisningsposter från en affärshändelse tillsammans måste den använda en verifikation. 

- **Landsspecifika funktioner**

  -   Funktionen för SAD (Single Administrative Document) för Polen kräver att en enda verifikation används. Tills ett grupperingsalternativ är tillgängligt för den här funktionen måste du fortsätta att använda funktionen för en verifikation. Det kan finnas ytterligare landsspecifika funktioner som kräver funktionen för en verifikation.

- **Betalningsjournal för förskottsbetalning som har skatter på flera "rader"”**

  -   En kund gör en förskottsbetalning för en order och raderna på ordern har olika skatter som måste bokföras för förskottsbetalningen. Kundens förskottsbetalning är en transaktion som simulerar raderna på ordern, så att lämplig skatt kan registreras för beloppet på varje rad.

I det här scenariot är kunder i en verifikation samma kund eftersom transaktionen simulerar raderna i en kundorder. Förskottsbetalningen måste anges i en verifikation eftersom momsberäkningen måste göras på "raderna" för en betalning som kunden har gjort.

-   **Underhåll av anläggningstillgångar: Catch-up-avskrivning, dela tillgång, beräkna avskrivning vid avyttring**

Följande transaktioner för anläggningstillgångar kan också skapa flera transaktioner inom en verifikation:
-   Ett ytterligare förvärv görs på en tillgång och "catch-up”-avskrivning beräknas.
-   En tillgång delas upp.
-   En parameter för att beräkna avskrivning vid avyttring aktiveras och sedan avyttras tillgången.

<a name="scenarios-that-dont-require-one-voucher"></a>Scenarier som inte kräver en verifikation
----------------------------------------

Följande scenarier kan utföras på annat sätt och bör inte använda en verifikation.

-   **Bokför kundbetalningar i sammanfattningsformulär till bankkontot**

En organisation sätter in kundbetalningar, eller banken sätter in kundbetalningar på organisationens vägnar och insättningen visas som en klumpsumma på bankkontot.

Sammanfattning av kundbetalningar stöds genom insättningsfunktionen när bryggning inte används på betalningsmetoden.

-   **Netting**

I nettning kvittas saldon för en leverantör och kund mot varandra eftersom leverantören och kunden är samma part. Denna metod minimerar utbyte av pengar mellan företaget och kund-/leverantörsparten.

Nettning kan åstadkommas genom att ange ökningen och minskningen i separata verifikationer och bokföra förskjutningen till ett clearingredovisningskonto.

-   **Bokföra i sammanfattning i redovisningen**

Organisationer vill ofta bokföra i redovisningen i sammanfattning för att minimera mängden data. Organisationer kräver dock fortfarande att transaktionsdetaljerna behålls. När bokföringen görs i sammanfattning genom en verifikation är transaktionsdetaljerna inte kända och kan inte behållas.

   -   Eftersom transaktionsdetaljer för närvarande inte kan behållas, rekommenderar vi att en verifikation inte används för att bokföra i sammanfattning.
   -   När stöd för en verifikation tas bort kan vi implementera källdokument och redovisningsramar i journalerna. Dessa ramar kommer sedan att underhålla transaktionsdetaljerna och ge stöd för sammanfattning till redovisningen.

-   **Kvitta flera ej bokförda betalningar till samma faktura**

Det här scenariot finns vanligtvis i butiksorganisationer där användare kan använda flera betalningsmetoder för inköp. I det här scenariot måste organisationen kunna registrera flera ej bokförda betalningar och kvitta dem mot den valda kundfakturan.

En ny funktion lades till i Microsoft Dynamics 365 for Operations version 1611 (November 2016) som tillåter flera ej bokförda betalningar att kvittas mot en enda faktura. +Flera kundbetalningar måste inte längre tas upp i en enda verifikation.

-   **Importera transaktioner för bankutdrag**

Banker betalar och tar ofta emot betalningar för organisationens räkning och dessa transaktioner bokförs i Finance and Operations via en fil som tas emot från banken. Organisationer vill ofta gruppera dessa transaktioner genom att använda bankutdragsnumret i filen. Eftersom varje transaktion visas i detalj på kontoutdraget från banken, krävs ingen sammanfattning i bankredovisningen.

Transaktioner kan grupperas genom att använda andra fält i journal, t.ex. själva journalbatchnumret eller verifikationsnumret.

-   **Överför saldo**

En organisation kan behöva överföra ett saldo från en leverantör till en annan leverantör, antingen på grund av fel eller för att en annan leverantör har tagit över ansvaret för skulden. Överföringar av denna typ inträffar även för kontotyper såsom kunder och bankkonton.

Saldoöverföringar från ett konto (leverantör, kund, bankkonto och så vidare) till ett annat konto bör göras via separata verifikationer och förskjutningen kan bokföras till clearingredovisningskonto.

-   **Ange ingående saldon.**

Organisationer anger ofta ingående saldon för redovisningsjournalkonton (leverantörer, kunder, anläggningstillgångar och så vidare) som en verifikationstransaktion. Ingående saldon för varje redovisningskonto kan anges som separata verifikationer och förskjutningen kan bokföras till clearingredovisningskonto.

-   **Korrigera redovisningsposten för ett bokfört kund- eller leverantörsdokument**

En organisation kan behöva korrigera redovisningskonto för Kundreskontra eller Leverantörsreskontra för en redovisningspost för en bokförd faktura, men den fakturan kan inte återföras eller korrigeras genom en annan metod.

Om en korrigering måste göras för redovisningskonto för Kundreskontra eller Leverantörsreskontra måste en justering göras direkt på redovisningskontot. Justeringen kan inte göras efter bokföringen via leverantören eller kunden. Den här metoden kräver att justeringen görs under en ”nedtid”, så att redovisningskontot tillfälligt kan tillåta manuell inmatning.

-   **”Det är möjligt i systemet”**

Organisationer använder ofta funktionen för en verifikation för att systemet låter dem använda det, utan att förstå följderna.

