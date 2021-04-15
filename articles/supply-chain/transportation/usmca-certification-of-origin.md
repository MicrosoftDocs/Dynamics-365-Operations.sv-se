---
title: USMCA-certifiering av ursprung
description: Med den här funktionen kan du skriva ut den certifiering av ursprungsdokument som krävs enligt Förenta staterna-Mexiko-Kanada-avtalet (USMCA).
author: Henrikan
ms.date: 10/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-23
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: e479c7686ab9445b012d335ddc9fc4cdc6b2275c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807714"
---
# <a name="usmca-certification-of-origin"></a>USMCA-certifiering av ursprung

[!include [banner](../includes/banner.md)]

Med den här funktionen kan du skriva ut den certifiering av ursprungsdokument som krävs enligt Förenta staterna-Mexiko-Kanada-avtalet (USMCA).

*USMCA-certifiering av ursprungsdokumentet* innehåller de dataelement som krävs för deklarationen. Vissa dataelement kan fyllas i förväg före utskrift medan andra måste fyllas i manuellt efter utskrift. För att erhålla förmånsbehandling av avgifter måste dokumentet fyllas i och importeras för importören vid den tidpunkt då deklarationen görs. Dokumentet kan vara ifyllt av importören, exportören eller producenten.

Du kan skriva ut dokumentet för en enda leverans från listsidan **Alla försändelser** eller från sidan **Försändelseinformation**.

Dokumentet är bara tillgängligt om landet på den primära adressen för den juridiska personen är USA.

Beroende på dokumentets utskriftsval kan dokumentet fyllas i på förhand med data från systemet. Det går att ändra eller lägga till data i det utskrivna dokumentet genom att exportera det utskrivna dokumentet till ett redigerbart format, t.ex. Microsoft Word. Efter exporten kan du tillämpa alla nödvändiga ändringar innan en deklaration görs.

## <a name="turn-on-the-usmca-feature"></a>Aktivera en USMCA-funktion

Innan du kan använda USMCA-funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Transporthantering*
- **Funktionsnamn:** *USMCA-certifiering av ursprungsdokument*

## <a name="document-content"></a>Dokumentinnehåll

USMCA-certifiering av ursprungsdokumentet innehåller följande dataelement:

- Adresselement
- Certifierande partens roll
- Enskild försändelse
- Fakturor
- Avropsperiod
- Artikeldetaljer
- Intygarens signatur
- Antal sidor

Mer information om dessa element och hur deras värden hittas finns i resten av avsnitten i det här avsnittet.

## <a name="print-a-usmca-certification-of-origin-document"></a>Skriv ut USMCA-certifiering av ursprungsdokument

Om du vill skriva ut en USMCA-certifiering om ursprungsdokument för en försändelse gör du följande:

1. Gör något av följande:
    - Gå till **Transporthantering > Leveranser > Alla leveranser** och välj den försändelse som du vill skriva ut dokumentet för.
    - Öppna sidan **Försändelsedetaljer** för den sändning du vill skriva ut dokumentet för (det finns flera sätt att komma hit, inklusive från sidan **Alla försändelser**).
1. I åtgärdsfönstret, öppna fliken **försändelser** och från gruppen **Utskrift** välj **USMCA-certifiering av ursprung**.
1. Dialogrutan **certifikat eller ursprung** öppnas. Gör de inställningar som beskrivs i följande underavsnitt och välj sedan **OK** för att generera dokumentet.
1. En förhandsgranskning av dokumentet öppnas. Använd kommandona som finns i åtgärdsfönstret för att skriva ut eller exportera dokumentet efter behov.

### <a name="certifying-party"></a>Intygspart

Använd **Certifierande part** för att identifiera den typ av part som skriver ut dokumentet. Ange om den attesterande parten är *exportören*, *exportören och producenten*, *producenten* eller *importören* eller lämna den tom om den attesterande parten inte är någon av dessa. Det alternativ du väljer avgör vad som skrivs ut i dokumentets adressavsnitt.

Den **Certifierande part** som du väljer kommer att inkluderas i det utskrivna dokumentet.

Dokumentet kan skrivas ut för både inkommande och utgående försändelser. Välj *Importören* som **Certifierande part** för inkommande försändelser.

I följande tabell beskrivs de typer av information som ingår i dokumentet, baserat på den **Certifierande part** som du väljer.

| Certifierande&nbsp;part | beskrivning |
|---|---|
| *\[Tom\]* | Lägger till följande information i dokumentet:<ul><li>**Intygarens information**: använder adressdetaljer för leveranslagret, om detta är tillgängligt. i annat fall används leveransadressen, om sådan finns. i annat fall används adressen till den juridiska personen (företaget) som valts i Supply Chain Management.</li><li>**Information om exportören**: Tom</li><li>**Information om producentern**: Tom</li><li>**Information om importören**: Tom</li><ul>|
| *Exportör* | Lägger till följande information i dokumentet:<ul><li>**Intygarens information**: använder adressdetaljer för leveranslagret, om detta är tillgängligt. i annat fall används leveransadressen, om sådan finns. i annat fall används adressen till den juridiska personen (företaget) som valts i Supply Chain Management.</li><li>**Information om exportören**: använder adressinformation för den juridiska personen.</li><li>**Information om producentern**: Tom</li><li>**Information om importören**: använder fakturakontot för den relaterade försäljningsordern.</li><ul>|
| *Exportör och producent* | Lägger till följande information i dokumentet:<ul><li>**Intygarens information**: använder adressdetaljer för leveranslagret, om detta är tillgängligt. i annat fall används leveransadressen, om sådan finns. i annat fall används adressen till den juridiska personen (företaget) som valts i Supply Chain Management.</li><li>**Information om exportören**: använder adressinformation för den juridiska personen.</li><li>**Information om producent**: använder adressinformation för den juridiska personen.</li><li>**Information om importören**: använder fakturakontot för den relaterade försäljningsordern.</li><ul>|
| *Importör* | Lägger till följande information i dokumentet:<ul><li>**Intygarens information**: använder adressdetaljer för leveranslagret, om detta är tillgängligt. i annat fall används leveransadressen, om sådan finns. i annat fall används adressen till den juridiska personen (företaget) som valts i Supply Chain Management.</li><li>**Information om exportören**: Tom</li><li>**Information om producentern**: Tom</li><li>**Information om importören**: använder adressinformation för den juridiska personen.</li><ul>|
| *Producent* | Lägger till följande information i dokumentet:<ul><li>**Intygarens information**: använder adressdetaljer för leveranslagret, om detta är tillgängligt. i annat fall används leveransadressen, om sådan finns. i annat fall används adressen till den juridiska personen som valts i Supply Chain Management.</li><li>**Information om exportören**: Tom</li><li>**Information om producent**: använder adressinformation för den juridiska personen.</li><li>**Information om importören**: Tom</li><ul>|

### <a name="has-various-producers"></a>Har olika producenter

Listrutan **Certifierande part** kontrollerar texten som ska användas till producentens uppgifter i dokumentet. Välj en av följande:

- *Olika producenter* - skriver ut texten "olika" i producentdetaljerna.
- *Tillgänglig på begäran* - skriver ut texten "tillgänglig på begäran av de importerade myndigheterna" i producentdetaljerna.

När **Certifierande part** är inställd på *exportör och producent* eller *producent* har inställningen **Har olika producenter** åsidosätts, och producentens adressuppgifter kommer att vara desamma som certifieraren.

### <a name="blanket-period"></a>Avropsperiod

Använd inställningar **Avropsperiod från** och **Avropsperiod till** för att skapa en avropsperiod, under vilken dokumentet omfattar flera försändelser av identiska varor, även om dokumentet bara skrivs ut för en leverans. Du kan ange datum för avropsperioden utan begränsningar och det läggs till i dokumentet. Du kan också lämna inställningarna tomma eller ange dem tidigare.

### <a name="is-single-shipment"></a>Är en enskild försändelse

I dialogrutan **certifiering av ursprung** ange **är enskild försändelse** till något av följande:

- *Ja* - lägger till "enskild försändelse: Ja" bredvid fakturanumret.
- *Nej* - lägger inte till någonting.

## <a name="other-information-included-in-the-document"></a>Annan information som ingår i dokumentet

Förutom de valfria element som du väljer med hjälp av dialogrutan **certifikat eller ursprung** innehåller USMCA-certifiering av ursprungsdokument den information och de anpassade fält som sammanfattas i följande underavsnitt. En del av den här informationen måste anges manuellt när du har skapat dokumentet.

### <a name="invoice-number"></a>Fakturanummer

ID för försäljningsfakturor som hör till försändelser skrivs ut på dokumentet oavsett avropsperiod. Fakturanummer skrivs ut oavsett om markering **är en enda leverans**.

### <a name="item-details"></a>Artikeldetaljer

Dokumentet innehåller flera avsnitt med detaljerad information om artiklar, som är:

- **SKU-nummer**: skriver ut den frisläppta produktens artikelnummer.

- **Beskrivning**: skriver ut en beskrivning eller ett namn för den frisläppta produkten. Om det finns en beskrivning på användarens språk skrivs det ut. Om det inte finns någon sådan beskrivning skrivs namnet på användarens språk ut. Om det namnet inte finns skrivs artikel namnet ut.

- **Harmoniserad system tariffklassificering (HS)**: skriver ut det harmoniserade tariffschema som är kopplat till produkten. Du kan ställa in dessa scheman genom att gå till **Transporthantering \> Inställningar \> Transportstandard \> Harmoniserade tariffscheman**.

- **Ursprungligt kriterium:** du måste ange data manuellt i det här avsnittet första gången du släpper dokumentet.

- **Ursprungsland:** skriver ut ursprungslandet, som du använder när du går till **produktinformationshantering \> inställning \> produktens regelefterlevnad \> ursprungsland** (se även [ursprungsland](../pim/country-of-origin.md)). ISO-koden för ursprungslandet skrivs ut baserat på destinationslandet/regionen i leveransadress och artikeln. Om inga uppgifter om ursprungsland har ställts in återgår detta värde till den inställning som finns på **frisläppt produkt \> utlandshandel \> ursprung**. Om det inte finns några ursprungliga uppgifter för ursprungslandet måste du ange ursprungslandet manuellt när du har genererat dokumentet.

### <a name="certifier-signature-and-date"></a>Intygarens signatur och datum

Du måste ange det manuellt när du har genererat dokumentet.

### <a name="consists-of-number-of-pages"></a>Består av antalet sidor

Användaren som signerar intyget måste manuellt ange antalet sidor (för verifiering) när dokumentet har genererats.

### <a name="page-numbers"></a>Sidnummer

Aktuell sida och antal sidor som skrivs ut längst ned i dokumentet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]