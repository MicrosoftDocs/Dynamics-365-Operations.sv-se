---
title: Faktura för underhåll av kundägda tillgångar
description: I det här avsnittet beskrivs hur du skapar, bearbetar och fakturerar underhåll som utförs på tillgångar som dina kunder äger.
author: johanhoffmann
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a93436d101e6201c9d86279ea5b1a37fcc644fd1
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500464"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a>Faktura för underhåll av kundägda tillgångar

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

Med hjälp av funktionen *Fakturering av arbetsorder* låter dig skapa, bearbeta och fakturera underhållsarbete som utförs på tillgångar som dina kunder äger. Denna funktion låter dig utföra följande uppgifter:

- Koppla kunder till tillgångarna de äger.
- Välj en kund och visa de tillgångar som kunden äger när du skapar en arbetsorder.
- Ställ in ett överordnat projekt för varje kund.
- Registrera timmar, artiklar, utgifter och avgifter mot arbetsordern, och skapa sedan ett fakturaförslag för kunden senare.

Funktionen innehåller dessutom följande funktioner:

- Projektkontraktet från en kunds överordnade projekt kopieras automatiskt till det relevanta arbetsorderprojektet.
- Nu kan tillgångshanteringen använda projekttransaktionstyp *avgift* på både arbetsorderprognoser och arbetsorderjournaler.

## <a name="turn-on-the-customer-billing-feature"></a>Aktivera funktionen för kundbetalning

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Projekthantering och redovisning*
- **Funktionsnamn:** *Fakturering av arbetsorder*

## <a name="example-scenario"></a>Exempelscenario

Om du vill veta hur funktionen fungerar arbetar du med följande exempelscenario.

Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Du måste välja den **USMF** juridiska personen innan du börjar.

Du kan också använda detta scenario som vägledning för funktionen när du arbetar med ett produktionssystem. I så fall måste du emellertid ersätta dina egna värden och du kanske saknar vissa typer av obligatoriska poster som används i standard demodata.

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a>Steg 1: Skapa ett nytt projektkontrakt för kunden

1. Gå till **Projekthantering och redovisning \> Projekt \> Projektkontrakt**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **nytt projektkontrakt** anger du följande värden:

    - **Namn:** *Pelican Wholesales*
    - **Finansieringstyp:** *Kund*
    - **Finansieringskälla:** *US-013* (*Pelican Wholesales*)

1. Välj **OK**.

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a>Steg 2: Skapa ett nytt överordnat projekt för kunden

Det överordnade projekt som du skapar här används när arbetsorder för kunden skapas.

1. Gå till **Projekthantering och redovisning \> Projekt \> Alla projekt**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Nytt projekt** anger du följande värden:

    - **Projekttyp:** *Tid och material*
    - **Projektnamn:** *Pelican Wholesales arbetsorder*
    - **Projektgrupp:** *TM*
    - **Projektkontrakts-ID:** *Pelican Wholesales* (det kontrakt som du skapade tidigare)
    - **Startdatum:** Välj dagens datum.

1. Markera **Skapa projekt**.
1. Det nya projektet öppnas. Gör en notering om värdet **Projekt-ID**. Du måste skriva in den senare.

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a>Steg 3: Skapa en ny arbetsordertyp i Tillgångshantering

1. Gå till **Tillgångshantering \> Inställningar \> Arbetsorder \> Arbetsordertyper**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. En ny post läggs till i listan. Ange följande värden för den:

    - **Typ av arbetsorder:** *Tjänst*
    - **Namn:** *Arbetsorder för tjänst*
    - **Livscykeltillstånd för arbetsorder:** *Standard*

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a>Steg 4: Koppla kundkontot till det överordnade projektet

Du måste nu koppla kundkontot till det överordnade projektet i projektinställningarna i Tillgångshantering.

1. Gå till **Tillgångshantering \> Inställningar \> Arbetsorder \> Projektinställningar**.
1. På fliken **Överordnat projekt**, välj **Lägg till** om du vill lägga till en rad.
1. Ställ in följande värden på denna nya rad:

    - **Kundkonto:** *US-013* (*Pelican Wholesales*)
    - **Projekt-ID:** Ange projekt-ID som du antecknade tidigare.

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a>Steg 5: Koppla projektgruppen och typen till arbetsorderprojektet

Du bör fortfarande vara på sidan **Projektinställning** (**Tillgångshantering \> Inställningar \> Arbetsorder \> Projektinställning**).

1. På fliken **Projektgrupp**, välj **Lägg till** om du vill lägga till en rad.
1. Ställ in följande värden på denna nya rad:

    - **Arbetsordertyp:** *Tjänst* (arbetsordertypen som du skapade tidigare)
    - **Projektgrupp:** *TM*

> [!NOTE]
> Projektkontraktet i arbetsorderprojektet ärvs alltid från det överordnade projektet.

### <a name="step-6-link-an-asset-to-the-customer-id"></a>Steg 6: Koppla en tillgång till kund-ID:t

1. Gå till **Tillgångshantering \> Tillgångar \> Aktiva tillgångar**.
1. I fältet **Filter** anger du *VE-102* och väljer att filtrera efter **Tillgång**.
1. Markera den tillgång som du vill öppna dess inställningar för.
1. På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-013* (*Pelican Wholesales*).

    Fältet **Namn** uppdateras automatiskt till *Pelican Wholesales*.

### <a name="step-7-create-a-new-work-order-on-the-asset"></a>Steg 7: Skapa en ny arbetsordertyp i tillgången

1. Gå till **Tillgångshantering \> Arbetsorder \> Aktiva arbetsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa arbetsorder** ställ in följande värden:

    - **Typ av arbetsorder:** *Tjänst*
    - **Beskrivning:** *Reparera lastbil*
    - **Kundkonto:** *US-013* (*Pelican Wholesales*)
    - **Tillgång:** *VE-102*

        > [!NOTE]
        > I söken visas bara tillgångar som är länkade till det valda kundkontot.

    - **Typ av underhållsjobb:** *Reparera*
    - **Handel:** *Mekanisk*
    - **Tjänstenivå:** *4*

1. Välj **OK**.

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a>Steg 8: Granska arbetsordern och börja arbeta med den

I det här avsnittet arbetar du med arbetsordern som du skapade i det föregående avsnittet.

1. Följ dessa steg för att kontrollera att det överordnade projektet är *Pelican Wholesales arbetsorder*:

    1. I avsnittet **Underhållsjobb för arbetsorder**, välj en rad.
    1. På snabbfliken **raddetaljer** kontrollera värdet **Projekt-ID-ID**. Det bör vara ett bindestrecksnummer i formuläret *\<Parent-Project-ID\>-\<Project-ID\>*. Det här värdet är en länk.
    1. Markera projekt-ID-länken om du vill öppna en sida där du kan visa namn på det överordnade projektet och projektnamn.

1. I åtgärdsfönstret, på fliken **Arbetsorder**, i gruppen **livscykeltillstånd**, väljer du **Uppdatera arbetsorderns tillstånd**.
1. I dialogrutan **Uppdatera arbetsorderns tillstånd** i kolumnen **Välj** markera kryssrutan för raden där fältet **livscykeltillstånd** anges till *Pågår*.
1. Välj **OK**.
1. I dialogrutan **livscykeltillstånd: pågår**, välj **OK**.

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a>Steg 9: Bokför de timmar som har ägnats åt arbetsordern och skapa ett nytt fakturaförslag

I det här avsnittet fortsätter du arbeta med arbetsordern som du arbetade med i det föregående avsnittet.

1. I åtgärdsfönstret på fliken **Arbetsorder** i gruppen **Projekt** väljer du **Journaler**.

    Sidan **Arbetsorderjournaler** visas. Här kan du registrera den tid som du har ägnat åt arbetsordern.

1. På snabbfliken **Timmar** klickar du på **Lägg till rad**.
1. På den nya raden ställer du in fältet **Timmar** till *4*.
1. Klicka på **Bokför journaler** i åtgärdsfönstret.
1. Stäng sidan **Arbetsorderjournaler** när du vill återgå till arbetsordern.
1. Välj **Fakturering** på fliken **Nytt fakturaförslag** i åtgärdsfönstret.
1. I dialogrutan **Skapa fakturaförslag** i avsnittet **Projekttransaktioner**, markera kryssrutan **Välj** för varje rad som du vill fakturera.
1. Välj **OK** för att stänga dialogrutan och visa det nya fakturaförslaget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]