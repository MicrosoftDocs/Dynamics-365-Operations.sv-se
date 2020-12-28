---
title: Utgående lageråtgärder i kassan
description: Det här ämnet beskriver möjligheterna i den utgående lageråtgärden för en kassa (POS).
author: hhaines
manager: annbe
ms.date: 07/30/2020
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
ms.openlocfilehash: 1f74df94b1647520880ff994581872b9d9f8e067
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415718"
---
# <a name="outbound-inventory-operation-in-pos"></a>Utgående lageråtgärder i kassan

[!include [banner](includes/banner.md)]


I Microsoft Dynamics 365 Commerce version 10.0.10 och senare ersätter inkommande och utgående åtgärder i kassan (POS) åtgärden plockning och inleverans.

> [!NOTE]
> I version 10.0.10 och senare kommer alla nya funktioner i kassaprogrammet som är relaterade till att ta emot butikslager att tas med i inköpsorder och överföringsorder att läggas till i inkommande åtgärden. Om du använder åtgärden för plockning och mottagning i kassa rekommenderar vi att du utvecklar en strategi för att flytta från den åtgärden till nya inkommande och utgående åtgärder. Även om åtgärden för plockning och mottagning inte tas bort från produkten, finns det inga ytterligare investeringar i den, från ett funktionellt eller resultatperspektiv efter version 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Förutsättning: Konfigurera ett asynkront dokumentramverk

Den utgående åtgärden omfattar prestandaförbättringar som säkerställer att användare med höga kvantiteter av inleverans kan bokföra över många butiker eller företag och stora lagerdokument, kan bearbeta dessa dokument till Commerce-administration (HQ) utan att uppleva timeout eller misslyckanden. Dessa förbättringar kräver användning av ett asynkront dokumentramverk.

När ett asynkront dokumentramverk används kan du tilldela ändringar i utgående dokument från kassa till Commerce-administration (HQ) och sedan flytta vidare till andra uppgifter medan behandlingen till Commerce-administration (HQ) sker i bakgrunden. Du kan kontrollera statusen för dokumentet via dokumentlistsidan **utgående åtgärd** i kassan för att säkerställa att bokföringen lyckades. I kassaprogrammet kan du även använda listan aktiva dokument i utgående åtgärd för att se alla dokument som inte kunde bokföras i Commerce-administration (HQ). Om ett dokument misslyckas kan kassaanvändare göra korrigeringar till det och sedan försöka bearbeta det till Commerce-administration (HQ).

> [!IMPORTANT]
> Det asynkrona dokumentramverket måste konfigureras innan ett företag försöker använda utgående åtgärd i kassan.

Följ instruktionerna nedan om du vill konfigurera ett asynkront dokumentramverk.

### <a name="create-and-configure-a-number-sequence"></a>Skapa och konfigurera en nummersekvens

1. Gå till **Organisationsadministration \> Nummerserier \> Nummerserier**.
2. På sidan **Nummerserier** skapar du två en nummerserie.
3. I fälten **Nummerseriekod** och **Namn** anger du användardefinierade värden.
4. På snabbfliken **Referenser** väljer du **Lägg till**.
5. I fältet **Område**, välj **Commerce-parametrar**.
6. I fältet **Referens**, välj **Åtgärdsidentifierare för butiksdokument**.
7. På snabbfliken **Allmänt** i avsnittet **Inställningar**, ange alternativet **Kontinuerligt** till **Nej** för att se till att det inte finns några prestandaproblem.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Skapa och tidsplanera två batchjobb för dokumentbearbetning och övervakning av uppgifter

> [!NOTE]
> I Commerce version 10.0.13 och senare behöver du inte konfigurera dessa batchjobb via batch-jobbets ramverk. Batchprocesser kan konfigureras från menyn **Retail och Commerce > Retail och Commerce IT**. Använd menyalternativen **Åtgärdsövervakare för butiksdokument** och **Åtgärdsbearbetning för butiksdokument** när du konfigurerar batchjobb

De batchjobb som du skapar kommer att användas för att bearbeta dokument som misslyckas eller timeout. De kommer också att användas när antalet aktiva lagerdokument som bearbetas från kassan överskrider ett systemkonfigurerat värde.

1. Gå till **Systemadministration \> Förfrågningar \> Batchjobb**.
2. På sidan **Batchjobb**, skapa två batchjobb:

    - Konfigurera ett jobb för att köra klassen **RetailDocumentOperationMonitorBatch**.
    - Konfigurera det andra jobbet att köra klassen **RetailDocumentOperationProcessingBatch**.

3. Tidsplanera de nya batchjobben så att de körs återkommande. Ställ t.ex. in schemat så att jobben körs var femte minut.

## <a name="prerequisite-add-outbound-operation-to-the-pos-screen-layout"></a>Förutsättning: Lägg till utgående operation i kassaskärmlayout

Innan din organisation kan använda funktionen för utgående åtgärd måste den konfigurera kassaåtgärden **utgående åtgärd** på en eller flera av dina [kassaskärmlayouter](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Innan du distribuerar den nya operationen i en produktionsmiljö bör du kontrollera att du testar den och träna dina användare att använda den.

## <a name="overview"></a>Översikt

I den utgående åtgärden utför kassaanvändare följande uppgifter:

- Bokföra försändelser för överföringsorderdokument i fall där användarens butik är det angivna utgående lagerstället.
- Visa information om historiska försändelser för överföringsorder som har bokförts i butiken.
- Skapa nya begäranden om utgående överföringsorder.

När den utgående åtgärden startas från kassaprogrammet visas en listsida. I den här vyn visas öppna överföringsorderdokument med lagerrader som användarens aktuella butik är avsedd att leverera och uppfylla. För att kunna söka efter ett dokument kan användarna bläddra i listan eller använda sökfunktionen.

Den utgående lagerdokumentlistan har tre flikar.

- **Aktiv** – på den här fliken visas överföringsorder som har statusen **begärd** eller **delvis levererad**. Order innehåller rader eller kvantiteter på rader som måste skickas av användarens aktuella butik. På den här fliken visas också order som har statusen **bearbetad i HQ** (det vill säga att de väntar på bekräftelse av bokföringen från Commerce-administration (HQ)) eller **bearbetningen misslyckades** (dvs. bokföring till Commerce-administration (HQ) misslyckades och användaren måste korrigera data och försöka skicka in orderna igen).
- **Utkast** – på den här fliken visas nya utgående begäran om överföringsorder som användarens butik har skapat. Dokumenten har dock endast sparats lokalt. De har inte skickats in till Commerce-administration (HQ) för bearbetning.
- **Slutförd** – på den här fliken visas en lista över överföringsorderdokument som butiken har levererat under de senaste sju dagarna. Denna flik är endast för informationssyften. All information om dokumenten är skrivskyddade data för butiken.

När du visar dokument på någon av flikarna kan fältet **status** hjälpa dig att förstå vilken fas dokumentet finns i.

- **Utkast** – överföringsorderdokumentet har endast sparats lokalt i butikens kanaldatabas. Ingen information om begäran om överföringsorder har ännu skickats till Commerce-administration (HQ).
- **Begärt** – inköpsordern eller överföringsordern har skapats i Commerce-administration (HQ) och är helt öppen. Användarens aktuella butik har ännu bearbetat alla försändelser mot dokumentet.
- **Delvis levererad** – i överföringsorderdokumentet finns en eller flera rader eller delrad antal som har bokförts som levererade av det avgående lagerstället. Dessa levererade rader är tillgängliga för inleverans via den inkommande operationen.
- **Fullständigt levererad** – överföringsordern har fått alla rader och fullständiga rad antal som har bokförts som levererade av det utgående lagerstället.
- **Pågår** – denna status används för att informera enhetsanvändare om att dokumentet aktivt bearbetas av en annan användare.
- **Pausad** – den här statusen visas när **Paus mottagning** har valts för att tillfälligt stoppa mottagningsprocessen.
- **Bearbetning i HQ** – dokumentet har skickats till Commerce-administration (HQ) från kassaprogrammet men har ännu inte bokförts i Commerce-administration (HQ). Dokumentet går via den asynkrona bokföringsprocessen för dokument. När dokumentet har bokförts till Commerce-administration (HQ) ska dess status uppdateras till **helt inlevererat** eller **delvis inlevererat**.
- **Bearbetningen misslyckades** – dokumentet bokfördes i Commerce-administration (HQ) och avvisades. Fönstret **information** visar orsaken till bokföringsfelet. Dokumentet måste redigeras för att korrigera dataärenden och måste skickas vidare till Commerce-administration (HQ) för bearbetning.

När du väljer en dokumentrad i listan visas ett **detalj**-fönster. I det här fönstret visas ytterligare information om dokumentet, t.ex. information om leverans och datum. En förloppsindikator visar hur många artiklar som fortfarande måste bearbetas. Om dokumentet inte kunde bearbetas utan problem till Commerce-administration (HQ), visar fönstret **Detaljer** också felmeddelanden som hör till felet.

I vyn sida i dokument listan kan du välja **orderdetaljer** i appfältet om du vill visa dokumentinformationen. Du kan också aktivera inleveransbearbetning på kvalificerade dokumentrader.

I vyn sidvisning i dokumentlista kan du också skapa en ny utgående överföringsorder för en butik.

## <a name="transfer-order-shipping-process"></a>Överföringsorder för leveransprocess

När du har valt ett överföringsorderdokument, på fliken **aktiv** kan du välja **orderdetaljer** för att påbörja uppfyllelseprocessen. Vyn **fullständig orderlista** visas. På den här sidan visas alla dokumentrader som innehåller artikeln. Den visar även detaljerad information om den beställda kvantiteten.

Vid varje skanning av en streckkod uppdateras kvantiteten i fältet **leverans nu** med en enhet. Alternativt kan du ange en leveranskvantitet genom att välja **leverera produkt** i appfältet, ange ett artikel-ID och sedan ange kvantiteten. Om artikeln är platskontrollerad kan du bekräfta eller ställa in leveransplatsen för dokumentraden.

I vyn **fullständig orderlista** kan du manuellt välja en rad i listan och sedan uppdatera kvantiteten **leverans nu** kvantitet för den valda raden i **Detalj**.

### <a name="over-delivery-shipping-validations"></a>Leveransvalideringar för överleverans

Valideringar sker under mottagningsprocessen för dokumentraderna. De inkluderar valideringar för överleverans. Om en användare försöker ta emot mer lager än vad som beställts på en inköpsorder, men antingen överleverans eller den kvantitet som har inlevererats överskrider den överleveranstolerans som har konfigurerats för inköpsorderraden, får användaren ett felmeddelande och får inte ta emot överskjutande kvantitet.

### <a name="underdelivery-close-lines"></a>Stäng rader för underleverans

I Commerce version 10.0.12 lades en funktion till som gör att kassaanvändare (POS) stänger eller annullerar resterande kvantiteter vid utgående orderleverans om berört utgående lagerställe bedömer att man inte kan leverera hela den kvantitet som har begärts. Kvantiteter kan också stängas eller annulleras senare. Om du vill använda den här funktionen måste företaget konfigureras att tillåta underleverans av överföringsorder. Dessutom måste en underleveransprocent definieras för överföringsorderraden.

Om du vill konfigurera företaget att tillåta underleverans av överföringsorder i Commerce-administration (HQ) går du till **Lagerhantering \> Inställningar \> Parametrar för hantering av lager och lagerstyrning**. På sidan **Parametrar för hantering av lager och lagerstyrning** på fliken **Överföringsorder** aktiverar du parametern **Acceptera underleverans**. Kör sedan jobb **1070** för distributionsscheman för att synkronisera parameterändringarna till butikskanalen.

Underleveransprocenten för en överföringsorderrad kan fördefinieras för produkter som en del av produktkonfigurationen i Commerce Headquarters. De kan också ställas in eller skrivas över på en specifik överföringsorderrad via Commerce-administration (HQ).

När en organisation har slutfört konfigureringen av underleveranser för överföringsorder kommer kassaanvändare att se alternativet **Stäng resterande kvantitet** i fönstret **Information** när de väljer en utgående överföringsorderrad via åtgärden **Utgående åtgärder** i POS. När användaren slutför leveransen med hjälp av åtgärden **Avsluta uppfyllelse** kan de skicka en begäran till Commerce-administration (HQ) om att annullera den återstående kvantiteten som ännu inte skickats. Om en användare stänger den återstående kvantiteten utförs en validering i Commerce i syfte att verifiera att den kvantitet som annulleras ligger inom den procentsats för underleverans som har definierats på överföringsorderraden. Om avvikelsen för underleverans överskrids visas ett felmeddelande och användaren kan inte stänga den återstående kvantiteten förrän den tidigare levererats och "skicka nu"-kvantiteten uppfyller eller överskrider toleransen för underleverans.

När leveransen har synkroniserats till Commerce-administration (HQ) uppdateras de kvantiteter som har definierats i fältet **Skicka nu** för överföringsorderraden i POS till statusen "Levererad" i Commerce-administration (HQ). Alla icke levererade kvantiteter som tidigare skulle ha betraktats som "att skicka"-kvantiteter (dvs. kvantiteter som kommer att skickas) betraktas istället som annullerade kvantiteter. Kvantiteten "att skicka" för överföringsorderraden är inställd på **0** (noll) och raden anses fullt levererad.

### <a name="shipping-location-controlled-items"></a>Leveransplatskontrollerade artiklar

Om artiklarna som ska levereras är platsstyrda kan användarna välja den plats som de vill utfärda lagret från under leveransprocessen. Vi rekommenderar att du konfigurerar en standardplats för frågor för butikslagret, så att processen blir mer effektiv. Även om en standardplats har konfigurerats kan användarna åsidosätta utleveransplatsen på valda rader när de behövs.

Operationen respekterar konfigurationen **Tom inleverans tillåten** på lagringsdimensionen **Plats** och kräver inte att en platsdimension anges om en tom inleverans har konfigurerats. Om tomma inleveransplatser inte är tillåtna för en artikel, visar kassaprogrammet ett fel och kräver att en plats registreras innan inleveransen kan bokföras.

### <a name="ship-all"></a>Leverera allt

Som du behöver kan du välja **Leverera allt** på appfältet för att snabbt uppdatera kvantiteten **leverans nu** för alla dokumentrader till det maximala värdet som är tillgängligt för att uppfylla för dessa rader.

### <a name="cancel-fulfillment"></a>Avbryt expediering

Använd funktion **Avbryt uppfyllelse** på appfältet endast om du vill säkerhetskopiera dokumentet och inte vill spara några ändringar. Du kan t.ex. från början välja fel dokument och inte vill att tidigare transportdata ska sparas.

### <a name="pause-fulfillment"></a>Pausa expediering

Om du uppfyller överföringsordern kan du använda funktionen **pausa uppfyllelse** för att pausa uppfyllelse om du vill ta en paus från processen. Du kanske till exempel vill utföra en annan åtgärd från kassa, t.ex. att ringa upp en kundförsäljning, eller att försena bokföringen av leveransen till Commerce-administration (HQ).

När du väljer **Pausa uppfyllelse** dokumentets status ändrades till **Pausa**. Därför vet användaren att data har registrerats i dokumentet, men dokumentet har ännu inte genomförts. När du är redo att återuppta uppfyllelseprocessen markerar du det pausade dokumentet och väljer **orderdetaljer**. Alla kvantiteter **leverans nu** kvantiteter som tidigare sparats kommer att behållas och kan ses från **fullständig orderlista**.

### <a name="review"></a>Granska

Innan det slutliga åtagandet till Commerce-administration (HQ) kan du validera det inkommande dokumentet med hjälp av funktionen **Granska**. Den här funktionen varnar för data som potentiellt saknas eller är felaktiga och ger dig möjlighet att rätta till problemen innan du skickar in begäran om uppfyllelse. Om du vill aktivera funktionen **Granska** i programfältet aktiverar du funktionen **Aktivera validering i kassans inkommande och utgående lageråtgärder** via Funktionshantering i Commerce-administration (HQ).

Funktionen **granska** validerar följande problem i ett utgående dokument:
- **Överleverans** – kvantiteten leverans nu är större än den beställda kvantiteten. Problemets allvar beror på överleveransens konfiguration i Commerce-administration (HQ).
- **Underleverans** – kvantiteten leverans nu är mindre än den beställda kvantiteten. Problemets allvar beror på underleveransens konfiguration i Commerce-administration (HQ).
- **Serienummer** – serienumret har inte angetts eller är inte tillgängligt för en serialiserad artikel som kräver att serienumret registreras i lagret.
- **Ingen plats angiven** – ingen plats har angetts för en plats kontrollerad artikel där tom plats inte är tillåten.
- **Borttagna rader** – ordern har rader tagits bort av Commerce-administration (HQ) som inte är känd för kassaprogram.

Om du ställer in parametern **Aktivera automatisk validering** till **Ja** i **Commerce-parametrar** > **Lager** > **Lagerhanteringsåtgärder** om du vill att valideringen ska utföras automatiskt när **Slutför uppfyllelse** är vald.

### <a name="finish-fulfillment"></a>Slutför expediering

När du har fyllt i alla kvantiteter **leverans nu** för produkter måste du välja **slutför påfyllning** i appfältet.

När asynkron dokumentbearbetning används skickas kvittot via ett asynkront dokumentramverk. Hur lång tid det tar att bokföra dokumentet beror på dokumentets storlek (antalet rader) och den allmänna bearbetningstrafik som sker på servern. Vanligtvis förekommer denna process på några sekunder. Om dokument bokföringen misslyckas meddelas användaren via dokument **utgående operation** på fliken **aktiv** där dokument status uppdateras till **bearbetningen misslyckades**. Användaren kan sedan välja det misslyckade dokumentet i kassan för att visa felmeddelandena och orsaken till misslyckandet i fönstret **information**. Ett misslyckat dokument förblir oförändrat och kräver att användaren går tillbaka till dokumentraderna genom att välja **orderdetaljer** i kassan. Användaren måste sedan uppdatera dokumentet med korrigeringar baserat på felen. När ett dokument har korrigerats kan användaren försöka att bearbeta det genom att välja **Slutför** på appfältet.

## <a name="create-an-outbound-transfer-order"></a>Skapa en utgående överföringsorder

Från kassan kan användare skapa nya överföringsorderdokument. Starta processen genom att välja **ny** i appfältet medan du är i huvuddokumentlistan för **utgående operation**. Du uppmanas sedan att välja lagerställe eller butik med **överföring till** som den aktuella butiken skickar lager till. Värdena begränsas till det val som har angetts i konfigurationen för butikens uppfyllelsegrupp. I en begäran om utgående överföringar är den aktuella butiken alltid **överföringen från** lagerstället för överföringsordern. Det går inte att ändra värdet.

Du kan ange värden i fälten **Transportdatum**, **Inleveransdatum** och **Leveranssätt** efter behov. Du kan också lägga till en notering som kommer att lagras tillsammans med överföringsorder rubriken, som en bilaga till dokumentet i Commerce-administration (HQ).

När informationen i huvudet har skapats kan du lägga till produkter på överföringsordern. Om du vill starta processen med att lägga till artiklar och begärda kvantiteter, skanna streckkoder eller välj **Lägg till produkt**.

När rader har angetts på den avgående överföringsordern måste du välja **Spara** för att spara dokumentändringarna lokalt eller **skicka begäran** för att skicka orderdetaljerna till Commerce-administration (HQ) för vidare bearbetning. Om du väljer **spara** sparas utkastdokumentet i kanaldatabasen och det avgående lagerstället kan inte köra dokumentet förrän det har bearbetats via **Skicka in begäran**. Välj **Spara** endast om du inte är redo att genomföra begäran till Commerce-administration (HQ) för bearbetning.

Om ett dokument sparas lokalt kan du hitta det på fliken **Utkast** på dokumentlistan **inkommande operation**. När dokumentet är i status **utkast** kan du redigera det genom att välja **redigera**. Du kan uppdatera, lägga till eller ta bort rader som du behöver. Du kan också ta bort hela dokumentet när det är i status **utkast** genom att välja **ta bort** på fliken **utkast**.

När utkastet till dokumentet har skickats till Commerce-administration (HQ) visas det på fliken **aktiv** och statusvärdet **begärt**. I det här läget kan bara användare i det utgående lagerstället redigera dokumentet, genom att välja **utgående operation** i kassaprogrammet. Användare i det ankommande lager stället kan visa överföringsorder på fliken **aktiv** i dokumentlistan **inkommande operation** men de kan inte redigera eller radera dem. Redigeringslåset garanterar att det inte uppstår konflikter eftersom en inkommande begärande ändrar överföringsordern samtidigt som den utgående speditören aktivt plockar och levererar ordern. Om det krävs ändringar från inkommande lager eller lagerställe efter att överföringsordern har skickats, ska den utgående speditören kontaktas och uppmanas att ange ändringarna.

När dokumentet har status **begärt** är det klart för bearbetning av det utgående lagerstället. När leverans bearbetas med hjälp av avgående operation uppdateras statusen för överföringsorder dokumenten från **begärt** till **helt levererat** eller **delvis levererat**. Efter att dokumenten är i status **Helt levererad** eller **Delvis levererad** kan inkommande lager eller lagerställe bokföra inleveranser mot dem genom att använda den inkommande operationen för inleverans.

Hela levererade överföringsorder flyttas till fliken **Slutför** på dokumentlistan **utgående operation**. Där finns de kvar för användare i den utgående butiken eller det avgående lagret i ett skrivskyddat läge, i sju dagar.

## <a name="related-topics"></a>Relaterade ämnen

[Ingående lageråtgärder i kassan](pos-inbound-inventory-operation.md)
