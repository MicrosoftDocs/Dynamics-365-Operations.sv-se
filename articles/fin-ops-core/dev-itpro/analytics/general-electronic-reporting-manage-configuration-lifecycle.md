---
title: Hantera livscykeln för konfiguration av elektronisk rapportering (ER)
description: Den här avsnittet beskriver hur du hanterar livscykeln för elektronisk rapportering (ER) konfigurationer för Microsoft Dynamics 365 Finance-lösningen.
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a4741784103817c270c4c7f730753ba59a327d1
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682633"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Hantera livscykeln för konfiguration av elektronisk rapportering (ER)

[!include [banner](../includes/banner.md)]

Den här avsnittet beskriver hur du hanterar livscykeln för elektronisk rapportering (ER) konfigurationer för Microsoft Dynamics 365 Finance.

## <a name="overview"></a>Översikt

Elektronisk rapportering (ER) är en motor som stöder lagstadgade behov och landsspecifika elektroniska dokument. I allmänhet förutsätter ER en förmåga att utföra följande uppgifter för ett enstaka elektroniskt dokument. Mer information finns i [översikt för (ER) elektronisk rapportering](general-electronic-reporting.md).

- Designa en mall för ett elektroniskt dokument:

    - Identifiera nödvändiga datakällor som kan presenteras i detta dokument:

        - Underliggande data, till exempel dataregister, dataentiteter och klasser.
        - Processens särskilda egenskaper, till exempel utförandedatum och tid och tidszon.
        - Användarindataparametrar som anges av slutanvändaren vid körtid.

    - Definiera nödvändiga dokument, liksom deras topologi för att specificera ett slutligt dokumentformat.
    - Konfigurera önskat flöde av data från utvalda datakällor för att definiera dokumentets element (via datakällbindningar till dokumentets formatkomponenter) och ange processkontrollogik.

- Gör en mall tillgänglig så att den kan användas i andra instanser:

    - Omforma en dokumentmall som har skapats till en ER-konfiguration och exportera konfigurationen från den aktuella appinstansen som ett XML-paket som antingen kan lagras lokalt eller i LCS.
    - Omforma en ER-konfiguration till en dokumentmall för appar.
    - Importera ett XML-paket som lagras lokalt antingen eller i LCS till den aktuella instansen.

- Anpassa en mall för ett elektroniskt dokument:

    - Hämta en mall från LCS till nuvarande instansen som en ER-konfiguration.
    - Utforma en anpassad version av en ER-konfiguration och behåll en hänvisning till basversionen.

- Integrera en mall med en viss arbetsprocess så att den är tillgänglig i appen:

    - Konfigurera inställningar så att appen börjar använda en ER-konfiguration, detta genom att referera till konfigurationen i en processrelaterad parameter. Till exempel, referera till ER-konfigurationen i en viss leverantörsreskontrabetalningsmetod för att skapa ett meddelande för elektronisk betalning för bearbetning av fakturor.

- Använd en mall i en viss affärsprocess.:

    - Köra en ER-konfiguration i en specifik affärsprocess. Till exempel, referera till ER-konfigurationen i en viss leverantörsreskontrabetalningsmetod när en betalningsmetod som hänvisar till en av ER-konfiguration är vald.

## <a name="concepts"></a>Begrepp
Följande roller och relaterade aktiviteter är associerade med ER-konfigurationslivscykeln.

| Roll                                       | Aktiviteter                                                      | beskrivning |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Konsult för funktionen för elektronisk rapportering | Skapa och hantera ER-komponenter (modeller och format).           | En affärsrörelsemänniska som designar modeller för ER-domänspecifika data, utformar önskade mallar för elektroniska dokument och binder dem. |
| Utvecklare för elektronisk rapportering             | Skapa och hantera mappningar för datamodellen.                          | En specialist som väljer de önskade Finance datakällorna och binder dem till ER-domänspecifika datamodeller. |
| Redovisningsansvarig                      | Konfigurera processrelaterade inställningar som refererar till ER-artefakter. | Till exempel, en **redovisningsansvarig**-roll som tillåter inställningarna för en ER-konfiguration att användas i en viss leverantörsreskontrabetalningsmetod för att skapa ett meddelande för elektronisk betalning för bearbetning av fakturor |
| Ansvarig för leverantörsreskontrabetalningar            | Använda ER-artefakter i en viss affärsprocess.                | Till exempel, **Ansvarig för leverantörsreskontrabetalningar**-rollen som gör att meddelanden för elektroniska betalningar skapas för att bearbeta fakturor som baseras på ER-formatet som konfigureras för en viss betalningsmetod. |

## <a name="er-configuration-development-lifecycle"></a>Livscykel för ER-konfigurationsutveckling
För följande ER-relaterade orsaker rekommenderas att du designar ER-konfigurationer i utvecklingsmiljön som en separat instans av Finance and Operations:

- Användare i antingen rollen **elektronisk rapportering utvecklare** eller **elektronisk rapportering funktionella konsult** kan redigera konfigurationer och köra dem för teständamål. Det här scenariot kan orsaka anrop av metoder för klasser och tabeller som kan vara skadliga för affärsdata och instansens prestanda.
- Anrop av metoder för klasser och tabeller som ER-datakällor eller ER-konfigurationer är inte begränsade av startpunkter och loggat företagsinnehåll. Därför känslig affärsinformation kan nås av användarna i antingen **elektronisk rapportering utvecklare** eller **elektronisk rapportering funktionella konsult**.

ER-konfigurationer som utformas i utvecklingsmiljön kan överföras till testmiljön för utvärdering av konfigurationen (rätt process integration, korrekta resultat, prestanda) och kvalitetssäkring, till exempel korrektheten i rollen som drivs av åtkomsträttigheter och uppdelning av uppgifter. Funktionerna som aktiverar ER-konfigurationsutbyte kan användas i detta syfte. Slutligen kan beprövade ER-konfigurationer överföras antingen till LCS där de kan delas med abonnenter eller till produktionsmiljön för intern användning, som visas i följande bild.

![Livscykel för ER-konfiguration](./media/ger-configuration-lifecycle.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]