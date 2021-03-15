---
title: Bekräfta och överför
description: I det här avsnittet beskrivs hur du använder funktionen bekräfta och överför, som gör att användarna kan leverera från lagret innan de slutför allt arbete som är kopplat till dessa laster.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate,WHSWorkTemplateTable,WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6ccfbe30e9d4a0fc4580c7036d222bfca9203a21
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996336"
---
# <a name="confirm-and-transfer"></a>Bekräfta och överför

[!include [banner](../includes/banner.md)]

Funktionen *bekräfta och överför*, som gör att användarna kan leverera från lagret innan de slutför allt arbete som är kopplat till dessa laster. När en leverans tas emot som inkluderar lastrader som inte har plockats helt, ombeds den bekräftade användaren att antingen dela upp de återstående kvantiteterna på en ny last eller annullera de ofullständiga kvantiteterna.

System som har konfigurerats för att tillåta hämtning av stöd scenarier där planerade och delvis lastade laster måste anpassas på grund av nya eller ändrade omständigheter.

Klienten inkluderar logik som gör att en delvis lastad last kan stängas och bekräftas som levererad. Alla återstående utleveranser och lastrader (inklusive fullständiga eller ofullständiga radantal) läggs sedan till i en nyskapad last och leverans, om den här förnyelsen krävs och inställningen tillåter det. Nya leveranser och laster skapas automatiskt baserat på de initiala kriterierna för att skapa och hämta och deras huvudattribut förblir oförändrade. Det finns också ett alternativ för att automatiskt annullera återstående kvantiteter om en arbetsorder ännu inte har skapats och användaren anser att denna annullering är nödvändig.

Den här funktionen har stöd för scenarier där den fullständiga beläggningen inte får plats på en enskild last, eller där en del av lasten lämnar lagret innan resten av lasten är klar för leverans. I dessa scenarier kan de återstående produkterna överföras till en ny last och därmed till en lastbil. Eftersom den här funktionen kan användas med laster som annars är avsedd att kräva fullastad leverans, ger den extra flexibilitet så att transportchefer kan lösa icke-standardiserade eller oförutsedda scenarier.

När en last är delad utför funktionen *Bekräfta och överför* följande åtgärder:

- Nya laster och leveranser skapas efter behov. Varje last eller leverans har de flesta av de attribut som är till för den ursprungliga lasten eller leveransen. Undantaget är laststatus, som kommer att räknas om baserat på arbetsstatus.
- Användaren informeras om att en ny last har skapats. Användaren meddelas även om ID för den nya lasten.
- Lastrader, arbetsrubriker och arbetsrader som delades upp uppdateras med den nya last- och leveransinformationen.
- Om en hel leverans delas, leveransen underhålls och endast lastreferenserna uppdateras. Om leveransen måste delas skapas en ny leverans.

När resterande kvantiteter annulleras, tas eventuella lastrader som inte har plockats bort och som inte har icke-annullerat arbete relaterat till dem borttaget från lasten. Om ett arbete pågår kan användaren bara dela upp lasten. Resterande kvantiteter kan inte annulleras.

Du kan bara dela upp laster som uppfyller följande kriterier:

- En eller flera lastrader har plockade kvantiteter.
- Laststatusen är mindre än den lastade.
- Det finns ingen lastraddata. (Denna data skapas via konsolideringen av ID-nummer på mellanlagringsplatsen och funktionen *bekräfta och överför* stöder inte konsolidering av ID-nummer.)
- Inget lager väntar på paketering på en förpackningsplats. (Funktionen *bekräfta och överför* saknar stöd för lager som har plockats till förpackningsstationen men ännu inte förpackats.)

> [!NOTE]
> Den här funktionen skiljer sig från funktionerna för transportlast, som bör användas i lagerställen som aldrig kan planera och skapa laster innan de plockas, utan att i stället lastas tillgängligt transportutrymme efter att plockningen har slutförts.
>
> Använd funktionen *bekräfta och överför* i situationer där laster vanligtvis planeras och skapas i förväg, men där undantag ibland uppstår där lasten inte passar den tillgängliga transporten (t.ex. lastbil).

## <a name="turn-on-confirm-and-transfer"></a>Aktivera bekräfta och överför

Innan du kan använda funktionen *bekräfta och överför* måste den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *Bekräfta och överför*

## <a name="set-up-confirm-and-transfer"></a>Ställ in bekräfta och överför

Om du vill använda funktionen *bekräfta och överför* måste du aktivera den i alla relevanta lastmallar. Du kan också, beroende på dina behov, förbereda arbetsmallarna så att de stöder funktionen. Om du vill arbeta i ett exempelscenario som finns senare i det här avsnittet konfigurerar du systemet enligt beskrivningen i det här avsnittet. (Det scenariot baseras på **USMF** demodata.)

### <a name="prepare-your-load-templates"></a>Förbereda dina lastmallar

1. Gå till **Lagerstyrning \> Inställningar \> Last \> Lastmallar**.
1. I åtgärdsfönstret, välj **Redigera** för att placera sidan i redigeringsläge.
1. Markera kryssrutan **Tillåt lastdelningen under leveransbekräftelse** för varje befintlig mall där du vill aktivera funktionen. Du kan också välja **ny** om du vill skapa en ny mall och konfigurera den efter behov. Varje last som du skapar med hjälp av mallen ärver den här funktionen. (Om du arbetar med **USMF** demodata aktiverar du funktionen för **20 behållare** lastmallen.)

### <a name="prepare-your-work-templates"></a>Förbereda dina arbetsmallar

Den här inställningen är inte obligatorisk i alla situationer. I exemplet som visas här ser du till att arbete kan delas upp per leverans för att stödja det exempel scenario som ges senare i det här avsnittet. Det finns också andra sätt att uppnå detta resultat.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. I rutnätet i den övre delen av sidan väljer du en befintlig arbetsmall där du vill ställa in funktionen *bekräfta och överför*. (Om du arbetar med **USMF** demodata markerar du **51 välj till fas** arbetsmallen.) Du kan också skapa en ny arbetsmall.
1. I åtgärdsfönstret, välj **Redigera fråga** för att öppna dialogrutan **Försäljning**.
1. I dialogrutan **Försäljning** på fliken **Sortering** välj **Lägg till** om du vill lägga till en rad i rutnätet.
1. I den nya raden anger du följande värden:

    - **Tabell:** *Tillfälliga arbetstransaktioner*
    - **Härlett register:** *Tillfälliga arbetstransaktioner*
    - **Fält:** *leverans-ID*
    - **Sökriktning:** *Stigande*

1. Välj **OK** om du vill spara inställningarna och stänga dialogrutan **Försäljning**.
1. Om du får ett meddelande om att gruppering kommer att återställas väljer **Ja** för att fortsätta.
1. I rutnätet i den övre delen av sidan **Arbetsmallar** välj den mall du just har redigerat och välj sedan i åtgärdsfönstret **Arbetsuppgiftshuvudet delas**.
1. I åtgärdsfönstret, välj **Redigera** för att placera sidan i redigeringsläge.
1. I rutnätet anger du följande värden:

    - **Tabellnamn:** *Tillfälliga arbetstransaktioner*
    - **Fältnamn:** *leverans-ID*
    - **Gruppera efter det här fältet:** Markera den här kryssrutan.

1. Klicka på **Spara** i åtgärdsfönstret.
1. Stäng sidan.

## <a name="scenario"></a>Scenario

Det här scenariot visar ett exempel där plockningsprocessen ännu inte har slutförts, men de artiklar som har plockats hittills måste lastas på en lastbil och levereras ändå. Därför kan användaren dela upp de plockade lastraderna till en ny last. Alla datarelationer kommer sedan att uppdateras automatiskt.

> [!NOTE]
> De specifika värden som beskrivs i det här scenariot baseras på **USMF** demodata. Vi rekommenderar att du använder dessa demodata när du demonstrerar eller lär dig att använda funktionen. Om du inte använder **USMF** demodata kan du ersätta de värden som behövs.

### <a name="step-1-create-a-load-that-has-multiple-load-lines"></a>Steg 1: skapa en last som har flera lastrader

Innan du kan använda den här funktionen måste du ha en last som innehåller flera lastrader. Du måste också se till att plockplatserna har tillräckligt med lager för alla objekt på de försäljningsorder som du skapar. Granska inställningen av platsdirektivet (**Lagerstyrning \> Inställning \> Platsdirektiv**) och anteckna de plockplatser som används för plockplatser av försäljningsorder. Om du måste justera inventeringen, skapa manuella rörelser, använda påfyllning eller använda något annat flöde efter behov.

Om du vill skapa en kvalificeringslast skapar du först tre försäljningsorder genom att följa stegen nedan.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. I åtgärdsfönstret välj **Ny** om du vill öppna dialogrutan **Skapa försäljningsorder**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden (till ett minimum):

    - På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-004* (*Cave Wholesales*).
    - På snabbfliken **Allmänt** anger du fältet **Lagerställe** till *51*.

1. Välj **OK** för att skapa försäljningsordern och stänga dialogrutan **Skapa försäljningsorder**.
1. Den nya försäljningsordern öppnas. I rutnätet **försäljningsorderrader** lägger du till en rad som har följande värden:

    - **Artikelnummer:** *M9200*
    - **Kvantitet:** *40*
    - **Enhet:** *ea*

1. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På åtgärdssfönstret, välj **Reservera parti** för att öppna sidan **Reservation**.
1. Reservera lagret på försäljningsraden och stäng sedan sidan **Reservation**.
1. Upprepa steg 1 till och med 4 om du vill lägga till en andra försäljningsorder för samma kund och lagerställe.
1. Lägg till två försäljningsrader med följande värden: När du har lagt till varje rad ska du reservera lagret för den som beskrivs i steg 6 till 8.

    - **Rad 1:** Ställ in fältet **Artikelnummer** till *M9200*, fältet **Kvantitet** till *30* och fältet **Enhet** till *ea*.
    - **Rad 2:** Ställ in fältet **Artikelnummer** till *M9201*, fältet **Kvantitet** till *20* och fältet **Enhet** till *ea*.

1. Upprepa steg 1 till och med 4 om du vill lägga till en tredje försäljningsorder för samma kund och lagerställe.
1. Lägg till två försäljningsrader med följande värden: När du har lagt till varje rad ska du reservera lagret för den som beskrivs i steg 6 till 8.

    - kvantitet **Rad 1:** Ställ in fältet **Artikelnummer** till *M9201*, fältet **Kvantitet** till *20* och fältet **Enhet** till *ea*.
    - **Rad 2:** Ställ in fältet **Artikelnummer** till *M9202*, fältet **Kvantitet** till *60* och fältet **Enhet** till *ea*.

#### <a name="load-planning-workbench"></a>Workbench för lastplanering

Vid workbench för lastplanering används mall-ID för att skapa leverans och frisläppa försäljningsorder raderna till lagerstället.

1. Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.
1. I fältet **Lagerställe**, välj *51*.

    Nu bygger du lasten för de försäljningsorder som du just har skapat.

1. På fliken **Försäljnings rader** i rutnätet markerar du försäljningsraderna för de nya försäljningsorderna.
1. I Åtgärdsfönster, på fliken **Tillgång och efterfrågan** i gruppen **Lägg till** välj **Till ny last**.
1. I dialogrutan **Tilldelning av lastmall** ange fältet **Lastmall-ID** till *20' behållare*.
1. Välj **OK**.
1. I avsnittet **Laster** på sidan **Workbench för lastplanering** letar du upp det nya last-ID för lagerställe 51 i rutnätet *51*. Rulla åt höger tills du ser kolumnen **Tillåt lastdelningen under leveransbekräftelse**. Kryssrutan ska vara markerad för din last.
1. Markera lasten.
1. På menyn **Frisläpp** ovanför rutnätet väljer du **Frisläpp till lagerställe** för att skapa arbete.
1. I dialogrutan **Frisläpp last till lagerställe**, kontrollera att snabbfliken **Poster att inkludera** visar ditt last-ID.
1. Välj **OK**.

    Meddelandet "bearbetningsåtgärd" kan visas medan systemet skapar leveranserna och arbetet.

1. I avsnittet **Last** på sidan **Workbench för lastplanering** bör lasten ha en laststatus *påfylld*. Välj last och sedan i menyn **Relaterad information** ovanför rutnätet välj **Påfyllnadsinformation** för att se leverans-ID:er som skapades. När du är klar, stäng **Påfyllnader**.
1. I avsnittet **Laster** på sidan **Workbench för lastplanering** väljer du last och sedan i menyn **Relaterad information** ovanför rutnätet **Arbetsuppgifter** för att visa det arbete som har skapats för försäljningsordern.
1. Anteckna de arbets-ID som har skapats. Du kanske måste rulla till höger för att se det försäljningsordernummer och det leverans-ID som är kopplat till arbets-ID:t.

### <a name="step-2-set-up-the-execution-flow-for-mobile-devices"></a>Steg 2: ställa in körningsflödet för mobila enheter

Uppgifter för mobila enheter kräver att information skickas till användaren, t.ex. arbets-ID eller nummer-ID. I fälten är den här informationen vanligtvis avsedd för användare av lagerställe i form av streckkoder som finns i dokumentation, förpackning eller montering. Du slutför stegen i den mobila enheten för scenarion genom att se till att du har identifierat arbets-ID för transaktionerna och nummer-ID för artikeln och platsen i transaktionerna.

1. Logga in på den mobila enheten genom att använda ett användar-ID och lösenord för lagerställe *51*.
1. Välj **utgående**.
1. Välj **försäljningsplockning**.
1. Du kan ange arbets-ID eller nummer-ID. Ange arbets-ID för den första försäljningsordern och välj sedan **Retur**.
1. I fältet **Loc** anger du den plats som ska bekräfta plockningsplatsen. Välj sedan **Retur**.
1. I fältet **LP** ange nummer-ID. Nummer-ID måste stämma överens med artikeln, lagret och platsen för artikeln som plockas från den valda platsen. Välj **Retur** när du är klar.
1. I fälten **Artikel** ange artikelnumret för att bekräfta det objekt som väljs och väljer sedan **Retur**.
1. I fälten **Kvt** ange kvantiteten av artikeln för att bekräfta det objekt som väljs och väljer sedan **Retur**.
1. I fältet **Mål-LP** ange målnummer-ID. Målregistreringsskylt är användardefinierade. Se till att du anger ett nummer-ID som du kommer ihåg. Vi rekommenderar att du använder aktuellt datum plus en tvåsiffrig sekvens (ÅÅMMDD\#\#) som format, t.ex. *19112301*. Välj **Retur** när du är klar.
1. Granska den information som visas. Den här informationen är den *plock* information som nu kommer att bli *Placera* data för placeringstransaktionen. Välj **Retur** när du är klar.

    - Du får ett meddelande **arbetet är slutfört**.

1. Upprepa steg 4 till och med 10 för arbets-ID:t för den andra försäljningsordern.

Nästa steg är att läsa in de två plockade ID-nummer på lastbilen.

1. Logga in på den mobila enheten genom att använda ett användar-ID och lösenord för lagerställe *51*.
1. Välj **utgående**.
1. Välj **försäljningslastning**.
1. Ange det användardefinierade målregistreringsskylt som du skapade för det första arbets-ID:t i föregående procedur. Välj sedan **Retur** för att placera målregistreringsskylten på platsen **FAS**.
1. Ange målregistreringsskylt igen och välj **Retur** för att placera ID-numret på platsen **BAYDOOR**.
1. Upprepa steg 4 till och med 5 för målnummer-ID som du skapade för det andra arbets-ID:t.

De två arbets-ID:na kommer nu att stängas (lastade).

### <a name="step-3-confirm-the-outbound-shipment"></a>Steg 3: bekräfta den utgående leveransen

I det här steget bekräftar du två försäljningsorder och arbete som har slutförts för lasten för att leverera plockade artiklar i lasten och skapa en ny last för de ej plockade artiklarna. Bekräftelse av utgående leverans måste utföras på sidan **Lastinformation**.

1. Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.
1. I avsnittet **Laster** i rutnätet, välj raden för det last-ID som du skapade.
1. Klicka på länken last-ID om du vill öppna sidan med **lastinformation**.
1. På sidan **lastinformation** i åtgärdsfönstret på fliken **Leverera och ta emot** i gruppen **Bekräfta** välj **Utgående leverans** för att börja bekräftelsen.
1. I dialogrutan **leveransbekräftelse** i fältet **lastdelningsmetod under leverans bekräftad** välj *dela kvantitet till ny last*.
1. Välj **OK**.

    Det kan hända att ett meddelande om bearbetning pågår.

    Du får informationsmeddelanden som anger att leveransen har bekräftats och att en ny last har skapats från den delade kvantiteten.

Uppdatera sidan **workbench för lastplanering** för att se den nya lasten.

Du kan också bekräfta att transaktionsrelationerna har uppdaterats på följande sätt:

- De återstående (obearbetade) leverans och leveransraderna uppdateras med det nya last-ID:t.
- Försäljningsordern är kopplad till det nya last-ID:t.
- Den ursprungliga lasten inkluderar inte återstående lastrader.
- Det återstående arbetet har uppdaterats med det nya last-ID:t.
- Påfyllnad förblir oförändrad.
- Statusen för den nya lasten är korrekt uppdaterad. (Om arbetsstatus är _Pågår_, ska även laststatus vara _Pågår_.)

## <a name="notes-and-tips"></a>Anteckningar och tips

- Du kan också aktivera parametern **Tillåt lastdelningen under leveransbekräftelse** efter att lasten har skapats med parametern **lastmall** inaktiverad men innan lastningsprocessen har startat. Gå till önskad last och aktivera sedan parametern i vyn sidhuvud.
- Alternativet **Dela kvantitet till ny last** fungerar även när vissa av de återstående arbetsrubrikerna har statusen *Pågår*. Därför kan du fortfarande använda funktionen även om arbetarna redan kör plockningsorder.
- Om du väljer **Avbryt ej uppfylld kvantitet** när det finns återstående arbete med statusen *Öppen* eller *Pågår* visas följande fel meddelande: "det går inte att avbryta resterande kvantitet för last. Det finns arbete för last."
- Om du väljer **Avbryt ej uppfylld kvantitet** när det inte finns något återstående arbete men det finns lastrader på ingången, visas följande felmeddelande: "Det gick inte att bekräfta inleveransen eftersom kvantiteten för artikeln överskrider procentsatsen som är definierad för under leveransen." Du undviker felet genom att ange procentsatsen **Under leverans** ej frisläppta raderna till 100 procent. Det går inte att flytta frisläppta rader till en ny last, men den aktuella last bekräftas med under leverans. I det här fallet kommer du inte att kunna frisläppa den ursprungliga ordern igen. Därför måste du hantera den på något annat sätt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]