---
title: Ställ in olika dimensioner för förpackning och lagring
description: I denna artikel visas hur du anger vilken process (förpackning, lagring eller kapslad förpackning) som varje dimension används för.
author: Mirzaab
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8ebea86e5ea63ab4f5a844cd3d0936c0d65bbe2b
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220255"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a>Ställ in olika dimensioner för förpackning och lagring

[!include [banner](../../includes/banner.md)]

Vissa artiklar packas eller lagras på ett sådant sätt att du kan behöva spåra fysiska dimensioner olika för vart och ett av flera olika processer. Funktionen *Dimensioner för förpackningsprodukt* gör att du kan konfigurera en eller flera typer av dimensioner för varje produkt. Varje dimensionstyp tillhandahåller en uppsättning fysiska mått (vikt, bredd, djup och höjd) och använder den process där de fysiska mätningsvärdena gäller. När den här funktionen är aktiverad har ditt system stöd för följande typer av dimensioner:

- *Lagring* - Lagringsdimensioner används tillsammans med platsvolym för att bestämma hur många av varje artikel som kan lagras på olika lagerställen.
- *Förpackning* - Förpackningsdimensioner används under skapande av behållare och manuell förpackningsprocess för att bestämma hur många av varje artikel som kommer att passa i olika behållartyper.
- *Kapslad förpackning* - Kapslade förpackningsdimensioner används när förpackningsprocessen innehåller flera nivåer.

*Lagringsdimensioner* stöds även om funktionen *Förpackningsproduktdimensioner* inte är aktiverad. Du konfigurerar dessa med hjälp av sidan **Fysisk dimension** i Supply Chain Management. Dessa dimensioner används av alla processer där förpacknings- och kapslade förpackningsdimensioner inte anges.

Dimensionerna *förpackning* och *kapslad förpackning* ställs in på sidan **Fysiska produktdimensioner** som läggs till när du aktiverar funktionen för *förpackningsproduktdimensioner*.
Denna artikel innehåller ett scenario som illustrerar hur den här funktionen används.

## <a name="turn-on-the-packaging-product-dimensions-feature"></a>Aktivera funktionen för förpackningsproduktdimensioner

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *förpackningsproduktdimensioner*

## <a name="example-scenario"></a>Exempelscenario

### <a name="set-up-the-scenario"></a>Ställ in scenario

Innan du kan köra exempelscenariot måste du förbereda systemet på det sätt som beskrivs i det här avsnittet.

#### <a name="enable-demo-data"></a>Aktivera demonstrationsdata

Om du vill arbeta genom detta scenario med hjälp av de demoposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) har installerats. Dessutom måste du välja den *USMF* juridiska personen innan du börjar.

#### <a name="add-a-new-physical-dimension-to-a-product"></a>Lägga till en ny fysisk dimension i en produkt

Lägg till en ny fysisk dimension för en produkt genom att göra följande:

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj produkten med **artikelnummer** *A0001*.
1. I åtgärdsfönstret, öppna fliken **Hantera lager**, i gruppen **Lagerställe**, väljer du **Fysiska produktdimensioner**.
1. Sidan **Fysiska produktdimensioner** öppnas. I åtgärdsfönstret, välj **Ny** för att lägga till en ny dimension i rutnätet med följande inställningar:
    - **Fysisk dimensionstyp** - *förpackning*
    - **Fysiska enheter** - *st*
    - **Vikt** - *4*
    - **Viktenhet** - *kg*
    - **Djup** - *3*
    - **Höjd** - *4*
    - **Bredd** - *3*
    - **Längd** - *cm*
    - **Volymenhet** - *cm3*

Fältet **Volym** beräknas automatiskt baserat på inställningarna **djup**, **höjd** och **bredd**.

#### <a name="create-a-new-container-type"></a>Skapa en ny behållartyp

Gå till **Lagerstyrning \> Inställningar \> Behållare \> Behållartyper** och skapa en ny post med följande inställningar:

- **Behållartyp** - *liten kartong*
- **Beskrivning** - *liten kartong*
- **Högsta nettovikt** - *50*
- **Volym** - *144*
- **Längd** - *6*
- **Bredd** - *6*
- **Höjd** - *4*

#### <a name="create-a-container-group"></a>Skapa en behållargrupp

Gå till **Lagerstyrning \> Inställningar \> Behållare \> Behållargrupper** och skapa en ny post med följande inställningar:

- **Behållargrupp-ID** - *liten kartong*
- **Beskrivning** - *liten kartong*

Lägg till en ny rad i avsnittet **Information**. Ange att **behållartypen** är *liten kartong*.

#### <a name="set-up-a-container-build-template"></a>Ställa in en behållarversionsmall

Gå till **Lagerstyrning \> Inställningar \> Behållare \> Mall för skapande av behållare** och välj **Kartonger**. Ändra **behållargrupp-ID** till *liten kartong*.

### <a name="run-the-scenario"></a>Kör scenariot

När du har förberett systemet enligt beskrivningen i det föregående avsnittet är du redo att köra scenariot enligt beskrivningen i nästa avsnitt.

#### <a name="create-a-sales-order-and-create-a-shipment"></a>Skapa en försäljningsorder och skapa en försändelse

I denna process skapar du en försändelse baserad på artikelns *förpackningsdimensioner*, för vilken höjden är mindre än 3.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *63*

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Detta bör innehålla en ny tom rad i rutnätet på snabbfliken **försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *5*

1. På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.
1. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.
1. Stäng sidan.
1. I åtgärdsfönstret öppna fliken **Lagerställe** och välj **Släpp till lagerställe** för att skapa arbete för lagerstället.
1. På snabbfliken **försäljningsorderrad** välj **Lagerställe \> Leveransdetaljer**.
1. Öppna fliken arbetsflöde i åtgärdsfönstret **Transport** och välj **Visa behållare**. Bekräfta att artikeln har förpackats i de två behållarna *liten kartong*.

#### <a name="place-an-item-into-storage"></a>Förvara artikel

1. Öppna den mobila enheten, logga in på lagerställe 63 och gå till **Lager \> Justera i**.
1. Ange **Loc** = *SHORT-01*. Gör ett nytt ID-nummer med **artikel** = *A0001* och **kvantitet** = *1 st*.
1. Välj **OK**. Du får felmeddelandet "Plats SHORT-01 misslyckades eftersom artikel A0001 inte får plats i platsens angivna dimensioner." Det beror på att produktens *lagringstypdimensioner* är större än de dimensioner som anges i platsprofilen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]