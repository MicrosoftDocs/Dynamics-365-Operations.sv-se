---
title: "Orsakskoder för lagerinventering"
description: "I det här avsnittet beskrivs hur du ställer in och tillämpar orsakskoder och inventeringsuppgifter."
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCountingReasonCodePolicy
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fe01425fa236655731e6e0723f3a1e57c05035cc
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="reason-codes-for-inventory-counting"></a>Orsakskoder för lagerinventering

[!INCLUDE [banner](../includes/banner.md)]

Orsakskoder låter dig analysera resultatet från en inventeringsprocess och eventuella avvikelser som inträffar under den här processen. Du kan ange en orsak till att göra inventeringen, t.ex. en trasig lastpall eller en lagerjustering som baseras på lagerexempel.

## <a name="recommendation"></a>Rekommendation

Innan du ställer in systemet rekommenderar vi att du definierar en strategi för att arbeta med orsakskoder. Exempelvis försök besvara följande frågor:

- Orsakskoder ska finnas på lagerställen?
- Orsakskoder ska vara obligatoriska eller valfria över vissa objekt?
- Hur många orsakskoder behöver du?
- Hur ska användarna av streckkodsskannrar använda orsakskoder? Orsakskoderna ska vara förvalda, obligatoriska eller inte redigerbara?
- Behöver lagerarbetare olika orakskodbeteenden på mobila skannrar? Om svaret är Ja kan du skapa fler menyalternativ och tilldela dem till olika personer.

## <a name="where-reason-codes-apply"></a>Var orsakskoder tillämpas

Du kan skapa flera orsakskodprinciper och varje orsakskodprincip kan ha två cykliska orsakskodprinciper. Orsakskodprinciper för inventering kan användas på lagerställenivå eller artikelnivå.

## <a name="set-up-reason-code-policies"></a>Ställa in orsakskodprinciper

1. Välj **lagerhantering**\>**inställningar**\>**lager**\>**orsakskodprinciper för inventering**, och skapa en ny orsakskodprincip.
2. På fältet **Typ av orsakskod för inventering** väljer du antingen **obligatorisk** eller **valfri** för att ange om valet av en orsakskod ska vara en valfri eller obligatorisk åtgärd på något av följande inventeringsjournaler:

    - Rullande inventering (mobil enhet)
    - Punktinventering (mobil enhet)
    - Tröskelinventering (mobil enhet)
    - Justering in (mobil enhet)
    - Justering ut (mobil enhet)
    - Inventeringsjournal (rich-klient)

Du kan också ställa in orsakskoder för enskilda lagerställen och produkter. Inställningen av orsakskod för produkter kan ignorera inställningarna för lagerställen.

## <a name="mandatory-reason-codes"></a>Obligatoriska orsakskoder

Om parametern **obligatorisk** anges i konfigurationen för orsakskoder för lager eller artiklar, kan inventeringsjournalen inte slutföras och stängas tills en orsakskod har angetts.

### <a name="set-up-reason-codes-for-warehouses"></a>Ställ in orsakskoder för lagerställen

1. Välj **Lagerhantering** \> **Inställningar** \> **Lagerindelning** \> **Lagerställen**
2. På fliken **lagerställe** i fältet **Policy för orsakskod för inventering** väljer du ett av följande alternativ:

    - **Tom** - parametern som ställts in för artikeln används för att bestämma om inventeringsjournaler är obligatoriska för produkten.
    - **Obligatorisk** – en orsakskod krävs alltid på inventeringsjournaler för lagerstället.
    - **Tillval** – en orsakskod krävs inte på inventeringsjournaler för lagerstället.

### <a name="set-up-reason-codes-for-products"></a>Ställ in orsakskoder för produkter

1. Välj **Produktinformationshantering** \> **Produkter** \> **Frisläppta produktersamprodukt**.
2. På fliken **Produkt** välj **Policy för orsakskod för inventering** och sedan väljer du ett av följande alternativ:

    - **Tom** - parametern som ställts in för lagerstället används för att bestämma om inventeringsjournaler är obligatoriska för produkten.
    - **Obligatorisk** – en orsakskod krävs alltid på inventeringsjournaler för produkten. Den här inställningen åsidosätter inställningen för varje orsakskod på lagernivå.
    - **Tillval** – en orsakskod krävs inte på inventeringsjournaler för produkten. Den här inställningen åsidosätter inställningen för varje orsakskod på lagernivå.

### <a name="use-reason-codes-in-counting-journals"></a>Använd orsakskoder i inventeringsjournaler

I en inventeringsjournal lägger du till orsakskoder för inventeringar av följande typer:

- Rullande inventering
- Punktinventering
- Tröskelinventering
- Justering in
- Justering ut

Orsakskoderna läggs till journalraderna i inventeringsjournaler av typen **inventeringsjournal**.

1. Välj **Lagerhantering** \> **Journalposter** \> **Artikelräkning** \> **Inventering**.
2. I raddetaljerna för inventeringsjournalen, i fältet **Orsakskod för inventering** väljer du ett alternativ.

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a>Visa inventeringshistorik enligt vad som noterats av orsakskoder

- Välj **lagerhantering**\>**förfrågningar och rapporter**\>**inventeringshistorik**, och sedan i fältet **Orsakskod för inventering** visar du inventeringshistorik som har registreras via en orsakskod.

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a>Använda en orsakskod för en kvantitetsjustering

1. På sidan **lagerbehållning** ange **Justera kvantitet**. Du kan öppna sidan **lagerbehållning** på flera olika sätt. Välj t.ex. **Lagerhantering** \> **Förfrågningar och rapporter** \> **Lagerbehållning**.
2. Välj **Justera kvantitet** och sedan, i fältet **Orsakskod för inventering** väljer du en orsakskod.

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a>Konfigurera orsakskoder för menyalternativ för mobila enheter

Du kan konfigurera orsakskoder för alla typer av inventering på ett menyalternativ för mobila enheter. Konfigurationen för menyalternativ för mobil enhet omfattar följande information:

- Om orsakskoden visas till mobiltelefonarbetaren under inventering.
- Standardorsakskoden som visas på ett menyalternativ för mobila enheter.
- Om användaren kan redigera orsakskoden.

### <a name="set-up-reason-codes-on-a-mobile-device"></a>Ställ in orsakskoder på en mobil enhet

1. Välj **Lagerstyrning** \> **InställningarSetup** \> **Mobil enhet** \> **Menyalternativ på mobil enhet**.
2. På fliken **Rullande inventering** Välj **Rullande inventering**.
3. På fältet **Orsakskod för standardinventering**, ställ in standardorsakskoden som ska registreras när inventeringen är klar genom att använda menyalternativet för mobil enhet.
4. I fältet **Visa orsakskod för inventering** välj **Rad** för att visa orsakskoden efter att varje avvikelse har registrerats. Du kan också välja **Dölj** om orsakskoden inte visas.
5. Ange alternativet **Redigera orsakskod för inventering** till antingen **Ja** eller **Nej**. Om du anger det här alternativet till **Ja** kan arbetaren redigera orsakskoden när det visas på den mobila enheten under inventering.

> [!NOTE]
> Knappen **rullande inventering** kan aktiveras på alla menyalternativ för mobil enhet när inventering kan göras. Exempel inkluderar menyalternativ för punktinventeringar, användarstyrt arbete och systemstyrt arbete.

## <a name="cycle-count-approvals"></a>Godkännande av rullande inventering

Användaren kan ändra orsakskoden som är kopplad till inventeringen innan inventeringen kan godkännas. Orsakskoden anges på journalraderna som skapas när inventeringen godkänns.

### <a name="modify-cycle-count-approvals"></a>Ändra godkännande av rullande inventering

1. Välj **lagerstyrning**\>**rullande inventering**\>**Granskning av väntande rullande inventeringsarbete**.
2. Välj **Rullande inventering** och sedan, i fältet **Orsakskod** väljer du en ny orsakskod.

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a>Ändra menyalternativet för mobil enhet för Justering in och Justering ut

1. Välj **lagerstyrning**\>**inställningar**\>**mobil enhet**\>**menyalternativ för mobil enhet**, och välj sedan **justering in och ut**.
2. Ange alternativet **Använd befintligt arbete** till **Nej**.
3. I fältet **Process för att skapa arbete** väljer du **justering i**.

Följande fält läggs till på menyalternativet för mobil enhet när **justering in** eller **justering ut** markeras under process för att skapa arbete:

- Orsakskod för standardinventering
- Visa orsakskod för inventering
- Redigera orsakskod för inventering

