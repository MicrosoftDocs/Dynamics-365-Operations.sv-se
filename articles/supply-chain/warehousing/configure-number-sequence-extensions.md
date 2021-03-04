---
title: Konfigurera nummerserier för lagerflöden
description: Det här ämnet innehåller en översikt över de funktioner som ger nummer serie tillägg för registreringsskylt-ID, påfyllnadsetikett-ID, behållar-ID och fraktsedel-ID.
author: GarmMSFT
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSNumberSequenceExt
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: e6faab834b4c1c514bcc23a59d74e2bd0e069754
ms.sourcegitcommit: a26e4963d40796da21ce6581cfb2f4d9db4f6776
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "4438110"
---
# <a name="configure-number-sequences-for-warehouse-flows"></a>Konfigurera nummerserier för lagerflöden

[!include [banner](../includes/banner.md)]

Funktionen *Nummerserietillägg* lägger till en ny konfigurationssida för inställning av nummerserier. Den möjliggör en flexibel konfiguration av GS1-reglerade ID, inklusive GS1 och kontrollsiffror (modulo 10) och tillämpar en längdgräns för befintliga nummerserier.

Standard nummerseriesegment är inte lämpliga för GS1-implementering, eftersom ingen kontrollsiffra beräknas och företagets GS1-prefix måste uppdateras manuellt.

Denna funktion omfattar följande funktioner:

- Fraktsedel-ID (BOL) kan genereras i förväg.
- En unik nummerserie kan skapas för SSCC-nummer (Serial Shipping Container Code).
- GS1-kompatibla nummerserier kan skapas för BOL- och SSCCa-nummer. Funktionen lägger till medföljande stöd för licens platta ID-nummer, behållar-ID, påfyllnadsetikett-ID och BOL-ID.
- Konfiguration av ID-nummer är flexibel. Du kan t.ex. inkludera eller utesluta appidentifierare (AI), t.ex. inledande nollor (00).

Den här funktionen gör det effektivare att stödja märkning av kartonger och att justera nya nummer som skapas av systemet.

## <a name="turn-on-the-number-sequence-extensions-feature"></a>Aktivera funktionen nummerserietillägg

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *nummerserietillägg*

## <a name="set-up-the-feature"></a>Ställ in funktionen

Om du vill ställa in nummerserietillägg i systemet följer du stegen nedan.

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
1. På fliken **Allmänt** i **GS1-företagsprefix** och ange ditt företagets GS1-prefix. Det här värdet påverkar alla nummerserier där GS1-prefixet ingår som ett segment.
1. Om du vill generera BOL-nummer för påfyllnadsetikett på fliken **Rapporter**, markera kryssrutan **Generera BOL-nummer när du skriver ut påfyllnadsetiketter**.

    > [!NOTE]
    > Den här kryssrutan är bara tillgänglig om funktionen för [utskrift av påfyllnadsetiketter](configure-wave-label-printing.md) är aktiverad.

1. Gå till **Hantering av distributionslager** \> **Inställningar** \> **Nummerserietillägg**
1. Klicka på **Skapa standardinställning** i åtgärdsfönstret. En GS1-kompatibel BOL-nummerserie och tre typer av SSCC-nummerserier skapas. Alla dessa nummerserier tar längden på ditt företags GS1-prefix i konton.

    Mer information om hur du anpassar dessa standard nummerserier och/eller lägger till nya sekvenser finns i nästa avsnitt. Du kan också ta bort dessa sekvenser om du inte behöver dem.

1. Gå tillbaka till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
1. På fliken **Nummerserier** väljer du ett relevant nummer serie tillägg som ska användas för att generera nummer för dina ID-nummer, behållare-ID (i det här fallet väljer du rätt **SSCC-18-nummer** sekvens), och/eller BOL-ID (i det här fallet, välj **BOL** sekvens). Som standard stöds tillägg för nummerserier bara för dessa fyra typer av ID.

Nästa gång ett nytt nummer genereras för en av dessa nummerserier kommer den nya logiken att användas.

> [!NOTE]
> Om du inte väljer ett nummerserie tillägg för ID-nummer, används de aktuella reglerna för att generera ID-nummer. I annat fall används den valda nummerserien. De övriga ID använder en vanlig nummerserie tills du använder en nummerserie tillägg för dem.

## <a name="create-and-edit-number-sequences"></a>Skapa och redigera nummerserier

I det föregående avsnittet genererade du en standarduppsättning med nummerserier. I det här avsnittet beskrivs hur varje nummerserie definieras. Det innehåller även information om hur du skapar anpassade sekvenser och hur du redigerar standardvärden eller anpassade sekvenser.

Följ stegen nedan när du vill skapa och redigera nummerserier.

1. Gå till **Hantering av distributionslager** \> **Inställningar** \> **Nummerserietillägg**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fält **nummerserietillägg** ange ett namn på den nya serien. Ange en beskrivning i fältet **beskrivning**.
1. På snabbfliken **segment** kan du använda knapparna i verktygsfältet för att samla ihop sifferformatet genom att lägga till, ta bort och ordna segment. I fältet **Segment** för varje rad, tilldela en segmenttyp för att definiera syftet och innehållet i det segmentet. I följande register finns tillgängliga beskrivningar av typer av segment som är tillgängliga.

    | Segmenttyp | beskrivning |
    |---|---|
    | Konstant | Den här segmenttypen lägger till samma konstant text för varje genererat tal i sekvensen. I fältet **Värde** anger du krävd texten. Fältet **Längd** uppdateras automatiskt till längden på den text som du har angett i fältet **Värde**. |
    | Nummerserie | I fältet **Värde** ange ett nummertecken (*\#*) för varje tecken som ska visas i den genererade sekvensen. Nummerserien kan generera längre nummer, men endast tecknen längst till höger visas. Fältet **Längd** uppdateras automatiskt till numret för nummertecken som du har angett i fältet **Värde**.<p>Om du vill uppfylla GS1-krav för SSCC-18s-nummer ser du till att längden på det här segmentet är 16 minus längden på ditt GS1-prefix.</p> |
    | GS1-prefix | Den här segmenttypen lägger till värdet som har ställts in i fältet **GS1-företagsprefix** på sidan **Parametrar för lagerstyrning**. Fältet **Värde** visar det värde som är angivet på sidan **Parametrar för lagerstyrning** och fältet **Längd** visar antalet tecken i värdet. Både fältet **Värde** och fältet **Längd** är skrivskyddade. |
    | Programidentifierare | I fältet **Värde** anger du en programidentifierare, som anges i relevant GS1-policy för den här typen av nummerserie. Ange till exempel *00* för SSCC eller *420* för BOL. Fältet **Längd** uppdateras automatiskt till längden på den identifierare som du har angett i fältet **Värde**. |
    | Packtyp | För artiklar som kan identifieras tydligt lägger den här segmenttypen till ett fältvärde från den relevanta enhetsseriegruppen (från sidan **Enhetssekvensgrupper**). (Det här beteendet matchar den befintliga logiken för ID-nummer.) För ID-nummer som innehåller flera lagerhållningsenheter (SKU) adderar denna segmenttyp *0* (noll) som standard. För den här segmenttypen är fältet **värde** alltid inställt på *P* och fältet **längd** är alltid inställt på *1*.|
    | Kontrollsiffra | Den här segmenttypen lägger till en kontrollsiffra, som är en beräkning av modulo 10. (Det här beteendet matchar den befintliga logiken för ID-nummer.) För den här segmenttypen är fältet **värde** fältet alltid inställt på ett inskjutningstecken (*^*) och fältet **längd** är alltid inställt på *1*. |

1. Om du vill visa ett exempel på det slutliga talformatet, kontrollerar du fältet **format** längst ned på snabbfliken **segment**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]