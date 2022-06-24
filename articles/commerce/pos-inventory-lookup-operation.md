---
title: Lagersökning i kassan
description: I denna artikel beskrivs hur du använder lagersökningsfunktionen i kassan i Dynamics 365 Commerce för att visa lagerbehållning av produkter i butiker och lager.
author: boycezhu
ms.date: 08/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 01f10c348c61ffbcb30be26a57b3edd436aacc8f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850259"
---
# <a name="inventory-lookup-operation-in-pos"></a>Lagersökning i kassan

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du använder lagersökningsfunktionen i kassan i Dynamics 365 Commerce för att visa lagerbehållning av produkter i butiker och lager.

En korrekt översikt över lager i en organisation kan ge snabb, effektiv kundservice. Den tidpunkt som är viktigast är den tidpunkt när kunden är redo att göra ett inköp. Det är viktigt att kassörerna i butiken har lagerinformation lättåtkomlig i realtid i nästan realtid, så att de korrekt kan lova produktleverans och hämtning.

Lagersökningsfunktionen i Commerce POS hjälper detaljhandlare att uppnå driftsäkerhet och få insikter genom att koppla butiker till Commerce Headquarters. Den här funktionen ger en lagertillgänglighetsvy av produkter mellan butiker och lagerställen. Den underlättar också för återförsäljare att skapa ytterligare effektivitet och kostnadsbesparingar genom att förbättra lagerplanering i realtid.

När lagersökningen startas från POS-programmet använder POS-kassören det numeriska tangentbordet för att ange ett produktnummer för att fråga efter lagerinformation. Om den angivna produkten har varianter kan kassören välja dimensioner eller andra värden för att kontrollera lagerinformationen för en specifik produktvariant.

## <a name="inventory-lookup-list-view-for-individual-products"></a>List vy över lagersökning för enskilda produkter

För en enskild produkt innehåller lagersökningsfunktionen en vy över lagersöklistan som visar följande produktinformation för en lista över platser:

- **Lager** – Refererar till den "tillgängliga fysiska" kvanheten för en produkt.
- **Reserverad** – Refererar till den "fysiska reserverade" kvanhet som hämtats från huvudkontoret.
- **Beställd** – Refererar till den kvanhet som "beställts totalt" och som hämtats från huvudkontoret.
- **Enhet** – Refererar till den lagermåttenhet som konfigurerats i huvudkontoret.

I listvyn över platser ingår alla butiker och lagerställen som har konfigurerats i uppfyllelsegrupperna som den aktuella butiken är kopplad till, enligt bilden nedan.

![Listvy över lagersökningsfunktionen.](media/inventory-lookup-list-view.png)

> [!NOTE]
> Kontrollera att din aktuella butik finns inkluderad i de associerade uppfyllelsegrupperna.

Följande åtgärder är tillgängliga i kassans appfält:

- **Sortera** – Med denna åtgärd kan POS-användaren sortera datan i listvyn baserat på olika kriterier. Platsbaserad sortering är standardsorteringsalternativet.

    - **Geografisk plats** (från närmaste till mest avlägsen plats, baserat på avståndet till den aktuella butiken)
    - **Namn** (i stigande eller fallande ordning)
    - **Butiksnummer** (i stigande eller fallande ordning)
    - **Lager** (i fallande ordning)
    - **Reserverad** (i fallande ordning)
    - **Beställd** (i fallande ordning)

- **Filter** – Med den här åtgärden kan POS-användaren visa filtrerade data för en viss plats.
- **Visa butikstillgänglighet** – Med den här åtgärden kan POS-användaren visa ATP-kvanheter ("disponibelt att utlova") för en produkt i den valda butiken.
- **Visa butiksplats** – Med den här åtgärden öppnas en separat sida där kartvyn, adressen och öppettiderna för den valda butiken visas.
- **Hämta i butik** – Den här åtgärden skapar en kundorder för produkten som ska hämtas i den valda butiken, samt dirigerar användaren till transaktionsskärmen.
- **Skicka produkt** – Den här åtgärden skapar en kundorder för produkten som ska skickas från den valda butiken, samt dirigerar användaren till transaktionsskärmen.
- **Visa alla varianter** – För en produkt med varianter växlar den här åtgärden från en listvy till en matris som visar lagerinformation för alla varianter av produkten.
- **Lägg till i transaktion** – Den här åtgärden lägger till produkten i kundvagnen och dirigerar användaren till transaktionsskärmen.

> [!NOTE]
> Den platsbaserade sortering som lanserades i Commerce version 10.0.17 visar den aktuella butiken högst upp. För övriga platser bestäms avståndet mellan en plats och den aktuella butiken av de koordinater (latitud och longitud) som definieras i Commerce headquarters. För en butik definieras platsinformationen i den primära adressen för den driftenhet som är kopplad till butiken. För ett lagerställe utan butik anges platsinformationen i lagerställesadressen. Före version 10.0.17 visar listvyn alltid den aktuella butiken högst upp och sorterar övriga platser i alfabetisk ordning.
>
> Åtgärderna **Visa butikstillgänglighet**, **Visa butiksplats**, **Hämta i butik** och **Skicka produkt** är inte tillgängliga för platser utan butik.

## <a name="inventory-lookup-matrix-view-for-variants"></a>Matrisvy av lagersökning efter varianter

För en huvudprodukt med varianter innehåller lagersökningsfunktionen också en dimensionsbaserad matrisvy som visar lagertillgänglighetsinformation för alla varianter av huvudprodukten på en vald plats. Som standard visar matrisvyn data för den aktuella butiken. Du kan använda åtgärden **Butik** i appfältet för att söka efter lagerinformation från andra butiker som konfigurerats i uppfyllelsegrupperna som den aktuella butiken är kopplad till.

Följande exempelbild visar matrisvyn av lagersökingen i kassan.

![Matrisvy över lagersökningsfunktionen.](media/inventory-lookup-matrix-view.png)

I matrisvyn representerar varje cell en enskild variant och visar lagerbehållning (fysiskt tillgängligt) i det nedre högra hörnet samt värden för **reserverade** (fysiskt reserverade) och **beställda** (beställt totalt) i det övre vänstra hörnet. Följande tabell förklarar innebörden av olika lagerbehållningsvärden.

| Behållningsvärde                            | beskrivning |
|------------------------------------------|-------------|
| Numeriskt värde som är större än 0 (noll) | En variant har frisläppts till den angivna platsen och du kan utföra ytterligare åtgärder i cellen. |
| **0** (noll)                             | En variant har frisläppts till den valda platsen, men artikeln är inte tillgänglig på den valda platsen. Du kan utföra ytterligare åtgärder i cellen. |
| **Ej tillämpligt** eller en inaktiv cell              | En variant har inte frisläppts till den angivna platsen och du kan inte utföra ytterligare åtgärder i cellen. |

Visningsordningen för dimensionsvärdena i matrisvyn baseras på konfigurationen av visningsordningen i Commerce Headquarters. Du kan ändra konfigurationen för visningsordningen genom att välja en ny dimension som ska användas. 

Följande åtgärder finns tillgängliga i matriscellen:

- **Sälj nu** – Den här åtgärden lägger till den valda varianten i kundvagnen samt dirigerar användaren till transaktionsskärmen.
- **Hämta i butik** – Den här åtgärden skapar en kundorder för den valda varianten som ska hämtas i den valda butiken, och dirigerar användaren till transaktionsskärmen.
- **Skicka produkt** – Den här åtgärden skapar en kundorder för den valda varianten som ska skickas från den valda butiken, samt dirigerar användaren till transaktionsskärmen.
- **Tillgänglighet** – Med denna åtgärd förs användaren till en separat sida som visar ATP-kvantiteter för den valda varianten i den valda butiken.
- **Visa alla platser** – Den här åtgärden växlar till standardvyn för lagertillgänglighetslista som visar lagerinformation för den valda varianten.
- **Visa produktdetaljer** – Den här åtgärden dirigerar om användaren till produktdetaljsidan (PDP) för den valda varianten.

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a>Öppna lagersökning från andra sidor i kassan

Kassaanvändarna kan komma åt lagersökningsfunktionen från andra sidor i kassan.

Följande exempelbild visar lagersökingsresultaten från en PDP i kassan.

![Lagersökning från produktinformationssidan.](media/inventory-lookup-from-product-details-page.png)

På PDP för en huvudprodukt kan du använda åtgärden **Visa alla varianter** i appfältet för att öppna matrisvyn av lagersökningen som visar information om lagertillgänglighet för den aktuella butiken för alla varianter av en produkt. För en enskild produkt visar PDP lagerbehållningen (tillgängligt fysiskt) för den produkten för den aktuella butiken. Dessutom kan du välja länken **Lager i andra butiker** för att öppna lagersökningsfunktionen för att kontrollera lagertillgängligheten av en produkt i andra butiker eller lager.

> [!NOTE]
> Åtgärden **Visa alla varianter** på PDP är bara tillgängligt för huvudprodukter som har varianter. Den är inte tillgänglig för specifika produkter eller paket.

Du kan konfigurera lagersökningsfunktionen så att den visas som en länk i knapprutnätet på kassatransaktionsskärmen. Efter konfigurationen, när användaren väljer en varukorgsrad och sedan väljer knappen **Lagersökning** visas listvyn av lagersökningen för den valda produkten. Mer information om hur du konfigurerar knapprutnät med hjälp av verktyget för layout av kassaskärm finns i [Visuella konfigurationer av kassaanvändargränssnitt](pos-screen-layouts.md).

## <a name="inventory-lookup-with-channel-side-calculation"></a>Lagersökning med beräkning på kanalsidan

I Commerce-utgåvan 10.0.9 och tidigare hämtas det **tillgängliga fysiska** värdet i lagersökningsfunktionen från Commerce Headquarters via ett servicesamtal i realtid. I Commerce-utgåvan 10.0.10 och senare kan du konfigurera lagersökningsfunktionen i kassan för att använda beräkning på kanalsidan på Commerce-servern för att fastställa det tillgängliga fysiska värdet, vilket kan ge en mer pålitlig och korrekt uppskattning av lagerbehållningen genom att ta transaktionsdata som ännu inte synkroniserats till huvudkontoret i beaktande. Mer information om lagerberäkning på kanalsidan och relaterad kassakonfiguration i huvudkontoret finns i [Beräkna lagertillgänglighet för butikskanaler](calculated-inventory-retail-channels.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Visuella konfigurationer för kassaanvändargränssnitt](pos-screen-layouts.md)

[Beräkna lagertillgänglighet för butikskanaler](calculated-inventory-retail-channels.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
