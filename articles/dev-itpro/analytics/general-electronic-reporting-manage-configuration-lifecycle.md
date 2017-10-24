---
title: "Hantera livscykeln för konfigurering av elektronisk rapportering"
description: "Det här avsnittet beskriver hur du hanterar livscykeln för elektroniska rapporteringskonfigurationer (ER) för Microsoft Dynamics 365 for Finance and Operations-lösningen."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 35288f5c2edfa8a340f963a5c7216041765a58b4
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="manage-the-electronic-reporting-configuration-lifecycle"></a>Hantera livscykeln för konfiguration av elektronisk rapportering

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur du hanterar livscykeln för elektroniska rapporteringskonfigurationer (ER) för Microsoft Dynamics 365 for Finance and Operations-lösningen.

<a name="overview"></a>Översikt
--------

Elektronisk rapportering (ER) är en motor som stöder enligt lag erforderliga samt landsspecifika elektroniska dokument i Microsoft Dynamics 365 for Finance and Operations. I allmänhet förutsätter ER en förmåga att utföra följande uppgifter för ett enstaka elektroniskt dokument. Mer information finns i [översikt för elektronisk rapportering](general-electronic-reporting.md).

-   Designa en mall för ett elektroniskt dokument:
    -   Identifiera nödvändiga datakällor som kan presenteras i detta dokument:
        -   Underliggande Finance and Operations-data, till exempel dataregister, dataentiteter och klasser.
        -   Processens särskilda egenskaper, till exempel utförandedatum och tid och tidszon.
        -   Användarindataparametrar som anges av slutanvändaren vid körtid.
    -   Definiera nödvändiga dokument, liksom deras topologi för att specificera ett slutligt dokumentformat.
    -   Konfigurera önskat flöde av data från utvalda datakällor för att definiera dokumentets element (via datakällbindningar till dokumentets formatkomponenter) och ange processkontrollogik.
-   Gör en mall tillgänglig så att den kan användas i andra Finance and Operations-instanser:
    -   Omforma en dokumentmall som har skapats i Finance and Operations till en ER-konfiguration, och exportera konfigurationen från den aktuella Finance and Operations-instansen som ett XML-paket som antingen kan lagras lokalt eller i LCS.
    -   Omforma en ER-konfiguration till en dokumentmall för Finance and Operations.
    -   Importera ett XML-paket som lagras antingen lokalt eller i LCS till den aktuella Finance and Operations-instansen.
-   Anpassa en mall för ett elektroniskt dokument:
    -   Hämta en mall från LCS till nuvarande Finance and Operations-instans som en ER-konfiguration.
    -   Utforma en anpassad version av en ER-konfiguration och behåll en hänvisning till basversionen.
-   Integrera en mall med en viss affärsprocess så att den blir tillgänglig i Finance and Operations:
    -   Konfigurera inställningar så att Finance and Operations börjar använda en ER-konfiguration, detta genom att referera till konfigurationen i en processrelaterad parameter. Till exempel, referera till ER-konfigurationen i en viss leverantörsreskontrabetalningsmetod för att skapa ett meddelande för elektronisk betalning för bearbetning av fakturor.
-   Använd en mall i en viss affärsprocess.:
    -   Köra en ER-konfiguration i en specifik affärsprocess. Till exempel, referera till ER-konfigurationen i en viss leverantörsreskontrabetalningsmetod när en betalningsmetod som hänvisar till en av ER-konfiguration är vald.

## <a name="concepts"></a>Begrepp
Följande roller och relaterade aktiviteter är associerade med ER-konfigurationslivscykeln.

| Roll                                       | Aktiviteter                                                      | beskrivning                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konsult för funktionen för elektronisk rapportering | Skapa och hantera ER-komponenter (modeller och format).           | En affärsrörelsemänniska som designar modeller för ER-domänspecifika data, utformar önskade mallar för elektroniska dokument och binder dem.                                                                           |
| Utvecklare för elektronisk rapportering             | Skapa och hantera mappningar för datamodellen.                          | En Finance and Operations-specialist som väljer önskade Finance and Operations-datakällor och binder dem till ER-domänspecifika datamodeller.                                                                 |
| Redovisningsansvarig                      | Konfigurera processrelaterade inställningar som refererar till ER-artefakter. | Till exempel, en **redovisningsansvarig**-roll som tillåter inställningarna för en ER-konfiguration att användas i en viss leverantörsreskontrabetalningsmetod för att skapa ett meddelande för elektronisk betalning för bearbetning av fakturor |
| Ansvarig för leverantörsreskontrabetalningar            | Använda ER-artefakter i en viss affärsprocess.                | Till exempel, **Ansvarig för leverantörsreskontrabetalningar**-rollen som gör att meddelanden för elektroniska betalningar skapas för att bearbeta fakturor som baseras på ER-formatet som konfigureras för en viss betalningsmetod.           |

## <a name="er-configuration-development-lifecycle"></a>Livscykel för ER-konfigurationsutveckling
För följande ER-relaterade orsaker rekommenderas att du designar ER-konfigurationer i utvecklingsmiljön som en separat instans av Finance and Operations:

-   Användare i antingen rollen **elektronisk rapportering utvecklare** eller **elektronisk rapportering funktionella konsult** kan redigera konfigurationer och köra dem för teständamål. Detta scenario kan orsaka metodanrop från klasser och tabeller som kan vara skadliga för affärsdata och för Finance and Operations-instansens prestanda.
-   Metodanrop från klasser och tabeller som ER-datakällor för ER-konfigurationer begränsas inte av Finance and Operations-startpunkter eller loggat företagsinnehåll. Därför känslig affärsinformation kan nås av användarna i antingen **elektronisk rapportering utvecklare** eller **elektronisk rapportering funktionella konsult**.

ER-konfigurationer som utformas i utvecklingsmiljön kan överföras till testmiljön för utvärdering av konfigurationen (rätt process integration, korrekta resultat, prestanda) och kvalitetssäkring, till exempel korrektheten i rollen som drivs av åtkomsträttigheter och uppdelning av uppgifter. Funktionerna som aktiverar ER-konfigurationsutbyte kan användas i detta syfte. Slutligen kan beprövade ER-konfigurationer överföras antingen till LCS där de kan delas med abonnenter eller till produktionsmiljön för intern användning, som visas i följande bild. ![Livscykel för ER-konfiguration](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Se även
--------

[Översikt över elektronisk rapportering](general-electronic-reporting.md)




