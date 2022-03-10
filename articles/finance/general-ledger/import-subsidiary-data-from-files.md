---
title: Importera data för dotterbolag från filer
description: I detta ämne beskrivs hur du förbereder data från externa system så att de kan importeras till Microsoft Dynamics 365 Finance.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 4be1e748724331c4e2089da8a08a9ac7e5cf88a2ac6d3d89b37b9fcd4480f516
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727310"
---
# <a name="import-subsidiary-data-from-files"></a>Importera data för dotterbolag från filer

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du förbereder data från externa system så att de kan importeras till Microsoft Dynamics 365 Finance. På sidan **Konsolidera med import** (**Konsolideringar \> Konsolidera med import**) kan du förbereda överföring av dotterbolagsdata från externa system.

1. Skapa en dotterbolag (juridisk person) för konsolideringen. Mer information om hur du skapar juridiska personer finns i [Skapa en juridisk person](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Mer information finns i [Förbered en juridisk person för användning i konsolideringsprocessen](prepare-company-for-consolidation.md) och [Skapa en juridisk person för dotterbolag för konsolidering](set-up-subsidiary-company-for-consolidation.md).

2. Förbered en fil som ska innehålla de data som importeras. Mer information om importprocessen finns i [Översikt över dataimport- och exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
3. Exportera datan till en fil genom att följa stegen i proceduren "Dataimport/exportprocess" i [Översikten över dataimport- och -exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md). Du kan använda den här proceduren när du konsoliderar data från antingen en annan Dynamics 365 Finance-instans eller från Dynamics 365 Business Central. Om du importerar data från externa system måste datan vara i det format som beskrivs i [Exportera data för dotterbolag till filer](export-subsidiary-data-to-file.md).
4. Gå till **Konsolideringar \> Konsolidera med import**. På sidan **Konsolidera med import**, på fliken **Kriterier**, anger du detaljer kring rapporten och/eller importen genom att ställa in följande fält.

    | Fält                                 | Värde för rapporten | Värde för importen |
    |---------------------------------------|----------------------|----------------------|
    | beskrivning                           | Inte aktuellt | Ange en beskrivning som identifierar importen. |
    | Huvudkonto                          | Definiera det kontointervall som rapporten ska innehålla. Om du inte definierar något intervall inkluderas alla konton. | Definiera det kontointervall som importen ska innehålla. Om du inte definierar något intervall inkluderas alla konton. |
    | Konsolideringsperiod                  | Definiera datumintervallet som ska konsolideras. | Definiera datumintervallet som ska konsolideras. |
    | Inkludera faktiska belopp                | Ange alternativet som **Ja** om du vill inkludera faktiska värden. | Ange alternativet som **Ja** om du vill inkludera faktiska värden. |
    | Inkludera budgetbelopp                | Ange alternativet som **Ja** om du vill inkludera budgetbelopp i konsolideringar. | Ange alternativet som **Ja** om du vill inkludera budgetbelopp i konsolideringar. |
    | Återskapa saldon under konsolideringen | Ange alternativet som **Ja** om återskapandeprocessen helt ska rensa saldo och nya poster samt återskapa saldot från grunden. | Ange alternativet som **Ja** om återskapandeprocessen helt ska rensa saldo och nya poster samt återskapa saldot från grunden. |
    | Budgetmodeller                         | Inte aktuellt | Om du har valt att importera budgetbelopp anger du de budgetmodeller som ska konsolideras. |
    | Budgetkurstyp                      | Inte aktuellt | Ange typen av valutakurs för budget. |

6. Om du har olika redovisningsvalutor använder du fälten på fliken **Valutakonvertering** för att konfigurera den konvertering som görs under konsolideringen.

    | Fält                      | beskrivning |
    |----------------------------|-------------|
    | Juridisk person, källa        | Välj den juridiska person som du importerar från. |
    | Källredovisningsvaluta | Standardvalutan är valutan som associeras med den juridiska person som du valde i fältet **Källa för juridisk person**. |
    | Från- och Till-konton       | Definiera intervallet med konton som ska importeras från den juridiska personen som är källan. |
    | Valutakurstyp         | Välj typen av valutakurs. Valutakurstyper tilldelas när du skapar ett huvudkonto. Mer information finns i [Skapa ett huvudkonto](tasks/create-main-account.md). |
    | Använd valutakurs från   | Ange ett datum för att använda valutakursen som gällde på det datumet. Alternativt kan du ange det värde som ska användas som valutakurs. |
    | Valutakurs              | Standardvärdet beror på typen av valutakurs som valdes i fältet **Valutakurstyp**. Om du har angett en användardefinierad valutakurs kan du definiera en kurs. |

7. Ange alternativet **Kör i bakgrund** som **Ja** om du vill låta importprocessen köras i bakgrunden.
8. Ange alternativet **Batchbearbetning** som **Ja** om du vill köra konsolideringen som ett batchjobb vid en viss tidpunkt. Om du vill köra konsolideringen direkt väljer du **OK**. 

De transaktioner och saldon som angetts för konsolideringen i dotterbolagen läggs till i de relevanta kontona i konsoliderad juridisk person.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]