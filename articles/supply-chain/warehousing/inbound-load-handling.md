---
title: Lagerhantering av inkommande laster för inköpsorder
description: Det här ämnet beskriver lagerhanteringsprocessen för inkommande laster för inköpsorder.
author: omulvad
ms.date: 03/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-21
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 62317f7e42c5392dce32a667f05f22e5c970abc7
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910025"
---
# <a name="warehouse-handling-of-inbound-loads-for-purchase-orders"></a>Lagerhantering av inkommande laster för inköpsorder

Det här ämnet beskriver lagerhanteringsprocessen för inkommande laster för inköpsorder.

För varje inkommande last bör systemet redan ha en relaterad försäljningsorder och den kan också innehålla en relaterad lastspecifikation och/eller transportplan. Mer information om hur du skapar och hanterar inkommande laster finns i [Affärsprocess: planera transport för inkommande laster](/dynamicsax-2012/appuser-itpro/business-process-planning-transportation-for-inbound-loads).

## <a name="overview-how-inbound-loads-are-created-registered-and-received"></a>Översikt: hur inkommande, registrerade och inlevererade laster skapas,

Följande bild visar det typiska flödet för hantering av inkommande laster som har inköpsorderkvantiteter när de anländer till lagret.

![Hanteringsprocess för inkommande last](media/inbound-process.png "Hanteringsprocess för inkommande last")

1. **Leverantören bekräftar inköpsordern.**

    Processen börjar när en inköpsorder registreras i systemet och sedan levereras till en leverantör, som bekräftar ordern. Inköpsordern måste finnas innan du kan skapa en inkommande lastpost. Du kan dock skapa en inkommande last även om ordern inte har bekräftats. För mer information, se [Godkänn och bekräfta inköpsorder](../procurement/purchase-order-approval-confirmation.md).

1. **En inkommande lastpost skapas för att planera införsel och dess innehåll.**

    Den inkommande lastposten representerar en leverantörs leverans av en eller flera inköpsorder. Lasten förväntas anlända till lagerstället som en fysisk transportenhet (t.ex. en lastbilslast). Den inkommande lastposten används i planeringssyfte och gör det möjligt för logistikkoordinatorn att spåra lastens förlopp från leverantören. Den används också för att registrera orderradkvantiteter och hantera status genom lageroperationer, t.ex. införsel- och inlagrat arbete. Laster kan skapas antingen automatiskt eller manuellt och kan antingen baseras på en inköpsorder eller ett avancerat leveransmeddelande (ASN) från leverantören. Mer information finns i [skapa eller ändra en inkommande last](/dynamicsax-2012/appuser-itpro/create-or-modify-an-inbound-load).

1. **Leverantören bekräftar lastavsändaren.**

    När leverantören skickar ut lasten bekräftar logistikkoordinatorn lastleveransen på det mottagande lagerstället. Om det mottagande företaget använder modulen **Transporthantering** utlöses en bekräftelse av inkommande försändelser om andra lasthanteringsprocesser som associeras med de inkommande lasterna. Mer information finns i [bekräfta en last för leverans](/dynamicsax-2012/appuser-itpro/confirm-a-load-for-shipping).

1. **Lasten inkommer till lagret och arbetare registrerar kvantiteter.**

    När en lastbilslast inkommer till den mottagande dockningsplatsen, registrerar lagerarbetarna lastens kvantiteter. När modulen **lagerstyrning** gör arbetare registreringen med hjälp av mobila enheter. Mer information finns i avsnittet [produktinleverans mot inköpsorder - registrering](../procurement/product-receipt-against-purchase-orders.md#registration) och [registrera artikelkvantiteter som inkommer i en inkommande last](#register-item-quantities-arriving).

1. **Registrerade lastkvantiteter bokförs mot inköpsorder.**

    När lastkvantiteterna har registrerats som införda, måste dessa kvantiteter vara produktinleveranser – bokföras i företagets lagerredovisning för att registrera den fysiska lagerökningen. Mer information finns i [Produktinleverans mot inköpsorder - produktinleverans](../procurement/product-receipt-against-purchase-orders.md#product-receipt) och [bokföra registrerade produktkvantiteter mot inköpsorder](#post-registered-quantities).

## <a name="register-item-quantities-that-arrive-on-an-inbound-load"></a><a name="register-item-quantities-arriving"></a>Registrera artikelkvantiteter som ankommer på en inkommande last

Microsoft Dynamics 365 Supply Chain Management har stöd för flera driftsmetoder för registrering av ankomst till beställda produkter. Därför kan du konfigurera systemet så att det motsvarar dina specifika affärsbehov. I det här avsnittet beskrivs hur du registrerar inkommande artikelkvantiteter med hjälp av en mobil enhet när avancerad lagerhantering är aktiverat i systemet. Det finns dock ett alternativt flöde som baseras på att artikelinförseljournal används i stället för en mobil enhet. För mer information om det flödet, se [Registrera artiklar för en avancerad lagerstyrningsaktiverad artikel med hjälp av en artikelinförseljournal](tasks/register-items-advanced-warehousing.md).

När en inkommande last först inkommer till lagret måste lagerarbetarna registrera de artikelkvantiteter som ingår i leveransen. De använder vanligtvis handhållna skannrar. Det här arbetsflödet är endast tillgängligt om följande objekt finns i systemet:

- **En inkommande lastpost som beskriver de artikelkvantiteter som förväntas i leveransen.**

    Normalt bekräftar leverantören inkommande lastpost innan leveransen anländer till lagerstället. Därför har lasten statusen _levererad_. Lagerarbetare kan emellertid även registrera postkvantiteter för laster som har statusen _öppen_ eller _inlevererad_.

- **En meny för mobila enheter som har konfigurerats för att stödja lastmottagning**

    [Mobilappen för distributionslagerhantering](../warehousing/install-configure-warehouse-management-app.md) för mobila enheter stöder följande processer för att skapa arbetsprocesser:

    - Mottagande av lastartikel
    - Mottagande och inleverans av lastartikel
    - Inleverans av blandad registreringsskylt fältet **Källdokument för metod för radidentifiering** för menyalternativ anges till _Mottagande av lastartikel_. Mer information finns i [Inleverans av blandad registreringsskylt](mixed-license-plate-receiving.md).
    - Inleverans av blandad registreringsskylt och artikelinförsel där fältet **Källdokument för metod för radidentifiering** för menyalternativ anges till _Mottagande av lastartikel_. Mer information finns i [Inleverans av blandad registreringsskylt](mixed-license-plate-receiving.md).

    > [!NOTE]
    > Oavsett processen kommer systemet att generera arbete för att utföra kvantiteter som är registrerade på mottagningsplatsen och lägga dem på den vanliga lagringsplatsen. När processen _Mottagande och inleverans av lastartikel_ eller _Inleverans och inlagring för blandad registreringsskylt_ används anvisas får den arbetare som registrerade lastkvantiteten instruktioner av enheten att utföra inlagrat arbete som en del av registreringsuppgiften. Däremot för processerna _Mottagande av lastartikel_ och _Inleverans av blandad registreringsskylt_ är antagandet att inlagrat arbete utförs separat från registreringsuppgiften.

- **En arbetsmall som definierar plockning och inlagrat arbete för inkommande laster**

    Den här artikeln är relaterad till föregående artiklar. Du måste ha minst en arbetsmall för arbetsordertypen _inköpsorder_ och den måste innehålla en uppsättning av jobbtyperna plock/plats.

Med hjälp av den mobila enheten guidas inleveransansvarige genom flödet för registrering av lastkvantitet. Detta flöde inkluderar minst följande steg för varje last-ID:

1. Ange last-ID.
2. Ange artikelnummer för en mottagen artikel.
3. Ange den kvantitet för det artikelnummer som inlevererats.
4. Ange ID-nummer för artikelns ursprungliga plats, om systemet inte är inställt på att automatiskt generera numret.
5. Klicka på **OK**.

När arbetaren har slutfört de här stegen görs följande uppdateringar på motsvarande enheter, förutsatt att kvantiteten på inköpsorderraden på en last och alla lastkvantiteter har registrerats:

| Enhet | Uppdateringar | Sedel |
|---|---|---|
| Lasta | Fältet **Arbetsskapad kvantitet** på lastraden uppdateras för att visa den registrerade kvantiteten. | Värdet **Laststatus** förblir _levererat_ eller _öppet_ om ingen bekräftelse har körts för lasten. Om minst en rad med inlagrat arbete har startats ändras den till _pågående_. |
| Lagertransaktionen för en inköpsorder som tillhör ande lastkvantiteter har registrerats för |<p>De följande fälten uppdateras:</p><ul><li>Fältet <b>kvitto</b> ställs in på <i>registrerad.</i></li><li>Fältet <b>plats</b> uppdateras med koden för den mottagande inlastningsplats. (Den här koden anges i fältet <b>Standardinleveransplats</b> för varje lagerställe.)</li><li>Fältet <b>registreringsskylt</b> uppdateras med det ID-nummer som angavs eller genererades under registreringen.</li><li>Fältet <b>Last-ID</b> uppdateras med numret på den last som kvantiteten har registrerats mot. (Se noteringen.)</li></ul> | Möjligheten att koppla mellan lagertransaktionen för inköpsordern och de kvantiteter som registreras mot lasten introducerades i version 10.0.9 som en valfri funktion som har fått namnet _Associera lagertransaktioner för inköpsorder med last_. Den här funktionen är särskilt bra för operativa flöden där en enda order med inköpta varor levereras som flera laster, eller när en last innehåller kvantiteter för flera inköpsorder. |
| Lagerställe | Arbetet skapas baserat på en arbetsmall, för att instruera arbetaren att flytta de registrerade kvantiteterna från mottagningsplatsen till en vanlig lagringsplats. | Valet av lagringsplats styrs av artikelinförsel. Om inget platsdirektiv har definierats är inlagringsplats för införseln på arbetet tom. |

Observera att lagerarbetare kan registrera inleveransen av en inköpsorder med en eller flera tillhörande last utan att använda processen för _Mottagande av lastartikel_. Följande metoder finns:

- **På den mobila enheten:** Använd _Inleverans av inköpsorderrad_ och _Inköpsorderrad har inlevererats och inlagrats_. (Om det finns fler än en last för kvantiteten på inköpsorderraden kan arbetaren inte använda _Inleverans av inköpsorderrad_. I stället uppmanas arbetaren att använda den enhetsåtgärd som är kopplad till processen _Mottagande av lastartikel_.)
- **På klienten:** Använd artikelinförseljournal.
- **På klienten:** Använd **registrering** åtgärden som kan nås från inköpsorderraden.

> [!NOTE]
> Om inleveransen av inköpsordern har registrerats med någon av föregående metoder, skapas ingen länk mellan lagertransaktionen för inköpsorder och last även när den första funktion _Associera lagertransaktioner för inköpsorder med last_ är aktiverad. Ett undantag till den här regeln är när du använder alternativet **Inleverans av inköpsorderrad** och endast en last har en annan status är _mottagen_ för orderraden.

### <a name="handle-discrepancies-during-registration-of-inbound-load-quantities"></a>Hantera avvikelser vid registrering av inkommande lastkvantiteter

Lagerarbetare kan göra en delvis registrering av inleverans av lastkvantitet. Varje kvitto på kvantitet för delbelastning skapar sedan en separat lagertransaktion som har en kvittosstatus på _Registrerad_ för den registrerade kvantiteten och parti-ID refererar till den ursprungliga inköpsorderraden.

#### <a name="load-under-receiving"></a>Last undermottagning

När en last ankommer, om artikelkvantiteterna är mindre än de kvantiteter som anges i lastposten, kan mottagningspersonalen på lagerstället arbeta direkt i klienten för att redovisa denna avvikelse genom att minska kvantiteten på lastraden så att den matchar den faktiska kvantitet som har ankommit och registrerats.

#### <a name="load-over-receiving"></a><a name="load-over-receiving"></a>Last övermottagning

Övermottagning sker när en last anländer, och artikelkvantiteten överskrider den förväntade lastradens kvantitet. Du kan kontrollera om och till vilken grad övermottagning tillåts under lastregistrering.

Använd fältet **Last övermottagning** för relevant menyartikel för mobilenhet för att kontrollera vad som ska hända när en lagerarbetare försöker registrera en överleverans. Det här fältet är tillgängligt för menyartiklar för mobila enheter som använder följande typer av processer för skapande av arbete:

- Mottagande av lastartikel
- Mottagande och inleverans av lastartikel
- Inleverans av blandad registreringsskylt (när fältet **Källdokument för metod för radidentifiering** anges till _Mottagande av lastartikel_)
- Inleverans och artikelinförsel av blandad registreringsskylt (när fältet **Källdokument för metod för radidentifiering** anges till _Mottagande av lastartikel_)

I följande tabell beskrivs de alternativ som är tillgängliga för fältet **Last övermottagning**.

| Värde | beskrivning |
|---|---|
| Tillåt | Arbetare kan registrera inleverans av kvantiteter som överskrider den återstående oregistrerade kvantiteten för en vald last, men bara om den totala registrerade kvantiteten inte överskrider kvantiteten på inköpsorderraden som är kopplad till lasten (efter justering för överleverans i procent). |
| Spärra | <p>Arbetare kan inte registrera inleverans av kvantiteter som är större än återstående oregistrerad kvantitet för en vald last (efter justering för överleverans i procent). En arbetare som försöker registrera kvitton får ett felmeddelande och kan inte fortsätta förrän han eller hon registrerar en kvantitet som är lika med eller mindre än den återstående oregistrerade lastkvantiteten.</p><p>Som standard kopieras värdet för överleveransen på en lastrad från den associerade inköpsorderraden. När fältet <b>Last överinleverans</b> är inställt på <i>blockera</i> använder systemet överleveransens procentvärde för att beräkna den totala kvantiteten som kan registreras för en lastrad. Detta värde kan dock skrivas över för enskilda laster efter behov. Det här beteendet blir relevant under inleverans av flöden där en del av eller hela den överskjutande kvantiteten som representerar överleveransprocenten för orderraden fördelas oproportionerligt över flera laster. Här är ett exempelscenario:</p><ul><li>Det finns flera laster för en inköpsorderrad.</li><li>Det finns en överleverans i procent som är större än 0 (noll) på inköpsorderraden.</li><li>Kvantiteterna har redan registrerats mot en eller flera laster utan att ta hänsyn till överleveransen i procent.</li><li>Överleveransen inkommer från den senaste lasten.</li></ul><p>I det här scenariot kan en mobil enhet endast användas för att registrera den överskjutande kvantiteten för den senaste lasten om lageradministratören ökar överleveransen i procent för den relevanta lastraden från standardvärdet till ett värde som är tillräckligt stort så att hela överleveransen kan registreras med den slutliga lasten.</p> |
| Spärra endast för stängda laster | Arbetare kan ta emot mer lastradkvantiteter för öppna laster, men inte för laster som har statusen _inlevererad_. |

> [!NOTE]
> Standardvärdet för fältet **Last övermottagning** är _tillåt_. När det här värdet används matchar beteendet det standardbeteende som fanns tillgängligt innan funktionen _Överinleverans av lastkvantiteter_ introducerades i version 10.0.11.

### <a name="put-away-the-registered-quantities"></a>Införa registrerade kvantiteter

När registreringen är slutförd på den mobila enheten uppdaterar åtgärden _inleverans av lastkvantitet_ åtgärden uppdaterar lager- och lagerställeposter för att indikera att kvantiteterna nu finns på den mottagande dockningsplatsen och är tillgängliga för bokning. Ett företags lageroperationer kräver dock vanligtvis att kvantiteterna flyttas från den mottagande dock till det vanliga lagerstället, så att de efterföljande plockningsprocesserna kan utföras. Instruktioner för artikelinförseln förs in i artikelinförsel arbetet som genereras automatiskt när inkommande last registreras som inlevererad.

När lager arbetaren har slutfört artikel införselarbetet, kommer systemet att registrera och spåra resultatet genom att uppdatera uppdateringar flera enheter, som sammanfattas i följande tabell.

| Enhet | Uppdateringar | Sedel |
|---|---|---|
| Lasta | <p>De följande fälten uppdateras:</p><ul><li>Värdet <b>sista status</b> ändras till <i>pågående</i>.</li><li>Värdet <b>arbetsstatus</b> ändras till <i>100,00 % av slutfört arbete</i>.</li></ul> | Värdet **Laststatus** ändras till _Pågår_ när arbetaren startar införseluppgiften för minst en rad inlagrat arbete. |
| Lagertransaktioner för arbete som tillhörande kvantiteter har inlagrats för | Fälten **inleverans** och **plats** och andra relevanta fält uppdateras för att återspegla flyttningen från inleveransplatsen till lagringsplatsen. | Värdet **inleveransstatus** för lagertransaktionen för inköpsordern förblir _registrerad_. |
| Lagerställe | Värdet **Arbetsstatus** ändras till _stängd_. | |

## <a name="post-registered-product-quantities-against-purchase-orders"></a><a name="post-registered-quantities"></a>Bokföra registrerade lastkvantiteter mot inköpsorder

När inkommande produktkvantiteter har registrerats i systemet blir de tillgängliga för reservation i samband med försäljning och andra avgående och interna operationer. Systemet uppdaterar dock inte lagerkontona (interim) ännu. Denna uppdatering kan endast uppstå när de registrerade produktinleveranser bokförs i Operations-teamet.

Om du vill öppna en sida där de kan bokföra en produktinleverans kan medlemmarna i Operations-teamet följa _ett_ av dessa steg:

- Öppna relevant lastpost och välj sedan åtgärden **produktinleverans**.
- Gå till **lagerstyrning \> periodiska uppgifter \> uppdatera produktinleveranser** och ange sedan i fältet **Last-ID** lasten som ska bokföras.
- Öppna relevant inköpsorder och välj sedan åtgärden **produktinleverans**.
- Gå till **Anskaffning och källa \> Inköpsorder \> Tar emot produkter \> Bokför produktinleveransjobb**.

Åtgärden **produktinleverans** är tillgänglig på sidan **last** (och på motsvarande sida för uppdateringsjobbet sidan **uppdatera produktinleveranser**) kan endast uppdatera kvantiteter för produktinleveranser på inköpsorderkvantiteter som har statusen _Registrerad_. Åtgärden **produktinleverans** om är tillgänglig på sidan **inköpsorder** kan dock inkludera kvantiteter i båda bearbetningsstatus (_beställt_ och _registrerat_). Den kan också styra omfattningen av bokföring av produktinleveransen genom ytterligare parametrar, till exempel _Kvantitet för Inleverera nu_ och _registrerad kvantitet och tjänster_.

Endast order som har statusen _bekräftad_ kan vara produktinleverans – bokförd. För icke-bekräftade inköpsorder visas åtgärden **produktinleverans** som ej tillgänglig.

### <a name="post-registered-quantities-from-the-load-page"></a>Bokför registrerade kvantiteter från sidan Last

Till produktinleverans – bokför registrerade kvantiteter från sidan **Last** måste följande förutsättningar vara på plats:

- Lasten måste ha minst en kvantitetsenhet som har statusen _registrerad_.
- Laststatus måste _levererats_.
- Den inköpsorder som är kopplad till lasten måste ha statusen _bekräftad_.

> [!NOTE]
> Om laddningsstatus inte har ställts _levererad_ bekräftar systemet automatiskt belastningen innan produktinleveransen körs. (Laststatusen ställs _leverans_ när en användare registrerar lastens inkommande leverans.)

Till produktinleverans – bokför införselregistreringarna som hör till en vald last, arbetaren väljer **produktinleveransen** på sidan **Last**. Den sida som öppnas har följande nyckelinformation:

- Fältet **kvantitet** i avsnittet **parametrar** på fliken **inställningar** visar den _registrerade kvantiteten_. Här finns inga andra alternativ.
- Rutnätet på snabbfliken **översikt** listar alla inköpsorder som ingår i den valda listan.
- Rutnätet på snabbfliken **rader** listar alla orderrader som har en registrerad kvantitet.

> [!NOTE]
> Kvantiteter för orderrader som visas på fliken **rad** beräknas på olika sätt beroende på om funktionen _Tillåt flera produktinleveranser per last_ är tillgänglig och aktiveras i din version av Supply Chain Management.
>
> | Version | Beräkning |
> |---|---|
> | Versioner före version 10.0.10, och nyare versioner där funktionen _Tillåt flera produktinleveranser per last_ inte är aktiverad | Radantalet är summan av alla registrerade kvantiteter _för den inköpsorderraden_, oavsett om registreringen utförts via flera laster, oberoende av lasten, från en mobil enhet eller från klienten. |
> | Version 10.0.10 och senare där funktionen _Tillåt flera produktinleveranser per last_ är aktiverad | Radens kvantitet är summan av alla registrerade kvantiteter _för lastposten_ som åtgärden **bokföring av produktinleverans** initierades från. |

När användaren väljer **OK** för att bekräfta bokföringen av produktinleveransen sker följande nyckeluppdateringar på lämpliga enheter i systemet.

| Enhet | Uppdateringar |
|---|---|
| Lagertransaktionen för den inköpsorder för vilken radens kvantiteter har inkluderats i bokföringsomfånget | <p>Följande fält uppdateras (men observera att det också finns flera andra uppdateringar):</p><ul><li>Fältet <b>kvitto</b> ställs in på <i>Inlevererad</i>.</li><li>Fältet <b>fysiskt datum</b> uppdateras med datumet för bokföringen.</li></ul> |
| Last som användaren har bokfört produktinleveransen från | Uppdateringar av lasten beror på vilken version som används och inställningen av fältet **Tillåt flera produktinleveranser per last**. Reglerna beskrivs i tabellen som visas senare i det här avsnittet. |

Fältet **Tillåt flera produktinleveranser per last** gör att företag väljer en policy för inkommande lastmottagning. Beroende på de operativa flödena kan det hända att företag väljer att tillåta eller inte tillåta att bokföra flera produktinleveranser för samma last. Vi rekommenderar att logistikchefen ställer in fältet **Tillåt flera produktinleveranser per last** till ett av följande värden:

- **Nej** – Välj detta värde om mottagande av inleveransansvarig på lager alltid ska registrera alla orderkvantiteter som medföljer varje last inom en bestämd tidsram. Om det inte finns några registrerade inleveranser, antar systemet att de inte inkommit eller inte fanns på lasten och därför inte ska betraktas som en del av lasten. Den bokföring av produktinleverans som från en last använder samma antagande. Förutom produktinleverans – uppdatera alla registrerade kvantiteter (dess huvudfunktion), deklarerar programmet lasten som har slutförts och stängts för vidare bearbetning. I det här fallet uppdateras alla lastrader automatiskt till registrerade kvantiteter, lastrader som inte har några registrerade kvantiteter och laststatus ändras till _Inlevererat_.
- **Ja** – Välj detta värde om mottagande av lagerställen kräver mer tid för att registrera alla kvantiteter av den inlevererade lasten, men under tiden måste du vara produktinleverans – bokför de kvantiteter som redan har registrerats. I det här fallet vill du att logistikchefen ska vara öppen även när bokföringsjobbet för produktinleverans har körts, så att återstående lastkvantiteter kan registreras och produktinleverans uppdateras till redovisningen kontinuerligt.
- **Fråga** – Välj detta värde om dina rutiner för lastmottagning är blandade och ett beslut krävs varje gång som bokföring av produktinleverans körs.

I följande tabell sammanfattas effekterna av inställningen **Tillåt flera produktinleveranser per last**.

| Tillåt flera produktinleveranser per last | Lastkvantitet | Laststatus | Sedel |
|---|---|---|---|
| När det här fältet inte är tillgängligt (versioner före 10.0.10) | <p>Lastkvantitet ställs in så att den motsvarar den registrerade kvantiteten.</p><p>Om lastkvantitet uppdateras till 0 (noll), vilket innebär att ingen registrering har gjorts, tas lastraden bort.</p><p>Om det inte finns några lastrader i lasten tas lasten bort.</p> | _Inlevererat_ | Om det finns flera laster för orderradens registrerade kvantitet, uppdateras bara statusen för den last som inleveransen bokfördes från uppdateras till _mottaget_. |
| Nr | <p>Lastkvantitet ställs in så att den motsvarar den registrerade kvantitet som är associerad med last-ID.</p><p>Om inget last-ID har registrerats för lagertransaktionen, matchar beteendet de som finns i versioner före 10.0.10.</p> | _Inlevererat_ | |
| Ja | Inga uppdateringar | _Mottaget_, om den totala registrerade lastkvantiteten är lika med eller större än lastkvantiteten | |
| Ja | Inga uppdateringar | _Levererad_ eller _Pågående_, om den totala registrerade lastkvantiteten är mindre än lastkvantiteten | |

När fältet **Laststatus** är inställt på _Inlevererat_ kan inga fler bokföringar av produktinleverans göras för den lasten. Arbetaren kan dock registrera den återstående orderkvantiteten mot inlevererad last under följande förhållanden. (Mer information finns i avsnitt [Last övermottagning](#load-over-receiving) tidigare i det här avsnittet.)

- Den version av Supply Chain Management som är äldre än version 10.0.11.
- Funktionen _Överinleverans av lastkvantiteter_ är aktiverad och fältet **Övermottagning av lastradens kvantitet** på mobilenhetens menyalternativ för åtgärden mottagande av lastartikel anges till _Allow_.

Till produktinleverans – bokför ytterligare registrerade lastkvantiteter som har statusen _inlevererad_ måste användaren köra bokföringsåtgärden från den associerade inköpsordern.

### <a name="post-registered-quantities-from-the-purchase-order-page"></a>Bokför registrerade kvantiteter från sidan Inköpsorder

För produktinleverans – bokför registrerade kvantiteter från sidan **inköpsorder** användaren slutför följande uppgifter innan han eller hon väljer åtgärden **produktinleverans**:

- Ange fältet **kvantitet** i avsnittet **parametrar** på fliken **inställningar** visar den _registrerade kvantiteten_.
- I fältet **Produktinleverans** ange de nummer för inköpsorder som är inkluderade i bokföringen.

> [!NOTE]
> Radkvantiteten som kommer att inkluderas i bokföringsomfånget är summan av alla registrerade kvantiteter för orderraden, oavsett om kvantitetsregistrering har gjorts över flera laster, oberoende av lasten, från en mobil enhet eller från klienten. Samma regel gäller när bokföring av produktinleverans körs från en last, om detta görs när fältet **Tillåt flera produktinleveranser per last** antingen inte är tillgängligt eller inte är aktiverat.

När användaren väljer **OK** för att bekräfta bokföringen av produktinleveransen sker följande nyckeluppdateringar på lämpliga enheter i systemet.

| Enhet | Uppdateringar |
|---|---|
| Lagertransaktionen för den inköpsorder för vilken radens kvantiteter har inkluderats i bokföringsomfånget | <p>Följande fält uppdateras (men observera att det också finns flera andra uppdateringar):</p><ul><li>Fältet <b>kvitto</b> ställs in på <i>Inlevererad</i>.</li><li>Fältet <b>fysiskt datum</b> uppdateras med datumet för bokföringsåtgärden för produktinleverans.</li></ul> |
| Lasta | Uppdateringar av laster beror på om fältet **Tillåt flera produktinleveranser per last** är tillgängligt och aktiverat. Reglerna beskrivs i nästa tabell. |

I följande tabell sammanfattas effekterna av inställningen **Tillåt flera produktinleveranser per last**.

| Tillåt flera produktinleveranser per last | Lastkvantitet | Laststatus | Sedel |
|---|---|---|---|
| När det här fältet antingen är inaktiverat eller inte tillgängligt (i versioner före 10.0.10) | Inga uppdateringar | Inga uppdateringar har utförts. (Statusen förblir _öppen_, _levererad_, eller _pågående_.) | Eftersom bokföring av produktinleverans initieras från en inköpsorder har inte uppdateringslogiken information om associationen mellan registrerade kvantiteter inom dess omfattning och den last som registreringen registrerades mot. Därför kan den inte välja last för statusuppdateringen. |
| Aktiverad | Inga uppdateringar | <p>En av följande åtgärder inträffar:</p><ul><li>Statusvärdet ändras till <i>mottagen</i> om den totala inlevererade och den inköpta kvantiteten av lagertransaktioner för inköpsorder är mer än eller lika med den kvantitet av lasten som de är kopplade till.</li><li>Statusen förblir <i>Öppen</i>, <i>Levererad</i> eller <i>Pågående</i> om det tidigare villkoret inte uppfylls för alla rader i last.</li></ul> | |

### <a name="select-the-appropriate-product-receipt-posting-option-for-your-logistics-operations"></a>Välj lämpligt bokföringsalternativ för produktinleverans för dina logistikåtgärder

Som tidigare har beskrivits erbjuder systemet två bokföringsalternativ för produktinleverans. Alternativen kan nås på följande platser:

- På sidan **last** eller från menyn **Lagerstyrning \> Periodiska uppgifter** som ett uppdateringsjobb
- På sidan **Inköpsorder** eller från menyn **Anskaffning och källa \> Inköpsorder \> Tar emot produkter** som ett uppdateringsjobb

Företag som använder laster för att planera och hantera transport- och lagerhantering för deras inkommande order bör använda följande funktioner, som är utformade för att användas med laster:

- Åtgärden **Mottagande av lastartikel** på deras mobila lagerenheter, för att registrera införsel av produktkvantitet mot lasten
- Åtgärder för **Bokföring av produktinleverans** som initieras från en last, för att uppdatera lagerredovisningen

> [!NOTE]
> Annan kvantitetsregistrering och funktioner för bokföring av produktinleverans kan användas för att stödja motsvarande inkommande operativa processer. Om du däremot använder dem i stället för särskilda funktioner som fokuserar på laster, kan du angripa dataprecisionen i lastposterna och därför att lasthanteringsflödena är sömlösa.

## <a name="example-scenarios"></a>Exempelscenarier

### <a name="prepare-your-system-to-run-the-sample-scenarios"></a>Förbered systemet för att köra exempelscenarier

Om du vill arbeta i de exempelscenarier som beskrivs i det här avsnittet måste du först kontrollera att alla funktioner som behövs har aktiverats i systemet. De nödvändiga demouppgifterna måste även finnas i systemet.

#### <a name="turn-on-the-required-features"></a>Aktivera de nödvändiga funktionerna

Dessa scenarier kräver funktionen _flera produktinleveranser per last_ och dess förutsättningsfunktion. Administratörer kan aktivera dessa funktioner genom att följa stegen nedan.

1. Öppna arbetsytan **Funktionshantering**. (Mer information om hur du hittar och använder den här arbetsytan finns [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)

1. Aktivera funktionen _Associera lagertransaktioner för inköpsorder med last_ som visas på följande sätt:

    - **Modul:** _Lagerstyrning_
    - **Funktionsnamn:** _Associera lagertransaktioner för inköpsorder med last_

1. Aktivera funktionen för _flera produktinleveranser per last_ som visas på följande sätt:

    - **Modul:** _Lagerstyrning_
    - **Funktionsnamn:** _flera produktinleveranser per last_

#### <a name="enable-sample-data"></a>Aktivera exempeldata

Om du vill arbeta genom dessa scenarier med hjälp av de angivna exempelposterna och värdena måste du använda ett system där standarddemodata har installerats. Du måste också välja den **USMF** juridiska personen innan du börjar.

#### <a name="add-a-menu-item-for-receiving-load-items-when-a-mobile-device-is-used"></a>Lägga till ett menyobjekt för mottagning av lastartiklar när en mobil enhet används

Innan mottagande av inleveransansvarig kan använda en mobil enhet för att registrera inkommande lager som är länkat till en last, måste du skapa menyalternativet mobilenhet för det syftet.

I det här avsnittet skapar du ett menyalternativ för mobila enheter och lägger till dem på en befintlig meny. Lagerarbetaren kan sedan välja menyalternativet i mobilappen för distributionslagerhantering.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyobjekt för mobil enhet** och kontrollera att menyn på din mobila enhet innehåller ett menyobjekt med följande inställningar:

    - **Läge:** _arbete_
    - **Process för att skapa arbete** _Mottagande av lastartikel_
    - **Generera ID-nummer:** _Ja_

    Du kan lämna alla andra inställningar med standardvärden.

    ![Inställning för menykommando på mobil enhet](media/inbound-mobile-menu-items.png "Inställning för menykommando på mobil enhet")

    Mer information om hur du konfigurerar menyartiklar för mobila enheter finns i [ställa in mobila enheter för lagerarbete](configure-mobile-devices-warehouse.md).

2. När du är klar med att ställa in menyalternativet går du till **lagerstyrning \> inställning \> mobil enhet \> meny för mobil enhet** och lägg till den i menystrukturen för dina mobila enheter.

### <a name="example-scenario-1-register-a-load-where-some-items-are-missing"></a>Exempelscenario 1: registrera en last där vissa artiklar saknas

Det här scenariot visar hur du registrerar kvantiteter för en inkommande last där inte alla förväntade kvantiteter finns. Sedan visas hur produktinleveransen för inköpsordern bokförs.

#### <a name="create-a-load-to-plan-receipt-of-a-purchase-order"></a>Skapa en last för att planera inleverans av en inköpsorder

I den här proceduren ska du skapa en inköpsorder och en tillhörande överföring manuellt. Därefter ska du uppdatera lasten för att simulera att den har levererats från leverantören (som uppdaterar laststatus). lagerplanerare kan sedan filtrera lasterna efter **laststatus** för att hitta förväntad inkommande last.

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Välj **Ny**.
1. I dialogrutan **Skapa inköpsorder** ange fältet **Leverantörskonto** till _1001_.
1. Välj **OK** för att stänga dialogrutan och skapa inköpsordern.
1. Den nya inköpsordern innehåller redan en rad under **inköpsorderrader**. Ange följande värden för den här raden:

    - **Artikelnummer:** _A0001_
    - **Lagerställe:** _24_
    - **Kvantitet:** _10_

1. I åtgärdsfönstret, på fliken **Inköp** välj **Åtgärd \> Bekräfta**. Orderstatusen är nu _bekräftad_.
1. I åtgärdsfönstret, på fliken **Lagerställe** välj **Åtgärd \> Workbench för lastplanering**.
1. På sidan **Workbench för lastplanering** i åtgärdsfönstret på fliken **Tillgång och efterfrågan**, välj **Lägg till \> Till ny last**.
1. I dialogrutan **Tilldelning av lastmall** ange fältet **Lastmall-ID** till _20' behållare_.
1. Välj **OK** för att stänga dialogrutan och returnera till workbench.
1. I avsnittet **Laster** välj **Last-ID** för att öppna den nyss skapade lasten.
1. Granska lastrubrik och raddetaljer och lägg märke till följande punkter:

    - På snabbfliken **last** anges fältet **laststatus** anges till _öppen_.
    - I avsnittet **Lastrader** finns en enda rad där fältet **kvantitet** anges till _10_ och fältet **Arbetsskapad kvantitet** anges till _0_ (noll).

    ![Information om last](media/inbound-load-details.png "Information om last")

1. I Åtgärdsfönster, på fliken **Leverera och ta emot** välj **Bekräfta \> Inkommande leverans**. Observera att **laststatus** har ändrats till _levererat_.
1. Anteckna värdet för **Last-ID** så att du kan använda det i nästa procedur.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-load"></a>Registrera inleverans av de kvantiteter som anlänt på lasten

När lasten inkommer till lagrets mottagningsplats registrerar en inleveransansvarig lastkvantitet på en mobil enhet.

1. Använd din mobila enhet för att logga in på lagerstället 24. (I standarddemodata, logga in med _24_ som användar-ID och _1_ som lösenord.)
1. Välj menyalternativ _Mottagande av lastartikel_ som du har skapat för det här scenariot.
1. Ange följande värden genom att följa instruktionerna för datainmatning på skärmen. (Ordningen kan variera beroende på vilken mobil enhet eller emulator som du använder.)

    - **Last**– ange det last-ID som du skapade under den föregående proceduren.
    - **Artikel** – ange _A0001_, vilket är den artikel som förväntas för lasten.
    - **Kvantitet** – ange _9_ som den faktiska kvantiteten som finns på lasten. Observera att kvantiteten är mindre än den förväntade kvantiteten.

1. Fortsätt att gå igenom arbetsflödet, lämna alla andra fält tomma eller ange standardvärden tills din enhet informerar att arbetet har slutförts.

Uppgiften för lastmottagning har nu slutförts och inleveransansvarig kan gå vidare till nästa uppgift. Mottagningspersonalen på lagerstället kommer dock att gå igenom lastposten och se att den inlevererade kvantiteten var mindre än den förväntade kvantiteten. De utför sedan följande steg med hjälp av webbklienten.

1. Gå till **Lagerstyrning \> Laster \> Alla laster**.
1. Sök efter den last som du just har fått i listan. (Du kanske måste markera kryssrutan **Visa stängd** om du vill inkludera inkommande laster som har statusvärdet _levererat_.) Markera sedan länken i kolumnen **Last-ID** för att öppna last.
1. Observera i lastposten att värdet **Laststatus** fortfarande är _levererat_, men värdet **Arbetsskapad kvantitet** det skapade antalet på lastraden har _9_.
1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Leta upp det inköp som du just har fått i listan och välj sedan länken i kolumnen **inköpsorder** för att öppna ordern.
\
1. I snabbfliken **Inköpsorderrader** välj **lager \> visa \> transaktioner**.
1. Granska detaljerna för de två inköpsorder transaktionerna. (Du kanske måste anpassa sidan **lagertransaktioner** för att se fält **Last-ID** till rutnätet.) Du bör se två transaktioner:

    - Transaktionen som har en inleverans _registrerad_ status representerar den registrerings kvantitet på _9_ som kördes mot en specifik last med hjälp av den mobila enheten. **Last-ID** är kopplat till den aktuella transaktionen.
    - Transaktionen som har en inleverans i _beställd_ status representerar den återstående ej registrerade kvantitet orderraden _1_.

#### <a name="product-receiptpost-the-registered-load-quantities-against-purchase-orders"></a>Produktinleverans - post de registrerade lastkvantiteterna mot inköpsorder

I den här proceduren kommer du att bli produktinleverans – bokför det lager som du har registrerat för en last. Som ett resultat av detta kommer det mottagna lagret och dess relaterade kostnader att läggas till i företagets redovisning.

1. Gå till **Lagerstyrning \> Laster \> Alla laster**.
1. Sök efter den last som du har fått i listan. (Du kanske måste markera kryssrutan **Visa stängd** om du vill inkludera inkommande laster som har statusvärdet _levererat_.) Markera sedan länken i kolumnen **Last-ID** för att öppna last.
1. I Åtgärdsfönster, på fliken **Leverera och ta emot** välj **Inleverera \> Produktinleverans**. Om du uppmanas att bekräfta åtgärden väljer du **Ja**.
1. Kontrol lera **rutnätet på** snabbfliken **rader** i dialog rutan Bokför produktinleverans. Du bör se den inköpsorderrad som kvantiteten har registrerats mot den valda last.

    > [!NOTE]
    > I versioner där funktionen _flera produktinleveranser per last_  är inte tillgänglig eller är inte aktiverad, standardkvantiteten som visas i rutnätet **Lastrader** är den totala kvantiteten som har registrerats över alla laster som är associerade med inköpsordern.

1. På snabbfliken **Översikt** kontrollera **produktinleverans** i rutnätet. Lägg märke till att du anger ett nummer som inkluderar ID:t för den valda lasten.
1. Välj **OK** för att bokföra produktinleveransen och stäng dialogrutan **Bokför produktinleverans**.
1. Du går tillbaka till lastinformationen. Observera följande punkter:

    - Fältet **Laststatus** är nu inställt på _mottaget_.
    - På lastraden har värdet **kvantitet** för lasten ändrats från _10_ till _9_ stycken för att matcha den registrerade kvantiteten, men värdet **Arbetsskapad kvantitet** är fortfarande _9_.

Om en inköpsgrupp inte förväntar sig att leverantören ska leverera den resterande orderkvantiteten för 1, kan den stänga ordern genom att uppdatera radens påminnelse till _0_. Om den saknade enheten snart har anlänt till den ursprungliga lasten kan lagerpersonalen utföra en av följande åtgärder:

- Registrera kvantiteten mot samma last. I det här fallet återställs fältet **Laststatus** till _levererad_ och värdet **Arbetsskapad kvantitet** uppdateras till _10_. Det här alternativet är endast tillgängligt i följande situationer:

    - Funktionen _Överinleverans av lastkvantiteter_ är inte tillgänglig eller inte aktiverad.
    - Funktionen _Överinleverans av lastkvantiteter_ är tillgänglig och aktiverad och fältet **Övermottagning av lastradens kvantitet** anges till _Tillåt_.

- Lägg till kvantiteten i en ny eller befintlig last och bearbeta den på vanligt sätt.
- Registrera och/eller ta emot kvantiteten på ett sätt som inte innebär lasthantering.

### <a name="example-scenario-2-register-quantities-that-arrive-on-multiple-inbound-loads-where-some-items-are-missing"></a>Exempelscenario 2: registrera kvantiteter som inkommer på flera ankommande laster där vissa artiklar saknas

I det här scenariot delas en inkommande leverans som är relaterad till en enskild inköpsorder rad i två laster. En inköpsorderrad kan till exempel delas upp i flera laster på grund av fysiska lastbegränsningar på vikt och/eller volym.

Det här scenariot visar också hur du kan bearbeta flera produktinleveranser för samma last. Du registrerar de kvantiteter som inkommer på flera inkommande laster, men kvantiteterna matchar inte de förväntade kvantiteterna. Kostnadsuppdateringarna som sker via bokföringen av produktinleverans utförs flera gånger för samma last.

#### <a name="set-up-load-receiving-policies"></a>Ställ in policyer för lastmottagning

I den här proceduren ska du aktivera flera produktinleveranser med samma last.

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
1. På fliken **laster** ställer du in fältet **Tillåt flera produktinleveranser per last** till _ja_.

#### <a name="create-two-loads-to-plan-receipt-of-a-purchase-order"></a>Skapa två laster för att planera inleverans av en inköpsorder

I den här proceduren ska du skapa en inköpsorder och två laster. Därefter ska du uppdatera varje last manuellt för att simulera att den har levererats av leverantören (som uppdaterar laststatus). lagerplanerare kan sedan filtrera lasterna efter **laststatus** för att hitta förväntad inkommande last.

Du får också lära dig att ställa in inköpsorderraden så att du kan ta emot en kvantitet som är 20 procent mer än den kvantitet som är angiven för raden.

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Välj **Ny**.
1. På snabbfliken **leverantör** ställer du in fältet **leverantörskonto** till _1001_ och väljer sedan **OK**.
1. Den nya inköpsordern öppnas och innehåller en tom rad i rutnätet **inköpsorderrad**. Ange följande värden för den här orderraden:

    - **Artikelnummer:** _A0001_
    - **Lagerställe:** _24_
    - **Kvantitet:** _10_

1. På snabbfliken **Raddetaljer** på fliken **leverans**, ange fältet **Överleverans** till _20_.
1. I åtgärdsfönstret, på fliken **Inköp** välj **Åtgärd \> Bekräfta**. Orderstatusen är nu _bekräftad_.
1. I åtgärdsfönstret, på fliken **Lagerställe** välj **Åtgärd \> Workbench för lastplanering**.
1. På sidan **Workbench för lastplanering** i åtgärdsfönstret på fliken **Tillgång och efterfrågan**, välj **Lägg till \> Till ny last**.
1. I dialogrutan **Tilldelning av lastmall** ange fältet **Lastmall-ID** till _20' behållare_. På fliken **Detaljer** ändra värdet **kvantitet** från _10_ till _5_ för att delvis lägga till inköpsorderradens kvantitet.
1. Välj **OK** om du vill använda inställningarna och stänga dialogrutan.
1. Upprepa steg 8 till och med 10 om du vill skapa en andra last. Den här gången ska fältet **kvantitet** redan vara inställt på _5_.
1. På sidan **workbench för lastplanering** i rutnätet **laster** välj värdet **last-ID** för den första lasten som du skapat. Sidan **lastinformation** visas och visar den valda lasten. Följ dessa steg:

    1. I Åtgärdsfönster, på fliken **Leverera och ta emot** välj **Bekräfta \> Inkommande leverans**.
    1. Observera att värdet **laststatus** har ändrats till _levererat_.
    1. Klicka på knappen stäng om du vill gå tillbaka till sidan **workbench för lastplanering**.

1. Upprepa föregående steg för den andra lasten du skapade.
1. Anteckna de två värdena för **last-ID** som visas i rutnätet **laster**.

#### <a name="register-partial-receipt-of-the-quantities-that-arrived-on-the-first-load-and-post-the-registered-load-quantities"></a>Registrera delvis inleverans av de kvantiteter som anlänt på den första lasten och bokför de registrerade lastkvantiteterna

När lasten inkommer till lagrets mottagningsplats registrerar en inleveransansvarig lastkvantitet på en mobil enhet. Det registrerade lagret som är länkat till en last uppdateras kostnadsuppdateras sedan i företagets redovisning genom att bokföra produktinleveransen för inköpsordern baserat på lasten.

Den här proceduren visar hur en inleveransansvarig kommer att registrera lastkvantiteter på en mobil enhet.

1. Använd din mobila enhet för att logga in på lagerstället 24. (I standarddemodata, logga in med _24_ som användar-ID och _1_ som lösenord.)
1. Välj menyalternativ _Mottagande av lastartikel_ som du har skapat för det här scenariot.
1. Ange följande värden genom att följa instruktionerna för datainmatning på skärmen. (Ordningen kan variera beroende på vilken mobil enhet eller emulator som du använder.)

    - **Last**– ange det första last-ID som du skapade under den föregående proceduren.
    - **Artikel** – ange _A0001_, vilket är den artikel som förväntas för lasten.
    - **Kvantitet** – ange _3_. Observera att kvantiteten är mindre än den förväntade kvantiteten. I det här scenariot ska du anta att du, som inleveransansvarig, inte har tid att registrera alla kvantiteter för den här lasten. Senare i den här proceduren registrerar du de återstående delarna genom att upprepa det här steget och ställa in **kvantitet** på _2_.

1. Fortsätt att gå igenom arbetsflödet, lämna alla andra fält tomma eller ange standardvärden tills din enhet informerar att arbetet har slutförts.
1. I webbklienten, gå till **Lagerstyrning \> Laster \> Alla laster**.
1. Sök efter den last som du just har tagit emot i listan och välj värdet **last-ID** för att öppna lasten. Observera att värdet **Laststatus** fortfarande är _levererat_, men värdet **Arbetsskapad kvantitet** det skapade antalet på lastraden har _3_.
1. I Åtgärdsfönster, på fliken **Leverera och ta emot** välj **Inleverera \> Produktinleverans**. Om du uppmanas att bekräfta åtgärden väljer du **Ja**.
1. I dialogrutan **Bokför produktinleverans** men ändra inte de värden som visas och välj sedan **OK**.
1. Du kommer tillbaka till sidan **lastinformation** för den valda lasten. Observera följande punkter:

    - Fältet **Laststatus** står kvar som _levererad_.
    - På lastraden är värdet **kvantitet** kvantitet för lasten fortfarande _5_ enheter vilket är den ursprungliga lastkvantiteten och värdet för **Arbetsskapad kvantitet** är fortfarande _3_.

1. Slutför registreringen av den återstående kvantiteten på denna last genom att upprepa den här proceduren. I steg 3 ställer du emellertid in fältet **kvantitet** på _2_.

Den mottagande uppgiften för den första lasten är nu slutförd. Två produktinleveranser har skapats, en för varje enskild uppdatering av produktinleveransen som du har kört.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-second-load-and-account-for-the-overdelivered-quantity"></a>Registrera inleverans av de kvantiteter som anlänt på den andra lasten och kontot för den överlevererade kvantiteten

I det här scenariot kommer inleveransansvarig att inkommande registrera en kvantitet som överstiger den kvantitet som finns på lasten. Övermottagning tillåts eftersom systemet är inställt på att tillåta överleverans.

1. Använd din mobila enhet för att logga in på lagerstället 24. (I standarddemodata, logga in med _24_ som användar-ID och _1_ som lösenord.)
1. Välj menyalternativ _Mottagande av lastartikel_ som du har skapat för det här scenariot.
1. Ange följande värden genom att följa instruktionerna för datainmatning på skärmen. (Ordningen kan variera beroende på vilken mobil enhet eller emulator som du använder.)

    - **Last** – ange det andra last-ID som du skapade tidigare.
    - **Artikel** – ange _A0001_, vilket är den artikel som förväntas för lasten.
    - **Kvantitet** – ange _7_, vilket är den återstående kvantiteten som leverantören är auktoriserad att leverera som en del av den totala kvantiteten i inköpsordern på 12 (där 10 är den ursprungliga orderkvantiteten och 2 är den tillåtna överleveransen på 20 procent). Kom ihåg att fem datorer redan har registrerats mot den första lasten.

Den andra lasten har nu uppdaterats med kvantiteten 7 och kan vara produktinleverans – uppdateras baserat på denna kvantitet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]