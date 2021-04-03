---
title: Förpackningsmaterial och avgifter
description: I det här avsnittet finns information om avgifter för förpackningsmaterial som betalas till återvinningsföretag med specifika intervall.
author: MarkusFogelberg
manager: tfehr
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2020-02-19
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b9ca8653bb3dc00285774d4ead9a8c14c606f24
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234739"
---
# <a name="packing-materials-and-fees"></a>Förpackningsmaterial och avgifter

[!include [banner](../includes/banner.md)]

Avgifter för förpackningsmaterial betalas i specifika intervaller till ett återvinningsföretag. Ett belopp per viktenhet måste betalas för varje material som en förpackningsenhet består av. Även om avgifter för förpackningsmaterial beräknas och rapporteras, bokförs inga redovisningstransaktioner eftersom avgifterna inte räknas som skatter som måste betalas till en myndighet.

Vikt och avgifter för förpackningsmaterial beräknas för försäljnings- och inköpsorderrader.

Du kan definiera en eller fler förpackningsenheter för en enda artikel, för en grupp med artiklar (förpackningsgrupp) eller för alla artiklar. En förpackningsenhet består av förpackningsmaterialen, deras vikt och antalet artiklar i förpackningsenheten. En kod för förpackningsmaterial tilldelas varje typ av förpackningsmaterial som definieras. Baserat på koden för förpackningsmaterial kan du ange ett pris för en specifik period. Debitering för förpackningsmaterial beräknas utifrån den här informationen.

> [!NOTE]
> Även om ditt företag inte betalar avgifter för förpackningsmaterial kan du använda funktionen för att beräkna statistik om förpackningsmaterialets vikt.

## <a name="set-up-packing-material-allocation"></a><a name="allocations"></a>Ställ in allokering för förpackningsmaterial

Innan du kan beräkna förpackningsmaterialets vikt, avgifter för förpackningsmaterial eller båda, måste du aktivera beräkningen och definiera vilka material och avgifter som gäller för vilka artiklar.

1. Gå till **Lagerhantering \> Inställningar \> Parametrar för hantering av lager och lagerstyrning**.
1. På fliken **allmänt** i avsnittet **förpackningsmaterial** anger du alternativet **beräkna förpackningsmaterial** till **ja**.
1. Gå till **lagerhantering \> inställningar \> förpackningsmaterial \> förpackningsgrupper** och skapa alla förpackningsgrupper som du använder. Alla artiklar i en förpackningsgrupp kommer att använda samma allokering av förpackningsmaterial. Om du inte använder förpackningsgrupper kan du hoppa över det här steget.

    > [!TIP]
    > När du har skapat förpackningsgrupperna kan du tilldela en grupp till varje produkt som du behöver. Gå till **produktinformationshantering \> produkter \> frisläppta produkter**, välj en produkt och sedan på snabbfliken **hantera lager** i fältet **förpackningsgrupp** väljer du lämplig förpackningsgrupp.

1. Gå till **lagerhantering \> inställningar \> förpackningsmaterial \> förpackningsmaterialkoder**, definiera varje typ av förpackningsmaterial som du använder och ange den enhet som förpackningsmaterialet förbrukas i när du förbereder leveranser.
1. Gå till **lagerhantering \> inställningar \> förpackningsmaterial \>avgifter för förpackningsmaterial** och ange en avgift för varje typ av förpackningsmaterial som du just har definierat. Avgifter beräknas baserat på priset per enhet som förbrukas.
1. Om du vill fördela förpackningsmaterial till artiklar **lagerhantering \> inställningar \> förpackningsmaterial \> allokering av förpackningsmaterial** och skapar allokeringar. Du kan skapa till så många allokering som du behöver. Du kan fördela förpackningsmaterial för enskilda artiklar, grupper av artiklar (förpackningsgrupper) eller alla artiklar, beroende på hur detaljerad allokeringar ska vara.

    Följ dessa steg för varje allokering du skapar.

    1. På snabbfliken **Allmänt** ange följande fält:

        - **Artikel kod** – Välj omfattningen för allokeringen:

            - **Register** – skapa en allokering för en specifik artikel.
            - **Grupp** – skapa en allokering för alla artiklar som tillhör en förpackningsgrupp som har definierats på sidan **förpackningsgrupper**.
            - **Alla** – skapa en allokering för alla artiklar.

            > [!NOTE]
            > Vanligtvis bör du göra alla dina allokeringar på samma nivå (**register**, **grupp** eller **alla**). Om du använder fler än en nivå används den mest specifika matchande allokeringen för varje artikel. (Nivån **Register** prioriteras över nivån **grupp** och båda dessa nivåer åsidosätter nivån **Alla**.)

        - **Artikelrelation** – Markera artikeln om du vill fördela för en enda artikel. Om du allokerar för en grupp av artiklar väljer du förpackningsgruppen. Lämna det här fältet tomt om du vill tilldela för alla artiklar.
        - **Konfiguration**, **storlek**, **färg** och **stil** – ange värden för dessa dimensioner som du behöver för att ytterligare definiera den artikel du allokerar för.
        - **Förpackningsenhet** – Välj den enhet som artikeln förpackas i när förpackningsmaterialet används. Den här enheten kan skilja sig från den enhet som artikeln köps in i eller lagras i.
        - **Faktor för förpackningsenhet** – ange den konverteringsfaktor som används för att konvertera från lagerenheten till förpackningsenheten. (Konverteringen använder formeln *förpackningsenheter* = *artikelenheter* × *faktor för förpackningsenhet*.)

    1. På snabbfliken **förpackningsmaterial** lägger du till en rad för varje del av förpackningsmaterial som krävs för den aktuella allokeringen. På varje rad anger du materialtypen (som definierats på sidan **Förpackningsmaterialskoder**) och det belopp som förbrukas för varje levererad enhet för den aktuella artikeln.

## <a name="packing-units-on-sales-order-lines"></a>Förpackningsenheter på försäljningsorderrader

När du har [aktiverat beräkningen av avgifter för förpackningsmaterial och skapat dina allokeringar](#allocations) verifierar systemet att förpackningsenheter har angetts för varje artikel som läggs till på en försäljningsorder. Därefter beräknar den eventuella avgifter som krävs. När en artikel läggs till på en försäljningsorder inträffar ett av följande steg:

- **Om en förpackningsallokering gäller för artikeln:** Systemet uppdateras med den angivna förpackningsenheten och kvantiteten i förpackningsenheten. (Kvantiteten i förpackningsenheten beräknas med formeln *Kvantitet i förpackningsenhet* = *Beställd kvantitet* ÷ *Antalet artiklar i den valda förpackningsenheten*.)
- **Om ingen förpackningsallokering gäller för artikeln:** Du kan manuellt ange en förpackningsenhet och en kvantitet i förpackningsenheten på försäljningsorderraden.

Det går också att ändra förpackningsenheten och kvantiteten i förpackningsenheten när du bokför försäljningsorderraden. Det här funktionen är relevant om försäljningsorderraden bara levereras eller faktureras delvis.

När du fakturerar försäljningsordern skapar systemet transaktioner för förpackningsmaterial. Transaktioner för förpackningsmaterial innehåller vikten för emballagematerialen för försäljningsraden. Du kan ändra transaktionerna när du har fakturerat dem. Du kan sedan skapa de nya transaktionerna.

## <a name="packing-units-on-purchase-order-lines"></a>Förpackningsenheter på inköpsorderrader

Systemet skapar inte förpackningsmaterialtransaktioner för inköpsorderrader. I stället kan du skapa transaktioner för fakturerade inköpsorderrader manuellt på sidan **Förpackningsmaterialtransaktioner**.

## <a name="set-up-license-numbers-for-customers-that-are-charged-packing-material-fees"></a>Ställ in licensnummer för kunder som debiteras avgifter för förpackningsmaterial

Om försäljningsorder för en viss kund ska ta med avgifter för förpackningsmaterial som används för varje order följer du dessa steg.

1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
1. Välj den kund som ska debiteras för förpackningsmaterial.
1. På snabbfliken **Faktura och leverans** anger du följande fält:

    - I avsnittet **Moms** i fältet **Licensnummer för förpackningsskatt** ange företagets licensnummer.
    - I avsnittet **Förpackningsmaterialavgift** i fältet **Licensnummer** ange företagets licensnummer.

När du nu skapar och fakturerar en försäljningsorder som innehåller en eller flera artiklar som använder förpackningsmaterial, visar fakturan avgifterna för förpackningsmaterial.

För kunder som inte ska betala avgifter för förpackningsmaterial följer du samma steg, men rensar licensnumren från fälten **Licensnummer för förpackningsskatt** och **Licensnummer**. Fakturor för kunder som inte betalar avgifter för förpackningsmaterial visar vikten för förpackningsmaterialen, men de visar inte avgifterna.

Gå till om du vill skapa en rapport som visar alla förpackningsmaterialavgifter som ditt företag kommer att vara skyldig under en viss period **Lagerhantering \> Frågor och rapporter \> Rapporter om förpackningsmaterial \> Beräkning av avgift för förpackningsmaterial**, ange ett datumintervall och välj sedan **OK**.

## <a name="print-packing-material-weights-on-invoices"></a>Skriv ut förpackningsmaterialets vikt på fakturor

Du kan skriva ut vikter för förpackningsmaterial på fakturan och ange vem som betalar relaterade avgifterna. Vikterna sammanställs efter förpackningsmaterialkod.

1. Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
1. På fliken **Uppdateringar** på snabbfliken **Faktura** ange alternativet **Skriv ut vikt på förpackningsmaterial** till **Ja**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]