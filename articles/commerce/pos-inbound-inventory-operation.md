---
title: Inkommande lageråtgärder i kassan
description: Det här ämnet beskriver möjligheterna i den inkommande lageråtgärden för en kassa (POS).
author: hhaines
manager: annbe
ms.date: 03/12/2020
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
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: b212906dcf037171af264c60720f361215eed599
ms.sourcegitcommit: 437170338c49b61bba58f822f8494095ea1308c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2020
ms.locfileid: "3123909"
---
# <a name="inbound-inventory-operation-in-pos"></a>Inkommande lageråtgärder i kassan

[!include [banner](includes/banner.md)]

I Microsoft Dynamics 365 Commerce version 10.0.10 och senare ersätter inkommande och utgående åtgärder i kassan (POS) åtgärden plockning och inleverans.

> [!NOTE]
> I version 10.0.10 och senare kommer alla nya funktioner i kassaprogrammet som är relaterade till att ta emot butikslager att tas med i inköpsorder och överföringsorder att läggas till i kassaåtgärden **Inkommande åtgärd**. Om du använder åtgärden för plockning och mottagning i kassa rekommenderar vi att du utvecklar en strategi för att flytta från den åtgärden till nya inkommande och utgående åtgärder. Även om åtgärden för plockning och mottagning inte tas bort från produkten, finns det inga ytterligare investeringar i den, från ett funktionellt eller resultatperspektiv efter version 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Förutsättning: Konfigurera ett asynkront dokumentramverk

Den inkommande åtgärden omfattar prestandaförbättringar som säkerställer att användare med höga kvantiteter av inleverans kan bokföra över många butiker eller företag och stora lagerdokument, kan bearbeta dessa dokument till Commerce-administration utan att uppleva timeout eller misslyckanden. Dessa förbättringar kräver användning av ett asynkront dokumentramverk.

När ett asynkront dokumentramverk används kan du tilldela ändringar i inkommande dokument från kassa till Commerce-administration och sedan flytta vidare till andra uppgifter medan behandlingen till Commerce-administration sker i bakgrunden. Du kan kontrollera statusen för dokumentet via dokumentlistsidan **inkommande åtgärd** i kassan för att säkerställa att bokföringen lyckades. I kassaprogrammet kan du även använda listan aktiva dokument i inkommande åtgärd för att se alla dokument som inte kunde bokföras i Commerce-administration. Om ett dokument misslyckas kan kassaanvändare göra korrigeringar till det och sedan försöka bearbeta det till Commerce-administration.

> [!IMPORTANT]
> Det asynkrona dokumentramverket måste konfigureras innan ett företag försöker använda inkommande åtgärd i kassan.

Följ instruktionerna nedan om du vill konfigurera ett asynkront dokumentramverk.

### <a name="create-and-configure-a-number-sequence"></a>Skapa och konfigurera en nummersekvens

1. Gå till **Organisationsadministration \> Nummerserier \> Nummerserier**.
2. På sidan **Nummerserier** skapar du två en nummerserie.
3. I fälten **Nummerseriekod** och **Namn** anger du användardefinierade värden.
4. På snabbfliken **Referenser** väljer du **Lägg till**.
5. I fältet **Område**, välj **Commerce-parametrar**.
4. I fältet **Referens**, välj **Åtgärdsidentifierare för butiksdokument**.
5. På snabbfliken **Allmänt** i avsnittet **Inställningar**, ange alternativet **Kontinuerligt** till **Nej** för att se till att det inte finns några prestandaproblem.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Skapa och tidsplanera två batchjobb för dokumentbearbetning och övervakning av uppgifter

De batchjobb som du skapar kommer att användas för att bearbeta dokument som misslyckas eller timeout. De kommer också att användas när antalet aktiva lagerdokument som bearbetas från kassan överskrider ett systemkonfigurerat värde.

1. Gå till **Systemadministration \> Förfrågningar \> Batchjobb**.
2. På sidan **Batchjobb**, skapa två batchjobb:

    - Konfigurera ett jobb för att köra klassen **RetailDocumentOperationMonitorBatch**.
    - Konfigurera det andra jobbet att köra klassen **RetailDocumentOperationProcessingBatch**.

2. Tidsplanera de nya batchjobben så att de körs återkommande. Ställ t.ex. in schemat så att jobben körs var femte minut.

## <a name="prerequisite-add-inbound-operation-to-the-pos-screen-layout"></a>Förutsättning: Lägg till inkommande operation i kassaskärmlayout

Innan din organisation kan använda funktionen för inkommande åtgärd måste den konfigurera kassaåtgärden **inkommande åtgärd** på en eller flera av dina [kassaskärmlayouter](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Innan du distribuerar den nya operationen i en produktionsmiljö bör du kontrollera att du testar den och träna dina användare att använda den.

## <a name="overview"></a>Översikt

I den inkommande åtgärden utför kassaanvändare följande uppgifter:

- Ta emot lager till butikslager från antingen bekräftade inköpsorderdokument eller levererade överföringsorderdokument.
- Visa information om historiska lagerinleveranser för en period på sju dagar efter att dokumentet har mottagits fullständigt.
- Skapa nya begäran om inkommande överföringsorder.

När den inkommande åtgärden startas från kassaprogrammet visas en listsida. I den här vyn visas öppna inköpsordern och överföringsorderdokument med lagerrader som är schemalagda att inlevereras av den aktuella butiken. För att kunna söka efter ett specifikt dokument kan användarna bläddra i listan eller använda sökfunktionen.

Den inkommande lagerdokumentlistan har tre flikar:

- **Aktiv** – på den här fliken visas dokument som är helt eller delvis öppna och som innehåller rader eller kvantiteter på rader som fortfarande måste inlevereras.
- **Utkast** – på den här fliken visas nya inkommande begäran om överföringsorder som butiken har skapat. Dokumenten har dock endast sparats lokalt. De har inte skickats in till Commerce-administration för bearbetning.
- **Slutförd** – på den här fliken visas en lista över inköpsorder och överföringsorderdokument som butiken har inlevererat under de senaste sju dagarna. Denna flik är endast för informationssyften. All information om dokumenten är skrivskyddade data för butiken.

När du visar dokument på någon av flikarna kan fältet **status** hjälpa dig att förstå vilken fas dokumentet finns i.

- **Utkast** – överföringsorderdokumentet har endast sparats lokalt i butikens kanaldatabas. Ingen information om begäran om överföringsorder har ännu skickats till Commerce-administration.
- **Begärt** – inköpsordern eller överföringsordern har skapats i Commerce-administration och är helt öppen. Inga inleveranser har bearbetats än dokumentet. För dokument av typen inköpsorderdokument kan inleveransen påbörjas när statusen är **begärd**.
- **Delvis levererad** – i överföringsorderdokumentet finns en eller flera rader eller delrad antal som har bokförts som levererade av det avgående lagerstället. Dessa levererade rader är tillgängliga för inleverans via den inkommande operationen.
- **Fullständigt levererad** – överföringsordern har fått alla rader och fullständiga rad antal som har bokförts som levererade av det utgående lagerstället. Hela dokumentet är tillgängligt för inleverans via den inkommande operationen.
- **Delvis inlevererad** – vissa av raderna eller rad kvantiteterna på inköpsordern eller överföringsorderdokumentet har inlevererats emot av butiken, men vissa rader förblir öppna.
- **Helt inlevererat** – alla rader och kvantiteter på inköpsordern eller överföringsorderdokumentet har mottagits i sin helhet. Dokumenten är bara tillgängliga på fliken **Slutför** och är skrivskyddade av butiksanvändarna.
- **Pågår** – denna status används för att informera enhetsanvändare om att dokumentet aktivt bearbetas av en annan användare.
- **Pausad** – den här statusen visas när **Paus mottagning** har valts för att tillfälligt stoppa mottagningsprocessen.
- **Bearbetning i HQ** – dokumentet har skickats till Commerce-administration från kassaprogrammet men har ännu inte bokförts i Commerce-administration. Dokumentet går via den asynkrona bokföringsprocessen för dokument. När dokumentet har bokförts till Commerce-administration ska dess status uppdateras till **helt inlevererat** eller **delvis inlevererat**.
- **Bearbetningen misslyckades** – dokumentet bokfördes i Commerce-administration och avvisades. Fönstret **information** visar orsaken till bokföringsfelet. Dokumentet måste redigeras för att korrigera dataärenden och måste skickas vidare till Commerce-administration för bearbetning.

När du väljer en dokumentrad i listan visas ett **detalj**-fönster. I det här fönstret visas ytterligare information om dokumentet, t.ex. information om leverans och datum. En förloppsindikator visar hur många artiklar som fortfarande måste bearbetas. Om dokumentet inte kunde bearbetas utan problem till Commerce-administration, visar fönstret **Detaljer** också felmeddelanden som hör till felet.

I vyn sida i dokument listan kan du välja **orderdetaljer** i appfältet om du vill visa dokumentinformationen. Du kan också aktivera inleveransbearbetning på kvalificerade dokumentrader.

I vyn sidvisning i dokumentlista kan du också skapa en ny inkommande överföringsorderbegäran för en butik. Dokumentens status är **utkast** och de kan justeras eller raderas tills de skickas till Commerce-administration för bearbetning. När de har skickats till Commerce-administration kan överföringsorderraderna inte längre ändras från kassaprogrammet.

## <a name="receiving-process"></a>Inleveransprocess

När du har valt en inköpsorder eller överföringsorderdokument, på fliken **aktiv** kan du välja **orderdetaljer** för att påbörja inleveransen.

Som standard visas vyn **Inleverera nu**. Den här vyn är optimerad för skanning av streckkoder. Den kan användas för att skapa en lista med de artiklar som har skannats, så att dessa artiklar kan tas emot. För att inleveransen ska inledas kan du börja skanna artikelstreckkoder.

När artikelstreckkoder skannas i vyn **Inleverera nu**, validerar programmet artiklarna mot det valda inköps- eller överföringsorderdokumentet, för att se till att varje skannad artikel matchar en giltig artikel i dokumentet. I vyn **Inleverera nu** antas varje skanning av en streckkod för att representera inleveransen av en kvantitet av en enhet, såvida inte en kvantitet är inbäddad i streckkoden. Du kan söka igenom streckkoder flera gånger i den här vyn när du vill skapa en lista med alla artiklar och kvantiteter för inleveransen.

### <a name="example-scenario"></a>Exempelscenario

En användare tar emot en inköpsorder som innehåller 10 enheter av streckkod 5657900266. Användaren kan skanna den streckkoden 10 gånger för att uppdatera fältet **Inleverera nu** med en enhet per skanning. När användaren har slutfört skanningarna visar fältet **mottagen nu** för artikelraden att en kvantitet på 10 har inlevererats.

Alternativt, i ett scenario där artikelkvantiteten är stor, kan användaren hellre ange kvantiteten manuellt i stället för att skanna streckkoden för varje artikel som inlevereras. I det här fallet kan användaren skanna streckkoden en gång för att lägga till artikeln i listan **Inleverera nu**. Användaren kan sedan välja den kopplade raden i vyn **Inleverera nu** och sedan i fönstret **Detaljer** som visas till höger på sidan, uppdatera fältet **mottagningskvantitet** för artikeln.

Även om vyn **Ta emot nu** är optimerad för skanning av streckkoder kan användarna också välja **Ta emot produkt** i appfältet och ange sedan objekt-ID eller streckkodsdata genom en dialogruta. När artikeln som angetts har validerats uppmanas användaren att ange inleveranskvantiteten.

Vyn **ta emot** nu är ett fokuserat sätt för användarna att se vilka produkter de får. Alternativt kan vyn **fullständig orderlista** användas. I den här vyn visas hela listan över dokumentrader för det valda inköps- eller överföringsorderdokumentet. Användarna kan manuellt välja rader manuellt i listan i fönstret **Detaljer** uppdaterar du fältet **mottagningskvantitet** för den valda raden. I vyn **fullständig orderlista** kan användarna skanna streckkoder, eller använda funktionen **Ta emot produkt** för att ange artikel-ID eller streckkod samt information om Inlevererad kvantitet, utan att först behöva välja den motsvarande artikelraden i listan.

### <a name="over-receiving-validations"></a>Valideringar av övermottagning

Valideringar sker under mottagningsprocessen för dokumentraderna. De inkluderar valideringar för överleverans. Om en användare försöker ta emot mer lager än vad som beställts på en inköpsorder, men antingen överleverans eller den mängd som har inlevererats överskrider den överleveranstolerans som har konfigurerats för inköpsorderraden, får användaren ett felmeddelande och får inte ta emot överskjutande kvantitet.

Övermottagning är inte tillåtet för överföringsorderdokument. Användarna får alltid felmeddelanden om de försöker ta emot fler än vad som levererats för överföringsorderraden.

### <a name="receiving-location-controlled-items"></a>Inleveransplatskontrollerade artiklar

Om artiklarna som ska inlevereras är platsstyrda kan användarna välja den plats som de vill inleverera artiklar från under inleveransprocessen. Vi rekommenderar att du konfigurerar en standardinleveransplats för butikslagret, så att processen blir mer effektiv. Även om en standardplats har konfigurerats kan användarna åsidosätta inleveransplatsen på valda rader när de behövs.

Operationen respekterar konfigurationen **Tom inleverans tillåten** på lagringsdimensionen **Plats** och kräver inte att en platsdimension anges om en tom inleverans har konfigurerats. Om tomma inleveransplatser inte är tillåtna för en artikel, visar kassaprogrammet ett fel och kräver att en plats registreras innan inleveransen kan bokföras.

### <a name="receive-all"></a>Ta emot alla

Som du behöver kan du välja **Inleverera alla** på appfältet för att snabbt uppdatera kvantiteten **inleverans nu** för alla dokumentrader till det maximala värdet som är tillgängligt för att uppfylla för dessa rader.

### <a name="cancel-receiving"></a>Annullera inleverans

Du bör bara använda funktion **Avbryt inleverans** på appfältet endast om du vill säkerhetskopiera dokumentet och inte vill spara några ändringar. Du kan t.ex. från början välja fel dokument och inte vill att tidigare inleveransdata ska sparas.

### <a name="pause-receiving"></a>Pausa mottagande

Om du uppfyller lagermottagning kan du använda funktionen **pausa inleverans** för att pausa uppfyllelse om du vill ta en paus från inleveransen. Du kanske till exempel vill utföra en annan åtgärd från kassa, t.ex. att ringa upp en kundförsäljning, eller att försena bokföringen av inleveransen.

När du väljer **Pausa inleverans** ändras dokumentets status till **Pausa**. Därför vet användaren att data har registrerats i dokumentet, men dokumentet har ännu inte genomförts. När du är redo att återuppta inleveransen markerar du det pausade dokumentet och väljer **orderdetaljer**. Alla kvantiteter **Inleverans nu** kvantiteter som tidigare sparats kommer att behållas och kan ses från **fullständig orderlista**.

### <a name="finish-receiving"></a>Slutför mottagande

När du har fyllt i alla kvantiteter **Inleverans nu** för produkter måste du välja **slutför inleverans** i appfältet för att behandla inleveransen.

När användarna slutför en inköpsorder, ombeds de ange ett värde i fältet **inleveransnummer** om funktionen har konfigurerats. Vanligtvis är detta värde detsamma som ID:t för leverantörens följesedel. Data för **Inleveransnummer** kommer att lagras i Produktinleveransjournal i Commerce-administration. Inleveransnumren hämtas inte för inleveranser av överföringsorder.

När asynkron dokumentbearbetning används skickas kvittot via ett asynkront dokumentramverk. Hur lång tid det tar att bokföra dokumentet beror på dokumentets storlek (antalet rader) och den allmänna bearbetningstrafik som sker på servern. Vanligtvis förekommer denna process på några sekunder. Om dokumentbokföringen misslyckas meddelas användaren via dokument **Ingående operation** där dokumentstatus uppdateras till **bearbetningen misslyckades**. Användaren kan sedan välja det misslyckade dokumentet i kassan för att visa felmeddelandena och orsaken till misslyckandet i fönstret **information**. Ett misslyckat dokument förblir oförändrat och kräver att användaren går tillbaka till dokumentraderna genom att välja **orderdetaljer** i kassan. Användaren måste sedan uppdatera dokumentet med korrigeringar baserat på felen. När ett dokument har korrigerats kan användaren försöka att bearbeta det genom att välja **Slutför** på appfältet.

## <a name="create-an-inbound-transfer-order"></a>Skapa en ingående överföringsorder

Från kassan kan användare skapa nya överföringsorderdokument. Starta processen genom att välja **ny** i appfältet medan du är i huvuddokumentlistan för **ingående operation**. Du uppmanas sedan att välja lagerställe eller butik med **överföring från** som ger lager till din butiksplats. Värdena begränsas till det val som har angetts i konfigurationen för butikens uppfyllelsegrupp. I en begäran om ingående överföringar är den aktuella butiken alltid **överföringen till** lagerstället för överföringsordern. Det går inte att ändra värdet.

Du kan ange värden i fälten **Transportdatum**, **Inleveransdatum** och **Leveransläge** efter behov. Du kan också lägga till en notering som kommer att lagras tillsammans med överföringsorder rubriken, som en bilaga till dokumentet i Commerce-administration.

När informationen i huvudet har skapats kan du lägga till produkter på överföringsordern. Om du vill starta processen med att lägga till artiklar och begärda kvantiteter, välj **Lägg till produkt**. I fönstret **information** kan du också lägga till en orderspecifik notering till journalraderna. Dessa anteckningar sparas som bifogade filer i en rad.

När rader har angetts på den ingående överföringsordern måste du välja **Spara** för att spara dokumentändringarna lokalt eller **skicka begäran** för att skicka orderdetaljerna till Commerce-administration för vidare bearbetning. Om du väljer **spara** sparas utkastdokumentet i kanaldatabasen och det avgående lagerstället kan inte köra dokumentet förrän det har bearbetats via **Skicka in begäran**. Du bör bara **Spara** endast om du inte är redo att genomföra begäran till Commerce-administration för bearbetning.

Om ett dokument sparas lokalt kan du hitta det på fliken **Utkast** på dokumentlistan **inkommande operation**. När dokumentet är i status **utkast** kan du redigera det genom att välja **redigera**. Du kan uppdatera, lägga till eller ta bort rader som du behöver. Du kan också ta bort hela dokumentet när det är i status **utkast** genom att välja **ta bort** på fliken **utkast**.

När utkastet till dokumentet har skickats till Commerce-administration visas det på fliken **aktiv** och statusvärdet **begärt**. I det här läget kan användare i det inkommande lagret eller lager stället inte längre redigera det begärda inkommande orderdokumentet. Endast användare i det utgående lagerstället kan redigera dokumentet, genom att välja **utgående operation** i kassaprogrammet. Redigeringslåset garanterar att det inte uppstår konflikter eftersom en inkommande begärande ändrar överföringsordern samtidigt som den utgående speditören aktivt plockar och levererar ordern. Om det krävs ändringar från inkommande lager eller lagerställe efter att överföringsordern har skickats, ska den utgående speditören kontaktas och uppmanas att ange ändringarna.

När dokumentet är i status **begärd** visas det på fliken **Aktiv**. Det kan dock inte tas emot av den inkommande butiken eller lagerstället. När det ingående lagerstället har levererat en del av eller hela överföringsordern kan den ankommande butiken eller lagerstället bokföra inleveranser i kassa. När den utgående sidan bearbetar dokumenten för överföringsorder, uppdateras deras status från **Begärd** till **Levererad** eller **Delvis levererad**. Efter att dokumenten är i status **levererad** eller **Delvis levererad** kan inkommande lager eller lagerställe bokföra inleveranser mot dem genom att använda den inkommande operationen för inleverans.

## <a name="related-topics"></a>Relaterade ämnen

[Utgående lageråtgärder i kassan](pos-outbound-inventory-operation.md)
