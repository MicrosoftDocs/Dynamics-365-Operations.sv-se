---
title: Huvudplanering med inköpshandelsavtal
description: Denna artikel beskriver hur Planeringsoptimering kan hitta leverantörs- och/eller produktionstid för en planerad order, baserat på det bästa priset eller den produktionstid som finns i inköpshandelsavtal.
author: t-benebo
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 29f0f44289e44b21cb304bd1f423d63f9f58f2db
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873765"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Huvudplanering med inköpshandelsavtal

[!include [banner](../../includes/banner.md)]

Denna artikel beskriver hur Planeringsoptimering kan hitta leverantören och/eller ledtiden för en planerad order, baserat på det bästa priset eller ledtiden som finns bland alla köphandelsavtal som har specificerats för en viss produkt.

## <a name="turn-on-the-purchase-trade-agreements-for-planning-optimization-feature"></a>Aktivera inköpshandelsavtal för Planeringsoptimerinsfunktion

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *huvudplanering*
- **Funktionsnamn:** *inköpshandelsavtal för Planeringsoptimerinsfunktion*

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Förbered systemet för utvärdering av inköpshandelsavtal under huvudplanering

Följ dessa steg för att konfigurera systemet för att tillämpa Planeringsoptimering som utvärderar inköpshandelsavtal.

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

    - På fliken **Allmänt** kan du konfigurera leverantörs åsidosättningar. Om du vill att Planeringsoptimering ska använda köphandelsavtal för att välja en leverantör bör du förhindra leverantörsöverskridande genom att rensa **Använd specifik inställning**.
    - På fliken **produktionstid** kan du konfigurera ledtidsåsidosättningar. Om du vill att Planeringsoptimering ska använda köphandelsavtal för att välja ledtider bör du förhindra överskridande av ledtid. Avmarkera kryssrutan för varje typ av produktionstid som du vill välja genom att använda inköpshandelsavtal ( **inköp**, **produktion** och/eller **överföring**).

1. Stäng sidan **artikeldisponering** återgå till informationssidan för den valda produkten.
1. I åtgärdsfönstret på fliken **Plan** i gruppen **Prognos** välj **Leveransprognos** för att öppna sidan **Leveransprognos**. Kontrollera att ingen rad som visas här har ett värde i kolumnen **leverantörskonto**.
1. Stäng sidan **Leveransprognos** återgå till informationssidan för den valda produkten.
1. I åtgärdsfönstret på fliken **Inköp** i gruppen **Handelsavtalen** väljer du **Visa handelsavtal**. Se till att alla relevanta inköpshandelsavtal listas. Se även till att alternativet **Se bort från ledtid** anges till **Nej** för varje avtal där du vill att Planeringsoptimering ska använda ledtiden som har angetts för avtalet.
1. Åtgärdsfönster, på fliken **Plan** i grupp **Orderinställningar** och klicka på **Standardorderinställningar** för att öppna sidan **Standardorderinställningar** för den valda produkten. På snabbfliken **Inköpsorder** visa värdet för fältet **Ledtid för inköp**. Om ingen åsidosättning av ledtidsöverskridande av artiklar definieras kommer Planeringsoptimering att använda detta värde när det väljer handelsavtal där alternativet **Se bort från ledtid** är inställt på **Ja**. Därför bör du justera det här värdet efter behov.
1. Upprepa den här proceduren för varje relevanta produkter.

> [!NOTE]
> Planeringsoptimeringen stöder inköpshandelsavtal med flera valutor. När systemet söker efter ett handelsavtal med alternativet **Lägsta enhetspris** överväger systemet inköpshandelsavtalsrader med olika valutor under förutsättning att en valutakurs har definierats mellan handelsavtalsradens valuta och redovisningsvalutan för den juridiska personen. I annat fall ignoreras handelsavtalsraden och ett fel visas under huvudplaneringen. Huvudplaneringen kommer därför att innehålla information från alla relevanta inköpshandelsavtalsrader där priser kan konverteras till redovisningsvalutan. Det är viktigt att notera att avrundningsreglerna inte kommer att beaktas under omräkningen av handelsavtalets radpris.

## <a name="examples-of-how-planning-optimization-finds-vendor-and-lead-times"></a>Exempel på hur Planeringsoptimering hittar leverantörs- och produktionstider

I följande tabell finns exempel som visar hur olika inställningar för en frisläppt produkt och den tillhörande inköpshandelsavtal påverkar de värden som finns för den resulterande planerade inköpsordern. De **fetstilta** värdena i de två kolumnerna längst till höger är de värden som väljs genom Planeringsoptimering. Värdena **_fet och kursiv_** i de andra kolumnerna är de inställningar som gav dessa resultat värden för varje rad.

| Frisläppt produkt: Leverantör | Standardorderinställningar: Ledtid | Artikeldisponering: åsidosätta leverantör | Artikeldisponering: åsidosätta ledtid | Handelsavtal: Leverantör | Handelsavtal: ledtid | Handelsavtal: ignorera ledtid | Resulterande leverantör | Resulterande ledtid |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ***US001** _ | _*_1_*_ | Nej | Nej | US003 | 3 | Nej | _ *US001** | **1** |
| US001 | 1 | ***Ja: US002** _ | _*_Ja: 2_*_ | US003 | 3 | Nej | _ *US002** | **2** |
| *(Tom)* | 1 | Nej | Nej | ***US003** _ | _*_3_*_ | Nej | _ *US003** | **3** |
| *(Tom)* | ***1** _ | Nej | Nej | _*_US003_*_ | 3 | Ja | _ *US003** | **1** |
| *(Tom)* | ***1** _ | _*_Ja: US002_*_ | Nej | US003 | 3 | Nej | _ *US002** | **1** |
| *(Tom)* | ***1** _ | _*_Ja: US002_*_ | Nej | US003 | 3 | Nej | _ *US002** | **1** |
| *(Tom)* | 1 | Nej | Ja: 2 | ***US003** _ | _*_3_*_ | Nej | _ *US003** | **3** |
| *(Tom)* | 1 | Nej | ***Ja: 2** _ | _*_US003_*_ | 3 | Ja | _ *US003** | **2** |

## <a name="additional-resources"></a>Ytterligare resurser

[Inköpsavtal](../../procurement/purchase-agreements.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
