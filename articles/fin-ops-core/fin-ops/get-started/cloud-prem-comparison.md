---
title: Jämförelse mellan moln- och lokala funktioner
description: Detta avsnitt anger vilka funktioner stöds i molnet och på plats.
author: sericks007
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 68082ad0ae264b76a852d8d12412af8c4ad917703441c41e67743d1b499a8d73
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736232"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Jämförelse mellan funktioner i molnet och lokalt

[!include [banner](../includes/banner.md)]

Det här ämnet visar en jämförelse av funktionerna som är tillgängliga i moln jämfört med lokal för följande program:

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

Information om [funktionerna utveckling och administration](cloud-prem-comparison.md#development-and-administration-features) ingår också.

Följande tabell anger appområdena. Lokalt stöd och molnstöd anges för funktionen som helhet. Funktionerna listas på en separat rad i kolumnen Funktion i de fall där specifika funktioner varierar från området som helhet.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **Område**             | **Funktion**                | **Moln** | **På plats** |
|---------------------|-----------------------------|-----------|-----------------|
| Efterlevnad och certifieringar        |                                                                                           | Ja       | Ja             |
|                                      | SOC 1 Typ 1-certifiering                                                                | Ja       | Nej              |
| Datahantering och integration      |                                                                                           | Ja       | Ja             |
|                                      | Exportera data till ditt eget datalager                                                    | Ja       | Ja             |
|                                      | Aktivera export av stegvisa uppdateringar till en dataentitet                                 | Ja       | Ja             |
|                                      | Dataintegrationer                                                                         | Ja       | Ja             |
| Dokumenthantering                  |                                                                                           | Ja       | Ja             |
| Ekonomistyrning                 |                                                                                           | Ja       | Ja             |
| Hjälp                                 |                                                                                           | Ja       | Nej              |
| Personal                      |                                                                                           | Ja       | Ja             |
| Intelligence                         |                                                                                           | Ja       | Ja             |
|                                      | Elektronisk rapportering (ER)                                                                 | Ja       | Ja             |
|                                      | ER: Integration med LCS                                                                  | Ja       | Nej              |
|                                      | ER: Integration med SharePoint                                                           | Ja       | Nej              |
|                                      | ER: Integration med Regulatory Configuration Services (RCS)                              | Ja       | Nej              |
|                                      | ER: Använder lokalt filsystem som lagringsplats för ER-konfigurationer som är tillgängliga via ER-databaser | Nej        | Ja             |
|                                      | Integrering med PowerBI.com                                                              | Ja       | Nej              |
|                                      | Integrering med Power BI Desktop                                                          | Nej        | Ja             |
|                                      | Analytiska arbetsytor                                                                     | Ja       | Nej              |
|                                      | Intelligent affärsprocess: Rekommendationer                                             | Ja       | Nej              |
|                                      | Skapa Power BI-rapporter med OData med hjälp av stationära Power BI- eller Excel PowerQuery-verktyg    | Ja       | Nej              |
|                                      | SQL Server Reporting Services (SSRS) har stöd för skalning                                 | Ja       | Ja             |
|                                      | Telemetri överförs till molnet                                                   | Ja       | Nej              |
| Livscykeltjänster                   |                                                                                           | Ja       | Ja             |
|                                      | Konfigurerbara affärsprocesser                                                           | Ja       | Nej              |
| Lokaliseringar                        |                                                                                           | Ja       | Ja             |
| Mobilapp, arbetsytor och plattform |                                                                                           | Ja       | Ja             |
| Office-integrering                   |                                                                                           | Ja       | Ja             |
| Organisationsadministration          |                                                                                           | Ja       | Ja             |
| Lön                              |                                                                                           | Ja       | Ja             |
|                                      | Direktinsättning                                                                            | Ja       | Nej              |
| Projekthantering och redovisning    |                                                                                           | Ja       | Ja             |
| Säkerhet                             |                                                                                           | Ja       | Ja             |
| Tjänsthantering                   |                                                                                           | Ja       | Ja             |
| Webbklient                           |                                                                                           | Ja       | Ja             |
|                                      | Uppgiftsregistrerare - Spara eller ladda uppgiftsregistreringar från BPM-biblioteket                         | Ja       | Nej              |
| Support                              |                                                                                           | Ja       | Ja             |
|                                      | Supportåtkomst via menyn Hjälp & Support                                             | Ja       | Nej              |
|                                      | Affärshändelser                                                                           | Ja       | Ja (antingen är Internet-anslutningen obligatoriskt eller så måste anpassade slutpunkter implementeras för att skicka/ta emot affärshändelser inom intranätet)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Område**                | **Funktion**             | **Moln** | **På plats** |
|-------------------------|-------------------|-----------|-----------------|
| Tillgångshantering                     |                                                                                           | Ja       | Ja             |
| Efterlevnad och certifieringar        |                                                                                           | Ja       | Ja             |
|                                      | SOC 1 Typ 1-certifiering                                                                | Ja       | Nej              |
| Kostnadsredovisning                      |                                                                                           | Ja       | Ja             |
|                                      | Innehållspaket för kostnadsredovisning för Power BI                                                 | Ja       | Nej              |
|                                      | Arbetsyta för kostnadsredovisning för mobilapp                                                  | Ja       | Nej              |
| Kostnadshantering                      |                                                                                           | Ja       | Ja             |
|                                      | Innehållspaket Kostnadshantering för Power BI                                                 | Ja       | Nej              |
| Datahantering och integration      |                                                                                           | Ja       | Ja             |
|                                      | Konfigurationsdrivet tillägg                                                            | Ja       | Nej              |
|                                      | Exportera data till ditt eget datalager                                                    | Ja       | Ja             |
|                                      | Aktivera export av stegvisa uppdateringar till en dataentitet                                 | Ja       | Ja             |
|                                      | Dataintegrationer                                                                         | Ja       | Ja             |
| Dokumenthantering                  |                                                                                           | Ja       | Ja             |
| Hjälp                                 |                                                                                           | Ja       | Nej              |
| Intelligence                         |                                                                                           | Ja       | Ja             |
|                                      | Elektronisk rapportering (ER)                                                                 | Ja       | Ja             |
|                                      | ER: Integration med LCS                                                                  | Ja       | Nej              |
|                                      | ER: Integration med SharePoint                                                           | Ja       | Nej              |
|                                      | ER: Integration med Regulatory Configuration Services (RCS)                              | Ja       | Nej              |
|                                      | ER: Använder lokalt filsystem som lagringsplats för ER-konfigurationer som är tillgängliga via ER-databaser | Nej        | Ja             |
|                                      | Integrering med PowerBI.com                                                              | Ja       | Nej              |
|                                      | Integrering med Power BI Desktop                                                          | Nej        | Ja             |
|                                      | Analytiska arbetsytor                                                                     | Ja       | Nej              |
|                                      | Intelligent affärsprocess: Rekommendationer                                             | Ja       | Nej              |
|                                      | Skapa Power BI-rapporter med OData med hjälp av stationära Power BI- eller Excel PowerQuery-verktyg    | Ja       | Nej              |
|                                      | SQL Server Reporting Services (SSRS) har stöd för skalning                                 | Ja       | Ja             |
|                                      | Telemetri överförs till molnet                                                   | Ja       | Nej              |
| Lagerhantering                 |                                                                                           | Ja       | Ja             |
| Livscykeltjänster                   |                                                                                           | Ja       | Ja             |
|                                      | Konfigurerbara affärsprocesser                                                           | Ja       | Nej              |
| Lokaliseringar                        |                                                                                           | Ja       | Ja             |
| Tillverkning                        |                                                                                           | Ja       | Ja             |
| Huvudplanering och prognosticering      |                                                                                           | Ja       | Ja             |
| Planeringsoptimering                |                                                                                           | Ja       | Nej              |
| Mobilapp, arbetsytor och plattform |                                                                                           | Ja       | Ja             |
| Integrering med Office                   |                                                                                           | Ja       | Ja             |
| Organisationsadministration          |                                                                                           | Ja       | Ja             |
| Anskaffning och källa             |                                                                                           | Ja       | Ja             |
|                                      | Utstämpling till extern katalog från inköpsrekvisition                                   | Ja       | Nej              |
|                                      | Inköps- och utgiftsanalys Power BI-rapporter                                                  | Ja       | Nej              |
| Produktinformationshantering       |                                                                                           | Ja       | Ja             |
| Produktmalldata                  |                                                                                           | Ja       | Ja             |
| Produktion                           |                                                                                           | Ja       | Ja             |
|                                      | Produktionsprestanda Power BI-rapporter                                                   | Ja       | Nej              |
| Projekthantering och redovisning    |                                                                                           | Ja       | Ja             |
| Försäljning                                |                                                                                           | Ja       | Ja             |
|                                      | Försäljnings- och lönsamhetsresultat Power BI-rapporter                                      | Ja       | Nej              |
| Säkerhet                             |                                                                                           | Ja       | Ja             |
| Servicehantering                   |                                                                                           | Ja       | Ja             |
| Hantering av underleverantörer              |                                                                                           | Ja       | Ja             |
| Transporthantering            |                                                                                           | Ja       | Ja             |
| Leverantörssamarbete                 |                                                                                           | Ja       | Nej              |
| Lagerstyrning                 |                                                                                           | Ja       | Ja             |
|                                      | Lagerapp för mobil                                                                      | Ja       | Ja             |
|                                      | Power BI-rapporter för lagerställe                                                              | Ja       | Nej              |
| Webbklient                           |                                                                                           | Ja       | Ja             |
|                                      | Uppgiftsregistrerare - Spara eller ladda uppgiftsregistreringar från BPM-biblioteket                         | Ja       | Nej              |
| Support                              |                                                                                           | Ja       | Ja             |
|                                      | Supportåtkomst via menyn Hjälp & Support                                             | Ja       | Nej              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

En lista över funktioner som är tillgängliga i lokal distribution finns i [Commerce-funktionerna i lokala distributioner](../../../commerce/retail-onprem.md).

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **Område**         | **Funktion**         | **Moln** | **Lokal** |
|------------------|---------------------|-----------|-----------------|
| Alla områden inom Personal | Alla funktioner i Personal | Ja       | Nej              |

## <a name="development-and-administration-features"></a>FUnktionerna utveckling och administration

| **Område**                   | **Funktion**                               | **Moln** | **Lokal** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| Bygg och testa             |                                           | Ja       | Ja             |
| Utbyggbarhet              |                                           | Ja       | Ja             |
| Övervakning och telemetri   |                                           | Ja       | Ja             |
| Plattformskompatibilitet     |                                           | Ja       | Ja             |
| Behandling                  |                                           | Ja       | Ja             |
|                            | Servicemiljöer                    | Ja       | Nej              |
| Trace Parser               |                                           | Ja       | Ja             |
| PerfTimer                  |                                           | Ja       | Ja\*           |
| Uppgradera                    |                                           | Ja       | Ja             |
|                            | Uppgradera                                   | Ja       | Nej              |
|                            | Uppgradering och stöd för tidigare versioner | Ja       | Nej              |
| Visual Studio-utveckling  |                                           | Ja       | Ja             |

\* I lokala miljöer visar PerfTimer endast resultat för-klienten.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
