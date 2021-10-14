---
title: Frågor och rapporter gällande farliga material
description: I det här avsnittet beskrivs hur du arbetar med olika rapporter som rör farliga material. Många av dessa rapporter krävs så att du blir kompatibel med olika regler för farligt material vid leverans och lagring.
author: t-benebo
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: ca8c973d3322bd51bf519e83fb5a5c19d35c0bed
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568553"
---
# <a name="hazardous-materials-inquiries-and-reports"></a>Frågor och rapporter gällande farliga material

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management tillhandahåller olika rapporter som är relaterade till farliga material. Många av dessa rapporter krävs så att du blir kompatibel med olika regler för farligt material vid leverans och lagring.

Alla dessa rapporter, utom rapporten **multimodal farliga gods** använder det leveranssätt som har definierats för leveransen för att hitta den förordning som ska användas för att skriva ut leveranstexten för artiklar. Leveranssättet är kopplat till transportföretaget och transporttjänsten. Därför måste du ställa in ett transportföretag och transportföretagstjänst och koppla dem till ett leveranssätt. Leveranssättet är relaterat till förordningen om farligt material.

Följande bild visar den sekvens med aktiviteter som inträffar när systemet genererar rapporter om farliga material.

![Verksamhetsordning för rapporter om farliga material.](media/hazmat-report-sequence.png "Verksamhetsordning för rapporter om farliga material")

## <a name="set-up-hazardous-materials-reporting"></a><a name="set-up"></a>Rapportera ställa in farliga material

Om du levererar artiklar som innehåller farliga material måste du vanligtvis generera specifika rapporter för att upprätthålla säkerheten och följa reglerna för farliga material. Följ dessa steg för att ställa in dina rapporter.

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
2. Öppna fliken **rapporter**. På snabbfliken **rapportparametrar för farliga material** anger du följande fält.

    | Avsnitt | Fält | beskrivning |
    |---|---|---|
    | Multimodalt farligt gods | Kod för föreskrift | Välj den regel som ska användas när rapporten **multimodalt farligt gods** genereras. |
    | Lagergränser för farligt material | Kod för föreskrift | Välj den regel som ska användas när lagergränser utvärderas. |
    | Vägtransport av varor | CMR-grupprodukt | CMR står frö "cancerframkallande, mutagena och reproduktionstoxiska ämnen." Ställ in det här alternativet på **Ja** för att konfigurera systemet för att skriva ut specifika varningar och meddelanden som rör hanteringen av dessa ämnen. |
    | Vägtransport av varor | Gruppbeskrivning av farligt material | Ange texten för specifika varningar som rör CMR och transport av varor på väg. Tenna text inkluderas i rapporten. |
    | avsändarintyg | Varning | Ange texten i ett varningsmeddelande som ska skrivas ut i formuläret avsändarintyg (t.ex. "Varning: farligt gods, brandfarligt"). |
    | avsändarintyg | Sidfotsdeklaration | Ange texten för ett meddelande som ska skrivas ut längst ned i intyget. |
    | Rapportspråk för farligt gods | Inhemskt rapportspråk för farligt gods | Välj standardspråk för rapporter om farligt material som är kopplade till inrikesleveranser. |
    | Rapportspråk för farligt gods | Exportrapportspråk för farligt gods | Välj standardspråk för rapporter om farligt material som är kopplade till utrikesleveranser. |

## <a name="hazardous-materials-report"></a>Rapport om farliga material

Rapporten om **farliga material** visar en lista över alla artiklar som har ställts in och definierats så att de har information om farligt gods. Du kan använda den här rapporten när du vill övervaka och granska den information som du måste underhålla. Sidan för rapporten visar ett begränsat urval av fält från inställningarna för det farliga materialet. Du kan dock anpassa den till att lägga till ytterligare fält som du behöver.

För att se denna rapport, gå till **Produktinformationshantering \> Förfrågningar och rapporter \> Dokumentation för leverans av farligt material \> Farliga material**.

## <a name="hazardous-material-stock-limit-report"></a><a name="stock-limit-report"></a>Rapporten lagergränser för farligt material

Med rapporten **lagergräns för farligt material** kan du övervaka lagernivåerna för de farliga materialen på dina lagerställen, för att se till att de ligger kvar under de säkerhetsgränser som fastställs. Dessa gränser kommer från de gränser som har definierats för varje frisläppt produkt.

För att se denna rapport, gå till **Produktinformationshantering \> Förfrågningar och rapporter \> Dokumentation för leverans av farligt material \> Lagergränser för farligt material**.

Mer information om hur du ställer in lagergränser för en frisläppt produkt finns i [ställa in lagergränser för farliga produkter](hazmat-items.md#stock-limits).

Den förordning som används för lagergränser anges på sidan **parametrar för lagerstyrning**. Gå till **Lagerstyrning \> Konfigurera \> Parametrar för lagerstyrning** och sedan **Rapporter** i **Lagergränser för farligt material**, ange en regelkod. För mer information, se avsnittet [Rapportera ställa in farliga material](#set-up) tidigare i det här avsnittet.

## <a name="verified-gross-mass-report"></a>Rapport med kontrollerade bruttovikter

Rapporten **kontrollerade bruttovikter** kan du skriva ut information om vikten av en leverans.

Om du vill generera och skriva ut den här rapporten går du till **lagerstyrning \> leverans \> alla leveranser** och öppnar relevant leverans. Sedan i åtgärdsfönstret på fliken **leveranser** i gruppen **Dokumentation för leverans av farligt material** välj **Kontrollerade bruttovikter**.

## <a name="multimodal-dangerous-goods-report"></a>Rapport för multimodalt farligt gods

Rapporten **Multimodalt farligt gods** tillhandahålls för försändelser som måste flyttas med hjälp av en kombination av transportmetoder. Den används vanligtvis när en leverans flyttas först på väg till sjöss eller senare.

Om du vill generera och skriva ut den här rapporten går du till **lagerstyrning \> leverans \> alla leveranser** och öppnar relevant leverans. Sedan i åtgärdsfönstret på fliken **leveranser** i gruppen **Dokumentation för leverans av farligt material** välj **Multimodalt farligt gods**.

När du genererar rapporten sparas informationen så att du kan redigera den och/eller skriva ut rapporten om du behöver. Om du vill redigera en genererad rapport går du till **Lagerstyrning \> Förfrågningar och rapporter \> Dokumentation för leverans av farligt material \> Multimodalt farligt gods** och söker efter relevant rapport i listan. När du är klar med redigeringen av innehållet måste du välja **Skriva ut** i åtgärdsfönstret.

## <a name="shippers-declaration-report"></a>Rapporten avsändarintyg

I rapporten **avsändarintyg** kan du skriva ut information som är relaterad till en deklaration av materialen som ingår i försändelsen.

Om du vill generera och skriva ut den här rapporten går du till **lagerstyrning \> leverans \> alla leveranser** och öppnar relevant leverans. Sedan i åtgärdsfönstret på fliken **leveranser** i gruppen **Dokumentation för leverans av farligt material** välj **Avsändarintygande**.

## <a name="carriage-of-merchandise-by-road-report"></a>Rapport för vägtransport av varor

Rapporten **Vägtransport av varor** liknar en fraktsedel men används vanligtvis för vägtransporter i Europa enligt avtalet om internationell transport av farligt gods enligt ADR-förordningar (ADR). I den här rapporten används leveranstexten för en artikel om du inte ställer in fältet **Beskrivning av grupp för farligt material** på sidan **Parametrar för lagerstyrning**.

Om du vill generera och skriva ut den här rapporten går du till **lagerstyrning \> leverans \> alla leveranser** och öppnar relevant leverans. Sedan i åtgärdsfönstret på fliken **leveranser** i gruppen **Dokumentation för leverans av farligt material** välj **Vägtransport av varor**.

När du genererar rapporten sparas informationen så att du kan redigera den och/eller skriva ut rapporten om du behöver. Om du vill redigera en genererad rapport går du till **Lagerstyrning \> Förfrågningar och rapporter \> Dokumentation för leverans av farligt material \> Vägtransport av varor** och söker efter relevant rapport i listan. När du är klar med redigeringen av innehållet måste du välja **Skriva ut** i åtgärdsfönstret.

## <a name="shipment-summary-report"></a>Sammanfattningsrapport för leverans

Rapporten **Leveranssammanfattning** innehåller information som summeras av den transportkategori som är relaterad till de frisläppta artiklarna.

Om du vill generera och skriva ut den här rapporten går du till **lagerstyrning \> leverans \> alla leveranser** och öppnar relevant leverans. Sedan i åtgärdsfönstret på fliken **leveranser** i gruppen **Dokumentation för leverans av farligt material** välj **Leveranssammanfattning**.

## <a name="bill-of-lading-report"></a>fraktsedel - rapport

När funktionen för farliga material är aktiverad i systemet innehåller rapporten **fraktsedel** inkluderar en kolumn **farliga material** som anger om en last omfattar farliga material. Den här rapporten är tillgänglig på sidan **alla laster** som vanligt.

## <a name="packing-list-report"></a>Packningslista - rapport

När funktionen för farliga material är aktiverad i systemet innehåller packningslistor ytterligare information som är relaterad till leveransens tryckta text för en artikel. Den här rapporten är tillgänglig på sidan **alla laster** som vanligt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]