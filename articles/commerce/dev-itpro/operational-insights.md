---
title: Konfigurera Operational Insights
description: Det här avsnittet beskriver hur du ställer in och använder funktionen Operational Insights i Microsoft Dynamics 365 Commerce.
author: ashishMSFT
ms.date: 12/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: ca0d31e403275d6131fa6d53f0a7b46a7ddb651d
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832142"
---
# <a name="set-up-operational-insights"></a>Konfigurera Operational Insights

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du ställer in och använder funktionen Operational Insights i Microsoft Dynamics 365 Commerce.

Operational Insights är en Dynamics 365 Commerce-funktion som har utformats för att ge kunderna bättre insyn i sin tjänststatus och sina affärsfunktioner genom att skicka telemetri direkt till ett kundägt Application Insights-konto.

Genom att aktivera Operational Insights för dina miljöer i Commerce headquarters kan du samla in en granskad lista med händelser från både Commerce Scale Unit (CSU) och kassaenheterna (POS). Händelserna gör att du får en bättre förståelse för hur systemet presterar och med dem kan du övervaka de tekniska värdena och affärsmåtten.

Även om du inte vill samla in den här telemetrin hela tiden kan du tjäna på att snabbt aktivera eller inaktivera insamling för specifika miljöer. Telemetrin kan på det här sättet hjälpa dig att felsöka under utveckling eller produktion.

## <a name="access-logs-in-application-insights"></a>Komma åt loggar i Application Insights

För att komma åt diagnoshändelseloggar för Commerce CSU- och kassakomponenter via Application Insights slutför du procedurerna i det här avsnittet.

### <a name="minimum-version-requirements-for-csu"></a>Minsta versionskrav för CSU

CSU har följande minsta versionskrav:

- 10.0.23 (Retail Server version 9.33.22062.15 och senare)
- 10.0.24 (Retail Server version 9.34.22062.14 och senare)
- 10.0.25 (Retail Server version 9.35.22062.13 och senare)
- 10.0.26 och senare (alla versioner)

### <a name="enable-diagnostic-events-in-application-insights"></a>Aktivera diagnoshändelser i Application Insights

> [!IMPORTANT]
> Om du tidigare har använt en förhandsgranskningsversion av Operational Insights måste du använda följande procedur för att aktivera Operational Insights. På det här sättet ser du till att den tillförlitliga och säkra åtkomsten till händelser kan fortgå.

Om du vill aktivera diagnoshändelser för handelskomponenter måste du ha ett Application Insights-konto. Du kan använda ett befintligt konto eller [skapa ett nytt konto](/azure/azure-monitor/app/create-workspace-resource#create-workspace-based-resource). Av sekretesskäl rekommenderar vi att du använder separata Application Insights-konton för produktions-, sandbox- och utvecklingsmiljöer. När du har skapat ett konto måste du aktivera funktionen **Operational Insights** i administration.

Aktivera diagnoshändelser i Application Insights med dessa steg.

1. I administration, öppna arbetsytan **Funktionshantering** och aktivera funktionen **Operational Insights**.
1. Gå till **Systemadministration \> Inställningar \> Operational Insights**.
1. På fiken **Konfigurera** ange alternativet **Händelser för Commerce-kanal** till **Ja**.
1. På fliken **Miljöer** ange värdena **LCS miljö-ID** och **Miljöläge** för varje miljö där du planerar att använda Application Insights. Du kan hitta miljö-ID för varje miljö på sidan **Miljöinformation** för den miljön i Microsoft Dynamics Lifecycle Services. Detta steg behövs för att förhindra att diagnoshändelser skickas felaktigt till fel miljö när databaskopior utförs.
1. På fliken **Application Insights register** ange värdet Application Insights **instrumenteringsnyckeln** och motsvarande värde för **Miljöläge** för de miljöer där du planerar att använda respektive Application Insights-konto.
1. När du har slutfört konfigurationen måste du köra **CDX-jobb 1110**. Du kan vänta tills jobbet körs enligt sitt eget schema, eller så kan du köra det manuellt.
1. I Lifecycle Services, gå till **Miljöinformation \> Handel \> Hantera**, välj en CSU-instans och välj sedan **Starta om**. Upprepa det här steget för varje CSU.
1. Upprepa de föregående stegen för varje miljö som du tänker använda Application Insights.

> [!NOTE]
> - Telemetrihändelser i Operational Insights kan ändras. Du rekommenderas att använda Operational Insights-händelser när du gör en preliminär analys och felsökning på egen hand, inte för att definiera instrumentpaneler eller notifieringar. Om du använder händelser i andra syften än felsökningar med självbetjäning rekommenderar vi att du validerar och uppdaterar dina frågor efter varje CSU/POS-version.
> - Med hjälp av Commerce version 10.0.29 aktiveras även procedurerna i det här avsnittet av POS Operational Insights-händelser till ditt Application Insights-konto. Mer information finns i [Operational Insights för POS – Händelser och frågor](https://download.microsoft.com/download/9/2/b/92be35b0-0e24-4a4d-940d-6f4db29791c0/Operational-Insights-Commerce-POS-events-queries.pdf).

#### <a name="use-the-dllhostexeconfig-file-to-control-pos-operational-insights-events"></a>Använd filen DLLHost.exe.config för att kontrollera POS Operational Insights-händelser

För att använda filen DLLHost.exe.config för att kontrollera POS Operational Insights-händelser, följer du dessa steg.

1. I en textredigerare, öppna filen **DLLHost.exe.config** i **C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\Retail Modern POS\\ClientBroker**.
1. I avsnittet **diagnosticsSection** tar du bort XML-element för mottagare som har klassnamnet **Microsoft.Dynamics.Retail.Diagnostics.OperationalInsights.OperationalInsightsLogger**.
1. Spara filen.

### <a name="disable-diagnostic-events-in-application-insights"></a>Inaktivera diagnoshändelser i Application Insights

> [!IMPORTANT]
> Om du vill inaktivera diagnoshändelser och inte längre skicka dem till Application Insights måste du genomföra följande procedur. Du kan inte bara inaktivera den här funktionen i funktionshantering.

Inaktivera diagnoshändelser i Application Insights med dessa steg.

1. I administration, gå till **Systemadministration \> Operational Insights**.
1. På fiken **Konfigurera** ange alternativet **Händelser för Commerce-kanal** till **Nej**.
1. När du har slutfört konfigurationen måste du köra **CDX-jobb 1110**. Du kan vänta tills jobbet körs enligt sitt eget schema, eller så kan du köra jobbet manuellt.
1. I Lifecycle Services, gå till **Miljöinformation \> Handel \> Hantera**, välj en CSU-instans och välj sedan **Starta om**. Upprepa det här steget för varje CSU.
1. Upprepa de föregående stegen för varje miljö som du tänker inaktivera Application Insights.

Om du vill inaktivera diagnoshändelser för en enskild miljö tar du bort instrumenteringsnyckeln på fliken **Application Insights register** på sidan **Operational Insights**. Slutför sedan steg 3 och 4 i föregående procedur.

> [!NOTE]
> I Commerce version 10.0.29 eller senare inaktiverar stegen i det här avsnittet strömning av POS Operational Insights-händelser till ditt Application Insights-konto. 
