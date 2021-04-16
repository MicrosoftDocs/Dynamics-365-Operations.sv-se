---
title: Gruppering av påfyllnadsmall
description: Gruppering av påfyllnadsmall gör att systemet kan använda inställningar för påfyllnadsmall för att fastställa, baserat på kriterier som du definierar, hur den ska dela upp frisläppta rader och tilldela dem till ny eller befintlig påfyllnad. Den här funktionen kan vara användbar i lagerställen där påfyllnad skapas baserat på specifika kriterier, men där chefer föredrar att skapa påfyllnad automatiskt i stället för manuellt.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: a591624f6611148abe4888e67d8d3a9bbea9cd27
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838044"
---
# <a name="wave-template-grouping"></a>Gruppering av påfyllnadsmall

[!include [banner](../includes/banner.md)]

Gruppering av påfyllnadsmall gör att systemet kan använda inställningar för [påfyllnadsmall](tasks/configure-wave-processing.md) för att fastställa, baserat på kriterier som du definierar, hur den ska dela upp frisläppta rader och tilldela dem till ny eller befintlig påfyllnad. Den här funktionen kan vara användbar i lagerställen där påfyllnad skapas baserat på specifika kriterier, men där chefer föredrar att skapa påfyllnad automatiskt i stället för manuellt. Det gör det möjligt för systemet att lägga till varje ny frisläppt utleverans till den första påfyllnad som den finner som har matchande värden i en grupp. Om ingen matchning hittas skapar systemet en ny påfyllnad för den nya försändelsen.

> [!IMPORTANT]
> Gruppering av påfyllnadsmallar stöds inte för arbetstypen *produktion av råmaterialplockning* eller *Kanban-plockning*. Detta beror på att påfyllnadsgrupperingen baseras på försändelser och att dessa arbetstyper inte använder försändelser.

## <a name="turn-on-the-wave-template-grouping-feature"></a>Aktivera funktionen gruppering av påfyllnadsmallar

Innan du kan använda funktionen *Gruppering av påfyllnadsmall* den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *Gruppering av påfyllnadsmall*

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a>Ställa in en påfyllnadsmall för att använda en gruppering av påfyllnadsmall

Följ stegen för att ställa in din gruppering av påfyllnadsmall tillgänglig [påfyllnadsmall](tasks/configure-wave-processing.md).

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. Välj den påfyllnadsmall som du vill ställa in i det vänstra fönstret. Om du förbereder dig att arbeta under scenariot senare i det här avsnittet genom att använda demodata, ska du välja mallen **62 standard för leverans**.
1. Välj **Redigera** om du vill placera sidan i redigeringsläge.
1. Ange följande värden på snabbfliken **Allmänt**:

    - **Automatisera skapande av påfyllnad:** *Ja*
    - **Tilldela till öppna vågor:** *Ja*
    - **Bearbeta påfyllnaden vid släpp till lager:** *Nej*

1. I åtgärdsfönstret, välj **Redigera fråga** för att öppna dialogrutan för fråga.
1. I dialogrutan för fråga, på fliken **Sortera** granska sorteringskriterierna och se till att det finns en regel som innehåller fältet som du vill använda för att gruppera dina påfyllnader.

    Om du förbereder dig att arbeta genom scenariot genom att använda demodata, lägger du till en rad med följande värden:

    - **Register:** *försändelser*
    - **Härlett register:** *försändelser*
    - **Fält:** *Transportföretag*

        > [!NOTE]
        > När du har valt det här värdet kan följande meddelande visas: "fältet transportföretagstjänst är inte ett indexfält. Vill du lägga till sortering i det här? " Välj **Ja** om du vill lägga till sortering.

    - **Sökriktning:** *Stigande*

1. Välj **OK** om du vill spara dina ändringar fråga och stänga dialogrutan för fråga.
1. I åtgärdsfönstret, välj **Gruppering av påfyllnadsmall**.
1. På sidan **Gruppering av påfyllnadsmall**, välj kryssrutan **Gruppera efter** för varje rad som du vill använda för att gruppera dina orderrader i påfyllnad, efter behov. Om du förbereder dig att arbeta genom scenariot genom att använda demodata markerar du kryssrutan **Gruppera efter** för *Transportföretagstjänsten*.
1. Välj **Spara**.
1. Stäng sidan **Gruppering av påfyllnadsmall**.
1. Spara din mall genom att klicka på **Spara**.

## <a name="scenario"></a>Scenario

I det här avsnittet finns ett skript som du kan arbeta igenom för att lära dig vad funktionen gör och hur du använder den.

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

Du kan också använda detta scenario som vägledning för funktionen när du arbetar med ett produktionssystem. I så fall måste du emellertid ersätta dina egna värden och du kanske saknar vissa typer av obligatoriska poster som används i standard demodata.

### <a name="scenario-wave-template-grouping"></a>Scenario: Gruppering av påfyllnadsmall

Det här scenariot visar hur du använder en gruppering av påfyllnadsmall för att automatiskt skapa flera påfyllningar, baserat på de grupperingsinställningar som har definierats i en påfyllnadsmall. I det här scenariot ställs påfyllnadsmallen in i systemet för att skapa en påfyllnad per transportföretagstjänst.

Innan du börjar ska du förbereda din påfyllnadsmall på det sätt som beskrivs i [Ställa in en påfyllnadsmall för att använda en gruppering av påfyllnadsmall](#set-up-template) i det här avsnittet. Om du kommer att arbeta med demodata för det här scenariot måste du använda de demodatavärden som föreslås i den proceduren. Den här inställningen grupperar påfyllnader enligt den transportföretagstjänst som ställs in för varje försäljningsorder.

#### <a name="create-sales-order-1"></a>Skapa försäljningsorder 1

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-004*.
    - På snabbfliken **Allmänt** anger du fältet **Lagerställe** till *62*.

1. Välj **OK** för att skapa försäljningsordern och stänga dialogrutan **Skapa försäljningsorder**.
1. Den nya försäljningsordern öppnas i vyn **Rader**. Anteckna försäljningsordernumret.
1. Växla till vyn **Rubrik**.
1. På snabbfliken **Leverans** i avsnittet **Transport** anger du följande värden:

    - **Transportföretag:** *Luftfrakt*
    - **Transportföretag:** *Flyg*

1. Växla tillbaka till vyn **Rader**.
1. I avsnittet **Försäljningsorderrader** välj **Lägg till** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Artikelnummer:** *A0002*
    - **Kvantitet:** *2*

1. Markera den nya orderraden och i menyn **Lager** ovanför rutnätet väljer du **Reservation**.
1. På sidan **Reservation** i åtgärdsfönstret väljer du **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.
1. Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern. Anteckna påfyllnadens ID-nummer och försändelsens ID-nummer.

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a>Visa påfyllnad som skapades från försäljningsorder 1

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj påfyllnads-ID som skapades från försäljningsorder.
1. Klicka på påfyllnad ID-länken om du vill öppna sidan med påfyllnadsinformation.
1. Observera att leveransen har lagts till på snabbfliken **Påfyllnadsrader**.

#### <a name="create-sales-order-2"></a>Skapa försäljningsorder 2

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-005*.
    - På snabbfliken **Allmänt** anger du fältet **Lagerställe** till *62*.

1. Välj **OK** för att skapa försäljningsordern och stänga dialogrutan **Skapa försäljningsorder**.
1. Den nya försäljningsordern öppnas i vyn **Rader**. Anteckna försäljningsordernumret.
1. Växla till vyn **Rubrik**.
1. På snabbfliken **Leverans** i avsnittet **Transport** anger du följande värden:

    - **Transportföretag:** *blomma, flytta*
    - **Transportföretag:** *Std*

1. Växla tillbaka till vyn **Rader**.
1. I avsnittet **Försäljningsorderrader** välj **Lägg till** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *1*

1. Markera den nya orderraden och i menyn **Lager** ovanför rutnätet väljer du **Reservation**.
1. På sidan **Reservation** i åtgärdsfönstret väljer du **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.
1. Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern. Anteckna påfyllnadens ID-nummer och försändelsens ID-nummer. Observera att påfyllnads-ID skiljer sig från påfyllnads-ID för den första försäljningsordern.

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a>Visa påfyllnad som skapades från försäljningsorder 2

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj påfyllnads-ID som skapades från den andra försäljningsordern.
1. Klicka på påfyllnad ID-länken om du vill öppna sidan med påfyllnadsinformation.
1. Observera att leveransen har lagts till på snabbfliken **Påfyllnadsrader**.

En ny påfyllnad skapades för den här leveransen eftersom den använder en annan transportföretagstjänst än den första försäljningsordern.

#### <a name="create-sales-order-3"></a>Skapa försäljningsorder 3

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-006*.
    - På snabbfliken **Allmänt** anger du fältet **Lagerställe** till *62*.

1. Välj **OK** för att skapa försäljningsordern och stänga dialogrutan **Skapa försäljningsorder**.
1. Den nya försäljningsordern öppnas i vyn **Rader**. Anteckna försäljningsordernumret.
1. Växla till vyn **Rubrik**.
1. På snabbfliken **Leverans** i avsnittet **Transport** anger du följande värden:

    - **Transportföretag:** *Luftfrakt*
    - **Transportföretag:** *Flyg*

1. Växla tillbaka till vyn **Rader**.
1. I avsnittet **Försäljningsorderrader** välj **Lägg till** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *1*

1. Markera den nya orderraden och i menyn **Lager** ovanför rutnätet väljer du **Reservation**.
1. På sidan **Reservation** i åtgärdsfönstret väljer du **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.
1. Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern. Anteckna påfyllnadens ID-nummer och försändelsens ID-nummer. Försändelsen har tilldelats den befintliga påfyllnaden från den första försäljningsordern.

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a>Visa påfyllnad för försäljningsorder 1 och 3

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj påfyllnads-ID som skapades från den tredje försäljningsordern.
1. Klicka på påfyllnad ID-länken om du vill öppna sidan med påfyllnadsinformation.
1. Observera att leveransen har lagts till på snabbfliken **Påfyllnadsrader**, tillsammans med leveransen för den första försäljningsordern.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]