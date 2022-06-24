---
title: Prova skalenheter i en distribuerad hybridtopologi
description: Denna artikel ger information om hur du testar moln- och kantskalningsenheter med arbetsbelastning för tillverkning och distributionslagerstyrning.
author: perlynne
ms.date: 05/02/2022
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-03-03
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 5645955109e7a942e617b3b90a27065c2a8fe4a3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893596"
---
# <a name="try-out-scale-units-in-a-distributed-hybrid-topology"></a>Prova skalenheter i en distribuerad hybridtopologi

[!include [banner](../includes/banner.md)]

Testprocessen för distribuerad hybridtopologi är enkel. Under den första fasen bör du validera anpassningar i syfte att säkerställa att dessa fungerar i den distribuerade topologin. Det finns två alternativ.

## <a name="option-1-evaluate-customizations-in-development-environments"></a>Alternativ 1: Utvärdera anpassningar i utvecklingsmiljöer

Innan du börjar registrera din sandboxmiljö rekommenderar vi att du utforskar skalningsenheter i en utvecklingskonfiguration, till exempel en enrutesmiljö (kallas även för en "tier-1"-miljö) så att du kan validera processer, anpassningar och lösningar. Under den här fasen används data och anpassningar i enrutesmiljöerna. Du kan köra i en enda miljö, som kan anta både rollen som företagshubb och rollen som skalningsenhet. Alternativt kan du ha två utvecklingsmiljöer, varav en har rollen som hubb och den andra rollen som skalningsenhet. Denna konfiguration är det bästa sättet att identifiera och åtgärda problem. Den senaste [förhandsversionsbygget](../../fin-ops-core/fin-ops/get-started/one-version.md#how-can-i-get-early-access-to-non-released-platform-updates) kan också användas för att slutföra den här fasen.

Du bör använda [distributionsverktygen för skalningsenhet för enskilda utvecklingsmiljöer](https://github.com/microsoft/SCMScaleUnitDevTools) för att installera och bibehålla miljöerna. Med dessa verktyg kan du konfigurera nav- och skalningsenheter i en eller två separata enskilda miljöer. Verktygen tillhandahålles både som en binär version och i källkod på GitHub. Läs projektets wiki, som innehåller en [användarhandbok steg för steg](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) som beskriver hur verktygen används. Om du distribuerar [kantskalningsenheter på anpassad maskinvara genom att använda lokala affärsdata (LBD)](cloud-edge-edge-scale-units-lbd.md) måste du följa en annan process.

## <a name="option-2-acquire-add-ins-and-deploy-in-your-sandbox-environments"></a>Alternativ 2: Skaffa tilläggsprogram och distribuera i dina sandbox-miljöer

Om du vill prova den distribuerade topologin måste du ha två sandbox-miljöer (nivå 2), av vilka en har dina data (enterprise-nav) och den andra finns för vågenheten och har "tomma data".

Du måste skaffa tillägg för minst en molnbaserad enhet eller kantskalningsenhet. Motsvarande projekt och miljö kommer sedan att beviljas [Microsoft Dynamics Lifecycle Services (LCS),](https://lcs.dynamics.com/) så att vågenhetens miljöer kan distribueras med hjälp av [Scale Unit Manager-portalen](https://aka.ms/SCMSUM).

Kontakta Microsoft Support om du vill begära att sandbox-miljöerna ska aktiveras.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
