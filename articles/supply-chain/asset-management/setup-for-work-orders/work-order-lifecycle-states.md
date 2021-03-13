---
title: Livscykeltillstånd för arbetsorder
description: Det här avsnittet innehåller förklaringar av arbetsorderns livscykeltillstånd i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderLifecycleState, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2a8052942ff97c9e8033d5915723e82c42f964c8
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021589"
---
# <a name="work-order-lifecycle-states"></a>Livscykeltillstånd för arbetsorder


[!include [banner](../../includes/banner.md)]

 

Arbetsorderns livscykeltillstånd definierar de tillstånd som en arbetsorder kan gå igenom. Exempel: **Skapad**, **Schemalagd**, **Pågående** och **Avslutad**. Livscykeltillstånd för arbetsorder kan uppdateras manuellt på en arbetsorder eller uppdateras automatiskt (t.ex. under arbetsorderplaneringen).

De livscykeltillstånd för arbetsorder som krävs för dina arbetsorder måste kopplas till matchande projektfaser på sidan **Parametrar för projekthantering och redovisning** (**Projekthantering och redovisning** \> **Parametrar för projekthantering och redovisning**). Du ställer först in projektfaser i Projekthantering och redovisning. Du ställer sedan in arbetsorderns livscykeltillstånd och arbetsorderns livscykelmodeller Tillgångshantering.

I följande tabell beskrivs alternativen i avsnitten **Arbetsorder** och **Tidsplan** på snabbfliken **Allmänt** på sidan **Livscykeltillstånd för arbetsorder** (**Tillgångshantering** \> **Inställning** \> **Arbetsorder** \> **Livscykeltillstånd**).

![Sidan Livscykeltillstånd för arbetsorder](media/09-setup-for-work-orders.png)

| Namn på alternativ                   | Beskrivning |
|-------------------------------|-------------|
| Aktiva                        | Ställ in det här alternativet på **Ja** om arbetsordern ska vara aktiv när den är i detta livscykeltillstånd. |
| Lägg till rad                      | Ställ in det här alternativet på **Ja** om arbetsorderjobb kan läggas till i en arbetsorder som är i det här livscykeltillståndet. |
| Radera                        | Ställ in det här alternativet på **Ja** om en arbetsorder kan tas bort när den är i detta livscykeltillstånd. |
| Ta bort rad                   | Ställ in det här alternativet på **Ja** om arbetsorderjobb kan tas bort från en arbetsorder som är i det här livscykeltillståndet. |
| Tillåt schemaläggning              | Ställ in det här alternativet på **Ja** om en arbetsorder kan planeras när den är i detta livscykeltillstånd. |
| Ställ in faktisk starttid              | Ställ in det här alternativet på **Ja** om användaren ska uppmanas att välja ett faktiskt startdatum och starttid för en arbetsorder när den uppdateras till detta livscykeltillstånd. |
| Ställ in faktiskt slut                | Ställ in det här alternativet på **Ja** om användaren ska uppmanas att välja ett faktiskt slutdatum och sluttid för en arbetsorder när den uppdateras till detta livscykeltillstånd. |
| Bokför journaler                 | Ställ in det här alternativet på **Ja** om arbetsorderjournaler ska bokföras automatiskt när en arbetsorder uppdateras till det här livscykeltillståndet. Om ett fel inträffar under journalbokföringen visas ett meddelande och uppdateringen av livscykeltillståndet för arbetsordern avbryts. Om du vill visa journalraderna för en arbetsorder väljer du **Tillgångshantering** \> **Allmänt** \> **Arbetsorder** \> **Alla arbetsorder**, **Aktiva arbetsorder** eller **Mina aktiva arbetsorder**, väljer arbetsordern i listan och väljer **Journaler**. Den här inställningen av automatisk bokföring av arbetsorderjournal i ett visst livscykeltillstånd är densamma som du väljer **Bokför journaler** på sidan **Arbetsorderjournaler**.<p>**Obs!** Om du ställer in detta alternativ till **Ja** bokförs journaler automatiskt om inget godkännandearbetsflöde har ställts in. Om ditt företag använder inställningarna för journalgodkännande som har konfigurerats på sidan **Journalgodkännande** (**Projekthantering och redovisning** \> **Inställningar** \> **Journaler** \> **Journalgodkännande**) måste en chef eller ansvarig validera och bokföra förbrukningsregistreringar.</p> |
| Bearbeta underhållschecklista | Ställ in det här alternativet på **Ja** om alla bifogade underhållschecklistor ska behandlas när en arbetsorder uppdateras till det här livscykeltillståndet. Under bearbetningen bokförs alla räknarregistreringar som gjorts på en underhållschecklista och resultatet av hela underhållschecklistan utvärderas. Rader med underhållschecklistor som har resultaten **Godkänd** och **Underkänd** utvärderas, och om minst en rad underkänns markeras hela underhållschecklistan som **Underkänd** i Tillgångshantering. |
| Klart                         | Ställ in det här alternativet på **Ja** om planeringsstatus för arbetsorderjobbet för alla arbetsorderjobb som skapas på en arbetsorder automatiskt ska uppdateras till **Klar** när arbetsordern uppdateras till detta livscykeltillstånd. |
| Startdatum                         | Ställ in det här alternativet på **Ja** om planeringsstatus för arbetsorderjobbet för alla arbetsorderjobb som skapas på en arbetsorder automatiskt ska uppdateras till **Startat** när arbetsordern uppdateras till detta livscykeltillstånd. |
| Slutdatum                           | Ställ in det här alternativet på **Ja** om planeringsstatus för arbetsorderjobbet för alla arbetsorderjobb som skapas på en arbetsorder automatiskt ska uppdateras till **Avslutat** när arbetsordern uppdateras till detta livscykeltillstånd. |
| Ta bort rader i tidsplan         | Ställ in det här alternativet på **Ja** om planering för alla arbetsorderjobb som skapas på en arbetsorder som redan har planerats ska tas bort när arbetsordern uppdateras till detta livscykeltillstånd. Med andra ord tas kapacitetsreservationer för tillgången, den relaterade underhållsarbetaren och de relaterade verktygen bort. Du kan till exempel ange det här alternativet till **Ja** för ett livscykeltillstånd för arbetsorder med namnet **Uppskattat**. När en arbetsorder sedan återställs till det här livscykeltillståndet eftersom en omplanering krävs, kan tidsplaneringen tas bort på den arbetsordern. |

## <a name="set-up-project-stages-and-work-order-lifecycle-states"></a>Ställa in projektfaser och arbetsorders livscykeltillstånd

1. Välj **Projekthantering och redovisning** \> **Inställningar** \> **Parametrar för projekthantering och redovisning**.
2. På fliken **Projektfas**, för varje fas som du vill använda, markerar du kryssrutan för varje projekttyp som krävs för dina arbetsorder. Projekttyperna definierar regler för de ekonomiska uppgifter som är tillåtna. Exempel på ekonomiska uppgifter är att skapa en prognos, skapa uppskattningar och skapa ingående saldon.

    > [!IMPORTANT]
    > Om en projektfas inte har valts för en projekttyp, men projektfasen används för en arbetsorders livscykeltillstånd, uppdateras inte arbetsorderprojekt på lämpligt sätt.

3. Stäng sidan **Parametrar för projekthantering och redovisning**.
4. Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Livscykeltillstånd**.
5. Skapa ett nytt livscykeltillstånd för arbetsorder genom att välja **Nytt**.
6. I fältet **livscykeltillstånd** anger du ett ID för livscykeltillståndet.
7. Ange sedan ett namn i fältet **Namn**.

    På snabbfliken **Detaljer** visar fältet **Livscykelmodeller** antalet livscykelmodeller för arbetsorder som använder det här livscykeltillståndet.

8. På snabbfliken **Allmänt**, i avsnittet **Arbetsorder**, väljer du de funktioner som ska vara tillgängliga för detta livscykeltillstånd genom att ange de relevanta alternativen till **Ja**. En beskrivning av alternativen finns i tabellen tidigare i det här avsnittet.
9. I avsnittet **Projekt**, i fältet **Fas**, väljer du den projektfas som ska vara relaterad till detta livscykeltillstånd.
10. I avsnittet **Projekt** ställer du in alternativet **Stäng aktiviteter** till **Ja** om projektaktiviteter som är relaterade till varje arbetsorderjobb ska stängas automatiskt när arbetsordern befinner sig i det här livscykeltillståndet.

    > [!NOTE]
    > Om du vill hitta det numret på projektaktiviteten som är relaterad till ett arbetsorderjobb väljer du **Tillgångshantering** \> **Allmänt** \> **Arbetsorder** \> **Alla arbetsorder**, **Aktiva arbetsorder** eller **Mina aktiva arbetsorder**. Öppna arbetsordern och välj sedan arbetsorderjobbet. Aktivitetsnumret visas i fältet **Aktivitetsnummer** i avsnittet **Projekt** på fliken **Allmänt** på snabbfliken **Radinformation**.

11. I avsnittet **Prognos** ställer du in alternativet **Kopiera timprognos**, **Kopiera artikelprognos** och/eller **Kopiera utgiftsprognos** till **Ja** om projektprognoser för arbetsorder ska automatiskt kopieras till arbetsorderjournaler när arbetsordern är i det här livscykeltillståndet.
12. Ange ett av alternativen i avsnittet **Tidsplan** till **Ja** om tidsplanstatus för arbetsorderjobb ska uppdateras när arbetsordern befinner sig i det här livscykeltillståndet. Beskrivningar av alternativen **Klart**, **Start**, **Slut** och **Ta bort tidsplansrader** finns i tabellen tidigare i det här avsnittet.

    > [!NOTE]
    > Om du vill visa tidsplansrader som är relaterade till arbetsorderjobb väljer du **Tillgångshantering** \> **Allmänt** \> **Arbetsorder** \> **Alla arbetsorder**, **Aktiva arbetsorder** eller **Mina aktiva arbetsorder**. Öppna arbetsordern, välj arbetsorderjobbet på snabbfliken **Arbetsorderjobb** och visa relaterad information på snabbfliken **Radinformation**. I fältet **Status** fliken **Tidsplan** visas status för arbetsorderjobbet. Fältet **Status** kan ställas in på följande värden: **Tidsplanerat**, **Klart**, **Startat**, **Stoppat** och **Avslutat**.

13. I avsnittet **Underhållsbegäranden** i fältet **Livscykeltillstånd** väljer du livscykeltillstånd för underhållsbegäranden som relaterade underhållsbegäranden ska uppdateras till. Den här uppdateringen sker automatiskt. Det kan bara göras om livscykeltillståndet för underhållsbegäran har valts i den livscykelmodell för underhållsbegäranden som används för underhållsbegäran.
14. I avsnittet **Tillgång** ställer du in alternativet **Uppdatera tillgångsstruktur** till **Ja** om alla artiklar som används på en arbetsorder automatiskt ska uppdateras på sidan **Tillgångsstruktur** när arbetsordern uppdateras till det här livscykeltillståndet. Den här inställningen kan vara relevant om t ex. livscykeltillståndet för arbetsorder definierar arbetsordern som slutförd eller avslutad.
15. I avsnittet **Arbetsorderpool** ställer du in alternativet **Ta bort poolreferens** till **Ja** om arbetsorder som är i det här livscykeltillståndet automatiskt ska tas bort från arbetsorderpooler.
16. På snabbfliken **Validera** väljer du de valideringstyper som ska aktiveras i det här livscykeltillståndet genom att ange de relevanta alternativen till **Ja**. I fältet **Typ** för varje valideringstyp som du väljer, väljer du den typ av meddelande som ska visas om obligatoriska fält som är relaterade till valideringstypen inte har validerats. Om du väljer **Fel** avbryts uppdateringen av livscykeltillståndet för arbetsorder tills de relaterade obligatoriska fälten har uppdaterats i arbetsordern.

    - Alternativen **Underhållsstopp**, **Underhållschecklista**, **Felsymptom**, **Felorsak** och **Felåtgärd** är relaterade till alternativen i avsnittet **Obligatoriskt** på sidan **Arbetsordertyper** (**Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Arbetsordertyper**). Om du vill aktivera dessa valideringar måste de relaterade alternativen också anges till **Ja** på arbetsordertypen som används för arbetsordern.
    - Om alternativet **Underhållschecklista** har inställningen **Ja** för det livscykeltillstånd som en arbetsorder uppdateras till, utförs valideringen för att verifiera att de rader i underhållschecklistan som är markerade som **Obligatoriskt** har registrerats som **Kontrollerat** eller **Inte aktuellt**. Om ingen av dessa registreringar har gjorts på de obligatoriska raderna visas ett informations-, fel- eller varningsmeddelande när arbetsordern uppdateras till detta livscykeltillstånd.
    - Om alternativet **Utfästa kostnader** är inställt på **Ja** för livscykeltillståndet som en arbetsorder uppdateras till, kan det totala beloppet för utfästa kostnader (dvs. det totala utgiftsbelopp som den juridiska personen har åtagit sig att betala) beräknas för varje arbetsorderjobb. Ett meddelande visas om det utfästa kostnadsbeloppet är större än 0 (noll). Du väljer vilka typer av kostnadsutfästelser som ska ingå på snabbfliken **Kostnadsutfästelser** på fliken **Kostnadskontroll** på sidan **Parametrar för projekthantering och redovisning** (**Projekthantering och redovisning** \> **Inställningar** \> **Parametrar för projekthantering och redovisning**).
    - Om alternativet **Underhållsstopp** är inställt på **Ja** för livscykeltillståndet som en arbetsorder uppdateras till görs en validering av underhållsstopp på tillgången som hör till arbetsordern. Om registrering av ett underhållsstopp har gjorts, men det inte finns någon **Avslutat** registrering, visas ett meddelande när arbetsordern uppdateras till detta livscykeltillstånd.
    - Om standardprojektsinställningarna inte innehåller alla faser som du behöver för inställningarna för Tillgångshantering kan du ställa in användardefinierade projektfaser på fliken **Projektfas** på sidan **Parametrar för projekthantering och redovisning**. I bilden nedan visas fliken **Projektfas** på sidan **Parametrar för projekthantering och redovisning**.

    ![Sidan Ställ in projektfaser för olika projekttyper](media/10-setup-for-work-orders.png)

> [!NOTE]
> Om livscykeltillståndet som du uppdaterar en arbetsorder till är inaktivt, raderas automatiskt journaler som är relaterade till arbetsordern, men som ännu inte har bokförts. Detta är ett sätt att garantera automatisk rensning av oanvända data. (Ett livscykeltillstånd är inaktivt om alternativet **Aktivt** för det har inställningen **Nej** på snabbfliken **Allmänt** på sidan **Livscykeltillstånd för arbetsorder**.)
>
> Men om du manuellt ställer in en arbetsorder så att den är inaktiv, raderas **inte** journaler automatiskt som är relaterade till arbetsordern, men som ännu inte har bokförts. (Om du vill inaktivera en arbetsorder manuellt väljer du **Tillgångshantering** \> **Allmänt** \> **Arbetsorder** \> **Alla arbetsorder** eller **Aktiva arbetsorder**. Öppna arbetsordern och växla till vyn **Sidhuvud**. Välj **Redigera** på snabbfliken **Allmänt** och ställ in alternativet **Aktivt** till **Nej**.)

## <a name="relations-among-work-order-lifecycle-models-work-order-types-and-work-order-lifecycle-states"></a>Relationer mellan arbetsorders livscykelmodeller, arbetsordertyper och arbetsorders livscykeltillstånd

Livscykelmodeller avser arbetsflöden och livscykeltillstånd väljs i en livscykelmodell i sekventiell ordning. Livscykel modeller ställs in på arbetsordertyper. Arbetsordertyper bestämmer storleken på och omfattningen för arbetsflöden och arbetsprocesser. Exempelvis kan **Underhåll**, som är en standardtyp av arbetsorder, relateras till en livscykelmodell för arbetsorder som har många livscykeltillstånd. Som kontrast kanske du har en **Korrigerande** arbetsordertyp som används för arbetsorder som inte har planerats, eller för arbetsorder där jobbet har slutförts innan arbetsordern görs på grund av en brådskande situation. Denna typ av arbetsorder kan vara relaterad till en livscykelmodell för arbetsorder som bara har ett fåtal livscykeltillstånd.

Anledningen till att använda typer är att när en typ har definierats på till exempel en arbetsorder eller en tillgång, definieras de relaterade arbetsprocesserna (livscykeltillstånd) automatiskt. För mer information om hur du ställer in arbetsordertyper, se [Arbetsordertyper](../setup-for-work-orders/work-order-types.md).

> [!NOTE]
> Livscykeltillstånd, livscykelmodeller och typer gäller för funktionsplatser, tillgångar och underhållsbegäranden, utöver arbetsorder.

Följande illustration visar relationen mellan arbetsordertyper, livscykelmodeller och livscykeltillstånd.

![Sidan arbetsordertyp jämfört med sidan Livscykelmodeller för arbetsorder](media/11-setup-for-work-orders.png)

## <a name="work-order-lifecycle-models"></a>Livscykelmodeller för arbetsorder

När du har skapat de livscykeltillstånd för arbetsorder som krävs för dina arbetsorder kan de delas upp i livscykelmodeller för arbetsorder. Du bör minst skapa en standardlivscykelmodell.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Livscykelmodeller**.
2. Skapa en ny livscykelmodell för arbetsorder genom att välja **Ny**.
3. I fältet **livscykelmodell** anger du ett ID för livscykelmodell.
4. Ange sedan ett namn i fältet **Namn**.

    På snabbfliken **Detaljer** visar fältet **Livscykeltillstånd** antalet livscykeltillstånd som väljs i den här livscykelmodellen. Fältet **Arbetsordertyper** visar antalet arbetsordertyper som använder den här livscykelmodellen.

5. På snabbfliken **livscykeltillstånd** väljer du de livscykeltillstånd som ska inkluderas i livscykelmodellen.

    - Om du vill inkludera ett livscykeltillstånd i livscykelmodellen markerar du avsnittet **återstående livscykeltillstånd** och markerar sedan högerpilknappen ![högerpil](media/12-setup-for-work-orders.png) för att flytta den till avsnittet **Valt livscykeltillstånd**.
    - Om du vill inkludera alla tillgängliga livscykeltillstånd i livscykelmodellen markerar du knappen **Välj alla tillgängliga faser** ![Välj alla tillgängliga faser](media/13-setup-for-work-orders.png). Alla livscykeltillstånd flyttas till avsnittet **markerade livscykeltillstånd**.
    - Om du vill ta bort ett livscykeltillstånd i livscykelmodellen markerar du avsnittet **valda livscykeltillstånd** och markerar sedan vänsterpilknappen ![vänsterpil](media/14-setup-for-work-orders.png) för att flytta den till avsnittet **Återstående livscykeltillstånd**.

6. Välj **Uppdateringar av livscykeltillstånd** för att definiera vilka livscykeltillstånd som kan följa ett valt livscykeltillstånd.
7. På snabbfliken **Uppdateringar** i fältet **Tidsplanerat tillstånd** väljer du det livscykeltillstånd som alltid ska väljas för en arbetsorder som du har slutfört en arbetsorderplanering för, oavsett föregående livscykeltillstånd för arbetsordern.
8. I fältet **Ej tidsplanerat livscykeltillstånd** väljer du det livscykeltillstånd som alltid ska väljas för en arbetsorder om tidsplanering för arbetsorder tas bort.
9. Spara arbetsorderns livscykelmodell.

![Sidan Livscykelmodeller för arbetsorder](media/15-setup-for-work-orders.png)
