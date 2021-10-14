---
title: Lagerställeparametrar för påfyllnadbearbetning
description: I det här avsnittet beskrivs hur du ställer in påfyllnadsparametrar för påfyllnadsprocessen. Du kan använda påfyllnadsbearbetning för att gruppera plockningsarbete för flera arbetsordrar till en enda påfyllnad.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: cd7961ae8f4237bcee7ae4c53365d24ab03c5aa9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572228"
---
# <a name="warehouse-parameters-for-wave-processing"></a>Lagerställeparametrar för påfyllnadbearbetning

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in påfyllnadsparametrar för påfyllnadsprocessen. Du kan använda påfyllnadsbearbetning för att gruppera plockningsarbete för flera arbetsordrar till en enda påfyllnad.

Om du vill använda påfyllnadsbearbetning anger du följande på sidan **Lagerstyrningsparametrar**:

- Om du kan bearbeta påfyllnader genom att använda ett batchjobb.
- Om du hämtar in information till en loggfil när påfyllnader bearbetas.

## <a name="set-up-warehouse-management-parameters-for-wave-processing"></a>Ställa in parametrar för lagerställehantering för påfyllnadsbearbetning

Ställ in lagerställeparametrar för påfyllnadsbearbetning, genom att följa dessa steg:

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Parametrar för lagerstyrning**.

1. På snabbfliken **påfyllnadsbearbetning**, gör följande inställningar:

    - **Påfyllnadsbearbetning av batchgrupp** - Välj den batchgrupp som ska användas när du bearbetar vågor genom att använda batchjobb. Batchgruppen anger den server där batchjobbet ska köras.
    - **Bearbeta påfyllnader i batch** - Välj om du vill aktivera vågar som automatiskt ska bearbetas av ett batchjobb. Du måste ställa in detta till *Ja* om du vill använda parallellbearbetning. Du ställer in batchjobbet på sidan för **Bearbeta påfyllnader**. (Se även noteringen i slutet av denna lista.)
    - **Skapa påfyllnadens förloppslogg** - Välj om systemet ska generera en loggpost varje gång tilldelning för ett objekt och dess dimensioner börjar och slutar. Du bör endast aktivera den här loggen om det behövs, till exempel under den första testningen eller vid felsökning. För mer information, se [Påfyllnadsallokering](wave-allocation-method.md).
    - **Skapa logg för vågbearbetningshistorik** - Välj om informationen om en våg automatiskt ska sparas i en loggfil efter att vågen har behandlats, inklusive vid parallell bearbetning av väntande tilldelningar. Vanligtvis bör du endast aktivera detta under felsökning eftersom det lägger till extra omkostnader. Om du vill visa loggen går du till **Lagerstyrning \> Utgående påfyllnader \> Påfyllnadsbearbetning historiklogg**. För mer information, se [Skapa och bearbeta påfyllnad](wave-processing.md).
    - **Skapa historiklogg för behållare** - Välj om information om behållare automatiskt ska sparas för en påfyllnad i en loggfil efter att påfyllnad har bearbetats. Om du vill visa loggen går du till **Lagerstyrning \> Packa och skapa behållare \> Skapande av behållare-historik**.
    - **Vänta till lås (ms)** - Ange tiden, i millisekunder, som ett allokeringssteg ska vänta på en systemresurs som har låsts av ett annat allokeringssteg. När denna tid överskrids, bearbetas påfyllnaden inte, och ett meddelande visas.

1. På fliken **Släpp till distributionslager**, gör följande inställningar:

    - **Fel vid batchfel** - Välj om du vill generera ett fel när en frisläppning till batchjobb för lagerställe misslyckas. Om det här alternativet aktiveras avslutas jobb som inte kan skapas med statusvärdet *Fel*. Om det här alternativet inaktiveras avslutas jobb som inte kan skapas med statusvärdet *Avslutat*.

> [!NOTE]
> I påfyllnadsmallen som används för att bearbeta påfyllnaden, kan du ange inställningar som automatiserar påfyllnadsbearbetningen. Om du ställer in ett schema för batchjobbet, ska du koordinera tidmätningen med inställningarna för automation i påfyllnadsmallen. Mer information finns i [Skapa en påfyllnadsmall](wave-templates.md).
>
> Om du använder *Transporthantering* och *Avancerad distributionslagerhantering*, kan du ange om konsolidering av beläggningar ska ske när du bearbetar en påfyllnad. Detta är till exempel praktiskt när flera små laster kan levereras samtidigt. Om du vill konsolidera belastningarna när du bearbetar en påfyllnad, på fliken **laster** markerar du kryssrutan **Konsolidera laster under påfyllnadsbearbetning**.</P>

## <a name="set-up-full-or-partial-reservation-for-production-waves"></a>Ställ in fullständig eller delvis reservation för produktionsvågor

För försäljnings - och kanbanorder måste lager reserveras om ordern har frisläppts till lagerstället. Annars kan artiklarna eller allokeringsraderna inte bearbetas i en våg. Tillverkningsorder är dock något mer flexibla. För tillverkningsorder kan du ange följande:

- Tillåt att produktionsorder frisläpps till lagerstället trots att allt material inte kan reserveras. Om du markerar det här alternativet måste du upprepa frisläppningen till lagerprocess när ytterligare material blir tillgängliga. Detta är till exempel praktiskt om du har material som behövs för att starta en produktion, och kan vänta tills ytterligare material är tillgängligt.
- Begär att alla material ska reserveras innan en order kan frisläppas till lagerstället.

Om du vill kräva fullständig reservation eller om du vill tillåta delvis reservation, följ dessa steg:

1. Gå till **Produktionskontroll** \> **Inställningar** \> **Produktionskontrollparametrar**.
1. På fliken **Allmänt** i fältet **Frisläpp till lagerställe**, välj följande standardinställningar.
