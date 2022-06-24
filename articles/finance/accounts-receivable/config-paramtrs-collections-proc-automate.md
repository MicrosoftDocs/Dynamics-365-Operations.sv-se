---
title: Konfigurera parametrar för att automatisera inkassoprocessen
description: I den här artikeln beskrivs parametrar som påverkar automatiska inkassoprocesser och ger riktlinjer till hur de kan konfigureras så att den automatiska processen återspeglar dina önskemål och förväntningar.
author: JodiChristiansen
ms.date: 08/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c5d0f801c47ef2d98d8ba410dc593bd7640839c1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900054"
---
# <a name="configure-parameters-for-collection-process-automation"></a>Konfigurera parametrar för att automatisera inkassoprocessen

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs parametrar som påverkar automatiska inkassoprocesser och ger riktlinjer till hur de kan konfigureras så att den automatiska processen återspeglar dina önskemål och förväntningar. Information om hur du automatiserar inkassoprocesser finns i [Automatisering av inkassoprocess](collections-process-automate.md).

## <a name="general"></a>Allmänt
Ange ett tal i **Procentandel kunder per batchuppgift** för att bestämma antalet batchuppgifter per automationsprocess. Ställ in **Bokför kravbrev automatiskt** till **Ja** så åtgärdstypen för kravbrev kommer att lägga ut brevet under automatiseringen. Ställ in **Skapa aktiviteter för automatisering** till **Ja** för att skapa och stänga aktiviteter för åtgärder som inte är aktiva för att visa alla automatiska steg som har tagits på ett konto. Definiera antalet dagar som samlingshistoriken lagras i **Antal dagar som insamling av inkassoprocesser ska fortsätta**.  När en faktura når det sista steget i insamlingsprocessen kommer den inte att användas för att skapa framtida typer av processautomatiseringsåtgärder om **Exkludera faktura efter aktivering av senaste processteg** anges till **Ja**. Den nästa äldsta fakturan fastställer nästa processautomatiseringssteg för att se till att insamlingsprocessens automationsåtgärder fortsätter. 

## <a name="payment-predictions"></a>Betalningsförutsägelser
Från version 10.0.21 anger kundbetalningsprognoser, som finns i Finance Insights, om fakturan ska betalas i tid, sent eller mycket sent. Du kan konfigurera var och en av dessa kategorier med Finance Insights. Om fakturor kommer att betalas för sent är det viktigt att starta inkassoprocessen innan fakturan förfaller. Dessa förutsägelser kan användas för att skapa samlingar aktiviteter när samlingar processautomatisering körs. Ställ in **Aktivera betalningsförutsägelser** till **Ja** att använda kundbetalningsprognoser för att skapa insamlingsaktiviteter utifrån sannolikheten att fakturan kommer att betalas för sent. 

För mer information om Förutsägelser för kundbetalning och Finance insights, se [Förutsägelser för kundbetalning](payment-insights-overview.md).

När modellen för kundbetalningsprognoser körs tilldelas en procentandel till förutsägelsen om att fakturan betalas i tid, sent eller mycket sent. Du kan använda den informationen när du automatiskt vill starta inkassoaktiviteter genom att använda inkassoprocessautomatisering i fall där försenade betalningar förväntas. Du kan visa dessa procentsatser på sidorna **Betalningsförutsägelse per kund** eller **Betalningsförutsägelse per transaktion** under **Kredit och inkasso > inkasso**. 

Om den genomsnittliga betalningen för en kundfaktura understiger referensprocenten, skapas ingen aktivitet. Om fakturaprognosen är större än eller lika med referensprocenten skapas en aktivitet per kund. För **Förutsägelse: Sent**, ange **referensprocenten** för när inkassoprocessautomatisering ska skapa inkassoaktiviteter. Detta är ett aggregerat värde som är både sent och mycket sent. Välj en **affärsdokumentmall** som ska användas för aktiviteten som skapas eller skapas med en ny. Denna identifierar **Typ**, **Syfte** och **Dagar tills aktiviteten stängs**. Ange eventuella **Anteckningar** som standard som beskrivning när aktiviteten skapas. För **Förutsägelse: Mycket sent**, ange **referensprocenten** när samlingsprocessens automatisering bör skapa insamlingsaktiviteter för en kund som förutspås betala fakturor mycket sent. Välj en **affärsdokumentmall** som ska användas för aktiviteten som skapas. Denna identifierar **Typ**, **Syfte** och **Dagar tills aktiviteten stängs**. Ange eventuella **Anteckningar** som standard som beskrivning när aktiviteten skapas. 

### <a name="example"></a>Exempel
Om den försenade referensprocenten ställs in på 60 %. När kundbetalningsprognoser körs för varje faktura tilldelar systemet en procentuell förutsägelse om att bli betald i tid, sent eller mycket sent. Om betalningsprognosen om att fakturan betalas sent är 59 % eller lägre, skapas ingen inkassoaktivitet för fakturan genom den automatiska inkassoprocessen. Om kundbetalningsprognosen för en faktura är större än eller lika med 60 %, skapas en inkassoaktivitet under automatisering av inkassoprocessen. 

> [!NOTE]
> Den mycket försenade förutsägelsen utvärderas före den försenade förutsägelsen eftersom mycket sent inkluderar fakturor som förutspås bli försenade. Inkassoprocessen genererar bara en aktivitet om fakturan infaller i både sent och mycket sent referenser. I sådana fall används den mycket försenade aktiviteten och affärsdokumentet eftersom det blir högre prioritet för mycket sent. Andra åtgärder som redan har genererats genereras inte en gång till.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
