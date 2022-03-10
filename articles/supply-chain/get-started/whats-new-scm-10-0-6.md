---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management (10.0.6 november 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Supply Chain Management 10.0.6.
author: kamaybac
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 87bcda25b89135e052a5a883b816ea0bb430479a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568913"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management (10.0.6 november 2019)

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.6. Den här versionen har ett versionsnummer på 10.0.234. Även om det allmänna tillgänglighetsdatumet är i november, är de nya funktionerna tillgängliga för tidig lansering i oktober. Mer information om version 10.0.6, se [Ytterligare resurser](whats-new-scm-10-0-6.md#additional-resources).

## <a name="product-configuration-models-v2-data-entity"></a>Produktkonfigurationsmodeller V2 datatabell

En andra version för datatabellen "produktkonfigurationsmodeller" har frisläppts (kallas "produkterkonfigurationsmodeller V2"). Standard mallen "418-produktkonfigurationsmodeller" måste också vara så att den nya enheten "produktkonfigurationsmodeller V2" används i mallarna importera/exportera. Mallen uppdateras inte automatiskt så att du måste läsa in mallen från standardvärdet manuellt. V2-enheten exporterar en rad som separat fil i en bifogad fil i stället för på infogad och löser storleksbegränsningarna för V1-enheten. 
 
Vad behöver du göra för att göra ändringen?
-    Eftersom V1-enheten är föråldrad ska du börja migrera från V1 till V2. Om du använder mallen "418-produktkonfigurationsmodeller" kan du klicka på knappen "Läs in standardmallar" och läsa in mallen på nytt "418 – produktkonfigurationsmodeller"
-    Om du behöver behålla kompatibiliteten med befintliga system kan du nu fortsätta att använda den befintliga mallen och den (inaktuella) V1-enheten tills du flyttar integrationerna till den nya mallen. 

## <a name="feature-management-enhancements"></a>Förbättringar över funktionshantering
Med funktionshantering kan du nu aktivera alla nya funktioner som standard, kräva bekräftelse för att aktivera en funktion och aktivera alla funktioner som inte redan har aktiverats. 


## <a name="purchase-agreement-responsible-party"></a>Ansvarig part för inköpsavtal
Nu kan du definiera primära och sekundära ansvariga parter i formuläret klassificering av inköpsavtal och resulterande inköpsavtal.  Detta ger användaren åtkomst till vem som ser över avtalen.

## <a name="rfq-link-on-the-purchase-order-line"></a>Länk för anbudsförfrågan för inköpsorderrad
Du kan lägga tillbaka en referens länk från inköpsorderraderna till motsvarande rader för anbudsförfrågningar som de kom från, vilket gör att användaren enkelt kan tillhandahålla det stödjande anbudsförfrågningsdokumentet.

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="bug-fixes"></a>Felkorrigeringar
Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.6 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).

### <a name="platform-update-30"></a>Plattform update 30
Microsoft Dynamics 365 Supply Chain Management 10.0.6 ingår plattformsuppdatering 30. Mer information om plattformsuppdatering 30 finns i [Nyheter och ändringar i plattformsuppdatering 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Dynamics 365: 2019 utgivningsvåg 2 plan
Har du frågeställningar om nya och kommande funktioner i våra affärsappar eller plattformen?

Se [Dynamics 365: 2019 utgivningsvåg 2 plan](/dynamics365-release-plan/2019wave2/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

De [borttagna eller föråldrade funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) i ämnet beskriver funktioner som har schemalagts eller är planerade att tas bort eller inaktuellt för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten visas understrykningsmeddelandet i ämnet [borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före avhämtningen.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]