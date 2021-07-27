---
title: Konfigurera en enhet för att köra körningsgränssnittet för produktionsgolvet
description: Körningsgränssnittet för produktionsgolvet är inställt för varje enhet på produktionsgolvet. Företag ställer vanligtvis in varje enhet på olika sätt, beroende på vilket syfte enheten har. Ett företag kan till exempel ha en enhet i mottagningsområdet, där arbetare stämplar in och stämplar ut och en annan på verkstadsgolvet där arbetare hanterar sina jobb.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution, HcmWorker, JmgProductionFloorExecutionDeviceConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 9a5911e81547134d3034d1a47ef94c553ccbb331
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353974"
---
# <a name="set-up-a-device-to-run-the-production-floor-execution-interface"></a>Konfigurera en enhet för att köra körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]

Körningsgränssnittet för produktionsgolvet är inställt för varje enhet på produktionsgolvet. Företag ställer vanligtvis in varje enhet på olika sätt, beroende på vilket syfte enheten har. Ett företag kan till exempel ha en enhet i mottagningsområdet, där arbetare stämplar in och stämplar ut och en annan på verkstadsgolvet där arbetare hanterar sina jobb.

## <a name="set-the-configuration-and-filters-for-a-specific-device"></a>Ställa in konfiguration och filter för en specifik enhet

Om du vill ange konfigurations- och jobbfilter för en enhet loggar du in på sidan **körning på produktionsgolvet** med hjälp av ett konto som har en säkerhets roll som inkluderar uppdraget *Underhåll tidsövervakning*. (Bland de medföljande säkerhetsrollerna i den här listan kan endast *Produktionslagerarbetsledaren* ha detta uppdrag.) Följ sedan de här stegen.

1. Gå till den enhet som du vill ställa in och logga in på Microsoft Dynamics 365 Supply Chain Management som en produktionslagerarbetsledare. (Använd ett konto som innehåller uppdraget *Underhåll tidsövervakning*.)
1. Kontrollera att det finns en konfiguration för enheten som du installerar. Om det inte redan finns en konfiguration anges en standardkonfiguration. Mer information om hur du ställer in en konfiguration finns i [Konfigurera körningsgränssnittet för produktionsgolvet](production-floor-execution-configure.md).
1. Gå till **Produktionskontroll \> Tillverkningskörning \> Körningsgränssnittet för produktionsgolvet**.

    Om körningsgränssnittet för produktionsgolvet redan har konfigurerats minst en gång på den aktuella enheten visas en inloggningssida. I annat fall visas en välkomstsida.

1. Välj **Konfigurera** på antingen inloggningssidan eller välkomstsidan.
1. Välj en konfiguration i listan.
1. Välj **Nästa**.
1. Välj ett eller flera filter som ska användas för den aktuella enheten. Dessa filter hjälper till att säkerställa att endast relevanta jobb visas på enheten. Om du vill ange ett filter väljer du filtertypen för att öppna en värdelista och väljer sedan det värde du vill filtrera på. Följande filter är tillgängliga:

    - **Produktionsenhet** – det här filtret är det högsta filtret. Det gäller vanligtvis ett stort arbetsområde med flera resursgrupper och enskilda resurser i den.
    - **Resursgrupp** – det här filtret är ett halv nivåfilter. Den refererar vanligtvis till en samling relaterade resurser i en begränsad del av arbetsytan. Om du först väljer ett filter för **produktionsenhet** visas endast grupper från den enheten i listan över resursgrupper. I annat fall visas alla tillgängliga resursgrupper.
    - **Resurs** – det här filtret är det mest specifika filtret. Den hänvisar vanligtvis till en specifik dator eller en viss resurs. Om du väljer filter för **Resursgrupp** och/eller **Produktionsenhet** först visas endast listan med resurser de resurser från den gruppen och/eller enheten. I annat fall visas alla tillgängliga resurser.

1. Välj **OK**.
1. Inloggningssidan visas och enheten är klar att användas.

## <a name="allow-a-worker-to-override-the-default-filters"></a>Tillåt en arbetare att åsidosätta standardfilter

Du kan ge vissa medarbetare behörighet att ändra filterinställningarna för alla enheter som de använder. För arbetare som har den här behörigheten innehåller körningsgränssnittet för produktionsgolvet en knapp för **Filter** på sidorna **Alla jobb** och **Aktiva jobb**.

> [!NOTE]
> Om en medarbetare ändrar ett filter används det nya filtret i stället framåt för alla användare som loggar in på enheten.

Gör så här om du vill att en arbetare ska kunna åsidosätta standard jobbfiltren som har ställts in för en enhet.

1. Gå till **Tid och närvaro \> Inställningar \> Tidsregistreringsarbetare**.
1. Välj en medarbetare i listan om du vill öppna sidan med medarbetarens **Tidsregistreringsarbetare**.
1. På fliken **Tidsregistrering** ange alternativet **Ange filter** till *Ja*.

## <a name="run-the-interface-in-full-screen-mode"></a>Köra gränssnittet i helskärmsläge

I många fall kör du körningsgränssnittet för produktionsgolvet på en enhet som uteslutande används för det syftet. Därför kan det vara klokt att köra gränssnittet i helskärmsläge utan att visa navigering och/eller webbläsaren Chrome.

- Om du vill dölja navigeringsfönstret som visas i Supply Chain Management lägger du till följande text i slutet av webbadressen i webbläsarens adressfält: `\&limitednav=true`.
- Om du också vill dölja webbläsarens adressfält använder du webbläsarens inbyggda helskärmsläge. (Instruktioner finns i dokumentationen till webbläsaren.)

I den övre delen av bilden nedan visas hur gränssnittet ser ut som standard. I den nedre delen visas hur den ser ut i helskärmsläge när navigeringsfönstret döljs.

![Standard- jämfört med helskärmsgränssnitt.](media/pfei-full-screen.png "Standard jämfört med helskärmsgränssnitt")

## <a name="extend-the-session-past-12-hours"></a>Förläng sessionen de senaste 12 timmarna

Som standard används körningsgränssnittet för produktionsgolvet automatiskt för att logga ut om ingen använder det i 12 timmar. En användare av Supply Chain Management måste sedan logga in igen. Du kan dock förlänga tidsgränsen till upp till 90 dagar.

Om du vill förlänga tidsgränsen loggar du in på Supply Chain Management, går till **Systemadministration \> Användare \> Sessionstillägg**. Ange användarkontot för Supply Chain Management som används för att logga in på enheten och antalet timmar som sessionen ska vara aktiv för.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]