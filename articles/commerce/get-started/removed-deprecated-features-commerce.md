---
title: Borttagna eller inaktuella funktioner i Dynamics 365 Commerce
description: I denna artikel beskrivs funktioner som har tagits bort eller har planerats för borttagning från Dynamics 365 Commerce.
author: josaw
ms.date: 07/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: a59d62ad846eed659fa4e70390ebafc40127df0f
ms.sourcegitcommit: ef56b5d0ed26e373add5dec63168e08ade40573e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9138597"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Borttagna eller inaktuella funktioner i Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs funktioner som har tagits bort eller har planerats för borttagning från Dynamics 365 Commerce.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i appar för ekonomi och drift finns i [Tekniska referensrapporter](/dynamics/s-e/). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i respektive version av appar för ekonomi och drift.

## <a name="feature-deprecation-effective-july-2022"></a>Utfasning av funktioner från och med juli 2022

### <a name="commerce-analytics-preview"></a>Commerce-analyser (förhandsversion)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Dynamics 365 Commerce-teamet har analyserat hur funktionen Commerce-analys (förhandsversion) används, och det har tagits ett beslut om att inte längre göra funktionen allmänt tillgänglig.   |
| **Ersatt av en annan funktion?**   | Vid den här tidpunkten ersätts inte Commerce-analys (förhandsversion) av någon annan funktion eller lösning. Exporten av råtransaktioner och huvuddata från appar för ekonomi och drift till Azure Data Lake kommer även fortsatt vara tillgänglig, vilket förklaras i [Exportera till Data Lake i appar för ekonomi och drift.](../../fin-ops-core/dev-itpro/data-entities/finance-data-azure-data-lake.md) Partner och kunder kan utnyttja dataflödet till att skapa eventuella avsedda analysrapporter för verksamhetens behov.
| **Produktområden som påverkas**         | Commerce-analyser (förhandsversion) |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Vi avser att inaktivera denna funktion senast den 30 augusti 2022.  Från och med detta datum sker ingen uppdatering i de aktuella Power BI-rapporter som tillhandahålls av Commerce-analys (förhandsversion).     |


## <a name="features-removed-or-deprecated-in-the-commerce-10025-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.25

### <a name="modern-point-of-sale-mpos"></a>Modern Point of Sale (MPOS)

Programmet Modern Point of Sale (MPOS) gamla i versionen av Commerce version 10.0.25 och ersätts med programmet Store Commerce.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Butiksappar är det som gör att det inte går att använda något Dynamics 365 Commerce flerkanalserbjudande. Vi arbetar kontinuerligt med att tillhandahålla moderna och förnyade butikserfarenheter, och för att ytterligare förnya vår lösning, rullar vi ut nya uppsättningar med ändringar som kommer att förbättra IT-åtgärderna och användarerfarenheterna med våra befintliga program för butik i Windows. Det nya programmet Store Commerce är en teknologiuppgradering av det befintliga MPOS. Den ger förbättrad prestanda, tillförlitlighet och långsiktig support för Windows-plattform, och eliminerar behovet av att packa om programmet vid varje uppdatering. |
| **Ersatt av en annan funktion?**   |  [Store Commerce](../dev-itpro/store-commerce.md) |
| **Produktområden som påverkas**         | Modern Point of Sale |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Förfallen: Från och med den version av Commerce 10.0.25 som levereras kommer MPOS-installationsprogrammet som levererats via LCS-virtuella maskiner att tas bort i oktober 2023. |

## <a name="features-removed-or-deprecated-in-the-commerce-10021-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.21

[!include [banner](../includes/preview-banner.md)]

### <a name="overlapping-discounts-handling-setting-in-commerce-parameters"></a>Inställning för överlappande rabatthantering i Commerce-parametrar

Inställningen **överlappande rabatthantering** på sidan **Commerce-parametrar** är inaktuell i Commerce version 10.0.21. Framöver kommer Commerce-prissättningsmotorn att använda en enda algoritm för att bestämma den optimala kombinationen av överlappande rabatter.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | <p>Inställningen **Hantering av överlappande rabatter** i Commerce-parametrar styr hur Commerce-prissättningsmotorn söker och bestämmer den optimala kombinationen av rabatter. Det har för närvarande tre alternativ:<p><ul><li> **Bäst prestanda** – Det här alternativet använder en avancerad heuristics-algoritm och en metod för [marginalvärderankning](../optimal-combination-overlapping-discounts.md) för att prioritera, utvärdera och bestämma den bästa rabattkombinationen i tid.</li><li>**Balanserad beräkning** – I den aktuella kodbasen fungerar det här alternativet på samma sätt som alternativet **Bästa prestanda**. Därför är det i grund och botten ett duplicerat alternativ.</li><li>**Fullständig beräkning** – I det här alternativet används en gammal algoritm som går igenom alla möjliga rabattkombinationer under prisberäkningen. För order som har stora rader och kvantiteter kan det här alternativet orsaka prestandaproblem.</li></ul><p>För att förenkla konfigurationen, förbättra prestanda och minska incidenter som orsakas av den gamla algoritmen kommer vi att ta bort inställningen **överlappande rabatthantering** helt och uppdatera den interna logiken för Commerce-prissättningsmotorn så att den nu bara använder den avancerade algoritmen (det vill säga algoritmen bakom alternativet **Bästa prestanda**).</p> |
| **Ersatt av en annan funktion?**   | Nej. Vi rekommenderar att organisationer som använder alternativet **Balanserad beräkning** eller **Fullständig beräkning** för att växla till alternativet **Bästa prestanda** innan den här funktionen tas bort. |
| **Produktområden som påverkas**         | Prissättning och rabatter |
| **Distribueringsalternativ**              | Alla |
| **Status**                         | Vid version 10.0.21 kommer inställningen **överlappande rabatthantering** att tas bort från Commerce-parametrar i oktober 2022. |

### <a name="retail-sdk-distributed-by-using-lifecycle-services"></a>Retail SDK som distribueras med hjälp av Lifecycle Services

Retail SDK levereras i Lifecycle Services (LCS). Detta distributionssätt är inaktuellt i version 10.0.21. Hädanefter kommer Retail SDK-referenspaket, -bibliotek och -exempel att publiceras i offentliga databaser på GitHub.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Retail SDK levereras i LCS. LCS-processen tar ett par timmar att slutföra, och processen måste upprepas för varje uppdatering. Hädanefter kommer Retail SDK-referenspaket, -bibliotek och -exempel att publiceras i offentliga databaser på GitHub. Tilläggsexempel och referenspaket kan enkelt förbrukas, och uppdateringarna slutförs på några få minuter. |
| **Ersatt av en annan funktion?**   |  [Hämta Retail SDK-exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/sdk-github.md) |
| **Produktområden som påverkas**         | Retail SDK |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från och med version 10.0.21 kommer de SDK som levereras via LCS-VM:ar att tas bort i oktober 2023. |

### <a name="retail-deployable-package-and-combined-pos-hardware-station-and-cloud-scale-unit-installers"></a>Paket som kan distribueras i butik och kombinerade installationsprogram för kassa, maskinvarustation och molnbaserad skalningsenhet

Paket som kan distribueras i Butik och som genereras med hjälp av Retail SDK MSBuild avskrivs i 10.0.21. Hädanefter använder du paketet CSU-paketet (Cloud Scale Unit, molnbaserad sakalningsenhet) för tillägg för molnbaserad skalningsenhet (Commerce Runtime, kanaldatabas, API:er för fjärrbaserad handel, betalningar och molnbaserad kassa (POS)). Använd rena tilläggsinstallationsprogram för kassa, maskinvarustation och självbetjäningsenhet för molnbaserad skalningsenhet.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Ett paket som kan distribueras inom Butik är ett kombinerat paket som innehåller en komplett uppsättning tilläggspaket och -installationsprogram. Detta kombinerade paket gör distributionen komplex när CSU-tillägg går till skalningsenhet för moln och installationsprogram distribueras i butiker. Installationsprogrammen omfattar tillägget och basprodukten, vilket försvårar uppdateringar. Vid varje uppgradering krävs en kodsammanslagning och en paketgenerering. För att förenkla denna process är tilläggspaketen nu uppdelade i komponenter för enkel distribution och hantering. Med denna nya metod separeras tillägg och installationsprogram för basprodukt och kan då uppgraderas utan kodsammanslagning eller generering av nytt paket.|
| **Ersatt av en annan funktion?**   | CSU-tillägg, installationsprogram för kassatillägg, installationsprogram för maskinvarustationstillägg |
| **Produktområden som påverkas**         | Dynamics 365 Commerce-tillägg och distribution |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuellt: Från och med version 10.0.21 kommer stöd för distribution av RetailDereleaseyablePackage i LCS att tas bort i oktober 2022. |

Mer information finns i:

+ [Generera ett separat paket för molnbaserad skalningsenhet för Commerce (CSU)](../dev-itpro/retail-sdk/retail-sdk-packaging.md#generate-a-separate-package-for-commerce-cloud-scale-unit-csu)
+ [Skapa ett Modern POS-tilläggspaket](../dev-itpro/pos-extension/mpos-extension-packaging.md)
+ [Integrera kassan med ny maskinvaruenhet](../dev-itpro/hardware-device-extension.md)
+ Kodexempel
    + [Molnskalningsenhet](https://github.com/microsoft/Dynamics365Commerce.ScaleUnit)
    + [Kassa, CSU och maskinvarustation](https://github.com/microsoft/Dynamics365Commerce.InStore)

### <a name="modernpossln-and-cloudpossln-in-the-retail-sdk"></a>ModernPos.Sln och CloudPos.sln i Retail SDK

Kassatilläggsutveckling med hjälp av ModernPos.sln, CloudPos.sln, POS.Extension.csproj och kassamappen blir inaktuella i version 10.0.21. I framtiden använder du kassaoberoende förpacknings-SDK för kassatillägg.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | I tidigare versioner av SDK för Retail måste kod sammanfogas och packas om för att uppdatera till den senaste kassaversionen (om kassatillägg finns). Kodsammanslagningen var en tidskrävande uppgraderingsprocess och man var tvungen att underhålla hela SDK för Retail i databasen. Man var också tvungen att kompilera kärnprojektet för POS.App. Genom att använda den oberoende förpackningsmodellen behöver du bara bibehålle ditt tillägg. Processen för uppdatering till den senaste versionen av kassatillägg är lika enkel som att uppdatera versionen av det NuGet-paket som ditt projekt använder. Tillägg kan distribueras oberoende, och tjänsterna använder installationsprogrammet för tillägg. Baskassan kan distribueras och hanteras separat, och ingen kodsammanslagning eller ompackning med basinstallationsprogram eller kod krävs. |
| **Ersatt av en annan funktion?**   | [SDK för kassaoberoende packning](../dev-itpro/pos-extension/pos-extension-getting-started.md) |
| **Produktområden som påverkas**         | Kassatillägg och distribution för Dynamics 365 Commerce |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuellt: Från och med release 10.0.21 kommer stöd för kombinerade kassapaket och tilläggsmodeller som använder ModernPos.Sln, CloudPOs.sln och POS. Extenseb.csproj i Retail SDK att tas bort i oktober 2023. |

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.17

### <a name="full-dataset-generation-interval-is-deprecated"></a>Fullständigt genereringsintervall för datauppsättning blir inaktuellt

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | I formuläret **Parametrar för handelsschema** i Dynamics 365-administationen kommer från och med denna version fältet **Intervall för komplett datauppsättningsgenerering** att bli inaktuellt. Från och med denna version tas fältet även bort visuellt så att värdet inte kan redigeras. Detta förblir värdet **0**. |
| **Ersatt av en annan funktion?**   | Nej |
| **Produktområden som påverkas**         | Dynamics 365 Commerce |
| **Distribueringsalternativ**              | Allt|
| **Status**                         | Inaktuell. Använd inte detta fält, och ändra heller inte värdet i det.|

## <a name="features-removed-or-deprecated-in-the-commerce-10015-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11-stöd för Dynamics 365 är inaktuellt

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Från och med december 2020 kommer Microsoft Internet Explorer 11-stöd för samtliga Dynamics 365-produkter att betraktas som inaktuellt, och Internet Explorer 11 kommer inte att stödjas efter augusti 2021.<br><br>Detta påverkar kunder som använder Dynamics 365-produkter som har utformats för användning med ett Internet Explorer 11-gränssnitt. Efter augusti 2021 stöds inte Internet Explorer 11 för sådana Dynamics 365-produkter. |
| **Ersatt av en annan funktion?**   | Vi rekommenderar våra kunder att övergå till Microsoft Edge.|
| **Produktområden som påverkas**         | Alla Dynamics 365-produkter |
| **Distribueringsalternativ**              | Alla|
| **Status**                         | Inaktuell. Internet Explorer 11 kommer inte att stödjas efter augusti 2021.|

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.11
### <a name="data-action-hooks"></a>Dataåtgärdshookar
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen dataåtgärdshookar har föråldrats på grund av prestandaproblem. |
| **Ersatt av en annan funktion?**   | Vi rekommenderar att du använder [dataåtgärdsåsidosättningar](../e-commerce-extensibility/data-action-overrides.md) för att ändra affärslogiken i dataåtgärdsskiktet.|
| **Produktområden som påverkas**         | Dataåtgärder för utbyggbarhet för näthandel |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Stöd för SDK för Retail för Visual Studio 2015, msbuild 14.0 och Retail SDK\Referensbibliotek och verktyg
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stöd för Retail SDK för Visual Studio 2015 har föråldrats och uppdaterats till att stödja VS 2017, msbuild 15.0 och alla referensbibliotek och verktyg för Commerce och proxy-generator i mappen RetailSDK\References har flyttat till NuGet-paket för att förenkla tilläggsmodellen och SDK-uppgraderingsprocessen.|
| **Ersatt av en annan funktion?**   | Vi rekommenderar att du följer informationen i [Flytta SDK för Retail från Visual Studio 2015 till Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) för att uppdatera systemet. |
| **Produktområden som påverkas**         | SDK-tillägg för Retail |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Tillägg i Retail Server med IEdmModelExtender och CommerceController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Tillägg Retail Server med IEdmModelExtender och CommerceController har ersatts för att ge förenklad tilläggsmodell. Den nya implementeringen har bara styrenhetsklassen utan ytterligare IEdmModelExtender klassimplementering. Detta eliminerar också beroendet med en särskild OData-version (om OData-versionen uppdateras kan det innebära att tillägg avbryts.) |
| **Ersatt av en annan funktion?**   |  Vi rekommenderar att du använder klasstilläggsmodellen IController genom att importera NuGet-paketet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Produktområden som påverkas**         | Tillägg för Retail Server |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Tillägget Hardware station med IHardwareStationController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Tillägget Hardware station med IHardwareStationController har ersatts för att ge förenklad tilläggsmodell. Den nya implementeringen har bara IController-klassen utan någon ytterligare klassimplementering och för att undvika beroendet av kärnbibliotek för Hardware station, måste du använda tidigare tillägg för att referera flera bibliotek.) |
| **Ersatt av en annan funktion?**   | Vi rekommenderar att du använder klasstilläggsmodellen IController genom att importera NuGet-paketet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Produktområden som påverkas**         | Tillägg för Hardware Station |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Kassaåtgärd 803 – Plockning och mottagning
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Plocknings- och mottagningsåtgärder föråldras på grund av att ny åtgärd har omdesignats. |
| **Ersatt av en annan funktion?**   | Ja. Den ersätts av två nya kassaåtgärder: inkommande åtgärd (804) och utgående åtgärd (805).|
| **Produktområden som påverkas**         | Program för kassa (POS) |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.10 kommer åtgärden för plockning och mottagning inte längre att erhålla funktionsuppdateringar. Endast viktiga felkorrigeringar kommer att utföras för den här åtgärden i framtida versioner. Alla kunder uppmuntras att flytta till de nya [Inkommande åtgärderna](../pos-inbound-inventory-operation.md) och [Utgående åtgärderna](../pos-outbound-inventory-operation.md) som fortsätter ingå i vår långsiktiga produktplan. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>Commerce GetProductAvailabilities och GetAvailableInventoryNearby API:er
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Nya optimerade API:er har skapats för att ersätta GetProductAvailabilities och GetAvailableInventoryNearby API:er. |
| **Ersatt av en annan funktion?**   | Ja: Det ersätts med GetEstimatedAvailability och GetEstimatedProductWarehouseAvailability API:er. |
| **Produktområden som påverkas**         | näthandelsprogram SDK |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.7 kommer du inte längre att kunna göra tekniska investeringar för GetProductAvailabilities och GetAvailableInventoryNearby. Organisationer som använder dessa API:er i sina näthandelsdistributioner bör konvertera till nya GetEstimatedAvailability och GetEstimatedProductWarehouseAvailability API:er och aktivera [optimerade beräkningsfunktionen för produkttillgänglighet](../calculated-inventory-retail-channels.md).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Tidigare meddelanden om borttagna eller inaktuella funktioner
Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

