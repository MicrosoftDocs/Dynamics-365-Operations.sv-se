---
title: Kvalitetskontroll
description: Denna artikel innehåller information om funktionen för kvalitetskontroll. Med den här funktionen kan lagerarbetarna göra snabba stickprov för att kontrollera kvaliteten medan de tar emot artiklar på inlastningsplatsen.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: ceb01205edc269690fda306bc90f465dbccc563b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855069"
---
# <a name="quality-check"></a>Kvalitetskontroll

[!include [banner](../includes/banner.md)]

Med funktionen *Kvalitetskontroll* kan lagerarbetarna göra snabba stickprov för att kontrollera kvaliteten medan de tar emot artiklar på inlastningsplatsen. Dessa stickprov är fördelaktiga när arbetarna inspekterar emballage eller andra lätt igenkännbara delar av en artikel. Med hjälp av funktionen kan arbetarna ta en snabbt titt på om något är uppenbart trasigt eller skadat innan det lagerförs på dess inlagringsplats.

Den här funktionen är ett alternativ till standardprocessen för kvalitetskontroll. Den erbjuder större flexibilitet och snabbare bearbetning.

När du använder den här funktionen inträffar införsel och kvalitetskontrollen på följande sätt:

1. När en leverans ankommer registrerar en lagerarbetare införseln. Arbetaren söker också igenom ett ID-nummer för att registrera platsen.
1. Arbetaren gör en snabb kvalitetskontroll och registrerar resultatet (godkänd eller underkänd) för det ID-numret.
1. En av följande åtgärder inträffar:

    - Om kvalitetskontrollen har godkänts accepteras ID-numret och guidas till mottagningsplatsen, som vanligt.
    - Om kvalitetskontrollen misslyckas avvisas ID-numret och befintligt inlagringsarbete för den dirigeras om till en alternativ plats för vidare granskning. En ny kvalitetsorder skapas. Om du vill visa kvalitetsordern som skapas med hjälp av den misslyckade kvalitetskontrollen går du till **lagerhantering \> periodiska uppgifter \> kvalitetshantering \> kvalitetsorder**.

Den här processen kan också ställas in så att alla ID-nummer omedelbart omdirigeras till kvalitetskontrollplatsen.

## <a name="turn-the-quality-check-feature-on-or-off"></a>Aktivera eller inaktivera funktionen kvalitetskontroll

För att använda de funktioner som beskrivs i denna artikel måste funktionen *Kvalitetskontroll* vara aktiverad för ditt system. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.25 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Kvalitetskontroll* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-the-feature-for-the-example-scenario"></a>Ställ in funktionen för det här exempelscenariot

Det här avsnittet innehåller riktlinjer och ett exempel som visar hur du konfigurerar funktionen *Kvalitetskontroll* och förbereder exempeldata för scenariot som ges senare i denna artikel.

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom detta [exempelscenario](#example-scenario) med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

### <a name="quality-check-template"></a><a name="quality-template"></a>Mall för kvalitetskontroll

Mallen för kvalitetskontroll definierar reglerna för att göra snabba stickprov av kvalitet vid mottagandet.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Kvalitetskontrollmall**.
1. Välj **Ny** om du vill lägga till en mall i rutnätet.
1. Ange följande värden för att definiera den nya mallen:

    - **Mallnamn för kvalitetskontroll:** *Lastkajskontroll*

        Ange ett namn som identifierar de principer som används för den här mallen.

    - **Acceptansprincip:** *Fråga användaren*

        Ange om användarna ska uppmanas att acceptera eller avvisa kvaliteten på lagret under bearbetningen av arbetet, eller om kvaliteten automatiskt ska avvisas. De tillgängliga alternativen är *automatiskt avvisa* och *fråga användaren*.

    - **Kvalitetsbearbetningsprincip:** *skapa kvalitetsorder*

        Välj den policy som ska användas när lagerkvalitet avvisas. Följande alternativ är tillgängliga:

        - *Skapa endast arbete* – Skapa bara arbete för att underlätta lagerrörelser.
        - *Skapa kvalitetsorder* – skapa en kvalitetsorder för att underlätta kvalitetstester.

    - **Testgrupp:** *bilaga*

        Ange testgruppen som ska användas i den kvalitetsorder som skapas. Testgrupper ställs in i modulen **Lagerhantering**.

        Lämna alternativet **Destruktiv text** inaktiverat för testgruppen. Det här alternativet definierar om provet ska förstöras under testerna i testgruppen. Om ett destruktivt test används genererar systemet en lagertransaktion när en kvalitetsorder skapas för ett objekt. Den nya lagertransaktionen förutsäger lagerreduceringen för testkvantiteten. Lagerreduktionen inträffar när kvalitetsordern slutförs genom valideringssteget. Lagertransaktionen identifieras som en kvalitetsorder.

### <a name="work-class--quality-check"></a><a name="work-class"></a>Arbetsklass – kvalitetskontroll

Arbetsklasser används för att styra och/eller begränsa den typ av arbetsorderrader som en lagerarbetare kan bearbeta på en mobil enhet.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsklasser**.
1. Skapa en arbetsklass genom att välja **Nytt**.
1. I rubriken anger du följande värden:

    - **Arbetsklass-ID:** *QC-kontroll*

        Ange ett namn som identifierar arbetsklassen.

    - **Beskrivning:** *QC-kontroll*

        Ange en kort beskrivning som anger vad arbetsklassen används till.

    - **Arbetsordertyp:** *kvalitet i kvalitetskontroll*

        Välj den typ av arbetsorder som skapas av arbetsklassen. Välj alltid kvalitet under kvalitetskontroll när du konfigurerar *kvalitet i kvalitetskontroll*.

1. På snabbfliken **giltiga platstyper** lämnar du fältet **platstyp** tomt.

    Om du väljer en platstyp kan du begränsa de platser där artiklar kan placeras efter att de har plockats. Detta fält används när ett platsdirektiv försöker lösa platsen, eller om en lagerarbetare manuellt anger platsen för menyobjektet för mobil enhet.

Mer information om arbetsklasser och hur du skapar dem finns i [skapa en arbetsklass](tasks/create-work-class.md).

### <a name="work-template"></a>Arbetsmall

Arbetsmallar låter dig definiera arbeten som måste utföras i lagret. Typiskt, warehouse arbeten består av ett par åtgärder: en lagerarbetare plockar upp lagersaldot på en plats och sedan lägger de plockade lager ned på en annan plats. En arbetsmall för kvalitetskontroll definierar vilka arbetsprocesser som ska utföra kvalitetskontroller.

#### <a name="purchase-orders"></a>Inköpsorder

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. I rubriken, ange **Inköpsorder** i fältet till *Inköpsorder*.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Välj en arbetsmall som ska innehålla ett kvalitetskontrollsteg. I avsnittet **Översikt** i fältet **Arbetsmall** väljer du *51 IO-inleverans*.
1. I avsnittet **Arbetsmallinformation** lägg märke till att rutnätet har två befintliga rader: en för *Plocka* och en för *Placera*.
1. I avsnittet **Arbetsmallinformation** välj **Ny** om du vill lägga till en rad för kvalitetskontroll i rutnätet. Observera att fältet **radnummer** för den nya raden har värdet *3*.
1. Ställ in följande värden på denna nya rad. Acceptera standardvärden för kvarvarande fält.

    - **Arbetstyp:** *kvalitetskontroll*
    - **Arbetsklass-ID:** *Inköp*
    - **Mallnamn för kvalitetskontroll:** *Lastkajskontroll*

        Välj det unika ID:t för arbetsklassen. Det här värdet används för att konfigurera menykommandona på den mobila enheten och typerna av arbete som dessa menykommandon kan bearbeta.

1. I åtgärdsfönstret, välj **Spara** för att spara ditt arbete hittills.

    Du får ett informationsmeddelande om att "Ogiltig kvalitetskontroll måste komma direkt efter en plockning". Därför måste du ändra värdet för **radnummer** för den rad som du just har lagt till.

1. Följ dessa steg för att ändra värdet för **radnummer** för den nya raden:

    1. I avsnittet **Arbetsmallinformation** väljer du den rad där fältet **Arbetstyp** anges till *Kvalitetskontroll*.
    2. Markera knappen **Flytta upp** eller **Flytta ned** om du vill flytta raden *Kvalitetskontroll* så att den är efter raden *Plocka*.

1. Klicka på **Spara** i åtgärdsfönstret.

#### <a name="quality-in-quality-check"></a>Kvalitet på kvalitetskontroll

Skapa sedan en arbetsmall för kvalitetskontrollen.

1. I rubriken på sidan **Arbetsmallar** ändra värdet på fältet **Arbetsordertyp** till *Kvalitet i kvalitetskontroll*.
1. I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i rutnätet i avsnittet **Översikt**.
1. I den nya raden anger du följande värden:

    - **Arbetsmall:** *51 kvalitetkontroll*

        Ange ett namn för mallen.

    - **Arbetsmallbeskrivning:** *51 kvalitetkontroll*

1. I åtgärdsfönstret, välj **Spara** om du vill göra avsnittet **Arbetsmallinformation** tillgänglig.
1. Medan den nya mallen fortfarande är markerad i avsnittet **Översikt** väljer du **Ny** i avsnittet **Arbetsmallinformation** för att lägga till en rad i rutnätet.
1. I den nya raden anger du följande värden:

    - **Arbetstyp:** *plockning*
    - **Arbetsklass-ID:** *QC-kontroll*

        Välj namnet på [arbetsklass](#work-class) som du skapade tidigare för arbete med kvalitetskontroll.

1. I avsnittet **Arbetsmallinformation** väljer du **Ny** igen för att lägga till en annan rad.
1. I den nya raden anger du följande värden:

    - **Arbetstyp:** *Placera*
    - **Arbetsklass-ID:** *QC-kontroll*

        Välj namnet på [arbetsklass](#work-class) som du skapade tidigare för arbete med kvalitetskontroll.

1. Klicka på **Spara** i åtgärdsfönstret.

Mer information om arbetsmallar finns i [Kontrollera lagerarbete med arbetsmallar och platsdirektiv](control-warehouse-location-directives.md).

### <a name="location-directive--quality-failures"></a>Plats direktiv – kvalitetsfel

Placering av direktiven är regler som hjälper till att identifiera och sätta platserna för lager. I en försäljningsordertransaktion fastställer till exempel ett direktiv platsen där artiklarna ska plockas och var de plockade artiklarna ska inlagras. Du måste konfigurera en platsdirektivregel för att definiera hur misslyckade kvalitetskontroller ska hanteras.

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I det vänstra fönstret anger du fältet **Arbetsordertyp** till *Inköpsorder* för att arbeta med platsdirektiv av den typen.
1. I åtgärdsfönstret, välj **Ny** för att skapa en platsdirektiv för kvalitetskontroller.
1. I rubriken anger du följande värden:

    - **Löpnummer:** Acceptera standardvärdet.
    - **Namn:** *51 till kvalitet*

1. Ange följande värden på snabbfliken **Platsdirektiv**. Acceptera standardvärden för kvarvarande fält.

    - **Arbetstyp:** *Placera*
    - **Plats:** *5*
    - **Lagerställe:** *51*

1. I åtgärdsfönstret **Spara** för att spara dina direktiv och gör **Rader** tillgänglig.
1. På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad. Acceptera standardvärden för kvarvarande fält.

    - **Från kvantitet:** *1*
    - **Till kvantitet:** *1000000*

1. I åtgärdsfönstret **Spara** för att spara den nya raden och gör snabbfliken **Platsdirektivåtgärder** tillgänglig.
1. Medan den nya raden fortfarande är markerad på snabbfliken **Rader** välj **Ny** på snabbfliken **Platsdirektivåtgärder** för att lägga till en rad i rutnätet där, så att du kan konfigurera en åtgärd för raden.
1. I nya rader, ange fältet **Namn** till *Kvalitet*. Acceptera standardvärden för kvarvarande fält.
1. I åtgärdsfönstret välj **Spara** så att knappen **Redigera fråga** i snabbfliken **Platsdirektivåtgärder** är tillgänglig.
1. Medan raden som du just har lagt till fortfarande är markerad på snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga** för att öppna en dialogruta där du kan redigera frågan för åtgärden.
1. På fliken **intervall**, välj **Lägg till** om du vill lägga till frågan.
1. I den nya raden anger du följande värden:

    - **Register:** *platser*
    - **Härlett register:** *platser*
    - **Fält:** *Plats*
    - **Kriterier:** *QMS*

    *QMS*-plats är ett lagerställe för kvalitet.

1. Välj **OK** för att stänga dialogrutan.
1. Du måste nu ändra ordningsföljden för direktiven för inköpsorderplats för lagerställe *51*. Spara det nya *51 till kvalitet* platsdirektivet, uppdatera sidan och markera platsdirektivet i listan. Använd sedan knapparna **Flytta upp** och **Flytta ned** i åtgärdsfönstret för att placera direktivet för lagerställe *51* i följande ordning. (Innan du väljer **Flytta upp** eller **Flytta ned** måste du välja ett platsdirektiv i listan.)

    1. 51 till kvalitet
    2. 51 PO direkt
    3. 51 QMS

### <a name="mobile-device-menu-items"></a>Menyalternativ på mobil enhet

Konfigurera ett menyalternativ så att funktionen för **kvalitetskontroll** kan utföras av mobila enheter.

#### <a name="purchase-putaway"></a>Inlagring av inköp

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I listan, välj menyalternativet **inköpsartikelinförsel**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På avsnittet **Arbetsklasser** välj **Ny** för att lägga till en rad i rutnätet.
1. I den nya raden anger du följande värden:

    - **Arbetsklass-ID:** *QC-kontroll*

        Ange namnet på [arbetsklass](#work-class) som du skapade tidigare för arbete med kvalitetskontroll.

    - **Arbetsordertyp:** *kvalitet i kvalitetskontroll*

1. Klicka på **Spara** i åtgärdsfönstret.

#### <a name="purchase-order-line-receiving"></a>Inleverans av inköpsorderrad

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken anger du följande värden:

    - **Menyalternativnamn:** *Inleverans av inköpsorderrad*
    - **Rubrik:** *Inleverans av inköpsorderrad*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Nej*

1. Ange följande värden på snabbfliken **Allmänt**. Acceptera standardvärden för kvarvarande fält.

    - **Arbetsskapandeprocess:** *Inköpsorderrad har inlevererats och inlagrats*
    - **Generera ID-nummer:** *Ja*
    - **Arbetsmallen:** *51 PO kvitto*

1. Klicka på **Spara** i åtgärdsfönstret.

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Lägg till menykommandot på en meny för mobila enheter

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. Välj menyn **Ankommande** i det vänstra fönstret.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I kolumnen **Tillgängliga menyer och menyartiklar** väljer du det nya menyalternativet **Inleverans av inköpsorderrad**.
1. Klicka på högerpilen om du vill flytta **Inleverans av inköpsorderrad** till en kolumn **Menystrukturen**.
1. I kolumnen **Menystruktur** väljer du **Inleverans av inköpsorderrad** och sedan knappen uppil eller nedpil för att flytta menyalternativet till önskad plats på menyn för den mobila enheten.
1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="example-scenario"></a><a name="example-scenario"></a>Exempelscenario

När du har gjort alla exempel data som du redan har beskrivit och ställt in dem kan du arbeta i det här scenariot för att testa funktionen *Kvalitetskontroll*. De värden som visas i det här scenariot förutsätter att du arbetar med standarddemodata, att du har valt den juridiska personen **USMF** och att du har förberett exempelposterna som beskrivs tidigare i denna artikel. Det här scenariot fungerar även som ett exempel som visar hur funktionen kan användas i en produktionsinställning.

### <a name="create-a-purchase-order"></a>Skapa en inköpsorder

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa inköpsorder** ställ in följande värden:

    - **Leverantörskonto:** *104*
    - **Lagerställe:** *51*

1. Välj **OK** för att stänga dialogrutan och öppna den nya inköpsordern.
1. På snabbfliken **Inköpsorderrader** innehåller rutnätet en ny tom rad. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *M9203*
    - **Kvantitet:** *3*
    - **Enhet:** *PL*

1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="process-quality-check-receiving"></a>Inleverans av processkvalitetskontroll

När inköps ordern har skapats kan den tas emot med hjälp av menyalternativet **Inleverans av inköpsorderrad** och funktionen för *Kvalitetskontroll*.

#### <a name="receive-pallet-1"></a>Inleverera lastpall 1

1. Logga in på mobilappen för distributionslagerhantering en användare i lager ställe *51*. (Ange *51* som användar-ID och *1* som lösenord.)
1. Gå till **inkommande \> inleverans av inköpsorderrader**.
1. I fältet **PONUM** anger du inköpsordernummer.
1. Bekräfta inköpsordernummer.
1. I fältet **LINENUM** anger du numret från den inköpsorderrad som inlevereras. Eftersom ordern bara har en rad i det här scenariot ska du ange *1* i fältet **LINENUM** för varje mottagningssteg.
1. Bekräfta radnumret.
1. I fältet **QTY** anger du kvantiteten som ska inlevereras. Eftersom inköpsordern är för tre lastpallar (*PL*) i det här scenariot och det finns tre mottagningssteg, anger du *1* i fältet **QTY** för varje mottagningssteg.
1. Bekräfta kvantiteten.

    Sidan **kvalitetskontroll** som visas har inga inmatningsfält. Den har bara knappen bekräfta (bockmarkering) längst ned och menyknappen (**≡**) högst upp. (Menyknappen kallas ibland för hamburger eller hamburgerknappen.) För att processen för kvalitetskontroll ska kunna påskyndas bekräftar användaren bara sidan kvalitetskontroll när lastpallen passerar **kvalitetskontrollen**.

    ![Sida för kvalitetskontroll.](media/quality-check.png "Sidan för kvalitetskontroll")

1. Välj knappen bekräftelse om du vill godkänna kvalitetskontrollen för lastpall 1 från rad 1.

    Sidan **inköpsorder: Placera** som visas visar information om det införda arbetet:

    - **LOC:** platsen som identifierats av systemet

        Den här platsen är den avsedda inlagringsplatsen för inleverans av inköpsorder.

    - **LP:** Det systemgenererade ID-numret
    - **Artikel:** *M9203*
    - **Qty:** *1 PL: 100 ea*

    Även artikelbeskrivningen visas.

1. Bekräfta artikelinförselarbetet.

    På sidan **uppgift** för inleverans av inköpsorderrader får du ett meddelande "Arbetet slutfört". Fältet **LINENUM** är tillgängligt så att du kan börja ta emot nästa lastpall.

#### <a name="receive-pallet-2"></a>Inleverera lastpall 2

I det här scenariot avvisas lastpall 2.

1. I fältet **LINENUM** ange *1* och bekräfta radnumret.
1. Fältet **QTY** är nu tillgängligt. Ange *1* och bekräfta kvantiteten.

    Sidan **Kvalitetskontroll** visas. För det här inleveransen avvisas lastpallen för kvalitet och kommer att placeras på *QMS* kvalitetsplats.

1. Markera menyknappen (**≡**) längst upp på sidan och välj sedan **avvisa** på menyn.
1. På sidan **Uppgift** som visas anger du **QMS** som *Placera* plats dit lastpallen ska skickas för vidare granskning.

    Sidan **kvalitet i kvalitetskontroll: Placera** som visas visar information om det införda arbetet:

    - **LOC:** *QMS*

        Den här platsen är den avsedda inlagringsplatsen för inleverans av avvisad kvalitet.

    - **LP:** Det systemgenererade ID-numret
    - **Artikel:** *M9203*
    - **Qty:** *1 PL: 100 ea*

    Även artikelbeskrivningen visas.

1. Bekräfta artikelinförselarbetet.

    På sidan **uppgift** för inleverans av inköpsorderrader får du ett meddelande "Arbetet slutfört". Fältet **LINENUM** är tillgängligt så att du kan börja ta emot nästa lastpall.

Du har nu slutfört kvalitetskontrollen och skapat en kvalitetsorder för den avvisade lastpallen. Om du vill visa den order som skapats gå till **lagerhantering \> periodiska uppgifter \> kvalitetshantering \> kvalitetsorder**.

Kvalitetsordertestning kan nu bearbetas. Kvalitetstestning beskrivs inte i denna artikel.

Mer information om kvalitetshantering finns i [Översikt över kvalitetshantering](../inventory/enable-quality-management.md).

#### <a name="receive-pallet-3"></a>Inleverera lastpall 3

I det här scenariot godkänns lastpall 3.

1. I fältet **LINENUM** ange *1* och bekräfta radnumret.
1. Fältet **QTY** är nu tillgängligt. Ange *1* och bekräfta kvantiteten.

    Sidan **Kvalitetskontroll** visas. För det här inleveransen godkänns lastpallen för kvalitet och kommer att placeras på en inlagringsplatsen i bulk.

1. Välj knappen bekräftelse om du vill godkänna kvalitetskontrollen.

    Sidan **inköpsorder: Placera** som visas visar information om det införda arbetet:

    - **LOC:** platsen som identifierats av systemet

        Den här platsen är den avsedda inlagringsplatsen för inleverans av inköpsorder.

    - **LP:** Det systemgenererade ID-numret
    - **Artikel:** *M9203*
    - **Qty:** *1 PL: 100 ea*

    Även artikelbeskrivningen visas.

1. Bekräfta artikelinförselarbetet.

    På sidan **uppgift** för inleverans av inköpsorderrader får du ett meddelande "Arbetet slutfört". Fältet **LINENUM** är tillgängligt så att du kan börja ta emot nästa lastpall.

1. Markera menyknappen (**≡**) längst upp på sidan och välj sedan **avbryt** för att återgå till menyn.

Nu kan du stänga mobilappen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]