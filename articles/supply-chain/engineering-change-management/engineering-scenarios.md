---
title: Genomgång av funktioner för konstruktionsändringshantering
description: Det här avsnittet innehåller en komplett genomgång som visar hur man arbetar med konstruktionsändringshantering.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 19fab4f6b81eaf6e3605b6668212eece10606360
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987589"
---
# <a name="engineering-change-management-feature-walkthrough"></a>Genomgång av funktioner för konstruktionsändringshantering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en komplett genomgång som visar hur man arbetar med konstruktionsändringshantering. Det går igenom vart och ett av de viktigaste scenarierna:

- Grundläggande funktionskonfiguration
- Hur ett tekniskt företag skapar en ny konstruktionsprodukt
- Hur ett tekniskt företag släpper en konstruktionsprodukt i ett lokalt företag
- Hur ett lokalt företag kan granska och acceptera en produkt som har frisläppts av ett tekniskt företag
- Hur ett lokalt företag kan använda en konstruktionsprodukt i standardtransaktioner
- Hur du lägger till en konstruktionsprodukt i en försäljningsorder
- Så här begär du ändringar av en konstruktionsprodukt genom att skapa en begäran om konstruktionsändring
- Hur du schemalägger och implementerar begärda ändringar genom att skapa en teknisk ändringsorder
- Så här släpper du en produkt som har ändrats

Alla övningar i det här avsnittet använder de standardexempeldata som finns för Microsoft Dynamics 365 Supply Chain Management. Dessutom bygger varje övning på den föregående övningen. Vi rekommenderar därför att du arbetar under övningarna i ordning, från början till slut, särskilt om du aldrig har använt funktionen för konstruktionsändringshantering tidigare. På så sätt får du en fullständig förståelse för funktionen.

## <a name="set-up-for-the-sample-scenario"></a>Ställ in exempelscenario

Om du vill följa det exempelscenario som finns i det här avsnittet måste du först förbereda funktionen genom att göra demodata tillgängliga och lägga till några anpassade poster.

Innan du försöker göra något av övningarna i resten av det här avsnittet följer du instruktionerna i alla följande underavsnitt. Dessa underavsnitt innehåller också flera viktiga inställningssidor som du kommer att använda när du konfigurerar konstruktionsändringshantering för din egen organisation.

### <a name="make-standard-demo-data-available"></a>Gör standarddemodata tillgängliga

Arbeta med ett system där [standarddemodata har installerats](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). I standarddemodata läggs data till flera juridiska demoenheter (företag och organisationer). När du arbetar igenom övningarna använder du företagsväljaren till höger om navigeringsfältet för att växla mellan ett företag (*DEMF*) som anges som en *teknikorganisation* och ett annat företag (*USMF*) som anges som en *driftorganisation*.

### <a name="set-up-an-engineering-organization"></a>Skapa en teknikorganisation

En teknikorganisation som äger den tekniska informationen och ansvarar för produktdesign och produktändringar. Så här ställs teknikorganisationen in.

1. Gå till **konstruktionsändringshantering &gt; inställningar &gt; teknikorganisation**.
1. Välj **Ny** för att lägga till en rad till rutnätet och ställa sedan in följande värden för den:

    - **Teknikorganisation:** *DEMF*
    - **Organisationens namn:** *Contoso Entertainment System Germany*

    ![Lägga till en teknikorganisation](media/engineering-org.png "Lägga till en teknikorganisation")

### <a name="set-up-the-version-product-dimension-group"></a>Ställ in produktdimensionsgruppen för version

1. Gå till **Produktinformationshantering &gt; Inställning &gt; Dimensioner och variantgrupper &gt; Produktdimensionsgrupper**.
1. Välj **Nytt** för att skapa en produktdimensionsgrupp.
1. Ange fältet **Namn** till *Version*.
1. Välj **Spara** om du vill spara den nya dimensionen och läsa in värden på snabbfliken **Produktdimensioner**.
1. På snabbfliken **Produktdimensioner** anger du **Version** som aktiv produktdimension.

    ![Lägga till produktdimensionsgrupp](media/product-dimension-groups.png "Lägga till produktdimensionsgrupp")

### <a name="set-up-product-lifecycle-states"></a>Ställa in produktens livscykeltillstånd

När en konstruktionsprodukt går igenom sin livscykel är det viktigt att du kan kontrollera vilka transaktioner som tillåts för varje livscykeltillstånd. Följ dessa steg för att ställa in produktens livscykelstatus.

1. Gå till **konstruktionsändringshantering &gt; inställningar &gt; produktens livscykeltillstånd**.
1. Välj **Ny** för att lägga till en livscykeltillstånd och ställa sedan in följande värden för den:

    - **Tillstånd:** *Drift*
    - **Beskrivning:** *Drift*

1. Välj **Spara** om du vill spara den nya livscykeltillstånd och läsa in värden på snabbfliken **Aktiverade affärsprocesser**.
1. På snabbfliken **Aktiverade affärsprocesser** väljer du de affärsprocesser som ska vara tillgängliga. I det här exemplet lämnar du fältet **Policy** inställt på *aktiverat* för alla affärsprocesser.

    ![Aktivera affärsprocesser för ett livscykeltillstånd](media/product-lifecycle-states-1.png "Aktivera affärsprocesser för ett livscykeltillstånd")

1. Välj **Ny** för att lägga till en livscykeltillstånd och ställa sedan in följande värden för den:

    - **Tillstånd:** *Prototyp*
    - **Beskrivning:** *Prototyp*

1. Välj **Spara** om du vill spara den nya livscykeltillstånd och läsa in värden på snabbfliken **Aktiverade affärsprocesser**.
1. På snabbfliken **Aktiverade affärsprocesser** väljer du de affärsprocesser som ska vara tillgängliga. I det här exemplet lämnar du fältet **Policy** inställt på *Aktiverad med varning* för alla affärsprocesser.

    ![Aktivera (med varningar) affärsprocesser för ett livscykeltillstånd](media/product-lifecycle-states-2.png "Aktivera (med varningar) affärsprocesser för ett livscykeltillstånd")

### <a name="set-up-a-version-number-rule"></a>Ställa in en regel för versionsnummer

1. Gå till **konstruktionsändringshantering &gt; inställningar &gt; produktversion nummerregel**.
1. Välj **Ny** för att lägga till en regel och ställa sedan in följande värden för den:

    - **Namn:** *Auto*
    - **Nummerregel:** *Auto*
    - **Format:** *V-\#\#*

    ![Lägga till en produktversion nummerregel](media/version-number-rule.png "Lägga till en produktversion nummerregel")

### <a name="set-up-a-product-release-policy"></a>Ställa in en policy för produktlansering

1. Gå till **konstruktionsändringshantering &gt; inställningar &gt; policy för produktlansering**.
1. Välj **Ny** för att lägga till en policy för produktlansering och ställa sedan in följande värden för den:

    - **Namn:** *Komponenter*
    - **Beskrivning:** *komponenter*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Produkttyp:** *Artikel*
    - **Använd mallar:** *alltid*
    - **Aktiv:** *Ja*

1. På snabbfliken **Arbetsmallinformation** välj **Lägg till** för att lägga till en rad och anger sedan följande värden:

    - **Företag:** *DEMF*
    - **Mall för släppt produkt:** *D0006*

1. Välj **Lägg till** för att lägga till en till rad och ställa in följande värden på den:

    - **ID för företagskonton:** *USMF*
    - **Mall för släppt produkt:** *D0006*
    - **Ta emot strukturlista:** Markera denna kryssruta.
    - **Kopiera godkännande av strukturlista:** Markera den här kryssrutan.
    - **Kopiera aktivering av strukturlista:** Markera den här kryssrutan.
    - **Ta emot flöde:** Markera denna kryssruta.
    - **Kopiera godkännande av flöde:** Markera den här kryssrutan.
    - **Kopiera aktivering av flöde:** Markera den här kryssrutan.

    ![Lägga till en policy för produktlansering](media/product-release-policy.png "Lägga till en policy för produktlansering")

### <a name="set-up-an-engineering-product-category"></a>Ställa in en konstruktionsproduktkategori 

Tekniska produktkategorier utgör grunden för att skapa tekniska produkter (dvs. produkter som skapas och kontrolleras med konstruktionsändringshantering). Så här ställs tekniska produktkategorier in.

1. Gå till **konstruktionsändringshantering &gt; information om konstruktionsproduktkategori**.
1. Skapa en kategori genom att välja **Nytt**.
1. Ange följande värden på snabbfliken **Detaljer**:

    - **Namn:** *Komponenter*
    - **Teknikorganisation:** *DEMF*
    - **Produkttyp:** *Artikel*
    - **Spåra version i transaktioner:** *Ja*
    - **Produktdimensionsgrupp:** *Version*
    - **Produktens livscykeltillstånd när det skapas:** *Drift*
    - **Versionsnummerregel:** *Auto*
    - **Påtvinga effektivitet:** *Nej*
    - **Använda nomenklatur för nummerregel:** *Nej*
    - **Använda nomenklatur för namnregel:** *Nej*
    - **Använda nomenklatur för beskrivningsregel:** *Nej*

1. På snabbfliken **frisläppningspolicy** ange fältet **produktfrisläppningspolicy** till *komponenter*.
1. Välj **Spara**.

    ![Lägga till en konstruktionsproduktkategori](media/product-category-details.png "Lägga till en konstruktionsproduktkategori")

### <a name="set-up-product-acceptance-conditions"></a>Ställ in villkor för produktgodkännande

1. Använd företagsväljaren på höger sida av navigeringsfältet för att växla till *USMF* juridisk person (företag).
1. Gå till **konstruktionsändringshantering &gt; inställningar &gt; parametrar för konstruktionsändringshantering**.
1. På fliken **frisläppningskontroll** i avsnittet **produktgodkännande** ange fältet **produktgodkännande** till *manuell*.

    ![Ställ in villkor för produktgodkännande](media/engineering-change-management-parameters.png "Ställ in villkor för produktgodkännande")

## <a name="create-a-new-engineering-product"></a>Skapa en ny konstruktionsprodukt

En konstruktionsprodukt är en produkt som har versionskontroll och styrs genom konstruktionsändringshantering. Med andra ord kan du kontrollera ändringar under dess livslängd och ändringsinformationen sparas med hjälp av teknisk ändringsorder. Följ dessa steg för att skapa tekniska produkter.

1. Se till att du befinner dig i den juridiska personen för tekniska organisationen (*DEMF* för det här exemplet). Använd företagsväljaren på höger sida om navigeringsfältet om det behövs.
1. Öppna sidan **frisläppta produkter** med något av följande steg:

    - Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**.
    - Gå till **konstruktionsändringshantering &gt; vanliga &gt; frisläppta produkter**.

1. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Ny**, markerar du sedan **konstruktionsprodukt**.
1. I dialogrutan **Ny produkt** anger du följande värden:

    - **konstruktionsproduktkategori:** *Komponenter*
    - **Produknummer:** *Z0001*
    - **Produktnamn:** *Högtalaruppsättning*

    ![Lägga till en konstruktionsprodukt](media/new-product-dialog.png "Lägga till en konstruktionsprodukt")

    Observera att fältet **Version** automatiskt ställs in med hjälp av nummerregeln för produktversion som du ställer in tidigare.

1. Välj **OK** för att skapa produkt och stänga dialogrutan.
1. Detaljsidan för den nya produkten öppnas. Observera att värden redan har fyllts i för vissa fält, till exempel **lagringsdimensionsgrupp**, **spårningsdimensionsgrupp** och/eller **artikelmodellgrupp**. Dessa fält ställdes in automatiskt eftersom produkten släpps i juridiska enheten *DEMF* och använder policy för produktlansering *Komponenter* som är kopplad till konstruktionsproduktkategori *Komponenter*. Eftersom du tidigare har använt artikeln *D0006* som mall för att ställa in en rad för den juridiska personen *DEMF* togs de värden som har fyllts i från artikel *D0006*.

    ![Information om frisläppt produkt](media/product-details.png "Information om frisläppt produkt")

1. I åtgärdsfönstret på fliken **Tekniker** i grupp **Konstruktionsändringshantering** välj **Teknikversioner** för att se versionerna av produkten.

    ![Konstruktionsversioner](media/engineering-versions-list.png "Konstruktionsversioner")

1. På sidan **Teknikversioner** ser du att det bara finns en version för produkten och att den är aktiv.
1. Välj version för att visa detaljerna.

    ![Information om konstruktionsversion](media/engineering-version-details.png "Information om konstruktionsversion")

1. På sidan **konstruktionsversion** på snabbfliken **Strukturlista** välj **Skapa strukturlista**.
1. I dialogrutan **Skapa strukturlista** ange följande värden:

    - **BOM-nummer:** Z0001
    - **Namn:** Högtalaruppsättning
    - **Plats:** 1

    ![Skapa en BOM](media/create-bom.png "Skapa en BOM")

1. Välj **OK** för att lägga till strukturlista och stänga dialogrutan.
1. På snabbfliken **strukturlista** välj **strukturlista**.
1. På sidan **strukturlista** på snabbfliken **strukturlisterader** lägga till tre rader, en var för artikelnumren *D0001*, *D0003* och *D0006*.

    ![Lägga till strukturlisterader](media/bom.png "Lägga till strukturlisterader")

1. Välj **Spara**.
1. Stäng sidan.
1. På sidan **konstruktionsversion** på snabbfliken **Strukturlista** välj **Godkänn**.
1. I dialogrutan som visas väljer du **OK**.

    ![Godkänna strukturlistan](media/approve-dialog.png "Godkänna strukturlistan")

1. På sidan **konstruktionsversion** på snabbfliken **Strukturlista** välj **Aktivera**.
1. Observera att kryssrutorna **Aktiv** och **Godkänd** är markerade för strukturlistan.

    ![Aktiv och godkända strukturlista](media/approved-bom.png "Aktiv och godkända strukturlista")

1. Stäng sidan.

## <a name="release-an-engineering-product-to-a-local-company"></a><a name="release"></a>Frisläpp en konstruktionsprodukt till ett lokalt företag

Produkten har nu skapats av teknikavdelningen. I det här exemplet är produkten en prototyp som har utformats för en kund. Eftersom kunden är en kund av juridiska personen *USMF* måste produkten frisläppas till den juridiska personen.

1. Behåll den juridiska personen som angetts som *DEMF*. (Använd företagsväljaren på höger sida om navigeringsfältet om det behövs).
1. Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**.
1. Välj produkt *Z0001*.
1. I åtgärdsföntstet, på fliken **Produkt** i gruppen **Underhåll** välj **struktur för frisläppt produkt** för att öppna guiden **frisläppta produkter**.
1. På sidan **Välj tekniska produkter att frisläppa**, välj kryssrutan **Välj** för produkt *Z0001*.

    ![Välja de teknikprodukter som ska frisläppas](media/select-eng-product-to-release.png "Välja de teknikprodukter som ska frisläppas")

1. Välj **frisläppningsdetaljer**.
1. Sidan **produkfrisläppningsinformation** visas, där du kan granska detaljerna för den produkt som ska frisläppas och dess produktstruktur. Observera att alternativet **Skicka strukturlista** har värdet *Ja*. Därför kommer både produkt *Z0001* och alla dess underordnade artiklar från strukturlistan att frisläppas.

    Du kan markera ett underordnat objekt i det vänstra fönstret om du vill granska dess information. Om ett underordnat objekt har en struktur kan du också välja att frisläppa strukturlistan för den underordnade artikeln.

    ![Granska produkfrisläppningsinformation](media/product-release-details.png "Granska produkfrisläppningsinformation")

1. Stäng sidan för att återgå till guiden **Frisläpp produkter**.
1. Välj **Nästa** för att öppna sidan **Välj produkter att frisläppa**. Om du har valt några standardprodukter (inte tekniker) visas de på den här sidan. Observera att när du släpper en standardprodukt genom att välja **Frisläpp produktstruktur**, frigörs också dess strukturlista och flöde.

    ![Välja de standardprodukter som ska frisläppas](media/select-std-product-to-release.png "Välja de standardprodukter som ska frisläppas")

1. Välj **Nästa** för att öppna sidan **Välj produktvarianter att frisläppa**. I det här exemplet finns det inte några varianter.
1. Välj **Nästa** för att öppna sidan **Välj företag**.
1. Välj de företag som produkten ska frisläppas till. I det här exemplet markerar du kryssrutan **USMF**.

    ![Välja ut de företag som ska frisläppas](media/select-release-companies.png "Välja ut de företag som ska frisläppas")

1. Välj **Nästa** för att öppna sidan **Bekräfta val**.
1. Välj **Slutför**.

## <a name="review-and-accept-the-product-before-you-release-it-in-the-local-company"></a><a name="accept"></a>Granska och acceptera produkten innan du släpper den i det lokala företaget

Teknikavdelningen har nu släppt informationen i de lokala företagen där produkten kommer att användas. För detta exempel är det lokala företaget *USMF*.

Eftersom du anger fältet **produktgodkännande** till *manuell* på sidan **parametrar för konstruktionsändringshantering** för företaget *USMF* måste produkterna godkännas manuellt innan de frisläpps till det företaget. De måste alltså granskas och accepteras innan de blir frisläppta produkter.

Om du vill granska produkten och släppa den i *USMF*-företaget följer du stegen nedan.

1. Ange den juridiska personen till *USMF*. (Använd företagsväljaren på höger sida om navigeringsfältet).
1. Gå till **teknik för ändringshantering &gt; vanliga &gt; produktversioner &gt; öppna produktversioner**.

    På sidan **öppna produktfrisläppningar** visas produkt *Z0001* som har statusen *väntar på att accepteras*.

    ![Öppna produktfrisläppningar](media/open-product-releases.png "Öppna produktfrisläppningar")

1. Välj värdet i kolumnen **produktnummer** om du vill öppna sidan **produkfrisläppningsinformation**. Observera följande information:

    - På snabbfliken **Allmänt** visas information om produkt utleveransen, till exempel det frisläppta företaget (*DEMF* för det här exemplet) frisläppande plats (*1*) och mottagande plats (*1*). Eftersom du inte angav någon mottagande plats i guiden **frisläppta produkter** kopieras värdet för den frisläppta platsen till mottagande platsen.
    - På snabbfliken **Frisläppningsinformation** visas information om produkten och den version som släpptes. Här kan du ändra inställningar som t.ex. effektivitetsdatum.
    - På snabbfliken **flöde** visas produktens flöde. I det här exemplet släpper du emellertid inga vägar.

    ![Information om produktfrisläppning](media/product-release-details-2.png "Information om produktfrisläppning")

1. När du är klar med granskningen av informationen kan du ta emot produkten och på det här sättet frisläppa företaget *USMF*. I åtgärdsfönstret, välj **Åtgärder &gt; Acceptera**.
1. Produkten släpps nu i frisläppt företaget *USMF*. Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**. Du bör se artikel *Z0001*.

## <a name="use-the-product-in-transactions-in-the-local-company"></a>Använd produkten i transaktioner i det lokala företaget

Master Data Manager för det *USMF*-företaget vill försäkra sig om att produkten är i ett *prototyp* tillstånd, så att användarna får en varning om de av misstag lägger till den i processer som de arbetar med.

1. Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**.
1. Välj produkt *Z0001* för att öppna sidan information om sidan. (Du kan söka efter produkten med hjälp av filtret.)
1. I åtgärdsfönstret på fliken **Tekniker** i grupp **Konstruktionsändringshantering** välj **Teknikversioner**.
1. På sidan **Teknikversioner** väljer du versionsnummer *V-01* för att öppna sidan med information.
1. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Livscykeltillstånd**, markerar du sedan **Ändra livscykeltillstånd**.
1. I listrutan **Ändra livscykeltillstånd** anger du fältet **Tillstånd** till *Prototyp* och välj sedan **OK**.

    ![Ändrar livscykeltillståndet](media/change-lifecycle-state.png "Ändrar livscykeltillståndet")

## <a name="add-the-engineering-product-to-a-sales-order"></a>Lägg till en konstruktionsprodukt i en försäljningsorder

Produkten kan nu säljas till en kund. Följ dessa steg om du vill lägga till produkten till en försäljningsorder.

1. Gå till **Försäljning och marknadsföring &gt; Försäljningsorder &gt; Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa försäljningsorder** ange fältet **Kundkonto** till *US-0002* och välj sedan **OK**.
1. Den nya försäljningsordern öppnas. PÅ snabbfliken **Försäljningsorderrader** lägg till en rad och ange fältet **Artikelnummer** till *Z000* för det.
1. Klicka på **Spara** i åtgärdsfönstret.

    En varning visas som informerar dig om att artikeln har statusen *prototyp*. Eftersom meddelandet bara är en varning, skapades dock fortfarande försäljningsordern.

    ![Försäljningsorder för en konstruktionsprodukt](media/sales-order-eng-product.png "Försäljningsorder för en konstruktionsprodukt")

## <a name="request-changes-in-the-engineering-product"></a>Begära ändringar i den tekniska produkten

Produkten skickades till en kund, men kunden var inte helt nöjd och ger feedback som innehåller förslag på förbättringar. Även om kunden pratar med en försäljningsansvarig i telefon, kan försäljningsansvarig begära de ändringar som kunden ska beskriva.

1. Gå till **Försäljning och marknadsföring &gt; Försäljningsorder &gt; Alla försäljningsorder**.
1. Leta upp och öppna försäljningsordern som du skapade i föregående övning.
1. På snabbfliken **Försäljningsorderrader** välj **Konstruktionsändringshantering &gt; Ny begäran om teknisk ändring**.

    ![Skapa en begäran om teknisk ändring från en försäljningsorder](media/sales-order-eng-change-request.png "Skapa en begäran om teknisk ändring från en försäljningsorder")

1. Fyll i begäran om teknisk ändring utifrån kundens feedback. Ange följande värden för det här exemplet:

    - **Ändringsbegäran:** *555*
    - **Titel:** *Z0001 kundändring*
    - **Prioritet:** *låg*
    - **Kategori:** ställ in ändring
    - **Allvarlighetsgrad:** *medium*

1. På snabbfliken **Information** välj **Ny &gt; Anteckning** för att lägga till en anteckning i rutnätet.
1. I fältet **Beskrivning** för den nya anteckningen, ange det objektet *D0003* ska tas bort från strukturlistan Om du måste lägga till mer information för noteringen kan du ange text i fältet **anteckningar**.

    ![Begäran om konstruktionsändring](media/eng-change-request.png "Begäran om konstruktionsändring")

1. Klicka på **Spara** i åtgärdsfönstret.
1. Lägg märke till att artikeln automatiskt har lagts till på snabbfliken **produkter** och att källan till begäran om teknisk ändring (försäljningsordern) har lagts till på snabbfliken **källa**.

## <a name="make-changes-to-the-product-by-using-an-engineering-change-order"></a>Göra ändringar i produkten genom att använda en begäran om teknisk ändring

Försäljningsansvarig vet att produkten är viktig och har utformats speciellt för kunden. Därför ringer försäljningsansvarig en tekniker i *DEMF*-företaget för att meddela dem om ändringsbegäran. På så sätt kan teknikern påskynda processen.

Teknikern granskar nu begäran från kunden och skapar en ändringsorder för produkten.

1. Eftersom teknikern arbetar i *DEMF*-företaget ställer du in den juridiska personen på *DEMF*. (Använd företagsväljaren på höger sida om navigeringsfältet).
1. Gå till **konstruktionsändringshantering &gt; vanlig &gt; begäran om teknisk ändring**.
1. Öppna ändringsbegäran *555*.
1. Granska informationen och godkänn sedan ändringen. I åtgärdsfönstret på fliken **Ändringsbegäran** i gruppen **Ändra status** väljer du **Godkänn**.
1. Gå till **konstruktionsändringshantering &gt; vanlig &gt; teknisk ändringsorder**.
1. I åtgärdsfönstret väljer du **Ny** för att skapa en ändringsorder och anger följande värden:

    - **Ändringsorder:** *555*
    - **Titel:** *Z0001 kundändring*
    - **Kategori:** *kundändring*
    - **Prioritet:** *låg*
    - **Allvarlighetsgrad:** *medium*

1. På snabbfliken **Påverkade produkter** välj **Ny &gt; Lägg till befintlig produkt** för att lägga till en rad i rutnätet och ställa in följande värden för det:

    - **Produkt:** *Z0001*
    - **Påverkan:** *Ny version*

    ![Skapa en teknisk ändringsorder](media/eng-change-order.png "Skapa en teknisk ändringsorder")

1. Observera att eftersom du ställer in fältet **Påverkan** till *Ny version*, fältet **Ny version** på fliken **Detaljer** av snabbfliken **Produktinformation** visar vad det nya versionsnumret kommer att bli (*V-02* för detta exempel).

    ![Produktinformation för teknisk ändringsorder](media/eng-change-order-product-details.png "Produktinformation för teknisk ändringsorder")

1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Produktinformation** på fliken **Strukturlista** välj **Rader** för att öppna strukturlistan för version *V-01* för produkt *Z0001*.

    ![Strukturlisterader för tekniska produkter](media/eng-product-bom-lines.png "Strukturlisterader för tekniska produkter")

1. Markera raden för artikelnumret *D0003* och välj sedan **ta bort** i åtgärdsfönstret. Värdet i fältet **Ändringstyp** för den här raden ändras till *Borttaget*.
1. Klicka på **Spara** i åtgärdsfönstret.

    ![Modifierad strukturlisterader för tekniska produkter](media/eng-product-bom-lines-modified.png "Modifierad strukturlisterader för tekniska produkter")

1. Stäng sidan **strukturlisteraden** för att återgå till sidan **Teknisk ändringsorder**.
1. På snabbfliken **Produktdetaljer** på fliken **Strukturlista**, meddela värdet av fältet **Ändringstyp** för strukturlista *Z0001* är nu *Ändrad*.

    ![Teknisk ändringsorder som innehåller en ändrad strukturlista](media/eng-change-order-changed-bom.png "Teknisk ändringsorder som innehåller en ändrad strukturlista")

    Beställningen måste nu godkännas innan ändringarna kan behandlas. När ändringarna bearbetas uppdateras produkterna med de ändringar som ingår i den teknisk ändringsorder. I det här exemplet har personen som skapar teknisk ändringsorder angetts som godkännare.

1. I åtgärdsfönstret på fliken **Ändringsorder** i gruppen **Ändra status** väljer du **Godkänn**.
1. Välj **Process** om du vill uppdatera produktensinformation.
1. Välj **Slutför** för att markera ändringsordning som slutförd.

## <a name="release-the-changed-product"></a>Frisläpp den ändrade produkten

Produkten kan nu frisläppas igen till *USMF*-företaget och skickas till kunden. Om du vill frisläppa produkten direkt från teknisk ändringsorder följer du stegen nedan.

1. Öppna den tekniska ändringsordern som du skapade i den föregående övningen, om den inte redan är öppen.
1. I åtgärdsfönstret på fliken **Ändringsorder** i gruppen **produktversioner** väljer du **sök**.
1. Sökresultaten visar vilka företag som de berörda produkterna har frisläppts till. Stäng sökresultatet.
1. I åtgärdsfönstret, på fliken **Ändringsorder** i gruppen **Produktversioner**, välj **Visa** för att öppna dialogrutan **Versioner** där du kan se resultaten från föregående sökning.
1. Välj varje företag som du vill frisläppa produkter till.
1. Välj **OK** för att stänga dialogrutan **Versioner** och returnera till ändringsorder.
1. På åtgärdsfönstret, på fliken **Ändringsorder** i gruppen **Produktfrisläppning**, välj **Process** för att frisläppa de berörda produkterna till de utvalda företagen. Du kan också välja **Frisläpp produktstruktur** för att starta frisläppningsprocessen.
