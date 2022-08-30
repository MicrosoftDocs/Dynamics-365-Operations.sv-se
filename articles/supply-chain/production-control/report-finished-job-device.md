---
title: Rapportera som färdigt från jobbkortsenheten
description: I denna artikel beskrivs hur du konfigurerar systemet så att användarna av en jobbkortsenhet kan rapportera färdiga produkter från en tillverkningsorder till lager.
author: johanhoffmann
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 56d19a966d93202668c34ffaaef561d72b7669ff
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334638"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Rapportera som färdigt från jobbkortsenheten

[!include [banner](../includes/banner.md)]

Arbetstagarna använder **rapportförlopp** på jobbkortsenheten för att rapportera kvantiteter som har slutförts för ett produktionsjobb. I denna artikel beskrivs hur du konfigurerar olika alternativ som bestämmer hur arbetare kan rapportera som färdiga med hjälp av den här sidan och vad som händer härnäst. Alternativen inkluderar:

- Kontrollera om och hur kvantiteter som rapporteras som färdiga ska läggas till i lagret.
- Ange om och hur batchnummer genereras och används vid rapportering som färdigt.
- Ange om och hur löpnummer genereras och används vid rapportering som färdigt.
- Kontrollera om och hur du rapporterar som färdig till en registreringsskylt

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Kontrollera om kvantiteter som rapporteras som färdiga ska läggas till i lagret

Följ de här stegen om du vill kontrollera om och hur de kvantiteter som rapporteras som färdiga i den sista åtgärden ska läggas till i lagret.

1. Gå till **Produktionsstyrning \> Inställningar \> Tillverkningskörning \> Standarder för produktionsorder**.
1. På fliken **rapportera som färdigt** anger du fältet **Uppdatera färdig rapport online** till något av följande värden:

    - **Nej** – Ingen kvantitet kommer att läggas till i lagret när kvantiteterna rapporteras för den senaste åtgärden. Status för produktionsorder kommer aldrig att förändras.
    - **Status + kvantitet** – status för tillverkningsordern ändras till *rapporterat som färdigt* och kvantiteten rapporteras som färdig till lagret.
    - **Kvantitet** – Kvantiteten kommer att rapporteras som färdig till lager, men status för produktionsordern kommer aldrig att förändras.
    - **Status** – Endast status produktion kommer aldrig att förändras. Ingen kvantitet kommer att läggas till i lagret när kvantiteterna rapporteras för den senaste åtgärden.

> [!NOTE]
> Kvantiteter spåras inte i lagret om de åtgärder som de rapporteras som färdiga inte definieras som den senaste åtgärden. Dessa kvantiteter kan dock användas för att visa förloppet. De kan också inkluderas i regler som kontrollerar om arbetare kan starta nästa åtgärd innan en definierad tröskel för rapporterade kvantiteter för den föregående åtgärden uppnås. Du kan definiera dessa regler på fliken **Kvantitetsvalidering** på sidan **Produktionsorderns standardvärden**.

För mer information om hur du arbetar med sidan **Standarder för produktionsorder** se [produktionsparametrar i tillverkningskörning](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Rapportera batchkontrollerade artiklar som färdiga

Jobbkortsenheten stöder tre scenarier för rapportering av batch-artiklar. Dessa scenarier gäller både artiklar som aktiveras för lagerstyrningsprocesser (WMS) och artiklar som inte är aktiverade för WMS.

- **Manuellt tilldelade batchnummer:** arbetare registrerar ett anpassat batchnummer. Det här batchnumret kan komma från en extern källa som inte är känd för systemet.
- **Fördefinierade batchnummer:** arbetare väljer ett batchnummer i en lista med batchnummer som genereras automatiskt innan tillverknings ordern frisläpps till jobbkortsenheten.
- **Fast batchnummer:** arbetare anger eller väljer inte ett batchnummer. I stället tilldelar systemet automatiskt ett batchnummer till produktionsordern innan den frigörs.

### <a name="enable-the-feature-on-your-system"></a>Aktivera funktionen i systemet

Om du vill att dina jobbkortsenheter ska kunna acceptera ett batchnummer när de rapporteras som färdiga, måste du använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera följande funktioner:

- *Förbättrad användarupplevelse för dialogrutan Rapportförlopp i jobbkortenheten*
- *Aktivera för att ange batch- och löpnummer vid rapportering som färdigt från jobbkortenheten*<br>(Från och med version 10.0.29 av Supply Chain Management är denna funktion aktiverad som standard.)

### <a name="configure-products-that-require-batch-number-reporting"></a>Konfigurera produkter som kräver rapportering av batchnummer

Gör så här om du vill aktivera en produkt som stöder alla tillgängliga batchstyrda scenarier:

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj produkten som ska konfigureras.
1. På snabbfliken **Hantera lager** i fältet **batchnummergrupp** väljer du den spårningsnummergrupp som har angetts som stöd för ditt scenario.

> [!NOTE]
> Om ingen batchnummergrupp tilldelas en batchkontrollerad produkt innehåller jobbkortsenheten som standard manuell inmatning för batchnumret vid rapportering som färdigt.

I följande avsnitt beskrivs hur du konfigurerar spårningsnummergrupper för att stödja var och en av de tre scenarierna för rapportering av batch-artiklar.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Skapa en spårningsnummergrupp som gör att arbetare manuellt kan tilldela ett batchnummer

För att tillåta manuellt tilldelade batchnummer följer du dessa steg för att konfigurera en spårningsgrupp.

1. Gå till **Lagerhantering \> Inställning \> Dimensioner \> Spårningsnummergrupper**.
1. Skapa eller välj den spårningsnummergrupp som du vill konfigurera.
1. På snabbfliken **Allmänt** ställer du in **Manuellt** till **Ja**.

    ![En spårningsnummergrupp för manuella batchnummer.](media/tracking-number-group-manual.png "En spårningsnummer grupp för manuella batchnummer")

1. Ange andra värden som du behöver och välj sedan spårningsnummergruppen som batchnummergrupp för frisläppta produkter som du vill använda det här scenariot för.

När du använder det här scenario **batchnummer** som sidan **Rapportförlopp** på jobbkortsenheten ger är en textruta där arbetare kan ange vilket värde som helst.

![Rapportstatussida med ett fält för manuella batchnummer.](media/job-card-device-batch-manual.png "Rapportstatussida med ett fält för manuella batchnummer")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Ställ in en spårningsnummergrupp som innehåller en lista över fördefinierade batchnummer

För att tillhandahålla fördefinierade batchnummer följer du dessa steg för att konfigurera en spårningsgrupp.

1. Gå till **Lagerhantering \> Inställning > Dimensioner \> Spårningsnummergrupper**.
1. Skapa eller välj den spårningsnummergrupp som du vill konfigurera.
1. På snabbfliken **Allmänt** ställer du in **Bara för lagertransaktioner** till **Ja**.
1. Använd fältet **per kvantitet** om du vill dela upp batchnummer per kvantitet, baserat på det värde som du anger. Du har till exempel en tillverkningsorder på tio enheter och fältet **per kvantitet** anges till *2*. I det här fallet kommer fem batchnummer att tilldelasverkningsordern när den skapas.

    ![En spårningsnummergrupp för fördefinierade batchnummer.](media/tracking-number-group-predefined.png "En spårningsnummer grupp för fördefinierade batchnummer")

1. Ange andra värden som du behöver och välj sedan spårningsnummergruppen som batchnummergrupp för frisläppta produkter som du vill använda det här scenariot för.

När du använder det här scenario kommer fältet **batchnummer** som sidan **Rapportförlopp** på jobbkortsenheten är en listruta där arbetare måste välja ett fördefinierat värde.

![Rapportstatussida med en lista över fördefinierade batchnummer.](media/job-card-device-batch-predefined.png "Rapportstatussida med en lista över fördefinierade batchnummer")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Skapa en spårningsnummergrupp som automatiskt tilldelar batchnummer

Om batchnummer ska tilldelas automatiskt, utan indata från arbetare, följer du dessa steg för att skapa en spårningsnummergrupp.

1. Gå till **Lagerhantering \> Inställning \> Dimensioner \> Spårningsnummergrupper**.
1. Skapa eller välj den spårningsnummergrupp som du vill konfigurera.
1. På snabbfliken **Allmänt** ställer du in **Bara för lagertransaktioner** till **Nej**.
1. Ange alternativet **Manuell** till **Nej**.

    ![En spårningsnummergrupp för fasta batchnummer.](media/tracking-number-group-fixed.png "En spårningsnummer grupp för fasta batchnummer")

1. Ange andra värden som du behöver och välj sedan spårningsnummergruppen som batchnummergrupp för frisläppta produkter som du vill använda det här scenariot för.

När du använder det här scenario **batchnummer** som sidan **Rapportförlopp** på jobbkortsenheten ger visas ett värde med arbetare kan inte redigera det.

![Rapportstatussida med ett fast batchnummer.](media/job-card-device-batch-fixed.png "Rapportstatussida med ett fast batchnummer")

## <a name="report-serial-controlled-items-as-finished"></a>Rapportera seriekontrollerade artiklar som färdiga

Jobbkortsenheten stöder tre scenarier för rapportering av seriekontrollerade artiklar. Dessa scenarier gäller både artiklar som aktiveras för lagerstyrningsprocesser (WMS) och artiklar som inte är aktiverade för WMS.

- **Manuellt tilldelade löpnummer:** arbetare registrerar ett anpassat löpnummer. Det här serienumret kan komma från en extern källa som inte är känd för systemet.
- **Fördefinierade löpnummer:** arbetare väljer ett löpnummer i en lista med löpnummer som genereras automatiskt innan tillverknings ordern frisläpps till jobbkortsenheten.
- **Fast löpnummer:** arbetare anger eller väljer inte ett löpnummer. I stället tilldelar systemet automatiskt ett löpnummer till produktionsordern innan den frigörs.

### <a name="enable-the-feature-on-your-system"></a>Aktivera funktionen i systemet

Om du vill att dina jobbkortsenheter ska kunna acceptera ett löpnummer när de rapporteras som färdiga, måste du använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera följande funktioner:

- *Förbättrad användarupplevelse för dialogrutan Rapportförlopp i jobbkortenheten*
- *Aktivera för att ange batch- och löpnummer vid rapportering som färdigt från jobbkortenheten*<br>(Från och med version 10.0.29 av Supply Chain Management är denna funktion aktiverad som standard.)

### <a name="configure-products-that-require-serial-number-reporting"></a>Konfigurera produkter som kräver rapportering av löpnummer

Gör så här om du vill aktivera en produkt som stöder alla tillgängliga seriestyrda scenarier:

För att aktivera varje scenario följer du stegen nedan.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj produkten som ska konfigureras.
1. På snabbfliken **Hantera lager** i fältet **löpnummergrupp** väljer du den spårningsnummergrupp som har angetts som stöd för ditt scenario.

> [!NOTE]
> Om ingen löpnummergrupp tilldelas en seriekontrollerad produkt innehåller jobbkortsenheten som standard manuell inmatning för serienumret vid rapportering som färdigt.

I följande avsnitt beskrivs hur du konfigurerar spårningsnummergrupper för att stödja var och en av de tre scenarierna för rapportering av seriestyrda artiklar.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-serial-number"></a>Skapa en spårningsnummergrupp som gör att arbetare manuellt kan tilldela ett löpnummer

För att tillåta manuellt tilldelade löpnummer följer du dessa steg för att konfigurera en spårningsgrupp.

1. Gå till **Lagerhantering \> Inställning \> Dimensioner \> Spårningsnummergrupper**.
1. Skapa eller välj den spårningsnummergrupp som du vill konfigurera.
1. På snabbfliken **Allmänt** ställer du in **Manuellt** till **Ja**.

    ![Sidan Spårningsnummergrupper, löpnummer.](media/tracking-number-group-manual-serial.png "Sidan spårningsnummergrupper, löpnummer")

1. Ange andra värden som du behöver och välj sedan spårningsnummergruppen som löpnummergrupp för frisläppta produkter som du vill använda det här scenariot för.

När du använder det här scenario **löpnummer** som sidan **Rapportförlopp** på jobbkortsenheten ger är en textruta där arbetare kan ange vilket värde som helst för serienumret. När du anger ett värde läggs det till i löpnummer listan. I denna lista kan arbetare göra på följande sätt:

- Om du vill markera ett löpnummer som kasserat väljer du knappen **kassation** för lämplig rad. Arbetaren uppmanas att ange en **felorsak**.
- Om du vill ta bort ett löpnummer väljer du knappen **Ta bort** för lämplig rad.

![Rapportstatussida med ett fält för manuella löpnummer.](media/job-card-device-serial-manual.png "Rapportstatussida med ett fält för manuella löpnummer")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-serial-numbers"></a>Ställ in en spårningsnummergrupp som innehåller en lista över fördefinierade löpnummer

För att tillhandahålla fördefinierade löpnummer följer du dessa steg för att konfigurera en spårningsgrupp.

1. Gå till **Lagerhantering \> Inställning \> Dimensioner \> Spårningsnummergrupper**.
1. Skapa eller välj den spårningsnummergrupp som du vill konfigurera.
1. På snabbfliken **Allmänt** ställer du in **Bara för lagertransaktioner** till **Ja**.
1. Använd fältet **per kvantitet** om du vill dela löpnummer per kvantitet av ett.

    ![En spårningsnummergrupp för fördefinierade löpnummer.](media/tracking-number-group-predefined-sn.png "En spårningsnummer grupp för fördefinierade löpnummer")

1. Ange andra värden som du behöver och välj sedan spårningsnummergruppen som löpnummergrupp för frisläppta produkter som du vill använda det här scenariot för.

När du använder det här scenario kommer fältet **löpnummer** som sidan **Rapportförlopp** på jobbkortsenheten är en listruta där arbetare måste välja ett fördefinierat värde.

![Rapportstatussida med en lista över fördefinierade löpnummer.](media/job-card-device-serial-predefined.png "Rapportstatussida med en lista över fördefinierade löpnummer")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-serial-numbers"></a>Skapa en spårningsnummergrupp som automatiskt tilldelar löpnummer

Om löpnummer ska tilldelas automatiskt, utan indata från arbetare, följer du dessa steg för att skapa en spårningsnummergrupp.

1. Gå till **Lagerhantering \> Inställning \> Dimensioner \> Spårningsnummergrupper**.
1. Skapa eller välj den spårningsnummergrupp som du vill konfigurera.
1. På snabbfliken **Allmänt** ställer du in **Bara för lagertransaktioner** till **Nej**.
1. Ange alternativet **Manuell** till **Nej**.

    ![En spårningsnummergrupp för fasta löpnummer.](media/tracking-number-group-fixed-sn.png "En spårningsnummer grupp för fasta löpnummer")

1. Ange andra värden som du behöver och välj sedan spårningsnummergruppen som löpnummergrupp för frisläppta produkter som du vill använda det här scenariot för.

När du använder det här scenario **löpnummer** som sidan **Rapportförlopp** på jobbkortsenheten ger visas ett värde med arbetare kan inte redigera det. Det här scenariot är bara relevant när en tillverkningsorder skapas för en kvantitet av ett löpnummer som kontrolleras av en artikel.

![Rapportstatussida med ett fast löpnummer.](media/job-card-device-serial-fixed.png "Rapportstatussida med ett fast löpnummer")

## <a name="report-as-finished-to-a-license-plate"></a>Rapportera som färdig till ett ID-nummer

Lagerstyrningsprocesser (WMS) kan använda dimensionen för ID-nummer för att spåra lager på lagerställen som har ställts in för detta syfte. I det här fallet krävs ID-nummer när en arbetare rapporterar kvantiteter som färdiga.

### <a name="enable-license-plate-reporting-and-label-printing"></a>Aktivera rapportering och etikettutskrift av ID-nummer

Om du vill använda funktionerna som beskrivs i det här avsnittet måste du använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera följande funktioner (i den här ordningen):

1. *ID-nummer för rapportering som färdig har lagts till på jobbkortenheten*<br>(Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk.)
1. *Aktivera automatisk generering av ID-nummer när rapportering slutförts i jobbkortenheten*<br>(Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk.)
1. *Skriv ut etikett från jobbkortenhet*<br>(Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk.)

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>Konfigurera rapportering som färdig till ett ID-nummer

Om du vill kontrollera om arbetare ska återanvända ett befintligt ID-nummer eller skapa ett nytt ID-nummer när de rapporterar kvantiteter som färdiga följer du dessa steg.

1. Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera jobbkort för enheter**.
2. Ställ in följande alternativ för varje enhet:

    - **Generera ID-nummer** – Ange det här alternativet **Ja** om du vill generera ett nytt ID-nummer för varje rapport som färdig. Ställ in det på **Nej** om ett befintligt ID-nummer ska användas för varje rapport som färdig.
    - **Skriv ut etikett** – Ställ in det här alternativet på **Ja** om arbetare måste skriva ut ett ID-nummer för varje rapport som färdig. Ställ in det på **Nej** om ingen etikett behövs. 

![Konfigurera jobbkort för enhetssida.](media/config-job-card-raf.png "Konfigurera jobbkort för enhetssidan")

> [!NOTE]
> För att konfigurera etiketten, gå till **Lagerstyrning \> Inställningar \> Dokumentflöde \> Dokumentflöde**. Mer information finns i [Aktivera utskrift av ID-nummeretiketter](../warehousing/tasks/license-plate-label-printing.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]