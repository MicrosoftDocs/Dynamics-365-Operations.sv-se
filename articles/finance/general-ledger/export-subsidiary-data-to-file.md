---
title: Exportera data för dotterbolag till filer
description: I detta ämne beskrivs hur du förbereder export av data från Microsoft Dynamics 365 Finance och sedan importerar den till en konsoliderad juridisk person.
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
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 02ae9945f7b67fb64be78a024910d7e1151c7446fd54b71034c5ba448c00b081
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768781"
---
# <a name="export-subsidiary-data-to-files"></a>Exportera data för dotterbolag till filer

[!include [banner](../includes/banner.md)]

Använd sidan **Export** (**Systemadministration \> Arbetsytor \> Import/Export**) för att förbereda export av data för dotterbolagen till filer som sedan kan importeras till en konsoliderad juridisk person. Mer information om processerna för import och export finns i [Översikt över dataimport- och exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

1. Skapa en juridisk person för konsolideringsprocessen. Mer information om hur du skapar juridiska personer finns i [Skapa en juridisk person](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Mer information finns i [Förbered en juridisk person för användning i konsolideringsprocessen](prepare-company-for-consolidation.md) och [Skapa en juridisk person för dotterbolag för konsolidering](set-up-subsidiary-company-for-consolidation.md). 

2. Gå till **Konsolideringar \> Exportera företagssaldon**. På sidan **Exportera företagssaldon**, på fliken **Kriterier**, anger du detaljer kring konsolideringen genom att ställa in följande fält.

    | Fält                             | beskrivning |
    |-----------------------------------|-------|
    | Huvudkonto                      | Ange kontona som ska konsolideras. Lämna det här fältet tomt om du vill inkludera alla konton. |
    | Använd konsolideringskonto         | Om du har angett konsolideringskonton ställer du in det här alternativet på **Ja**. |
    | Välj konsolideringskonto från | Välj antingen **Huvudkonto** eller **Konsolideringskontogrupp**. |
    | Konsolideringskontogrupp       | Välj en konsolideringskontogrupp för det konsolideringskonto som du har valt. |
    | Konsolideringsperiod              | Ange "från och till"-datum för konsolideringen. |
    | Inkludera faktiska belopp            | Ange alternativet som **Ja** om du vill inkludera faktiska belopp. |
    | Inkludera budgetbelopp            | Ange alternativet som **Ja** om du vill inkludera budgetbelopp i konsolideringar. |
    | Budgetmodeller                     | Ange den budgetmodell som ska inkluderas. |

3. På fliken **Ekonomiska dimensioner** anger du detaljer för konsolideringen:

    - Anger du den information för ekonomisk dimension som ska föras över från transaktioner i dotterbolaget till transaktioner i konsoliderad juridisk person.
    - Välj ekonomiska dimensioner i listan .
    - Identifiera de korrekta specifikationerna för varje ekonomisk dimension som konsolideras. De tillgängliga alternativen inkluderar **Dimension**, **Gruppdimension**, **Företagskonton** och **Konto**.

        > [!NOTE]
        > Med alternativet **Gruppdimension** kan du definiera dimensionsvärdet som används i den grupp med företag som konsolideras.

    - Ange den segmentordning som du vill konsolidera i.

4. Gå till fliken **Juridiska personer** och följ sedan dessa steg för att ange den juridiska person du exporterar:

    1. Välj **Ny**.
    2. I fältet **Källa för juridisk person** anger du den juridiska personen.

        Om samma kriterier gäller för flera dotterbolag som finns i databasen, kan du föra över data från dessa dotterbolag till separata exportfiler i en och samma åtgärd:

        1. Skapa en rad för respektive juridisk person vars konton ska exporteras till filer. Dessa filer kommer senare att importeras till konsoliderad juridisk person.
        2. För varje dotterbolag anger du dess namn och namnet på den exportfil som kommer att skapas under exportjobbet.

    3. I fältet **Kontotyp för konverteringsdifferenser** väljer du **Vinst och förlust** eller **Balansräkning**.
    4. Ange ett filnamn för exportfilen som ska skapas.

5. Klicka på **OK** om du vill köra exporten.

När exporten är slutförd får du ett meddelande som visar antalet poster som sparats i respektive fil. Du kan sedan importera filerna till den konsoliderade juridiska personen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]