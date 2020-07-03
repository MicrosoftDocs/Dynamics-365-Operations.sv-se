---
title: Rapportera som färdigt från jobbkortsenheten
description: I det här avsnittet beskrivs hur du konfigurerar systemet så att användarna av en jobbkort kan rapportera färdiga produkter från en tillverkningsorder till lagret.
author: johanhoffmann
manager: tfehr
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f5d34893ddc8adc3785ec50dbd72438cf8f68c5d
ms.sourcegitcommit: 52ba8d3e6af72df5dab6c04b9684a61454d353ad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2020
ms.locfileid: "3403272"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Rapportera som färdigt från jobbkortsenheten

[!include [banner](../includes/banner.md)]

Arbetstagarna använder **rapportförlopp** på jobbkortsenheten för att rapportera kvantiteter som har slutförts för ett produktionsjobb.

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Kontrollera om kvantiteter som rapporteras som färdiga ska läggas till i lagret

Följ de här stegen om du vill kontrollera om och hur de kvantiteter som rapporteras som färdiga i den sista operationen ska läggas till i lagret.

1. Gå till **Produktionsstyrning \> Inställningar \> Tillverkningskörning \> Standarder för produktionsorder**.
1. På fliken **rapportera som färdigt** anger du fältet **Uppdatera färdig rapport online** till något av följande värden:

    - **Nej** – Ingen kvantitet kommer att läggas till i lagret när kvantiteterna rapporteras för den senaste operationen. Status för produktionsorder kommer aldrig att förändras.
    - **Status + kvantitet** – status för tillverkningsordern ändras till *rapporterat som färdigt* och kvantiteten rapporteras som färdig till lagret.
    - **Kvantitet** – Kvantiteten kommer att rapporteras som färdig till lager, men status för produktionsordern kommer aldrig att förändras.
    - **Status** – Endast status produktion kommer aldrig att förändras. Ingen kvantitet kommer att läggas till i lagret när kvantiteterna rapporteras för den senaste operationen.

> [!NOTE]
> Kvantiteter spåras inte i lagret om de operationer som de rapporteras som färdiga inte definieras som den senaste operationen. Dessa kvantiteter kan dock användas för att visa förloppet. De kan också inkluderas i regler som kontrollerar om arbetare kan starta nästa operation innan en definierad tröskel för rapporterade kvantiteter för den föregående operationen uppnås. Du kan definiera dessa regler på fliken **Kvantitetsvalidering** på sidan **Produktionsorderns standardvärden**.

För mer information om hur du arbetar med sidan **Standarder för produktionsorder** se [produktionsparametrar i tillverkningskörning](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Rapportera batchkontrollerade artiklar som färdiga

Jobbkortsenheten stöder tre scenarier för rapportering av batch-artiklar. Dessa scenarier gäller både artiklar som aktiveras för avancerade lagerprocesser och artiklar som inte är aktiverade för avancerade lagerprocesser.

- **Manuellt tilldelade batchnummer:** arbetare registrerar ett anpassat batchnummer. Det här batchnumret kan komma från en extern källa som inte är känd för systemet.
- **Fördefinierade batchnummer:** arbetare väljer ett batchnummer i en lista med batchnummer som genereras automatiskt innan tillverknings ordern frisläpps till jobbkortsenheten.
- **Fast batchnummer:** arbetare anger eller väljer inte ett batchnummer. I stället tilldelar systemet automatiskt ett batchnummer till produktionsordern innan den frigörs.

För att aktivera varje scenario följer du stegen nedan.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj produkten som ska konfigureras.
1. På snabbfliken **Hantera lager** i fältet **batchnummergrupp** väljer du den spårningsnummergrupp som har angetts som stöd för ditt scenario.

> [!NOTE]
> Om ingen batchnummergrupp tilldelas till en batchkontrollerad produkt innehåller jobbkortsenheten som standard manuell inmatning för batchnumret vid rapportering som färdigt.

I följande underavsnitt beskrivs hur du ställer in spårningsnummergrupper för att stödja var och en av de tre scenarierna för rapportering av batch-artiklar.

### <a name="enable-batch-number-reporting-on-the-job-card-device"></a>Aktivera rapportering av batchnummer på jobbkortsenheten

Om du vill att dina jobbkortsenheter ska kunna acceptera ett batchnummer när de rapporteras som färdiga, måste du använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera följande funktioner (i den här ordningen):

1. Förbättrad användarupplevelse för dialogrutan Rapportförlopp i jobbkortenheten
1. Aktivera för att ange batch- och serienummer vid rapportering som färdiga från jobbkortenheten (förhandsversion)

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Skapa en spårningsnummergrupp som gör att arbetare manuellt kan tilldela ett batchnummer

För att tillåta manuellt tilldelade batchnummer följer du dessa steg för att ställa in en spårningsgrupp.

1. Gå till **Lagerhantering \> Inställning \> Dimensioner \> Spårningsnummergrupper**.
1. Skapa eller välj den spårningsnummergrupp som du vill ställa in.
1. På snabbfliken **Allmänt** ställer du in **Manuellt** till **Ja**.

    ![Sidan spårningsnummergrupper](media/tracking-number-group-manual.png "Sidan spårningsnummergrupper")

1. Ange andra värden som du behöver och välj sedan spårningsnummergruppen som batchnummergrupp för frisläppta produkter som du vill använda det här scenariot för.

När du använder det här scenario **batchnummer** som sidan **Rapportförlopp** på jobbkortsenheten ger är en textruta där arbetare kan ange vilket värde som helst.

![Rapportstatussida med ett fält för manuella batchnummer](media/job-card-device-batch-manual.png "Rapportstatussida med ett fält för manuella batchnummer")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Ställ in en spårningsnummergrupp som innehåller en lista över fördefinierade batchnummer

För att tillhandahålla fördefinierade batchnummer följer du dessa steg för att ställa in en spårningsgrupp.

1. Gå till **Lagerhantering \> Inställning > Dimensioner \> Spårningsnummergrupper**.
1. Skapa eller välj den spårningsnummergrupp som du vill ställa in.
1. På snabbfliken **Allmänt** ställer du in **Bara för lagertransaktioner** till **Ja**.
1. Använd fältet **per kvantitet** om du vill dela upp batchnummer per kvantitet, baserat på det värde som du anger. Du har till exempel en tillverkningsorder på tio enheter och fältet **per kvantitet** anges till *2*. I det här fallet kommer fem batchnummer att tilldelas tillverkningsordern när den skapas.

    ![Sidan spårningsnummergrupper](media/tracking-number-group-predefined.png "Sidan spårningsnummergrupper")

1. Ange andra värden som du behöver och välj sedan spårningsnummergruppen som batchnummergrupp för frisläppta produkter som du vill använda det här scenariot för.

När du använder det här scenario kommer fältet **batchnummer** som sidan **Rapportförlopp** på jobbkortsenheten är en listruta där arbetare måste välja ett fördefinierat värde.

![Rapportstatussida med en lista över fördefinierade batchnummer](media/job-card-device-batch-predefined.png "Rapportstatussida med en lista över fördefinierade batchnummer")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Skapa en spårningsnummergrupp som automatiskt tilldelar batchnummer

Om batchnummer ska tilldelas automatiskt, utan indata från arbetare, följer du dessa steg för att skapa en spårningsnummergrupp.

1. Gå till **Lagerhantering \> Inställning \> Dimensioner \> Spårningsnummergrupper**.
1. Skapa eller välj den spårningsnummergrupp som du vill ställa in.
1. På snabbfliken **Allmänt** ställer du in **Bara för lagertransaktioner** till **Nej**.
1. Ange alternativet **Manuell** till **Nej**.

    ![Sidan spårningsnummergrupper](media/tracking-number-group-fixed.png "Sidan spårningsnummergrupper")

1. Ange andra värden som du behöver och välj sedan spårningsnummergruppen som batchnummergrupp för frisläppta produkter som du vill använda det här scenariot för.

När du använder det här scenario **batchnummer** som sidan **Rapportförlopp** på jobbkortsenheten ger visas ett värde med arbetare kan inte redigera det.

![Rapportstatussida med ett fast batchnummer](media/job-card-device-batch-fixed.png "Rapportstatussida med ett fast batchnummer")

## <a name="report-as-finished-to-a-license-plate"></a>Rapportera som färdig till ett ID-nummer

Avancerade lagerprocesser kan använda dimensionen ID-nummer för att spåra lager på lagerställen som har ställts in för detta syfte. I det här fallet krävs ID-nummer när en arbetare rapporterar kvantiteter som färdiga.

### <a name="enable-license-plate-reporting-and-label-printing"></a>Aktivera rapportering och etikettutskrift av ID-nummer

Om du vill använda funktionerna som beskrivs i det här avsnittet måste du använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera följande funktioner (i den här ordningen):

1. ID-nummer för rapportering som färdig har lagts till på jobbkortenheten
1. Aktivera automatisk generering av ID-nummer när rapportering slutförts i jobbkortenheten
1. Skriv ut etikett från jobbkortenhet

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>Konfigurera rapportering som färdig till ett ID-nummer

Om du vill kontrollera om arbetare ska återanvända ett befintligt ID-nummer eller skapa ett nytt ID-nummer när de rapporterar kvantiteter som färdiga följer du dessa steg.

1. Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera jobbkort för enheter**.
2. Ställ in följande alternativ för varje enhet:

    - **Generera ID-nummer** – Ange det här alternativet **Ja** om du vill generera ett nytt ID-nummer för varje rapport som färdig. Ställ in det på **Nej** om ett befintligt ID-nummer ska användas för varje rapport som färdig.
    - **Skriv ut etikett** – Ställ in det här alternativet på **Ja** om arbetare måste skriva ut ett ID-nummer för varje rapport som färdig. Ställ in det på **Nej** om ingen etikett behövs. 

![Konfigurera jobbkort för enhetssidan](media/config-job-card-raf.png "Konfigurera jobbkort för enhetssidan")

> [!NOTE]
> För att konfigurera etiketten, gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Dokumentflöde**. Mer information finns i [Aktivera utskrift av ID-nummeretiketter](../warehousing/tasks/license-plate-label-printing.md).
