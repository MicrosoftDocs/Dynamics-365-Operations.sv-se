---
title: Arbetsradsdetaljer
description: Det här avsnittet innehåller information om sidan arbetsraddetaljer, som innehåller en omfattande, sorterbar och filterbar lista över de enskilda arbetsraderna i systemet.
author: mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkLocationChange, WHSWorkLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: f37d161bf3d27e15eaaf1230c05270f3769f9901
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778291"
---
# <a name="work-line-details"></a>Arbetsradsdetaljer

[!include [banner](../includes/banner.md)]

Sidan **Information om arbetsrad** visar en omfattande, sorterbar och filtrerbar lista över de enskilda arbetslinjerna i ditt system. Den ger en fullständig översikt över arbete som planeras och körs i lagerstället. Du kan enkelt växla mellan att visa alla arbetsrader och bara visa öppna arbetsrader. Information som finns för varje rad är arbetsstatus, artikelnummer, plats, arbetskvantitet, last-ID och leverans-ID.

## <a name="turn-on-the-work-line-details-feature"></a>Aktivera funktionen arbetsraddetaljer

Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Administratörer kan använda sidan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera/inaktivera den vid behov. Här visas funktionen i listan:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *Arbetsraddetaljer*

## <a name="open-and-use-the-work-line-details-page"></a>Öppna och använd sidan med information om arbetsrader

Om du vill visa listan med arbetsraddetaljer går du till **Lagerstyrning \> Arbete \> Arbetsraddetaljer**. Härifrån kan du sedan utföra följande åtgärder:

- Använd fältet **Filter** om du vill söka efter rader som har ett specifikt värde för valfri tillgänglig parameter. (Tillgängliga parametrar inkluderar många parametrar som inte visas som kolumner i rutnätet.)
- Använd kryssrutan **Visa stängda** om du vill visa eller dölja stängda rader.
- Välj **Visa dimensioner** du vill öppna dialogrutan **Dimensionsvisning** där du kan välja att visa eller dölja olika dimensionskolumner i rutnätet.
- Välj en kolumnrubrik om du vill öppna en meny där du kan välja att sortera eller filtrera listan efter värden i den kolumnen.
- Markera en arbetsrad och välj sedan **ändra plats** du vill öppna en dialogruta där du kan ändra platsen för arbetsraden. Den plats du anger åsidosätter inställningen för platsdirektivet.
- Markera en arbetsrad och välj sedan **Avbryt arbetsrad** om du vill öppna en dialogruta där du helt eller delvis kan minska kvantiteten för den arbetsraden.
- Justera kvantiteter.
- Visa transaktionerna bakom valfri arbetsrad.

## <a name="try-out-the-feature"></a>Testa funktionen

Det här avsnittet innehåller en demonstration på tre delar som visar hur du arbetar med arbetsraddetaljer.

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom denna demo med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

Du kan också använda denna demo som vägledning när du arbetar med ett produktionssystem. Du måste emellertid ersätta dina egna värden och du kanske saknar vissa typer av obligatoriska poster som används i standard demodata.

### <a name="verify-that-the-scenario-setup-includes-enough-available-inventory"></a>Kontrollera att scenarioinställningen innehåller tillräckligt med tillgängligt lager

Om du arbetar med **USMF** demodata, bör du först se till att ditt system är konfigurerat så att tillräckligt med lager finns tillgängliga på varje relevant plats. I den här demon är det förväntat att du har följande lager tillgängligt:

- **Artikel M9200:** 45 ea. (eller mer)
- **Artikel M9202:** 10 ea. (eller mer)

Följ dessa steg för att kontrollera att det finns tillräckligt med tillgängligt lager och du måste göra eventuella justeringar.

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv** och bestäm vilka plockningsplatser som används för plockning av försäljningsorder på lagerställe 51. (Mer information finns i [Lagerpåfyllnad och Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv](control-warehouse-location-directives.md).)
1. Kontrollera lagernivåerna på de relevanta platserna.
1. Justera lagret efter behov. Du kan skapa manuella transporter, använda återanskaffning eller använda andra flöden för att justera lagret.

### <a name="part-1-create-picking-work"></a>Del 1: Skapa plockarbete

Innan du börjar skapa arbete ska du se till att distributionslagret är inställt på att svara på arbetsförfrågningar på det sätt som förväntas.

Följ dessa steg för att skapa lite plockningsarbete.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Välj **Ny** om du vill öppna dialogrutan **Skapa försäljningsorder**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - På snabbfliken **Kund** ställer du in fältet **Kundkonto** på _US-001_.
    - På snabbfliken **Allmänt** anger du fältet **Lagerställe** till _51_.

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Den innehåller en ny, tom rad i rutnätet **Försäljningsorderrader**. Ställ in följande värden på denna orderrad:

    - **Artikelnummer:** _M9200_
    - **Kvantitet:** _20_
    - **Enhet:** _ea_

1. Välj den nya orderraden och sedan på menyn **Lager** väljer du **Reservation** för att öppna sidan **Reservation**.
1. På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**. Systemet skapar en leverans, lägger till den i en ny last och skapar det begärda arbetet.
1. Skapa en andra försäljningsorder för samma kundkonto och lagerställe som du använde för den första ordern. Lägg till följande två orderrader till denna order:

    - **Rad 1:** Ställ in fältet **Artikelnummer** till _M9200_, fältet **Kvantitet** till _25_ och fältet **Enhet** till _ea_.
    - **Rad 2:** Ställ in fältet **Artikelnummer** till _M9202_, fältet **Kvantitet** till _10_ och fältet **Enhet** till _ea_.

1. Upprepa steg 6 till 8 för att reservera lagret för varje orderrad (ett i taget) och upprepa sedan steg 9 för att frisläppa ordern till lagerstället.

### <a name="part-2-change-the-location-for-a-work-line"></a>Del 2: ändra platsen för en arbetsrad

1. Gå till **Lagerstyrning \> Arbete \> Arbetsraddetaljer**.
1. Sök reda på och välj en av de arbetsrader som du har skapat för den här demon.
1. Välj **Ändra plats** om du vill öppna dialogrutan **Välj ny plats**.
1. I dialogrutan **Välj ny plats** i fältet **Plats** väljer du en ny plats för arbetsraden.
1. Välj **OK** om du vill tillämpa ändringen och stänga dialogrutan.

> [!IMPORTANT]
> Du kan bara skicka platsändringar om det finns tillräckligt med lager tillgängligt för den nya lagerstället (för en plockning) eller om det skickar validering av platstyp (för en läggning).

### <a name="part-3-change-the-quantity-of-a-work-line-or-cancel-a-work-line"></a>Del 3: ändra kvantiteten för en arbetsrad eller avbryt en arbetsrad

1. Gå till **Lagerstyrning \> Arbete \> Arbetsraddetaljer**.
1. Sök reda på och välj en av de arbetsrader som du har skapat för den här demon. Observera att du bara kan annullera eller ändra kvantiteter för arbetsrader där arbetstypen är _plocka_.
1. Välj **Avbryt arbetsrad** om du vill öppna dialogruta **Kvantitet att avbryta**.
1. I dialogrutan **Kvantitet att avbryta** ändrar du värdet i fältet **Kvantitet** för att ange den kvantitet som ska *dras av från* den kvantitet som redan har angetts för raden. Som standard visar fältet **kvantitet** hela kvantiteten.

    - Om du avbryter hela kvantiteten kommer **Arbetsstatus** att ändras till _Annullerad_, men fältet **Arbetskvantitet** visar fortfarande det ursprungliga värdet.
    - Om du endast avbryter en del av kvantiteten kommer fältet **Arbetskvantitet** att uppdateras och visa det nya värdet men värdet **Arbetsstatus** ändras inte.

1. Välj **OK** om du vill tillämpa ändringen och stänga dialogrutan.

> [!IMPORTANT]
> Om du avbryter bara en del av kvantiteten för en arbetsrad, måste du också ta bort den inaktuella kvantiteten från lastraden. Annars, om inte under leverans har ställts in korrekt, kan lastraden inte bekräftas för levererans.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]