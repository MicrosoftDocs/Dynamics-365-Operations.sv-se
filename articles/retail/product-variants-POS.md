---
title: "Lagersökning i kassan"
description: "Det här avsnittet beskriver de alternativ som är tillgängliga för visning av lagerinformation i kassan."
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 933875f56b0f47990cb1cb767f84b23b9c9710d4
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="inventory-lookup-in-the-point-of-sale"></a>Lagersökning i kassan 

[!include [banner](includes/banner.md)]

Lagersökning i kassan hjälper återförsäljare att effektivisera verksamheten i realtid och få inblick genom att ansluta butiker, kassor och backoffice. Den här funktionen ger en korrekt produktinformation i realtid genom butiker och distributionscenter. Den underlättar också för återförsäljare att skapa ytterligare effektivitet och kostnadsbesparingar genom att förbättra lagerplanering i realtid.

En korrekt översikt över lager i realtid i en organisation kan ger snabb, överlägsen kundservice. Den tidpunkt som är viktigast är den tidpunkt när kunden är redo att göra ett inköp. Det är viktigt att kassörerna i butiken har lagerinformation lättåtkomlig i realtid, så att de korrekt kan lova produktleverans och hämtning.

Du kan öppna sidan **Lagersökning** från arbetsytan **Retail Modern POS** eller arbetsytan **Retail Cloud POS**.

![Lagersökningspanelen i kassans startsida](media/POSHomepage.png)

På sidan **Lagersökning** kan du använda det numeriska tangentbordet för att ange ett produktnummer. Du kan sedan visa lagerbehållningen för flera butiker och lagerställen.

![Standardinställda lagersökningssidan](media/InventoryLookUp.png)

Kvantiteterna **Reserverat** och **Beställt** visas också för varje plats.

- **Reserverat** – denna kvantitet syftar till värdet **Reserverat fysiskt** från backoffice för det angivna produktnumret på platsen.
- **Beställt** – denna kvantitet syftar till värdet **Totalt beställt** från backoffice för det angivna produktnumret på platsen.

## <a name="locations-that-inventory-availability-information-is-shown-for"></a>Platser som lagertillgänglighetsinformation visas för

Listan över platser innehåller två typer av enheter:

- **Butiker** – Listab visar butiker som konfigureras med hjälp av butikslokaliserargruppen för den aktuella butiken i Butik administration. 
- **Distributionscenter** – olika typer av distributionscenter (till exempel lagerställen) kan konfigureras i Microsoft Dynamics 365 for Retail. I listan visas dock endast lagertillgänglighetsinformation för distributionscenter av standardtypen **Standard**. 

    > [!NOTE]
    > Lagertillgänglighetsinformation visas inte för lagerställe av typerna **transport**, **karantän** och **varor på väg** för kassan.

På sidan **Lagersökning** kan du visa  disponibelt att lova-kvantiteter (ATP) för varje butik, utöver de aktuella lagerbehållningskvantiteterna, reserverade kvantiteter och beställda kvantiteter. Välj butiken som du vill visa ATP-information för och välj sedan **Visa tillgänglighet för butik**.

![ATP-mängder](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a>Öppna vyn Dimensionsbaserad matris för att visa alla varianter

På sidan **produktinformation** för en produktmall eller på sidan **Lagersökning** anger du **visa alla varianter** från appfältet längst ned på sidan. Vyn **Dimensionsbaserad matris** för första resultatet från dessa sidor visar lagertillgänglighetsinformation för alla varianter av en produkt för den aktuella butiken.

> [!NOTE]
> Knappen **visa alla varianter** är bara tillgängligt för artikelproduktmallar som har produktvarianter. De är inte tillgängliga för fristående produkter eller paket.

![Visa knappen för alla varianter på lagersöksidan](media/StandardToMatrix.png)

Välj **Visa alla varianter** på sidan **Produktinformation** för en produktmall eller sidan **Lagersökning** utan att välja en plats för att gå till vyn **Dimensionsbaserad matris** för att visa lagertillgänglighetsinformationen för alla varianter av en produkt för den aktuella butiken.

![Vyn Dimensionsbaserad matris för lagersöksidan](media/Matrix.png)

> [!NOTE]
> I den föregående bilden är visningsordningen för dimensionerna alfabetiskt, eftersom visningsordningen för dimensioner inte konfigurerats för den valda produkten.

I vyn **Dimensionsbaserad matris** inkluderar cellerna för produktvarianter ett lagerbehållningsvärde i det nedre högra hörnet. Följande tabell förklarar innebörden av olika värden.

| Behållningsvärde                            | beskrivning |
|------------------------------------------|-------------|
| Numeriskt värde som är större än 0 (noll) | En variant har frisläppts till den angivna platsen och du kan utföra ytterligare åtgärder i cellen. (Dessa åtgärder kommer att beskrivas mer utförligt i detta ämne.) |
| **0** (noll)                             | En variant har frisläppts till den valda platsen, men artikeln är inte tillgänglig på den valda platsen. Du kan emellertid utföra ytterligare åtgärder i cellen. (Dessa åtgärder kommer att beskrivas mer utförligt i detta ämne.) |
| **Ej tillämpligt** eller en inaktiv cell              | En variant har inte frisläppts till den angivna platsen och du kan inte utföra ytterligare åtgärder i cellen. |

Du kan också ändra pivot för dimensioner genom att välja att använda den nya dimensionen. 

![Ändra pivot](media/ChangePivot.png)

![Pivot ändrad](media/PivotChanged.png)

> [!NOTE]
> I föregående illustrationer är visningsordningen för dimensionerna för den valda produkten anpassade (icke-alfabetiska). Den är baserad på visningsordningen för dimensioner som har angetts i backoffice.

Dessutom i vyn **Dimensionsbaserad matris** kan fler åtgärder utföras för att öka en butiksmedarbetares produktivitet. Nedan följer några exempel:

- Ändra lagringsplats för att slå upp lagerdispositionen för alla produktvarianter på andra platser. De här platserna inkluderar andra butiker i butikslokaliserargruppen och distributionscenter av standardtypen **Standard**.
- Sälja ett enskild produktvariant till en kund med hjälp av cash and carry, hämtning i butik eller leverans till en adress.
- Tillhandahålla kunden ATP-information för en enskild produktvariant på en viss plats.

![Ytterligare åtgärder för variantpaneler](media/VariantActions.png)

> [!NOTE]
> I den föregående bilden är visningsordningen för dimensionerna alfabetiskt, eftersom visningsordningen för dimensioner inte konfigurerats för den valda produkten.

Följande tabell visar mer information om ytterligare åtgärder som är tillgängliga.


|        Åtgärd        |                                                                                                                    beskrivning                                                                                                                    |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       Sälj nu       |                               Lägg till vald artikelvariant till transaktionen och omdirigera användaren till skärmbilden för transaktionen. (Den här åtgärden är inte tillgänglig när den markerade platsen är ett distributionscenter.)                               |
|   Hämta i butik   |      Skapa kundorder för produktvarianten som ska hämtas från den valda platsen och dirigera om användaren till skärmbilden för transaktionen. (Den här åtgärden är inte tillgänglig när den markerade platsen är ett distributionscenter.)       |
|     Leverera produkt     |                                                 Skapa kundorder för produktvarianten som ska levereras från den valda platsen och dirigera om användaren till skärmbilden för transaktionen.                                                 |
|     Tillgänglighet     |                                                                             Visa ATP-information om den valda variantkombinationen för den valda platsen.                                                                              |
|  Visa alla platser  | Växla till standardinställda lagersökningsvyn och markera lagertillgänglighetsinformation för artikelvarianten i alla butiker i butikslokaliserargruppen samt i distributionscenter av typen <strong>Standard/standard</strong>. |
| Visa produktinformation |                                                                         Omdirigera användaren till sidan <strong>produktinformation</strong> med den associerade produktmallen.                                                                          |


