---
title: Rensning av ER-migrering
description: I den här artikeln beskrivs hur du kan använda funktionen för rensning av ER-migrering för att lösa problem med ER-mallar.
author: kfend
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
ms.openlocfilehash: bf32981ed5f43647038018bf2cd98e55ce233b3f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285104"
---
# <a name="er-migration-cleanup"></a>Rensning av ER-migrering 

[!include[banner](../includes/banner.md)]

När du hanterar dina ekonomiinstanser kanske du bestämmer dig för att flytta din aktuella instans till en annan plats. Du kan till exempel migrera produktionsinstansen till en ny miljö för begränsat läge. Om du konfigurerade ER-ramverket för att lagra mallar i Microsoft Azure blob-lagring, refererar **DocuValue**-registret i den nya miljön för begränsat läge till instansen av blob-lagring i produktionsmiljön. Den här instansen kan dock inte nås från miljön för begränsat läge, eftersom migreringsprocessen inte stöder migrering av artefakter i blob-lagring. I stället förväntas att du i den nya miljön för begränsat läge refererar till blob-lagringsplatsen i miljön för begränsat läge som ännu inte har tillgång till ER-mallar.

Om du försöker köra ett ER-format som använder en mall för att generera affärsdokument, uppstår ett undantag och du meddelas om den saknade mallen. Du kan också använda alternativet för rensning av ER-migrering för att radera och sedan åter importera konfigurationen för ER-format som innehåller mallen.

[![Köra ett ER-format.](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)

Du får ett liknande felmeddelande om du navigerar till sidan **Konfigurationer** (**Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**) och i konfigurationsträdet försöker radera en ER-formatskonfiguration som använder en mall.

[![Radera ett ER-format.](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)

Gör på följande sätt för att lösa problem med ER-mallar som du inte kan komma åt.

1.  Gå till sidan **Organisationsadminitration** \> **Periodisk** \> **Rensning av migrering**.
2.  Välj en ER-formatskonfiguration som inte går att köra eller ta bort.
3.  Välj **Ta bort**.
4.  Bekräfta radering av den valda ER-formatkonfigurationen.
5.  [Importera](download-electronic-reporting-configuration-lcs.md) den raderade ER-formatkonfigurationen till den aktuella ekonomiinstansen.

## <a name="applicability"></a>Tillämplighet

> [Viktigt] Alternativet **Rensning av migrering** är endast avsett för ER-formatkonfigurationer som innehåller icke-tillgängliga ER-mallar. När du tar bort en ER-formatkonfiguration med alternativet **Rensning av migrering**, raderar ER de mallar som är relaterade till konfigurationsartefakterna i den enda programdatabasen. Det går inte att verifiera att lämpliga fysiska filer finns i blob-lagring. I stället förutsätts det att det inte finns några. Därför bör du inte använda alternativet **Rensning av migrering** i stället för alternativet för radering av ER-konfiguration på sidan **Konfigurationer**. Använd alternativet **Rensning av migrering** enbart när alternativet för radering av ER-konfiguration på sidan **Konfigurationer** inte fungerar.
>
> Om du raderar en ER-formatkonfiguration med alternativet **Rensning av migrering** när den refererade mallen finns i blob-lagring så raderar du enbart konfigurationsartefakterna i programdatabasen. Den fysiska filen för mallen i blob-lagringen finns kvar. Filöverskrivning i blob-lagring är inte längre tillåten. Mer information finns i [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217). Dessutom kan du inte längre återimportera konfigurationerna som raderats med hjälp av rensning av migrering i den här miljön. För att lösa det här problemet måste du hitta motsvarande fil i blob-lagring och manuellt radera den.

[![Importera ett ER-format.](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)

Ett liknande problem kan uppstå om du migrerar programinstansen till en annan plats som har använts som migreringsmål mer än en gång och för vilken blob-lagring redan innehåller ER-mallfiler.

Eftersom du kan ha flera ER-formatkonfigurationer, kan den här processen ta lång tid. Därför rekommenderas du att använda funktionen [Säkerhetslagring av ER-mallar](er-backup-storage-templates.md) för att automatiskt återställa mallar med brutna referenser.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
