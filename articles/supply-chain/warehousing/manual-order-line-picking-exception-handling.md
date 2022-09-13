---
title: Hantera undantag för försäljning och överföring av radplock manuellt
description: I den här artikeln beskrivs hur administratörer kan plocka (eller häva plockningen) lagertransaktioner manuellt för att korrigera problem som orsakas av skadade försäljnings- och överföringsorderdata.
author: perlynne
ms.date: 08/19/2022
ms.topic: article
ms.search.form: WHSManualSalesLinePicking, WHSManualInventTransferLinePicking, InventTransPick, WHSLoadLineManualCorrection, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d2f89a7109060e69aca6a06eadaedc017728bbae
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403702"
---
# <a name="manually-handle-sales-and-transfer-line-picking-exceptions"></a>Hantera undantag för försäljning och överföring av radplock manuellt

[!include [banner](../includes/banner.md)]

Manuell hantering av plockundantag för försäljnings- och överföringsorder gör det möjligt för administratörer att åtgärda problem som orsakas av skadade försäljnings- och överföringsorderdata. Det är bara betrodda användare som plockar (eller tar bort plockning) lagertransaktioner som hör till försäljnings- och överföringsorderrader medan lagerställeprocesser redan pågår.

Funktionaliteten som beskrivs här bör endast användas i de fall där systemet inte kan avsluta bearbetningen av lagerprocessstapeln på vanligt sätt. Som standard är det bara användare med en systemadministratörsroll som tillåts använda den. Du kan dock bevilja åtkomst till det genom att tilldela *plockförsäljningsraderna manuellt* behörigheter till andra roller efter behov.

## <a name="turn-on-this-feature-for-your-system"></a>Aktivera funktionen i systemet

Innan du kan använda någon av funktionerna som beskrivs i det här ämnet måste den aktiveras i systemet. Administratörer kan använda inställningarna för [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera statusen för dessa funktioner och aktivera dem. I arbetsytan **utgiftshantering** funktionerna listas genom att använda följande namn:

- *Manuell plockningstjänst för försäljningsrad för admin eller liknande betrodda användare*<br>(Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras.)
- *Manuell plockningstjänst för överföringsrad för admin eller liknande betrodda användare*

## <a name="correct-transactions-related-to-sales-or-transfer-order-lines"></a>Korrigera transaktioner relaterade till försäljnings- eller överföringsorderrader

Använd följande procedur för att korrigera transaktioner som är relaterade till försäljnings- eller överföringsorderrader.

1. Följ ett av dessa steg, beroende på vilken typ av beställning du måste korrigera:

    - För att korrigera en transaktion som är relaterad till en försäljningsorder, gå till **Warehouse Management \> Periodiska uppgifter \> Rensa \> Plocka försäljningsrader manuellt**.
    - För att korrigera en transaktion som är relaterad till en överföringsorder, gå till **Warehouse Management \> Periodiska uppgifter \> Rensa \> Plocka överföringsrader manuellt**.

1. På sidan **Plocka försäljningsrader manuellt** eller **Plocka överföringsrader manuellt** använd filtren överst i rutnätet för att hitta raden du letar efter och välj sedan målorderraden i det övre rutnätet.
1. Använd flikarna **Lagertransaktioner**, **Beläggningsrader**, **Arbetsrader** och **Behållarrader** i det nedre avsnittet om du vill visa mer information om den valda raden. Informationen på de här flikarna ger en grundläggande översikt över de relaterade lagerställeprocesserna och deras status.
1. I åtgärdsfönstret, välj **Plocka** för att öppna den valda orderraden på sidan **Plocka** för lagertransaktioner. Du kan genomföra det här steget även för orderrader som redan har frisläppts till lagerstället. (Vanligtvis går det inte att öppna orderrader som har frisläppts till lagerstället på sidan **Plocka**.)

    > [!NOTE]
    > Du kan få olika varningar när du öppnar sidan **Plocka**. Vidta alla åtgärder som dessa varningar rekommenderar. Du kan till exempel få en varning om orderrader som är länkade till lagerställearbete. I det här fallet är det klokt att försöka att avbryta arbetet genom att använda standardfunktionen för att [avbryta arbetet](cancel-warehouse-work.md) innan du korrigerar manuellt.

1. Markera raden i rutnätet **Transaktioner** och välj sedan **Lägg till plockrad** i verktygsfältet **Transaktioner**.
1. Den valda raden flyttas till rutnätet **Plockrader**. Ställ in tillämpliga värden för eventuella kolumner som saknar obligatorisk information. (Ange till exempel platsen och licens för den plats som artikeln ska plockas/tas bort från.)
1. Välj **Bekräfta Plocka alla** på verktygsfältet **Plockrader**.

## <a name="correct-load-line-quantities"></a>Korrigera lastradkvantiteter

Använd följande procedur för att korrigera lastradkvantiteten.

1. Följ ett av dessa steg, beroende på vilken typ av beställning du måste korrigera:

    - För att korrigera en transaktion som är relaterad till en försäljningsorder, gå till **Warehouse Management \> Periodiska uppgifter \> Rensa \> Plocka försäljningsrader manuellt**.
    - För att korrigera en transaktion som är relaterad till en överföringsorder, gå till **Warehouse Management \> Periodiska uppgifter \> Rensa \> Plocka överföringsrader manuellt**.

1. På sidan **Plocka försäljningsrader manuellt** eller **Plocka överföringsrader manuellt** använd filtren överst i rutnätet för att hitta raden du letar efter och välj sedan målorderraden i det övre rutnätet.
1. På fliken **Lastrader** i det nedre avsnittet, välj **Korrigera lastrader manuellt** i verktygsfältet.
1. På sidan **Korrigera lastrader manuellt** i rutnätet **Lagertransaktioner**, granska de lagertransaktioner som är relaterade till den valda lastraden.
1. I det övre rutnätet ska du korrigera inläsningsradkvantiteterna i följande kolumner efter behov:

    - **Kvantitet för skapat arbete**
    - **Plockad kvantitet**
    - **Planerad kvantitet för direktleverans**

    Systemet kommer att validera alla ändringar som du gör i dessa kolumner.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
