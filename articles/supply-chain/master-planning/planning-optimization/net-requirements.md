---
title: Nettobehov och pegging-information med Planeringsoptimering
description: Avsnittet innehåller information om beräknade nettobehov och pegging-information i Planeringsoptimering.
author: t-benebo
ms.date: 7/28/2021
ms.topic: article
ms.search.form: ReqTransOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: edfa6010074a4b04b3200115891723cd45871624
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468872"
---
# <a name="net-requirements-and-pegging-information-with-planning-optimization"></a>Nettobehov och pegging-information med Planeringsoptimering

[!include [banner](../../includes/banner.md)]

När du kör huvudplanering i Planeringsoptimering är det viktigt att du förstår resultatet, hur befintlig tillgång täcker efterfrågan och varför specifik tillgång genererades. På sidan **Nettobehov** kan du bättre se vilka beräknade behov huvudplanering leder till.

På sidan **Nettobehov** visas det nettobehov som Planeringsoptimering har beräknat för produkten. Här visas också de disponeringsinställningar som har tillämpats vid körning av huvudplanering, en uppdelning av behovsantal per transaktionstyp samt pegging-information.

## <a name="open-the-net-requirements-page"></a>Öppna sidan Nettobehov

Du kan öppna sidan **Nettobehov** på något av följande sätt:

- Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**. Välj eller öppna en produkt. I åtgärdsrutan på fliken **Plan** i gruppen **Behov** väljer du **Nettobehov**.
- Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**. Öppna en försäljningsorder. På snabbfliken **Försäljningsorderrader** väljer du sedan **Produkt och tillgång \> Nettobehov** i verktygsfältet.
- Gå till **Huvudplanering \> Huvudplanering \> Planerade order**. Välj eller öppna en planerad order. I åtgärdsrutan på fliken **Visa** i gruppen **Behov** väljer du **Behovsprofil**.

## <a name="use-the-net-requirements-page"></a>Använda sidan Nettobehov

Sidan **Nettobehov** består av övre och nedre delar. Det finns en knapp för **Uppdatering** i åtgärdsrutan på sidan. När den här knappen väljs visas en meny med kommandon.

### <a name="select-a-master-plan-to-view"></a>Välj en huvudplan som ska visas

Innan du granskar nettobehoven för produkten måste du välja relevant huvudplan i fältet **Plan** längst upp på sidan.

### <a name="upper-section"></a>Övre delen

På sidans övre del finns följande flikar:

- **Översikt** – Visa artikelbehov för produktdimensionerna.
- **Artikeldisponering** – Visa disponeringsinställningarna som användes vid beräkningen av behov.
- **Sammanfattning** – Visa en uppdelning av behovssummorna efter transaktionstyp.
- **Period** – Visa inleveranser, utleveranser och förväntat tillgängligt lager för varje period som definieras av periodmallen. Du kan också få en grafisk vy av förväntat tillgängligt lager.

### <a name="lower-section"></a>Nedre delen

På sidans nedre del finns följande flikar:

- **Översikt** – Visa listan med produktbehov som beräknades vid körning av huvudplanering tillsammans med ut- och inleveranstransaktioner som motsvarar behoven. Listan sorteras som standard efter behovsdatum. När du väljer ett behov visas antingen behovskällan eller de transaktioner som uppfyller behovet på snabbfliken **Pegging** i nedre delen.
- **Allmänt** – Visa detaljerad information om det valda behovet.
- **Åtgärd** – Visa åtgärdsmeddelanden för behoven.

### <a name="the-action-pane"></a>Åtgärdsrutan

Följande kommandon är tillgängliga i åtgärdsrutan:

- **Uppdatering \> Huvudplanering** – Kör huvudplanering direkt från sidan **Nettobehov**.
- **Uppdatering \> Prognosplanering** – Kör prognosplanering direkt från sidan **Nettobehov**. Planeringsoptimering stöder ännu inte denna åtgärden.
- **Uppdatering \> Kontinuitetsplanering** – Kör kontinuitetsplanering direkt från sidan **Nettobehov**. Planeringsoptimering stöder ännu inte denna åtgärden.

## <a name="example-scenario"></a>Exempelscenario

I exemplet visas hur pegging-information visas på sidan **Nettobehov**.

### <a name="prerequisites"></a>Förutsättningar

Innan du börjar arbeta med detta scenario måste följande förutsättningar förberedas:

1. Du måste arbeta med ett system där standardexempeldata finns tillgängliga, och du måste ställa in den juridiska personen som *USMF*.
2. I exemplet används produkt *1000* som ingår i USMF exempeldata. Se till att den här produkten är tillgänglig och att den är inställd på följande sätt:

    - **Standardordertyp:** *Inköpsorder*
    - **Lagerbehållning:** *10,00*

3. Skapa en försäljningsorder för en kvantitet på *25,00* av produkten *1000*. Använd de lagringsdimensioner där lagerbehållningen finns.
4. Kör huvudplanering för huvudplanen *DynPlan*.

### <a name="review-the-calculated-requirements"></a>Granska de beräknade behoven

Nu ska du öppna sidan **Nettobehov** för produkt *1000* för att granska hur beräknade behov motsvarar varandra.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj den produkt som har ett värde för **Artikelnummer** på *1000*.
1. I åtgärdsrutan på fliken **Plan** i gruppen **Behov** ska du välja **Nettobehov**.
1. Ställ in fältet **Plan** som *DynPlan* på sidan **Nettobehov**.
1. Kontrollera på fliken **Översikt** på nedre delen av sidan att följande behov visas som rader i rutnätet.

    | Referens | Behovskvantitet | Ackumulerat |
    |---|---|---|
    | Behållning | 10,00 | 10,00 |
    | Planerade inköpsorder | 15.00 | 25.00 |
    | Försäljningsorder | -25,00 | (Tom) |

    > [!NOTE]
    > Fältet **Behovskvantitet** representerar den totala kvantitet som behovet antingen kräver (om värdet är negativt) eller tillhandahåller (om värdet är positivt). Fältet **Ackumulerat** visar de totala in- och utleveranskvantiteterna som ackumulerats under den valda perioden.

1. Markera behovsraden *Behållning* och granska sedan de behov som tillgången täcker på snabbfliken **Pegging**. Där visas följande rad.

    | Referens | Behovskvantitet | Täckt kvantitet |
    |---|---|---|
    | Försäljningsorder | -25,00 | -10.00 |

    Den befintliga lagerbehållningen omfattar delvis den efterfrågan som kommer från försäljningsordern.

    ![Pegging-information för lagerbehållning](media/pegging-on-hand.png "Pegging-information för lagerbehållning")

1. Markera raden behovsraden *Planerade inköpsorder* och granska sedan de behov som tillgången täcker på snabbfliken **Pegging**. Där visas följande rad.

    | Referens | Behovskvantitet | Täckt kvantitet |
    |---|---|---|
    | Försäljningsorder | -25,00 | -15,00 |

    Eftersom försäljningsordern redan är delvis täckts, skapas en planerad inköpsorder för den återstående inte täckta kvantiteten.

    ![Pegging-information för den planerade inköpsordern](media/pegging-planned-purchase-order.png "Pegging-information för den planerade inköpsordern")

1. Markera behovsraden *Försäljningsorder* och granska sedan de behov som täcker tillgången på snabbfliken **Pegging**. Där visas följande rader.

    | Referens | Behovskvantitet | Täckt kvantitet |
    |---|---|---|
    | Behållning | 10,00 | 10,00 |
    | Planerade inköpsorder | 15.00 | 15.00 |

    ![Pegging-information för den planerade försäljningsordern](media/pegging-planned-purchase-order.png "Pegging-information för den planerade försäljningsordern")

> [!NOTE]
> Eftersom Planeringsoptimering ännu inte har stöd för vissa funktioner, inkluderas inte behovstyperna *Säkerhetslager* och *Utgången batch* på sidan **Nettobehov**. Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).
>
> Om du använder den inbyggda huvudplaneringsmotorn stöds batchkontrollerade produkter. För batchkontrollerade produkter visas utgången lagerbehållning på sidan **Nettobehov** men den är inte peggad med efterfrågekrav. Utgångna behållningsrader av den här typen visas som behovsrader *Utgången batch* på sidan **Nettobehov**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
