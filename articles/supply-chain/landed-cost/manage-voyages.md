---
title: Hantera resor
description: I det här avsnittet beskrivs hur du arbetar med resor. En resa representerar vanligtvis ett fartyg. Beroende på vad du använder och vilka procedurer du har kan det dock representera en leverantör, en inköpsorder eller någon annan artikel som för är vettig för din organisation.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMTableListPage, ITMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 953677a0d7ebe3343b888fdff2867334ef69d861d85a9145aa003177617434d6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757840"
---
# <a name="manage-voyages"></a>Hantera färder

[!include [banner](../../includes/banner.md)]

En resa representerar vanligtvis ett fartyg. Beroende på vad du använder och vilka procedurer du har kan det dock representera en leverantör, en inköpsorder eller någon annan artikel som för är vettig för din organisation.

Sidan **Alla färder** innehåller information, leverans- och kostnadsinformation samt information om artiklar, inköpsorder och överföringsorder. Om du vill öppna sidan **Alla färder** går du till **Hemtagningskostnad \> Färder \> Alla färder**. På den här sidan visas en lista över alla aktuella färder. Med knapparna i åtgärdsfönstret kan du skapa, ta bort och arbeta med färder. Välj en valfri färd för att visa detaljerad information om den.

> [!NOTE]
> Leveransbehållare och folio är kopplade till en färd. Inköpsrader är länkade till en leveransbehållare. Om leveransbehållare och folio är inaktiverade kan de även länkas direkt till en färd. Dessutom fördelas kostnader som anges här till alla kopplade inköpsrader.

## <a name="action-pane"></a>Åtgärdsfönster

Åtgärdsfönstret på sidan **färder** ger knappar som gör att du kan arbeta med en vald färd. Varje knapp utför en enskild åtgärd. I åtgärdsfönstret finns även flikar, och varje flik, som i sin tur innehåller en uppsättning relaterade knappar. Om inget annat anges är alla knappar och flikar tillgängliga både i listvyn för sidan **Alla färder** och i den detaljerade vyn för en enskild vald enhet.

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Knappar som visas direkt i åtgärdsfönstret

I följande tabell beskrivs de knappar som finns tillgängliga direkt i åtgärdsfönstret.

| Knapp | beskrivning |
|---|---|
| Nytt | Skapa en färd. <!-- KFM: Link to scenario --> |
| Radera | Ta bort aktuell färd. Det är bara färder som har statusen *Bekräftad* som kan tas bort. När en sådan färd lämnar hamnen och bearbetar varor på väg kan det inte längre tas bort. |
| Sjötransportredigare | Öppna sidan **Färdredigeraren**, där du kan lägga till eller ta bort inköpsrader för den, skapa nya behållare och ändra information om själva inköpsordern. |
| Kostnader för sjötransport | Öppna sidan **Färdkostnader**, där du kan visa och lägga till kostnader för alla varor i färden. När resekostnader läggs till manuellt i resan läggs de automatiskt till **Kostnadsförfrågan** och fördelas på varje vara enligt metoden som anges på sidan **Färdkostnader**. |

### <a name="buttons-on-the-voyage-tab"></a>Knappar på fliken Färd

I följande tabell beskrivs de knappar som finns tillgängliga på fliken **Färd** i åtgärdsfönstret. Den här fliken är bara tillgänglig när du arbetar i listvyn för sidan **Alla färder**.

| Knapp | beskrivning |
|---|---|
| Fraktcontainer | Öppna en sida som visar alla leveransbehållare som är kopplade till den valda färden. Det kan finnas en eller flera behållare. |
| Folio | Öppna en sida som visar alla folio som är kopplade till den valda färden. Det kan finnas en eller flera folio. |

### <a name="buttons-on-the-manage-tab"></a>Knappar på fliken Hantera

I följande tabell beskrivs de åtgärder som finns tillgängliga på fliken **Hantera** i åtgärdsfönstret.

| Knapp | beskrivning |
|---|---|
| Mottagna dokument | Uppdatera den så att alternativet **Dokument som mottagits** ställs in på *Ja*. Du kan använda den här knappen om du vill låsa artikeln och/eller inköpsraden så att den inte kan uppdateras ytterligare. |
| På väg | Uppdatera statusfältet **Färdstatus** till statusen under transport som fastställs på sidan **[Hemtagningskostnad parametrar](landed-cost-parameters.md)**. Det finns ingen ytterligare logik i den här processen. En färd kan också uppdateras automatiskt till statusen under transport baserat på inställningarna i [Spårningskontrollcentret](delivery-information-setup.md).
| Klar för kostnadsredovisning | Uppdatera statusfältet **Färdstatus** till statusen redo för kostnadsredovisning som fastställs på sidan **[Hemtagningskostnad parametrar](landed-cost-parameters.md)**. En färd kan kostnadsredovisas när alla fakturor har bearbetats (både lagerfakturor och kostnadsfakturor) och varorna har tagits emot. Om de uppskattade kostnaderna som är associerade med en avgift inte har kostnadsredovisats, uppstår ett fel när du försöker bearbeta kostnadsredovisningen för en färd. |
| Kostnadsberäknats | Rensa bort eventuella kostnadsredovisningar efter att det finns en faktura för alla inköpsorder och inköpskostnader. När du väljer den här knappen visas dialogrutan **Färd uppdatering - Kostnadsredovisad**. Där kan du välja att bokföra på ett ekonomiskt standarddatum eller ange ett bokföringsdatum och sedan köra åtgärden. Du kan köra åtgärden igen så många gånger du vill. Du kan också använda dialogrutan **Färd uppdatering - Kostnadsredovisad** för att upprätta en plan för hur åtgärden ska köras som en periodisk uppgift (batchjobb). Vi rekommenderar att du regelbundet kör åtgärden genom att ställa in den som ett batchjobb. |
| Bokför inleveranslista | Bokför en inleveranslista för alla inköpsorderrader i färden. Om multiföretagsinställningar används öppnas en ny dialogruta för bokföring av inleveranslistor för varje företag och måste bearbetas i varje juridisk person. |
| Bokför produktinleverans | Bokför en produktinleverans för alla inköpsorderrader i färden. Produktinleveransprocessen för inköpsorderraderna som är associerade med en färd kommer endast att användas om varorna **inte** går igenom bearbetningen av varor under transport. Om varorna ska bearbetas under transport får du ett felmeddelande när du försöker bokföra produktinleveransen för en inköpsorderrad. Om multiföretagsfärd används öppnas en ny dialogruta för bokföring av följesedel för varje företag. |
| Bokför faktura | Bokför en faktura för alla inköpsorderrader i färden. Om varorna i färden går igenom bearbetningen av varor på väg, kommer inköpsorderraderna att faktureras innan inleveransen är klar. När den ursprungliga inköpsordern faktureras skapas de varor på väg som är associerade med de ursprungliga inköpsorderraderna. Dessa order kan sedan tas emot på lagerstället. Om multiföretagsleverans används öppnas en ny dialogruta för bokföring av faktura för varje företag. |
| Leverera överföringsorder | Bokför en överföringsorderfärd för alla överföringsorderrader i färden. När den här knappen är vald är endast överföringsorder tillgängliga för uppdatering. |
| Inleverera överföringsorder | Bokför en inleverans av överföringsorder för alla överföringsorderrader i färden. |
| Inleverera varor på väg | Ta emot alla orderrader som är på väg i färden. Den här knappen är ett av de tre alternativ som är tillgängliga för mottagning av varor på väg i en färd. (De övriga två alternativen är knappen **Skapa införseljournal** som beskrivs senare i denna tabell och mobilappen för distributionslagerhantering.) Det här alternativet är det enklaste alternativet och kommer att behandla varorna i transit från varulageret och till det slutliga destinationslagret. Om du vill ha mer kontroll över processen kan du använda införseljournalen eller en mobil enhet för att bearbeta inleveransen av varor. |
| Sök efter automatiska kostnader | Hitta alla relevanta kostnader. Om dessa kostnader redan har hittats eller uppdaterats visas följande meddelande: "Ej fakturerade kostnadsrader finns. Vill du skriva över dem? Alla kostnader som inte är associerade med den tidpunkten då den skapades kommer att finnas. Färdkostnader som är kopplade till en färd och som har fakturerats kommer inte att skrivas över. |
| Skapa införseljournal | <p>Öppna dialogrutan **Skapa införseljournal**, där du kan skapa en införseljournal som anger en plats. Den här dialogrutan innehåller följande alternativ:</p><ul><li>**Skapa från varor på väg** eller **Skapa från överföringsorder** – Etiketten för det här alternativet ändras beroende på om du använder vara på väg-processen. Ställ in det till *Ja* för att öppna en införseljournalsida där du kan bearbeta en standardinföringsjournal för de varor på väg som är associerade med färden. Om artikeln redan har inkommit till lagerstället vid slutdestinationen läggs den inte till på raderna i införseljournalen.</li><li>**Initiera kvantitet** – Ange det här alternativet till *Ja* om du vill initiera den kvantitet som ska tas emot, baserat på den kvantitet av varor som angetts på färdraden. Om färdraden är delvis inlevererad kommer denna kvantitet att vara den återstående kvantiteten. Vi rekommenderar att du ställer in detta alternativ på *Ja*.</li><li>**Skapa från orderrader** – Ange det här alternativet till *Ja* om du vill ta värdet från orderraderna.</li></ul><p>Den här knappen är ett av de tre alternativ som är tillgängliga för mottagning av varor i en färd. (De övriga alternativen är knappen **Ta emot varor på väg** som beskrivs tidigare i det här registret och mobilappen för distributionslagerhantering.)</p> |
| Periodisera kostnader | Du kan periodisera kostnader där en kostnadstyp har ett redovisningskonto angivet för debet. Den här knappen används normalt när lagret är under transport eller när varor har tagits emot och fakturerats. |
| Aggregera kostnader | Flytta kostnader från nivån för leveransbehållare till färdnivån. Du kan använda den här knappen i ett delat tjänst-/leveransscenario, där flera enheter delar en leveransbehållare eller ett kartongutrymme. Den har till exempel en 40 meters leveransbehållare och en 20 meters leveransbehållare, och fördelningen görs efter volym. I det här fallet kan varorna/enheterna som delar eller använder utrymmet i den 20 meter långa leveransbehållaren bestraffas. Om du vill fördela kostnaderna korrekt, kanske vissa organisationer vill överföra kostnaderna till den och fördela dem baserat på fördelningsmetoden på färdnivå. |
| Ändra resemallen | Öppna en dialogruta där du kan ändra en resmall. När du har ändrat mallen tas färdkostnaderna bort. Därför måste du kanske välja **Sök efter automatiska kostnader** (se beskrivningen tidigare i den här tabellen) eller manuellt lägga till kostnader igen. |

### <a name="buttons-on-the-general-tab"></a>Knappar på fliken Allmän

I följande tabell beskrivs de knappar som finns tillgängliga på fliken **Allmän** i åtgärdsfönstret.

| Knapp | beskrivning |
|---|---|
| Inleveranslista | Öppna en lista över produktinleveranser för alla inköpsorderrader i färden. Om multiföretagsfärder används öppnas en ny inleveranslista för varje företag. Om inga produktinleveranslistor har bearbetats är den här knappen inte tillgänglig. |
| Produktinleverans | Öppna produktinleveransposten för inköpsorderraderna som är kopplade till avbetalningsposten, om denna post används. Om inga produktinleveranser har bokförts är den här knappen inte tillgänglig. Inleveransprocessen för produkter används inte om du använder bearbetning av varor på väg. |
| Artikelinförsel | Öppna artikelinförseljournalen om den används. |
| Spårning | Öppna sidan **Inkommande spårning** där du kan uppdatera förväntat införseldatum för varor i en leveransbehållare och en färd och sedan uppdatera de förväntade leveransdatumen för inköpsorderrader. |
| Kostnadsförfrågan | <p>Öppna sidan **Kostnadsförfrågan**, som visar alla kostnader för en färd.</p><p>Välj **Visa** i åtgärdsfönstret för att justera vyn. Du kan visa alla nivåer samt artikel- och kostnadstypskoden.</p><p>Endast koder för kostnadstyper som är direkt relaterade till lagertransaktioner visas på sidan **Kostnadsförfrågan**. Genom att ta bort kostnadstypkoder kan du justera sidan genom att gruppera kostnader tillsammans. Den här kapaciteten kan vara användbar om du använder storlekar och färger.</p><p>Sidan **Kostnadsförfrågan** visar bara kostnadstypskoder där fältet **Debet** är inställt på *Artikel*.</p> |
| Order för varor på väg | Öppna sidan **Order för varor på väg** som visar posterna för varor på väg endast för den valda artikeln. |

## <a name="lines-view"></a>Radvy

Öppna vyn **Rader** genom att öppna en rad och sedan välja fliken **Rader** i den övre högra delen av färdens rubrik.

### <a name="information-on-the-voyage-header-fasttab"></a>Information på snabbfliken färdens rubrik

Snabbfliken **färdens rubrik** i vyn **rader** för en färd innehåller grundläggande information som beskriver färden. Många av fälten som visas på den här snabbfliken visas även i vyn **huvud**, enligt beskrivningen senare i det här avsnittet.

### <a name="information-on-the-voyage-lines-fasttab"></a>Information på snabbfliken färdens rader

Snabbfliken **färdens rader** i vyn **rader** av en färd är relaterad till reseinformation och kostnadsinformation som gäller på färdnivå. Här kan du granska leveransbehållare, folio och artiklar som är kopplade till färden. Även pris och kvantitet för artiklarna i färden visas. Du kan visa vilken leveransbehållare eller folio som helst som finns i listan genom att välja relevant länk.

### <a name="information-on-the-line-details-fasttab"></a>Information på snabbfliken raddetaljer

Snabbfliken **Raddetaljer** i vyn **Rader** för en färd ger mer information om raden som för närvarande är vald på snabbfliken **Färdrader**. Observera att det på den här snabbfliken ingår information om var varje rad ryms i behållaren och att den deklarerade kvantiteten.

## <a name="header-view"></a>Huvudvy

Öppna vyn **Huvud** genom att öppna en rad och sedan välja fliken **Huvud** i den övre högra delen av färdens rubrik.

### <a name="settings-on-the-general-fasttab"></a>Inställningar på snabbfliken Redovisning

I tabellen nedan beskrivs fälten som är tillgängliga på snabbfliken **Allmänt** i vyn **Huvud** för en färd.

| Fält | beskrivning |
|---|---|
| Sjötransport | Ange färd- eller flygnummer. |
| Bokningsreferens | Om din speditör eller fraktcenter tillhandahåller ett referensnummer för att identifiera färden (d.v.s. speditörens eller fraktcenters interna referens) anger du det här. |
| Fartyg | Ange eller välj fartyg. Om fartyget inte anges som ett värde kan du ange ID:t som fritext. I sådana fall uppdateras inte huvudregistret, så att ditt lösenords-ID kan väljas i det här fältet senare. |
| ID för extern sjötransport | Ange det allmänt tillgängliga ID:t för den tillgängliga färden (t.ex. flygnummer). |
| Huvud för flygfraktsedel/fraktsedel | Ange huvudfraktsedel eller fraktsedelnummer. Du kan ange detta värde när du skickar med flyg. |
| HAWB/fraktsedel | Ange flygfraktsedeln eller fraktsedeln för leveransbehållaren. |
| Hyra | Markera den här kryssrutan om du vill ange att behållaren är en hyresbehållare som måste returneras. |
| beskrivning | Ange en beskrivning av den för att göra det enklare att känna igen. |
| Sjötransportens status | Statusen för färden. Bland värdena finns *Skapad*, *På väg*, *Dokument som mottagits* och *Kostnadsberäknad*. Det här fältet är inte beräknat baserat på logik. Den uppdateras bara via bokföringsåtgärden. Värdet *kostnadsberäkna* som anger att en faktura för lagret och alla kostnader har tagits emot. Om inte en faktura tas emot kan en kund inte uppnå statusen *kostnadsberäknad*. |
| Status på inköpsorder | Den högsta statusen som har nåtts bland alla inköpsorder som är kopplade till denna. |
| Mottagna dokument | Ett värde som anger om ditt företag har tagit emot alla dokument som är kopplade till färden. Om du vill ändra värdet väljer du **Dokument som mottagits** i gruppen **Uppdatering av färd** på fliken **Hantera** i åtgärdsfönstret. |
| Speditör | Välj transportföretag för den här färden. Detta fält kan användas för att bestämma automatiska kostnader. |
| Namn | Namnet på det företag som är valt i fältet **transportföretag**. |
| Mått | Det här fältet gör att en mätning kan anges i en automatisk kostnad. Mått används ofta av organisationer som inte känner till den individuella volymen eller vikten av varorna, men som kräver en mer korrekt fördelning än alternativen för belopp och kvantitet. Fraktspeditören ger med vikt- eller kubiska mått och du kan lägga den på antingen en artikel eller inköpsorder.. Den kan uppdateras automatiskt om parametern väljs eller anges manuellt. |
| Måttenhet | Måttenheten som gäller för numret i fältet **Mått**. |
| Antal lastpallar | Ange antalet lastpallar på färdraden. Det här fältet uppdateras automatiskt om alternativet **Automatiskt uppdatera antalet kartonger** är inställt som *Ja* på fliken **Allmänt** på sidan **Parametrar för hemtagningskostnad**. |

### <a name="settings-on-the-delivery-fasttab"></a>Inställningar på snabbfliken Leverans

I tabellen nedan beskrivs fälten som är tillgängliga på snabbfliken **Leverans** i vyn **Huvud** för en färd.

| Fält | beskrivning |
|---|---|
| Skapades datum och klockslag | Det datum och den tid då färdposten skapades. |
| Datum för fritt fabrik | I det här fältet väljer du det tidigaste ex-fabriksdatumet bland de inköpsorder som är kopplade till färden. Datumet för ex-fabrik är tillgängligt i inköpsorderrubriken och uppdateras med spårningskontrollfunktionen. |
| Transportdatum | Det beräknade datumet när planet eller fartyget lämnar ursprungsorten. |
| Avresedatum | Avresedatum är vanligtvis det datum när flyget eller fartyget lämnar den utländska porten. Transportdatum och utgående datum behöver inte matcha. Fältet **Avresedatum** är endast till för information. Det används inte för att uppskatta det förväntade leveransdatumet. Spårningskontrollfunktionen används för uppskattning av förväntat leveransdatum och detta fält kan ställas in så att det fylls i automatiskt med spårningskontrollfunktionen. |
| Datum för till butik | Detta fält väljer det tidigaste datumet då varorna från de inköpsorder som är kopplade till färden den ska vara tillgängliga för försäljning. |
| Uppskattat leveransdatum | Det uppskattade leveransdatumet är vanligtvis det datum då varorna ska ankomma till lagerstället. Det här fältet är bara avsett för information. Det används inte för huvudplanering för varor. Det förväntade leveransdatumet på inköpsorderraden används i huvudplaneringen för varor i en sådan och uppdateras med hjälp av spårningskontrollfunktionen. Fältet kan ställas in så att det uppdateras när fylls i av spårningskontrollfunktionen. |
| Faktiskt leveransdatum | Det tidigaste leveransdatumet, baserat på de varor som är kopplade till färden. |
| Beräknad ankomst vid leveranshamn | Ange det datum då du förväntar dig att den ska ankomma till leveransporten, baserat på informationen som din transportagent har tillhandahållit. |
| Mottagna originaldokument | Ange datumet när originaldokumenten togs emot. |
| Mäklaren har informerats | Ange datumet när mäklaren informerades. |
| Ursprungligt fraktsedel skickad | Ange datumet när den ursprungliga fraktsedeln skickades. |
| Varor som frisläppts | Ange det datum då varorna frisläppts från tull. |
| Kundmöte | Ange datumet för kundbokningen, vilket är det datum då du förväntar dig att kunden ska vara ägare till varorna. |
| Levererad vid distributionslager | Ange datumet när varorna levererades till lagerstället. |
| Verifieringsdatum | Ange verifieringsdatumet. |
| Leveransinstruktioner | Ange datum då leveransinstruktionerna togs emot. |
| Leveranssätt | Det här fältet ger information om den metod som används för att leverera färden av och kostnadsurvalet för automatiska kostnader som är kopplade till denna leveransmetod. |
| Från hamn | Leveransporten som färden avgår från. |
| Till hamn | Leveransporten där färden anländer. Leveransbehållare kan olika portar eftersom den kan stoppas vid flera portar. Genom att verifiera "till"-porten på leveransbehållarnivå anger du korrekt portinformation för varje leveransbehållare på en färd. Automatisk kostnad som associeras med frakten bestäms utifrån kombinationen av leveransbehållartyp, "till"-port och "från"-porten. |
| Lokal vidarebefordrare | Det här fältet är bara avsett för information. Den lokala vidarebefordraren bör väljas från leverantörsregistret. |
| Datum för lokal transport | Det datum som den lokala transporten är bokad för. Det här fältet kan hjälpa lagerstället att planera. |
| Tid för lokal transport | Den tidpunkt som den lokala transporten är bokad för. Det här fältet kan hjälpa lagerstället att planera. |
| Resemall | Den resmall för sådd som angetts för färden. Färdmallen används för att ange "till"-porten och "från"-porten i leveransbehållaren och färden. De värdena i sin tur hjälper till att identifiera de automatiska kostnader som associeras med färden. |

### <a name="settings-on-the-other-fasttab"></a>Inställningar på snabbfliken Andra

I tabellen nedan beskrivs fälten som är tillgängliga på snabbfliken **Andra** i vyn **Huvud** för en färd.

| Fält | beskrivning |
|---|---|
| Kommentarer | Ange ytterligare information som är relaterad till färden. |
| Värderingsdatum | Välj det tidigaste ex-fabriksdatumet för de inköpsorder som är kopplade till färden. |
| Väntande sjötransport | Detta kan du använda för att ange om leveransen eller färden har avgått. Detta är endast för informationssyften.  |
| Ändra namn på leveransbehållare | För färder som har mer än en behållare har antalet behållare som ännu inte inkommit. |

## <a name="voyage-update-periodic-tasks"></a>Färduppdatering av periodiska uppgifter

Modulen **Hemtagningskostnad** innehåller flera färdrelaterade periodiska uppgifter som kan massuppdatera flera aspekter av färder. Om du vill köra eller planera dessa periodiska uppgifter går du till **Hemtagningskostnad \> Periodiska uppgifter \> Färduppdateringar** och välj sedan en av följande uppgiftstyper:

- **Mottagna dokument** – I den här uppgiften kan du ange **Mottagna dokument** som *Ja* för flera dokument samtidigt. Använd **filter** inställningarna för att definiera den uppsättning färder som du vill uppdatera.
- **På väg** – Denna uppgift låter dig ange fältet **Färdstatus** till den status på väg som etableras på sidan **[parametrar för hemtagningskostnad](landed-cost-parameters.md)** för flera färder samtidigt. Använd **filter** inställningarna för att definiera den uppsättning färder som du vill uppdatera.
- **Redo för kostnadsredovisning** – Denna uppgift låter dig ange fältet **Färdstatus** till den status redo för kostnadsredovisning som etableras på sidan **[parametrar för hemtagningskostnad](landed-cost-parameters.md)** för flera färder samtidigt. Vanligtvis ställer du in den här uppgiften så att den körs på ett vanligt schema.
- **Kostnadsberäknad**  – Med den här uppgiften kan du ställa in fältet **Färdstatus** till den kostnadsberäknad status som upprättas på sidan **[parametrar för hemtagningskostnad](landed-cost-parameters.md)** för flera resor samtidigt, förutsatt att de har kostnadsberäknats men ännu inte har uppdaterats om färden. Vanligtvis ställer du in den här uppgiften så att den körs på ett vanligt schema.
