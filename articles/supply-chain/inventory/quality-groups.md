---
title: Kvalitetsgrupper för artiklar
description: I detta ämne beskrivs hur du använder och skapar artikelkvalitetsgrupper för att logiskt gruppera produkter så att dessa kan tilldelas kvalitetsassociationer för automatisk generering av kvalitetsorder.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3074a6a8cc054be045bf593b509e76a1043af0b7
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956830"
---
# <a name="item-quality-groups"></a>Kvalitetsgrupper för artiklar

[!include [banner](../includes/banner.md)]

En kvalitetsgrupp representerar gemensamma testbehov för artiklar. I detta ämne beskrivs hur du använder och skapar artikelkvalitetsgrupper för att logiskt gruppera produkter så att dessa kan tilldelas kvalitetsassociationer för automatisk generering av kvalitetsorder.

Gå till **Lagerhantering \> Inställningar \> Kvalitetsgrupper** om du vill ställa in, redigera och visa de artiklar som har tilldelats en kvalitetsgrupp eller de kvalitetsgrupper som är tilldelade en artikel. När du har definierat testkraven på sidan **Testgrupper** kan du definiera reglerna för automatisk generering av kvalitetsorder. För att förenkla processen definierar du inte regler för enskilda artiklar. I stället kan du definiera regler för en kvalitetsgrupp på sidan **Kvalitetsassociationer**.

## <a name="example-of-an-item-quality-group"></a>Exempel på en kvalitetsgrupp för artiklar

Ett tillverkningsföretag köper in flera olika råmaterial som har samma testbehov för inkommande inspektion. Företaget definierar därför en kvalitetsgrupp och tilldelar sedan artikelnumren som är kopplade till råmaterialet till den gruppen. Senare köper företaget en ny typ av råmaterial som har samma testbehov. I stället för att konfigurera nya testbehov för det nya materialet lägger företaget till artikelnumret för det nya materialet till den befintliga kvalitetsgruppen.

Samma företag tillverkar också artiklar som har samma krav på tillverkningstest och levererar artiklar med samma krav på testning före leverans. Företaget definierar därför två ytterligare kvalitetsgrupper och tilldelar sedan relevanta artikelnummer till respektive grupp.

## <a name="create-a-quality-group"></a>Skapa en kvalitetsgrupp

Gör så här om du vill skapa en kvalitetsgrupp:

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsgrupper**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Kvalitetsgrupp** – Ange ett unikt ID eller namn för kvalitetsgruppen.
    - **Beskrivning** – Ange en detaljerad beskrivning av kvalitetsgruppen.

1. Stäng sidan.

## <a name="manually-add-items-to-a-quality-group"></a>Lägg till artiklar i en kvalitetsgrupp manuellt

Följ de här stegen om du vill lägga till artiklar manuellt i en kvalitetsgrupp.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsgrupper**.
1. Välj den kvalitetsgrupp som du vill lägga till artiklar i.
1. Klicka på **Artiklar** i åtgärdsfönstret.
1. Ppå sidan **Artiklar i kvalitetsgrupper** väljer du **Ny** i åtgärdsfönstret om du vill lägga till en ny rad i rutnätet. Ange sedan fältet **Artikelnummer** för den nya raden som det artikelnummer du vill lägga till.
1. Upprepa föregående steg för varje ytterligare artikel som måste läggas till.
1. Stäng sidorna.

## <a name="add-multiple-items-to-a-quality-group"></a>Lägg till flera artiklar i en kvalitetsgrupp

Följ de här stegen om du vill lägga till flera artiklar i en kvalitetsgrupp.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsgrupper**.
1. Skapa eller välj den kvalitetsgrupp som du vill lägga till artiklar i.
1. Klicka på **Lägg till artiklar** i åtgärdsfönstret.
1. I dlialogrutan **Förfrågan** anger du filterkriterier för de artiklar som du vill lägga till. Du kan till exempel filtrera för alla artiklar i en viss artikelgrupp.
1. Välj **OK**.
1. I dialogrutan **Lägg till objekt** visar ett rutnät alla objekt som matchar frågan. Granska resultaten.

    Om du behöver genomföra ändringar väljer du **Välj** för att återgå till dialogrutan **Förfrågan**, och justerar sedan din fråga.

1. När resultatet inkluderar alla artiklar som du vill lägga till väljer du **OK**.
1. Stäng sidan.

## <a name="manually-associate-an-item-with-a-quality-group"></a>Associera en artikel med en kvalitetsgrupp manuellt

Följ de här stegen om du vill lägga till artiklar manuellt i en kvalitetsgrupp.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Artikelkvalitetsgrupper**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Artikelnummer** – Välj det artikelnummer som du vill lägga till.
    - **Kvalitetsgrupp** – Välj den kvalitetsgrupp som ska tilldelas artikeln.

1. Upprepa föregående steg för varje ytterligare kombination av en artikel och en kvalitetsgrupp som måste läggas till.
1. Stäng sidorna.

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a>Lägga till en kvalitetsgrupp manuellt från sidan Frisläppta produkter

Följ dessa steg om du vill lägga till en kvalitetsgrupp från sidan **Frisläppta produkter** manuellt.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj den produkt som du vill tilldela en kvalitetsgrupp till.
1. På fliken **Hantera lager** i åtgärdsfönstret, i gruppen **Kvalitet**, väljer du **Artikelkvalitetsgrupper**.
1. Ppå sidan **Artiklar i kvalitetsgrupper** väljer du **Ny** i åtgärdsfönstret om du vill lägga till en ny rad i rutnätet. Ange sedan fältet **Kvalitetsgrupp** för den nya raden som den kvalitetsgrupp du vill tilldela produkten.
1. Upprepa föregående steg för varje ytterligare kvalitetsgrupp som du vill tilldela produkten.
1. Stäng sidorna.

## <a name="additional-resources"></a>Ytterligare resurser

- [Testinstrument för kvalitetshantering](quality-test-instruments.md)
- [Kvalitetshanteringstester](quality-tests.md)
- [Testgrupper för kvalitetshantering](quality-test-groups.md)
- [Testvariabler för kvalitetshantering](quality-test-variables.md)
- [Kvalitetsassociationer](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
