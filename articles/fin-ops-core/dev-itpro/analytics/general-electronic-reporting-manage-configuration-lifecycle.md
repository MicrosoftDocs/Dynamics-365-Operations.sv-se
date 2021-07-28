---
title: Hantera livscykeln för konfiguration av elektronisk rapportering (ER)
description: Detta ämne beskriver hur du hanterar konfigurationer för elektronisk rapportering (ER) konfigurationer för Dynamics 365 Finance.
author: NickSelin
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: bb7844a009bc35f7151827b8e675cb39f71459fd
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345748"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Hantera livscykeln för konfiguration av elektronisk rapportering (ER)

[!include [banner](../includes/banner.md)]

Detta ämne beskriver hur du hanterar konfigurationer för elektronisk rapportering (ER) konfigurationer för Dynamics 365 Finance.

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

    - Omforma en dokumentmall som har skapats till en ER-konfiguration, och exportera konfigurationen från den aktuella programinstansen som ett XML-paket som antingen kan lagras lokalt eller i Lifecycle Services (LCS).
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

ER-konfigurationer som utformas i utvecklingsmiljön kan [laddas upp](#data-persistence-consideration) till testmiljön för utvärdering av konfigurationen (korrekt processintegrering, korrekta resultat samt prestanda) och kvalitetssäkring, till exempel korrektheten i rollbaserad åtkomsträttigheter och ansvarsfördelning. Funktionerna som aktiverar ER-konfigurationsutbyte kan användas i detta syfte. Beprövade ER-konfigurationer kan laddas upp till LCS i syfte att dela dem med tjänsteprenumeranter, eller också kan de [importeras](#data-persistence-consideration) till produktionsmiljön för internt bruk.

![Livscykel för ER-konfiguration.](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a><a name="data-persistence-consideration" />Beaktande av databeständighet

Du kan [importera](tasks/er-import-configuration-lifecycle-services.md) olika [versioner](general-electronic-reporting.md#component-versioning) av en ER-[konfiguration](general-electronic-reporting.md#Configuration) individuellt till din Finance-instans. När en ny version av en ER-konfiguration importeras, kontrollerar systemet innehållet i utkastversionen av denna konfiguration:

   - När den importerade versionen är lägre än den högsta versionen av denna konfiguration i den aktuella Finance-instansen, förblir innehållet i utkastversionen för denna konfiguration oförändrat.
   - När den importerade versionen är högre än någon annan version av den här konfigurationen i den aktuella Finance-instansen kopieras innehållet i den importerade versionen till utkastversionen av den här konfigurationen så att du kan fortsätta att redigera den senast ifyllda versionen.

Om den här konfigurationen ägs av konfigurations [leverantören](general-electronic-reporting.md#Provider) som för tillfället är aktiverad, visas utkastversionen för den här konfigurationen för dig på snabbfliken **Versioner** på sidan **Konfigurationer** (**Organisationsadministrering** > **Elektronisk rapportering** > **Konfigurationer**). Du kan välja utkastversionen av konfigurationen och [ändra](er-quick-start2-customize-report.md#ConfigureDerivedFormat) ess innehåll genom att använda relevant ER-designer. När du har redigerat utkastversionen av en ER-konfiguration matchar denna inte längre innehållet i den högsta versionen av denna konfiguration i aktuell Finance-instans. För att förhindra att dina ändringar går förlorade visas ett felmeddelande om att importen inte kan fortsätta, detta eftersom versionen av denna konfiguration är högre än den högsta versionen av konfigurationen i den aktuella Finance-instansen. När detta inträffar, till exempel med formatkonfiguration **X**, visas felet **Versionen Format "X" har ej slutförts**.

Om du vill ångra de ändringar som du infört i utkastversionen väljer du den högsta slutförda eller delade versionen av ER-konfigurationen i Finance på snabbfliken **Versioner** och sedan alternativet **Hämta denna version**. Innehållet i den valda versionen kopieras till utkastversionen.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
