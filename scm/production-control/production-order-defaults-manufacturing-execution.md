---
title: "Standarder för produktionsorder inom tillverkningskörning"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70073
ms.assetid: 620944ae-3e20-444a-807e-65495f160904
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: b310e799c1ef0756291c5f7ab886531e4caf1945
ms.lasthandoff: 03/31/2017


---

# <a name="production-order-defaults-in-manufacturing-execution"></a>Standarder för produktionsorder inom tillverkningskörning

[!include[banner](../includes/banner.md)]




Överväg noga alla inställningar på sidan **Standarder för produktionsorder** innan arbetare börjar göra registreringar på produktionsjobb. Om ditt företag använder multisitefunktionen, kanske du vill ställa in olika standarder för produktionsorder för varje plats. Orderstandard för integration med produktionsstyrning ställs in på följande flikar på sidan **Standarder för produktionsorder**:

-   **Allmänt** - Allmän orderstandard för produktionsjobb i tillverkningskörning.
-   **Start** – Orderstandard som används när produktionsjobb eller operationer startar.
-   **Operationer** – Orderstandard som används för produktionsjobb eller operationer och återrapportering för operationer under produktionsprocessen.
-   **Rapportera som färdigt** – Orderstandarder som används när artiklar rapporteras som färdiga i den sista operationen på produktionsordern.
-   **Kvantitetvalidering** – Orderstandarder för att validera start- och återrapporterade kvantiteter på produktionsorder.

## <a name="types-of-production-jobs"></a>Typer av produktionsjobb
På fliken **Operationer** väljer du de typer av produktionsjobb som måste registreras på sidan **Jobbregistrering**. Vanligtvis gör anställda registreringar på inställningsjobb och processjobb. Om finplanering används kan du välja andra jobbtyper till exempel transportjobb, arbetare som måste också göra registreringar på när en produktionsorder bearbetas. **Viktigt:** Se till att alla relevanta jobbtyper väljs. Annars kan inte jobb registreras på sidan **Jobbregistrering**. Justera dina val med de val som du gör på kolumnen **Jobbhantering** på sidan **Flödesgrupper**. Om **Jobbhantering** markeras i flödesgruppen, kommer jobbtypen att rapporteras som färdig på produktionsordern. Denna rapportering sker, när jobbet rapporteras som färdigt i tillverkningskörning. När alla jobbtyper som **Jobbhantering** väljs för har rapporterats som färdiga i en operation, kommer Tillverkningskörning också att rapportera operationen som färdig. **Obs!** Vissa jobbtyper kan rapporteras manuellt via produktionsjournaler. I det här fallet väljer du **Jobbhantering** för jobbtypen men väljer inte jobbtypen för registrering på fliken **Operationer** på sidan **Standarder för produktionsorder**.

## <a name="bom-consumption-and-picking-list-journals"></a>Strukturlisteförbrukning och flödeskortjournaler
Material kan ställas in så att de förbrukas automatiskt eller fylls i manuellt under produktionen. Automatisk förbrukning kontrolleras av avräkningsprincipen stämmer överens med inställningarna av strukturlisteraderna (BOM) och genom inställningen av fältet **Automatisk strukturlisteförbrukning** i standarder för produktionsorder. Automatiskt förbrukning kan ställas in så att den infaller när en produktionsorder startas eller rapporteras som färdig. Alternativt kan den ske på jobbnivå när ett jobb har påbörjats eller avslutats.

### <a name="controlling-material-consumption-when-a-production-order-is-started"></a>Kontrollera materialförbrukning när en produktionsorder startas

Materialförbrukning under starten för en produktionsorder kontrolleras av fältet **Automatisk strukturlisteförbrukning** på fliken **Start**. Följande värden finns:

-   **Avräkningsprincip** – När en produktionsorder startas, kommer kvantiteter av material att förbrukas enligt avräkningsprincipen som anges på produktionsstrukturlisteraderna. Endast materialrader där avräkningsprincipen är inställd på **Start** förbrukas under produktionstarten.
-   **Alltid** – Kvantiteter av materia som är proportionell mot den startade kvantiteten, ska alltid förbrukas.
-   **Aldrig** – Kvantiteter av material ska aldrig förbrukas.

### <a name="controlling-material-consumption-when-a-production-job-is-started-or-completed"></a>Kontrollera materialförbrukning när ett produktionsjobb startas eller avslutas

Materialförbrukning under start eller avslutning av ett produktionsjobb kontrolleras av fältet **Automatisk strukturlisteförbrukning** på fliken **Operationer**. Följande värden finns:

-   **Avräkningsprincip** – När en kvantitet på ett produktionsjobb startas eller avslutas kommer kvantiteter av material att förbrukas enligt avräkningsprincipen som anges på produktionsstrukturlisteraderna. Endast materialrader där avräkningsprincipen är inställd på **Start** eller **Avsluta** kommer att konsumeras.
-   **Alltid** – Kvantiteter av materia som är proportionell mot den startade kvantiteten på jobbet, ska alltid förbrukas.
-   **Aldrig** – Kvantiteter av material ska aldrig förbrukas.

### <a name="controlling-material-consumption-when-a-production-order-is-reported-as-finished"></a>Kontrollera materialförbrukning när en produktionsorder rapporteras so avslutad

Materialförbrukning under processen Rapportera som färdigt för en produktionsorder kontrolleras av fältet **Automatisk strukturlisteförbrukning** på **Rapportera som färdigt**. Följande värden finns:

-   **Avräkningsprincip** – När en produktionsorder rapporteras som avslutad, kommer kvantiteter av material att förbrukas enligt avräkningsprincipen som anges på produktionsstrukturlisteraderna. Endast materialrader där avräkningsprincipen är inställd på **Avsluta** kommer att konsumeras.
-   **Alltid** – Kvantiteter av materia som är proportionell mot den kvantiteten som rapporteras som avslutad ska alltid förbrukas.
-   **Aldrig** – Kvantiteter av material ska aldrig förbrukas.





