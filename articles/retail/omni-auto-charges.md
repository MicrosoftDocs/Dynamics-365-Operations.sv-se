---
title: Avancerade automatiska avgifter för flera kanaler
description: Det här avsnittet beskriver funktionerna för hantering av ytterligare avgifter för beställningar i butikskanal med hjälp av funktioner för avancerade automatiska avgifter.
author: hhaines
manager: annbe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10
ms.openlocfilehash: a980ae9571fb47522d3966dc172b2343641b827e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "345569"
---
# <a name="omni-channel-advanced-auto-charges"></a>Avancerade automatiska avgifter för flera kanaler

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet innehåller information om konfiguration och distribution av funktionen för avancerade automatiska avgifter som är tillgängliga i Dynamics 365 for Retail version 10.0.

När avancerade funktioner för automatiska avgifter är aktiverade stöds order som har skapats i någon Butikskanal (kassa, kundtjänst och online), kan utnyttja den [automatisk debitering](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) konfigurationer som fastställs i ERP-programmet för både huvud- och relaterade avgifter på radnivå.  

I versioner före Dynamics 365 for Retail version 10.0, är konfigurationer av [automatiska avgifter](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) endast tillgängliga för order som har skapats i e-handels- och kundtjänstkanaler. I versioner 10.0 och senare kan kassaskapade order utnyttja konfigurationer av automatiska avgifter. På så sätt kan ytterligare avgifter systematiskt läggas på försäljningstransaktioner.

När du använder versioner före version 10.0 uppmanas POS-användare att manuellt ange en leverans avgift när skapas fartygets ”alla” eller ”skicka valda” POS-transaktionen. När funktionerna för diverse avgifter i programmet används i förhållande till hur avgifterna skrivs till ordern, ges inte någon systematisk beräkning – beräkningen är beroende av användarens indata för att bestämma värdet på avgifterna. Avgifterna endast läggas till som en enda ”leverans”-relaterad kod och enkelt redigeras eller ändras när de har skapats i kassan. 

Manuella anvisningar för att lägga till leveransavgifter används fortfarande i version 10.0 eller senare. Om en organisation inte har aktiverat parametern **avancerade automatiska avgifter** kommer kassauppmaningar om manuell inmatning av avgifter inte att påverkas.

Med funktionen för avancerade automatiska avgifter kan kassaanvändare ha systematiska beräkningar för alla definierade diverse avgifter baserat på inställningstabeller för automatiska avgifter. Dessutom kan har användare möjlighet att lägga till eller redigera en obegränsad mängd ytterligare debiteringar och avgifter till en försäljningstransaktion i kassa i rubrik eller radnivå (för en hämtköp eller kundorder).

## <a name="enabling-advanced-auto-charges"></a>Aktivera avancerade automatiska avgifter

På sidan **Butik \> Administrationsinställning \> Parametrar \> Butiksparametrar**, gå till fliken **kundorder**. På snabbfliken **Avgifter**, ange **Använd avancerade automatiska avgifter** till **Ja**.

![Parametrar för avancerade automatiska avgifter](media/advancedchargesparameter.png)

När avancerad automatiska avgifter aktiveras uppmanas användare att manuellt ange en fraktkostnad vid kassaterminalen när man skapar en leverera alla eller leverera utvalda kundorder. Kassans orderavgifter beräknas systematiskt och läggs till kassatransaktionen (om det finns en motsvarande tabell för automatiska avgifter som matchar kriteriet om ordern som skapats). Användare kan också lägga till eller underhålla sidhuvud eller radnivå tillägg manuellt via tillagda kassaoperationer som kan läggas till kassaskärmens layout.  

När avancerade automatiska tillägg är aktiverade kommer befintliga **butiksparametrar** för **leveransavgiftskod** och **återbetala leveransavgifter** inte längre användas. Dessa parametrar kan endast användas om parametern **Använd avancerade automatiska avgifter** är inställd på **Nej**.

Innan du aktiverar den här funktionen, kontrollera att du har testat och utbildad personal, eftersom detta ändrar affärsprocessflödet för hur frakt och andra avgifter beräknas och läggs till försäljningsorder från kassan. Kontrollera att du förstår effekten av processflödet för att skapa transaktioner från kassan. För kundtjänst och e-handel är effekterna av att aktivera avancerade automatiska tillägg minimal. Kundtjänst och e-handelsprogram fortsätter att ha samma sätt som de tidigare har haft relaterade till register för automatiska avgifter för att beräkna ytterligare avgifter. Användare av kundtjänstkanal kommer även fortsättningsvis ha möjlighet att manuellt redigera beräknade automatiska avgifter på rubrik- eller radnivå eller lägga till ytterligare tillägg manuellt på rubrik- eller radnivå.

## <a name="additional-pos-operations"></a>Ytterligare kassaåtgärder

För att avancerade automatiska avgifter ska fungera korrekt i din kassaapplikationsmiljö, har nya kassaåtgärder lagts till. Dessa åtgärder måste du lägga till dina [kassaskärmlayouter](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) och distribuera till kassaenheter när du distribuerar avancerade automatiska avgifter. Om dessa åtgärder inte läggs till kan användare inte hantera eller underhålla diverse avgifter för kassatransaktioner och har inget sätt att justera eller ändra tilläggsvärden som systematiskt beräknas utifrån konfigurationer av automatiska avgifter. Vi rekommenderar åtminstone att du distribuerar åtgärden **Hantera avgifter** i kassalayouten.

Följande nya åtgärder finns.

- **142 - Hantera avgifter** - Använd följande åtgärd för att kassaanvändare ska kunna visa och redigera tillägg för kassatransaktionen som är läggs till manuellt eller systematiskt genom beräkningar av avgifter.
- **141 - Lägg till huvudavgifter** - Använd denna åtgärd för att ge användaren möjlighet att manuellt lägga till en tilläggsavgift på huvudnivå till en försäljningstransaktion i kassan (och välj avgiftskoden som ska användas).
- **140 - Lägg till radavgifter** - Använd denna åtgärd för att ge användaren möjlighet att manuellt lägga till en tilläggsavgift på radnivå till en försäljningstransaktionsrad i kassan (och välj avgiftskoden som ska användas).
- **143 - beräkna om avgifter** - Använd följande åtgärd för att utföra en fullständig ny beräkning av avgifterna för försäljningstransaktionen. Tidigare överskrivna automatiska avgifter för användare beräknas om utifrån den aktuella vagnkonfigurationen.  

Som med alla kassaoperationer kan säkerhetskonfigurationen kräva godkännande av chef för att utföra operationen.

## <a name="use-case-examples"></a>Använd fallexempel
I det här avsnittet visas exempel på användningsfall som hjälper dig att förstå konfiguration och användning av automatiska avgifter och övriga kostnader i samband med order för butikskanal. De här exemplen visar hur programmet uppför sig när parametern **Använd avancerade automatiska avgifter** har aktiverats.

### <a name="auto-charges-header-charges-example"></a>Exempel på automatiska avgifter för huvudavgifter
#### <a name="use-case-scenario"></a>Använd fallstudie  

En återförsäljare vill automatiskt lägga till avgifter för frakt när transaktioner skapas i någon butikskanal som kräver en leverans av varor till kunden.  Återförsäljaren erbjuder 2 leveransmetoder: mark och luft. Om en kund väljer markleverans och ordervärdet är mindre än $100, vill återförsäljaren debitera kunden en fraktavgift på $10,00. Om kunden väljer markleverans och ordern är över $100 debiteras kunden inte några ytterligare fraktavgifter.  Om kunden väljer flygleveranssätt för alla order, oavsett deras totala värde debiteras en avgift för frakt på $20,00.

#### <a name="setup-and-configuration"></a>Installation och konfiguration

Detta scenario kräver konfiguration av två tabeller för automatiska avgifter.   

Gå till **Kundreskontra \> Ställa in avgifter \> Automatiska avgifter**.  

Konfigurera två olika automatiska avgifter på huvudnivå. Konfigurera en för ”markleverans” och en ”flygleverans”. I det här scenariot kan du konfigurera de som ska användas för ”alla kunder”.  

För markleverans, i radavsnittet på sidan **automatiska avgifter** kan du definiera ett tillägg som ska användas för order mellan $,01- och $100 som $10,00. Skapa en annan avgiftsrad för att ange att order under $100,01 inte har avgifter.

![Exempel på automatiska avgifter](media/headerchargesexample.png)

För luftsleverans, i radavsnittet på formuläret automatiska avgifter kan du definiera ett tillägg på $20,00 som ska användas för alla order (mellan $,01och $9 999 999).

Skicka ändringarna till Retail Server/Channel DB så att kassan kan utnyttja dem genom att köra jobbet **1040 distributionsschema**.

#### <a name="sales-processing-for-this-scenario"></a>Försäljningsbearbetning för det här scenariot

När du är klar med ovanstående konfiguration och ändringarna har tillämpats för databaskanal, alla kundorder eller försäljningstransaktioner som skapats i kassan, kundtjänst eller e-handelskanaler som har mark- eller flygleverans metoderna i huvudnivå ska använda dessa avgifter och tillämpa dem automatiskt på försäljningen.   

Vid denna tidpunkt kommer avgifterna att gälla för alla försäljningstransaktioner som skapats inom den juridiska enheten som använder dessa leveranssätt, eftersom det inte finns någon funktionalitet för att ange att en konfiguration av automatiska avgifter endast gäller en specifik försäljningskanal.

För kassa- och e-handelsscenarier, eftersom det inte finns någon tydligt definierad "huvud" på dessa beställningar gäller avgifter på huvudnivå endast om alla försäljningsrader på transaktionen är inställda att skickas med exakt samma leveranssätt. Om ”blandade sätt” för utförande av transaktioner skapas av kassan eller e-handel beaktas och tillämpas endast automatiska avgifter på radnivå.

I kundtjänstscenarier har användaren kontroll över inställningen för leveransläge vid orderhuvudet. Därför gäller avgifter på huvudnivå för dessa order även om några av försäljningsraderna har konfigurerats för att använda ett annat leveranssätt. Avgifter på huvudnivå för kundtjänstorder kommer alltid att baseras på leveranssättet som definieras vid orderhuvudnivån i försäljningsordern.

### <a name="auto-charges-line-charges-example"></a>Exempel på automatiska avgifter för radavgifter
#### <a name="use-case-scenario"></a>Använd fallstudie 
En återförsäljare vill lägga till en extra avgift för kunden för installationskostnader när kunden köper en viss modell av datorn. Den här datorn kräver ytterligare icke valfria inställningar som återförsäljaren utför för kunden. Återförsäljaren har meddelat kunder att en avgift tas för denna inställning. Återförsäljaren föredrar att hantera avgifter relaterade till denna avgift separat från produktens försäljningspriset för ekonomisk rapportering. En inställningsavgift på $19,99 debiteras kunden när den specifika datorn köps i någon butikskanal.

#### <a name="setup-and-configuration"></a>Installation och konfiguration

Detta scenario kräver konfiguration av tabell för automatiska avgifter på en radnivå.

Gå till **Kundreskontra \> Ställa in avgifter \> Automatiska avgifter**.  

Ange listrutan **nivå** till **rad** och skapa en ny post för automatiska avgifter för alla kunder och för en viss produkt eller produktgrupp där inställningsavgifter tas ut.

![Exempel på automatiska avgifter](media/linechargesexample.png)

Skicka avgifter till Retail Server/Channel DB så att kassan kan utnyttja dem genom att köra jobbet **1040 distributionsschema**.

#### <a name="sales-processing-for-this-scenario"></a>Försäljningsbearbetning för det här scenariot

När du är klar med ovanstående konfiguration och ändringarna har tillämpats för databaskanal, alla kundorder eller försäljningstransaktioner som skapats i kassan, kundtjänst eller e-handelskanaler som har denna post i ordern kommer att utlösa en radnivåavgift som systematiskt läggs till i orderantalet.   

Vid denna tidpunkt kommer avgifterna att gälla för alla försäljningsrader som matchar konfigurationen av automatiska avgifter på radnivå inom juridisk enhet, eftersom det inte finns någon funktionalitet för att konfigurera en automatisk avgift på radnivå för att endast vara tillämplig på en viss försäljningskanal.

### <a name="manual-header-charges-example"></a>Exempel på manuella huvudavgifter
#### <a name="use-case-scenario-description"></a>Beskrivning av att använda fallstudie
En återförsäljare gör undantag från vanliga processer genom att erbjuda en särskild hemleverans av produkter till kunder som beställer produkter i butiken. Återförsäljaren och kunden har kommit överens om att kunden kommer att betala en extra avgift på $25 för den här tjänsten. Ordermottagaren behöver lägga till denna avgift i transaktionen. Eftersom avgiften är avgiftsbelagd och inte hör till en enda produkt i ordern, ska en huvudkostnad användas.

#### <a name="setup-and-configuration"></a>Installation och konfiguration

Kontrollera att avgiftskoden som används i det här scenariot har konfigurerats korrekt genom att gå till **kundreskontra \> inställningar av avgifter \> avgifter** för att definiera en lämplig avgiftskod för scenariot.

![Exempel på avgifter](media/chargesexample.png)

Ange om avgiften ska betraktas som en ”frakt”-relaterad avgift för fraktrelaterade rabatter eller kampanjer, ange **leveransavgift** för avgiftskoden till **Ja**. Om denna avgift också kan återbetalas systematiskt under bearbetningen av en returtransaktion i kassaprogram ställer du in **Återbetalningsbar** till **Ja**. Flaggan **Återbetalningsbar** gäller endast när parameter **Använd avancerade automatiska avgifter** är inställd på **Ja**.   

Skicka avgifter till Retail Server/Channel DB så att kassan kan utnyttja dem genom att köra jobbet **1040 distributionsschema**.

Åtgärden **lägg till huvudavgift** måste konfigureras i din [kassaskärmlayout](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) så att en knapp som är tillgänglig för användaren från kassan kan anropa åtgärden (åtgärd 141).  Skärmens layoutändringar måste distribueras till butikskanalen samt via distributionsplanen. 

#### <a name="sales-processing-of-manual-header-charges"></a>Försäljningsprocesserna för manuella huvudavgifter

Om du vill köra scenariot i kassaprogrammet kommer kassaanvändaren att skapa försäljningstransaktionen som vanligt, lägga till produkter och andra konfigurationer för försäljning. Innan betalningen samlas in ska användaren utföra åtgärden **Lägg till huvudavgift** som uppmanar användaren att välja avgiftskod och ange avgiftsvärdet. När användaren slutför processen läggs avgiften till försäljningsorder som ett tillägg på huvudnivå.  

Proceduren kan tillämpas i kundtjänst genom att använda den befintliga funktionen **avgifter** som finns på fliken **sälja** i verktygsfältet. På sidan **Underhåll avgifter** kan användaren kan lägga till en ny rad i orderrubriken.

### <a name="manual-line-charges-example"></a>Exempel på manuella radavgifter
#### <a name="use-case-scenario"></a>Använd fallstudie
En kund har begärt att 2 av 5 artiklar på deras försäljningsorder ska slås in. Återförsäljaren erbjuder valfria tjänsten till en kostnad av $2,00 per artikel. Ordermottagaren måste lägga till dessa avgifter till de artiklar som behöver slås in.

#### <a name="setup-and-configuration"></a>Installation och konfiguration

Kontrollera att avgiftskoden som används i det här scenariot har konfigurerats korrekt genom att gå till **kundreskontra \> inställningar av avgifter \> avgifter** för att definiera en lämplig avgiftskod för scenariot.

Ange om avgiften ska betraktas som en ”frakt”-relaterad avgift för fraktrelaterade rabatter eller kampanjer, ange **leveransavgift** för avgiftskoden till **Ja**. Om denna avgift också kan återbetalas systematiskt under bearbetningen av en returtransaktion i kassaprogram ställer du in **Återbetalningsbar** till **Ja**. Flaggan **Återbetalningsbar** gäller endast när parameter **Använd avancerade automatiska avgifter** är inställd på **Ja**.  

Skicka avgifter till Retail Server/Channel DB så att kassan kan utnyttja dem genom att köra jobbet **1040 distributionsschema**.

Åtgärden **lägg till radavgift** måste konfigureras i din [kassaskärmlayout](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) så att en knapp som är tillgänglig för användaren från kassan kan anropa åtgärden (åtgärd 140).  Skärmens layoutändringar måste distribueras till butikskanalen samt via distributionsplanen. 

#### <a name="sales-processing-of-the-manual-line-charge"></a>Försäljningsprocesserna för manuella radavgifter

Om du vill köra scenariot i kassaprogrammet kommer kassaanvändaren att skapa försäljningstransaktionen som vanligt, lägga till produkter och andra konfigurationer för försäljning. Innan man tar betalt måste användaren markera den rad som avgiften tillämpas från kassans visning av artikellista och köra åtgärden **lägga till radavgift**. Användaren uppmanas att välja avgiftskod och ange värdet för avgiften. När användaren slutför processen kopplas avgiften till raden och läggs till ordersumman som en avgift på radnivå. Användaren kan upprepa processen för att lägga till ytterligare radavgifter för andra artikelrader i transaktionen om det behövs.

Samma tillvägagångssätt kan användas i kundtjänst med funktionen ”Underhåll avgifter” som du hittar under listrutan **ekonomi** i avsnittet **försäljningsorderrader** på dian **försäljningsorder**.  Då öppnas sidan **Underhåll avgifter** där användaren kan lägga till en ny radspecifik avgift i transaktionen.

## <a name="additional-features"></a>Ytterligare funktioner

### <a name="editing-charges-on-a-pos-sales-transaction"></a>Redigera avgifter i en kassaförsäljningstransaktion

Åtgärden **Hantera tillägg** (142) ska läggas till i [kassaskärmlayout](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) så att en användare kan visa och redigera eller åsidosätta eventuella systemberäknade eller manuellt skapade avgifter på huvud- eller radnivå. Om operationen inte läggs till kommer användaren inte att kunna justera värdet av avgifterna på kassatransaktionen, och inte heller kan de visa information om avgifter såsom typ av avgiftskod kopplad till avgiften.  

På sidan **Hantera avgifter** i kassan kan användaren visa information om avgifter på både huvud- och radnivå. Användaren kan använda **redigera** som är tillgänglig på den här sidan för att ändra det belopp som debiteras en specifik avgiftsrad. När en avgiftsrad läggs till manuellt räknas den inte om systematiskt om inte användaren initierar åtgärden **beräkna om avgifter**.

Om **Orsakskod för åsidosättning av avgift** har konfigurerats på installationssidan **butiksparametrar**, användaren uppmanas att ange en orsakskod när avgifter har ändrats i kassaprogrammet.

Om orsakskoder registrerays för överskrivna avgifter, finns även en ny rapport för att granska dessa åsidosättningar. Rapporten finns i **butik \> förfrågningar och rapporter \> historik för avgiftsåsidosättning**.

### <a name="refunding-charges-on-a-pos-return-transaction"></a>Återbetalning av avgifter för en kassareturtransaktion

Om parametern **Använd avancerade automatiska avgifter** är inställd på **Ja** kommer befintlig butiksparameter för **återbetala leveransavgifter** inte längre gälla. Om du vill ange vilka avgifter som systematiskt återbetalas till en kund vid användning av avancerade automatiska avgifter, kontrollera att relaterade avgiftskoden har konfigurerats som **Återbetalningsbar** på installationssidan **avgiftskod**. Kontrollera att inställningarna har synkroniserats med databaserna för butikskanal via distributionsplan.

### <a name="refunding-charges-on-a-return-order-transaction"></a>Återbetalning av avgifter för en ordertransaktion

Avgifter återbetalas inte systematiskt till **returorder** som skapats i Retail. Användare måste välja alternativet **kopiera avgifter** när de skapar **returorder**. Om **kopiera avgifter** inte är markerat kommer avgifter från den ursprungliga försäljningstransaktionen inte att återbetalas automatiskt. Om **kopiera avgifter** är markerat kopieras alla avgifter till returordern och användaren kan manuellt redigera eller ta bort ändringar som de inte vill ha tillbaka. Returorderprocessen för kundtjänst accepterar för närvarande inte flaggan **Återbetalningsbar** på **Avgiftskod**-inställningen.

### <a name="configuring-pos-receipts-to-show-charges"></a>Konfigurera kassainleveranser för att visa debiteringar

Följande inleverans har lagts till inleveransraden och sidfoten för att stödja funktionen för avancerade automatiska avgifter.

- **Leveransavgifter för rad** - Detta element på radnivå kan användas för att sammanfatta koder för särskilda avgifter som har kopplats till försäljningsraden. Endast avgiftskoder som har flaggats som **leverans**-avgifter på sidan **avgiftskoder** visas här.

- **Övriga avgifter för rad** - Detta element på radnivå kan användas för alla icke leveransspecifika avgiftskoder som har kopplats till försäljningsraden. Dessa är avgiftskoder där flaggan **leverans** på sidan den **avgiftskod** inte har aktiverats.

- **Leveransavgiftsdetaljer för order** - Detta element på sidfotnivå visar beskrivningar av avgiftskoder som gäller för ordern som har flaggats som **leverans** på installationssidan **avgiftskod**.

- **Leveransavgifter för order** - Detta element på sidfotnivå visar belopp för leveransrelaterade avgifter.

- **Övriga leveransavgiftsdetaljer för order** - Detta element på sidfotnivå visar beskrivningar av avgiftskoder som gäller för ordern som inte har flaggats som leveransrelaterade avgifter.

- **Övriga avgifter för order** - Detta element på sidfotnivå visar belopp för andra avgifter som inte är leveransrelaterade.

Det rekommenderas att organisationen även lägger till fritextfält på kvittosidfoten för att definiera områden där avgifter ska sammanfattas. 

### <a name="preventing-charges-from-being-calculated-until-the-pos-order-is-completed"></a>Förhindrar att avgifter beräknas innan kassaordern är klar.

Vissa organisationer föredrar att vänta tills användaren är klar med att lägga till alla försäljningsrader i kassatransaktionen innan de beräknar avgifter. För att undvika beräkning av avgifter när artiklar läggs till i kassatransaktionen, aktiverar du parametern **Manuell beräkning av avgifter** i den **funktionsprofil** som används i butiken. För att aktivera den här parametern måste kassaanvändaren använda åtgärden **beräkna summa** när de är klara med att lägga till produkter i kassatransaktionen. Åtgärden **beräkna summa** utlöser sedan beräkning av eventuella automatiska avgifter för orderrubriken eller rader.
