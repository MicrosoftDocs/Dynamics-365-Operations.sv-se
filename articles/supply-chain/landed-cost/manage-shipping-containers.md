---
title: Hantera leveransbehållare
description: I denna artikel beskrivs hur du arbetar med leveransbehållare. Leveransbehållare används för att gruppera varor som fysiskt grupperas tillsammans. De används även i fall där kostnader endast måste fördelas mellan dessa varor, oftast på grund av att de är fysiskt tillsammans.
author: Weijiesa
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 22f2512125679f160cb658923893d5f5aa739a2d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906165"
---
# <a name="manage-shipping-containers"></a>Hantera leveransbehållare

[!include [banner](../../includes/banner.md)]

Leveransbehållare används för att gruppera varor som fysiskt grupperas tillsammans. De används även i fall där kostnader endast måste fördelas mellan dessa varor, oftast på grund av att de är fysiskt tillsammans.

För att se och bearbeta varor via sidan för leveransbehållare, gå till **Hemtagningskostnad \> Leveransbehållare \> Alla leveransbehållare**. Sidan **All leveransbehållare** visar en lista över alla tillgängliga leveransbehållare. Med knapparna i åtgärdsfönstret kan du skapa, ta bort och arbeta med leveransbehållare.. Markera valfri leveransbehållare i listan om du vill visa information om den på sidan **Leveransbehållare**.

På den övre delen av informationssidan för leveransbehållare visas information om leveransbehållare och kostnadsredovisning. Avsnittet **Rader** visar folio, artiklar och inköpsorder eller överföringsorder som finns kopplade till behållaren.

## <a name="action-pane"></a>Åtgärdsfönster

Åtgärdsfönstret på sidan **Alla leveransbehållare** och **leveransbehållare** ger knappar som gör att du kan arbeta med en vald leveransbehållare. Varje knapp utför en enskild åtgärd. I åtgärdsfönstret finns även flikar, och varje flik, som i sin tur innehåller en uppsättning relaterade knappar. Utom i de fall där detta anges finns alla knappar och flikar som beskrivs i följande delgrupper tillgängliga både i listvyn (det vill säga på sidan **Alla leveransbehållare**) och i den detaljerade vyn (d.v.s. på sidan **leveransbehållare**).

### <a name="buttons-on-the-manage-tab"></a>Knappar på fliken Hantera

I följande tabell beskrivs de knappar som finns tillgängliga på fliken **Hantera** i åtgärdsfönstret.

| Knapp | Beskrivningar |
|---|---|
| Bokför inleveranslista | Bokför en inleveranslista eller visa produktinleveranslistorna för alla inköpsorderrader i leveransbehållaren. Om multiföretagsleverans används öppnas en ny inleveranslista för bokföring av faktura för varje företag. |
| Bokför produktinleverans | Bokför en produktinleverans för alla inköpsorderrader i leveransbehållare. |
| Bokför faktura | Bokför en faktura för alla inköpsorderrader i leveransbehållare. Om multiföretagsleverans används öppnas en ny dialogruta för bokföring av faktura för varje företag. |
| Leverera överföringsorder | Bokför en leverans av överföringsorder för alla överföringsorderrader i leveransbehållaren. Endast de rader i leveransbehållaren som är av typen överföringsorder visas i dialogrutan. |
| Inleverera överföringsorder | Bokför en inleverans av överföringsorder för alla överföringsorderrader i leveransbehållaren. Dialogrutan inleverans är det enkla sättet att ta emot gods i en leveransbehållare eller färd och är ett av de tre tillgängliga alternativen. Du kan också ta emot detta via införseljournaler eller bearbetning av den mobila enheten. |
| Skapa införseljournal | Du kan generera en införseljournal för organisationer med hjälp av avancerade lagerställefunktioner. Alternativen är _Initiera kvantitet_ (rekommenderas) och antingen _Skapa från varor under transport_ och/eller _Skapa från inköpsorder_. De sista två alternativet beror på om bearbetning av varor på väg används. |
| Byt namn | Öppna en dialogruta där du kan byta namn på en vald leveransbehållare. |
| Ändra resemallen | Ändra resemallen. När du har ändrat resemallen måste du kanske välja **Sök efter automatiska kostnader** eller lägga till kostnader manuellt igen, eftersom leveranskostnaderna raderas. |
| Konvertera till hyrd | Omvandla en vald leveransbehållare till en hyrd leveransbehållare. |

### <a name="buttons-on-the-general-tab"></a>Knappar på fliken Allmän

I följande tabell beskrivs de knappar som finns tillgängliga på fliken **Allmän** i åtgärdsfönstret.

| Knapp | Beskrivningar |
|---|---|
| Inleveranslista | Bokför en inleveranslista för alla inköpsorderrader i leveransbehållare. Om multiföretagsfärd används öppnas en ny dialogruta för bokföring av inleveranslista för varje företag. |
| Produktinleverans | Visa produktinleveransposten, om den används. Inleveransprocessen för produkter används endast om varorna inte använder funktionen för varor på väg. |
| Artikelinförsel | Visa artikel för införseljournalen för leveransbehållare, om journalen används. |
| Etapper | Sträckor används för att identifiera separata delar av en resa. Ledtider kan kopplas till varje del som hjälp vid spårning av försändelser. Mer information finns i [Inställning av resa med flera sträckor](multi-leg-journey-setup.md). |
| Spårning | Visa eller uppdatera spårning av försändelser. |
| Order för varor på väg | Du kan öppna sidan **Varor på väg** direkt från behållaren. På den sidan visas bara posterna för varor på väg för den valda leveransbehållaren. |

## <a name="header-view"></a>Huvudvy

Öppna vyn **Huvud** genom att öppna en leveransbehållare och sedan välja fliken **Huvud** i den övre högra delen av leveransbehållarens rubrik.

### <a name="settings-on-the-general-fasttab"></a>Inställningar på snabbfliken Redovisning

I tabellen nedan beskrivs inställningarna som är tillgängliga på snabbfliken **Allmänt** i vyn **Huvud** för en leveransbehållare.

| Fält | beskrivning |
|---|---|
| Fraktcontainer | Namnet på leveransbehållaren. |
| Sjötransport | Den färd som är associerad med leveransbehållare. |
| Typ av fraktcontainer | Ange typ av leveransbehållare. Det här fältet måste anges. Du kan använda den för att bestämma kostnaden för frakten, till exempel genom att välja den automatiska kostnad som är associerad med typen av leveransbehållare. |
| Fartyg | Ange eller välj fartyg. Om fartyget inte anges som ett värde kan du ange ID:t som fritext. I sådana fall uppdateras inte huvudregistret, så att ditt lösenords-ID kan väljas i det här fältet senare. För mer information, se [fartyg](shipping-information-setup.md#vessels). |
| Enhetstyp | Enhetstyper används som ett ytterligare sätt att gruppera och identifiera leveransbehållare. De visas och markeras på sidan för leveransbehållare. Mer information finns i [Ställ in enhetstyper](shipping-container-setup.md#unit-types). |
| Kylningstyp | Kyltyper används som ett ytterligare sätt att gruppera och identifiera leveransbehållare, vanligtvis kylbehållare. De visas och markeras på sidan för leveransbehållare. Mer information finns i [Ställ in kyltyper](shipping-container-setup.md#refrigeration-types). |
| Mått | Det här fältet gör att en mätning kan anges i modulen **Hemtagningskostnad**. Mått används ofta av organisationer som inte känner till den individuella volymen eller vikten av varorna, men som kräver en mer korrekt fördelning än alternativen för belopp och kvantitet. Fraktspeditören ger med vikt i kilogram eller kubiska mått och du kan lägga den på antingen en artikel eller inköpsorder.. Den kan uppdateras automatiskt om parametern väljs eller anges manuellt. |
| Måttenhet | Måttenheten som gäller för numret i fältet **Mått**. |
| Faktisk vikt | Du kan registrera den faktiska vikten för kartongen eller behållaren. Det här värdet kan användas för verifiering mot den maxvikt som är tillåten i inställningarna för en leveransbehållare. |
| Antal kartonger | Antalet kartonger uppdateras automatiskt om parametern väljs. |
| Beskrivning av varor | Du kan välja en beskrivning av gods i leveransbehållarens rubrik eller i folio sidhuvud. Den används för att identifiera en leveransbehållare eller folio med varor. För mer information, se [Beskrivning av varor](shipping-information-setup.md#description-of-goods). |
| HAWB/fraktsedel | Du kan ange flygfraktsedeln eller fraktsedeln för leveransbehållaren. |
| Kommentarer | Ytterligare information som är relaterad till leveransbehållaren. |
| Returnerbara | Ett värde som indikerar om leveransbehållaren kan returneras efter färden. |
| Sjötransportens status | Status för färden som är associerat med leveransbehållaren. |
| Status på inköpsorder | Status för inköpsordern som är associerat med leveransbehållaren. |

### <a name="settings-on-the-delivery-fasttab"></a>Inställningar på snabbfliken Leverans

I tabellen nedan beskrivs inställningarna som är tillgängliga på snabbfliken **Leverans** i vyn **Huvud** för en leveransbehållare.

| Fält | beskrivning |
|---|---|
| Skapades datum och klockslag | Det datum och den tid då behållaren skapades. |
| Datum för fritt fabrik | Detta datum anges vanligtvis till fabriks-/leverantören för att ange när du förväntar dig att varorna ska lämna dess lokal. När du arbetar med en fabrik i Asien krävs ofta det här datumet istället för det datum som du förväntar dig att varorna ska ha. (Däremot för en lokal leverans är det från det datum då du förväntar dig att varorna ska levereras.) Det här fältet kan fyllas i från inköpsorderraderna i listan för leveransbehållare. Du kan även ange det manuellt här. |
| Transportdatum | Datumet kan skrivas ut på inköpsorderdokumentet. Vanligtvis informerar den fabriks-/leverantör om datumet då varorna ska levereras till porten. Det här fältet är bara avsett för information. Det används inte för att uppskatta förväntat leveransdatum för varorna i leveransbehållaren. Fältet kan ställas in så att det uppdateras automatiskt när spårningskontrollsidan uppdateras. |
| Datum för till butik | Det tidigaste datumet då varorna från de inköpsorder som är kopplade till färden den ska vara tillgängliga för försäljning.|
| Uppskattat leveransdatum | Vanligen det datum då varorna ska ankomma till lagerstället. Det här fältet är bara avsett för information. Den används inte för att beräkna huvudplanering på inköpsorderrader i leveransbehållare. Det förväntade leveransdatumet på inköpsorderraderna uppdateras med spårningskontroll. Fältet kan ställas in så att det uppdateras när spårningskontrollsidan uppdateras. |
| Avresedatum | Vanligtvis lämnar det datum när flyget eller fartyget lämnar den utländska porten. |
| Beräknad ankomst vid leveranshamn | Uppskattat ankomstdatum vid destinationsporten ("till"-porten). |
| Mottagna originaldokument | Valfritt: Uppdatera datumet när originaldokumenten togs emot. |
| Mäklaren har informerats | Valfritt: Uppdatera det datum då mäklaren underrättades. |
| Ursprungligt fraktsedel skickad | Valfritt: Uppdatera datumet när den ursprungliga fraktsedeln skickades. |
| Varor som frisläppts | Valfritt: Uppdatera datumet när varorna frisläpptes. |
| Kundmöte | Valfritt: Uppdatera datumet för kundbokningen. |
| Levererad vid distributionslager | Valfritt: Uppdatera datumet när varorna levererades till lagerstället. |
| Verifieringsdatum | Valfritt: Uppdatera verifieringsdatumet. |
| Leveransinstruktioner | Valfritt: Uppdatera datumet för leveransinstruktionerna. |
| Från hamn | Den port som artiklarna ska levereras från. |
| Till hamn | Den port som artiklarna ska levereras till. |
| Lokal vidarebefordrare | Det här fältet är bara avsett för information. Den lokala vidarebefordraren bör väljas från leverantörsregistret. |
| Datum för lokal transport | Ange det datum som den lokala transporten är bokad för. Det här fältet kan hjälpa lagerstället att planera. |
| Tid för lokal transport | Ange en tidpunkt. Det här fältet kan hjälpa lagerstället att planera. |
| Resemall | Den resmall för sådd som angetts för färden. Resemallen innehåller information om portarna "till" och "från" samt de ledtider som används för spårning av leveransbehållaren. |

### <a name="settings-on-the-other-fasttab"></a>Inställningar på snabbfliken Andra

I tabellen nedan beskrivs inställningarna som är tillgängliga på snabbfliken **Andra** i vyn **Huvud** för en leveransbehållare.

| Fält | beskrivning |
|---|---|
| Hyra | Ett värde som anger om leveransbehållaren är en hyrd leveransbehållare. Hyreskostnader kan kopplas till hyrda behållare. |
| Konverterad till hyrd | Ett värde som anger om leveransbehållaren konverterades till en hyrd leveransbehållare. Hyreskostnader kan kopplas till hyrda behållare. |
| Ursprunglig sjötransport | Om leveransbehållaren flyttades till en ny färd, den ursprungliga färden. |
| Används | Använd det här när du vill registrera om en leveransbehållare har använts eller inte. Detta är endast för informationssyften. |
| Förväntat lastningsdatum | Det datum då leveransbehållaren förväntas lastas med varor. |
| Vårt serienummer | Ange det serienummer som ditt företag använder internt för leveransbehållaren. |
| Leveransföretagets serienummer | Ange det serienummer som transportföretaget eller agenten har för leveransbehållaren. |
| Kontrollintyg tillämpat den | Det datum då en granskning begärdes av leveransbehållaren. |
| Mottagningsdatum för kontrollintyg | Datum när kontrollintyget togs emot. |
| Utgångsdatum för kontrollintyg | Datum när kontrollintyget kommer att gå ut. |
| Nummer på kontrollintyg | Intygsnumret för det intyg som utfärdades efter att en granskning utförts. |

## <a name="lines-view"></a>Radvy

Öppna vyn **Rader** genom att öppna en leveransbehållare och sedan välja fliken **Rader** i den övre högra delen av leveransbehållarens rubrik.

### <a name="information-on-the-shipping-container-fasttab"></a>Information på snabbfliken leveransbehållare

Snabbfliken **Leveransbehållare** i vyn **Rader** visar information om folio. Större delen av den här informationen visas även i vyn **Rubrik**, på det sätt som beskrivs tidigare i denna artikel.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Information och knappar på snabbflikarna Rader

Snabbfliken **Rader** i vyn **Rader** visar information om alla fullständiga eller delvisa inköpsorderrader som ingår i den aktuella leveransbehållaren.

I följande tabell beskrivs de knappar som finns tillgängliga i verktygsfältet på snabbfliken **Rader** i vyn **Rader**.

| Knapp | beskrivning |
|---|---|
| Ta bort | Ta bort den valda inköpsorderraden från färden. |
| Lager \> Transaktioner | Visa lagertransaktioner för den valda inköpsordern. Observera att om du använder varor på väg visas även den ursprungliga ordern och ordern för varor som överförs under transport. |
| Lager \> Visa dimensioner | Öppna en dialogruta där du kan välja lagerdimensionerna som visas för de transaktioner som du visar. |
| Förnya | Uppdatera information som är relaterad till radbelopp, vikt eller volym för den valda inköpsorderraden. |

### <a name="information-on-the-lines-details-fasttab"></a>Information på snabbfliken raddetaljer

Snabbfliken **Raddetaljer** i vyn **Rader** visar information om inköpsorderraden som för närvarande är vald på snabbfliken **Rader**.
