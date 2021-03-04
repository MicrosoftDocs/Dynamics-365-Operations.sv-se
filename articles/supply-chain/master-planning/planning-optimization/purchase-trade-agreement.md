---
title: Huvudplanering med inköpshandelsavtal
description: Det här ämnet beskriver hur planeringsoptimering kan hitta leverantörs-och/eller produktionstid för en planerad order, baserat på det bästa priset eller den produktionstid som finns i inköpshandelsavtal.
author: ChristianRytt
manager: tfehr
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: b302c5ace34a11a53a98c733b59633a11a463bfa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437446"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Huvudplanering med inköpshandelsavtal

[!include [banner](../../includes/banner.md)]

Det här ämnet beskriver hur planeringsoptimering kan hitta leverantören och/eller ledtiden för en planerad order, baserat på det bästa priset eller ledtiden som finns bland alla köphandelsavtal som har specificerats för en viss produkt.

## <a name="turn-on-the-purchase-trade-agreements-for-planning-optimization-feature"></a>Aktivera inköpshandelsavtal för planeringsoptimeringsfunktion

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *huvudplanering*
- **Funktionsnamn:** *inköpshandelsavtal för planeringsoptimeringsfunktion*

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Förbered systemet för utvärdering av inköpshandelsavtal under huvudplanering

Följ dessa steg för att konfigurera systemet för att tillämpa planeringsoptimering som utvärderar inköpshandelsavtal.

1. Gå till **Huvudplanering \> Inställningar \> Huvudplaneringsparametrar**. På fliken **planerade order** i avsnittet **leverantör** anger du följande värden:

    - **Sök efter handelsavtal** – Ställ in det här alternativet på **Ja** om du vill inkludera inköpshandelsavtal i huvudplaneringen.
    - **Sökkriterium** – Välj den faktor som du vill prioritera för varje inköpshandelsavtal: **minsta produktionstid** eller **lägsta enhetspris**.

1. Gå till **Anskaffning och källa \> Inställningar \> Priser och rabatter \> Aktivera pris/rabatt** och se till att alternativet **leverantör** är inställt på **Ja**.
1. Gå till **Produktinformationshantering \> Inställning \> Dimension- och variantgrupper \> Lagringsdimensionsgrupper** och välj lagringsdimensiongrupp som gäller för produkter som behärskar planering bör utvärdera köphandelsavtal för. Se till att varje relevant lagringsdimension i den här gruppen har en bockmarkering i kolumnen **För inköpspriser**. Upprepa det här steget för alla andra relevanta lagringsdimensionsgrupper.

## <a name="prepare-a-released-product-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Förbered en släppt produkt för utvärdering av inköpshandelsavtal under huvudplanering

När systemet har beretts enligt beskrivningen i föregående avsnitt ska du se till att varje produkt som du vill använda med den här funktionen är korrekt inställt.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter** och öppna en målprodukt.
1. På snabbfliken **Inköp** ser du till att ingen leverantör har tilldelats i fältet **Leverantör**.
1. Åtgärdsfönster, på fliken **Plan** i grupp **Disponering** och klicka på **Artikeldisponering** för att öppna sidan **Artikeldisponering** för den valda produkten. Verifiera följande inställning:

    - På fliken **Allmänt** kan du ställa in leverantörs åsidosättningar. Om du vill att Planeringsoptimering ska använda köphandelsavtal för att välja en leverantör bör du förhindra leverantörsöverskridande genom att rensa **Använd specifik inställning**.
    - På fliken **produktionstid** kan du ställa in ledtidsåsidosättningar. Om du vill att planeringsoptimering ska använda köphandelsavtal för att välja ledtider bör du förhindra överskridande av ledtid. Avmarkera kryssrutan för varje typ av produktionstid som du vill välja genom att använda inköpshandelsavtal ( **inköp**, **produktion** och/eller **överföring**).

1. Stäng sidan **artikeldisponering** återgå till informationssidan för den valda produkten.
1. I åtgärdsfönstret på fliken **Plan** i gruppen **Prognos** välj **Leveransprognos** för att öppna sidan **Leveransprognos**. Kontrollera att ingen rad som visas här har ett värde i kolumnen **leverantörskonto**.
1. Stäng sidan **Leveransprognos** återgå till informationssidan för den valda produkten.
1. I åtgärdsfönstret på fliken **Inköp** i gruppen **Handelsavtalen** väljer du **Visa handelsavtal**. Se till att alla relevanta inköpshandelsavtal listas. Se även till att alternativet **Se bort från ledtid** anges till **Nej** för varje avtal där du vill att planeringsoptimering ska använda ledtiden som har angetts för avtalet.
1. Åtgärdsfönster, på fliken **Plan** i grupp **Orderinställningar** och klicka på **Standardorderinställningar** för att öppna sidan **Standardorderinställningar** för den valda produkten. På snabbfliken **Inköpsorder** visa värdet för fältet **Ledtid för inköp**. Om ingen åsidosättning av ledtidsöverskridande av artiklar definieras kommer planeringsoptimering att använda detta värde när det väljer handelsavtal där alternativet **Se bort från ledtid** är inställt på **Ja**. Därför bör du justera det här värdet efter behov.
1. Upprepa den här proceduren för varje relevanta produkter.

> [!NOTE]
> Valutan på inköpshandelsavtalsraden måste stämma överens med valutan för den valda leverantören. Huvudplaneringen innehåller endast information från inköpshandelsavtalsrader där valutan matchar valutan på leverantören.

## <a name="examples-of-how-planning-optimization-finds-vendor-and-lead-times"></a>Exempel på hur planeringsoptimering hittar leverantörs- och produktionstider

I följande tabell finns exempel som visar hur olika inställningar för en frisläppt produkt och den tillhörande inköpshandelsavtal påverkar de värden som finns för den resulterande planerade inköpsordern. De **fetstilta** värdena i de två kolumnerna längst till höger är de värden som väljs genom planeringsoptimering. Värdena ***fet och kursiv*** i de andra kolumnerna är de inställningar som gav dessa resultat värden för varje rad.

| Frisläppt produkt: Leverantör | Standardorderinställningar: Ledtid | Artikeldisponering: åsidosätta leverantör | Artikeldisponering: åsidosätta ledtid | Handelsavtal: Leverantör | Handelsavtal: ledtid | Handelsavtal: ignorera ledtid | Resulterande leverantör | Resulterande ledtid |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ***US001*** | ***1*** | Nr | Nr | US003 | 3 | Nr | **US001** | **1** |
| US001 | 1 | ***Ja: US002*** | ***Ja: 2*** | US003 | 3 | Nr | **US002** | **2** |
| *(Tom)* | 1 | Nr | Nr | ***US003*** | ***3*** | Nr | **US003** | **3** |
| *(Tom)* | ***1*** | Nr | Nr | ***US003*** | 3 | Ja | **US003** | **1** |
| *(Tom)* | ***1*** | ***Ja: US002*** | Nr | US003 | 3 | Nr | **US002** | **1** |
| *(Tom)* | ***1*** | ***Ja: US002*** | Nr | US003 | 3 | Nr | **US002** | **1** |
| *(Tom)* | 1 | Nr | Ja: 2 | ***US003*** | ***3*** | Nr | **US003** | **3** |
| *(Tom)* | 1 | Nr | ***Ja: 2*** | ***US003*** | 3 | Ja | **US003** | **2** |

## <a name="additional-resources"></a>Ytterligare resurser

[Inköpsavtal](../../procurement/purchase-agreements.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]