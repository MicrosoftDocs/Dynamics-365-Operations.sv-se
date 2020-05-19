---
title: Säkerhetslagring av ER-mallar
description: Det här avsnittet innehåller information om hur du använder säkerhetslagring för elektroniska rapporter (ER) för återställning av mallar.
author: NickSelin
manager: AnnBe
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-13
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2e399290153c2c63ac1c02f0f9cdb956ff5031e5
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321676"
---
# <a name="backup-storage-of-er-templates"></a>Säkerhetslagring av ER-mallar

[!include [banner](../includes/banner.md)]

[Elektronisk rapportering (ER) - översikt](general-electronic-reporting.md) gör att affärsanvändare kan konfigurera format för utgående dokument i enlighet med lagkraven för olika länder/regioner. Konfigurerade ER-format kan använda fördefinierade mallar för att skapa utgående dokument i olika format, t.ex. Microsoft Excel arbetsböcker, Microsoft Word dokument eller PDF-dokument. Mallarna fylls i med data som det konfigurerade dataflöde för genererade dokument kräver.

Varje konfigurerat format kan publiceras som en del av en ER-lösning. Alla ER-lösningar kan exporteras från en instans av Finance and Operations och importeras till annan instans.

ER-ramverket använder [Konfigurera dokumenthantering](../../fin-ops/organization-administration/configure-document-management.md) för att behålla de mallar som krävs för den aktuella Finance and Operations-instansen. Beroende på inställningarna för ER-ramverk kan du välja Microsoft Azure blob-lagring eller en Microsoft SharePoint-mapp som den fysiska primära lagringsplatsen för mallar. (Mer information finns i [konfigurera om ER-ramverket (Elektronisk rapportering)](electronic-reporting-er-configure-parameters.md).) DocuValue-registret innehåller en enskild post för varje mall. I varje post lagrar fältet **AccessInformation** sökvägen till mallfilen som finns på den konfigurerade lagringsplatsen.

När du hanterar dina Finance and Operations-instanser kanske du bestämmer dig för att flytta aktuell instans till en annan plats. Du kan till exempel migrera produktionsinstansen till en ny miljö för begränsat läge. Om du konfigurerade ER-ramverket för att lagra mallar i blob-lagring, refererar DocuValue-registret i den nya miljön för begränsat läge till instansen av blob-lagring i produktionsmiljön. Den här instansen kan dock inte nås från miljön för begränsat läge eftersom migreringsprocessen inte stöder migrering av artefakter i blob-lagring. Om du försöker köra ett ER-format som använder en mall för att generera affärsdokument, uppstår ett undantag och du meddelas om den saknade mallen. Du kan också använda återställningsverktyget för att ta bort och sedan åter importera konfigurationen för ER-format som innehåller mallen. Eftersom det kan finnas flera ER-format-konfigurationer, kan den här processen ta lång tid.

Lagrings utrymmet för funktionen ER-mallar i säkerhetskopian kan hjälpa dig att göra mallarna så att de alltid är tillgängliga för generering av affärsdokument.

> [!NOTE]
> Den här funktionen kan bara användas när ett blob-lagringsutrymme har valts som lagringsplats för ER-mallar.

## <a name="automated-recovery-and-notification"></a>Automatisk återställning och meddelanden

För den här funktionen sparas alla mallar i en ny ER-formatkonfiguration i den aktuella miljön automatiskt på säkerhetskopieringsplatsen för mallar (ERDocuDatabaseStorage databasregister) när följande händelser inträffar:

- Du importerar en ny konfiguration för ER-format som innehåller en mall.
- Du fyller i utkastversionen av en ER-formatskonfiguration som innehåller en mall.

Säkerhetskopior av mallar flyttas till en ny instans av Finance and Operations som en del av programdatabasen.

Om en mall i ett ER-format krävs för att generera utgående dokument, ska du bearbeta leverantörsbetalningar inklusive genereringen av betalningsavi och kontrollrapporter, till exempel att den obligatoriska mallen inte finns på den primära lagringsplatsen, följande händelser inträffar:

- Om mallen är tillgänglig på lagringsplatsen för säkerhetskopiorna tas den automatiskt från lagringsplatsen för säkerhetskopian, återställs till den primära lagringsplatsen och används för den aktuella körningen.
- Alla användare som tilldelats rollen **Utvecklare för elektronisk rapportering** eller **Systemadministratör** meddelas om det saknade problemet i åtgärdscentret. Meddelandet som visas beror på värdet i parametern **Kör automatiskt procedur för att återställa de brutna mallarna i batch**:

    - Om den här parametern har värdet **av**rekommenderar meddelandet att du startar batchprocessen så att liknande problem korrigeras automatiskt för andra konfigurationsmallar för ER-format. Meddelandet innehåller en länk som du kan använda för att starta batchprocessen.
    - Om den här parametern anges till **På** visas ett meddelande om ett problem med ärende som saknas har upptäckts och att en ny batchprocess **återställa de brutna mallarna från intern säkerhetskopia av databas** har planerats automatiskt. Den här batchprocessen korrigerar automatiskt liknande problem för andra mallar.

För att konfigurera parametern **Kör automatiskt procedur för att återställa de brutna mallarna i batch** slutför du följande steg:

1. I Finance and Operations öppnar du sidan **Organisationsadministration \> Elektronisk rapportering \> Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. I dialogrutan **användarparametrar** anger du det obligatoriska värdet för parametern **Kör automatiskt procedur för att återställa de brutna mallarna i batch**.

> [!NOTE]
> Den här parametern definieras som programanvändare och protokollförda företag.

![Sidan ER-konfigurationer](./media/GER-BackupTemplates-1.png)

I bilden nedan visas ett exempel på det meddelande som visas när parametern **Kör automatiskt procedur för att återställa de brutna mallarna i batch** anges till **på.**

![Sida för leverantörsbetalningsjournal](./media/GER-BackupTemplates-2.png)

Bilden nedan visar hur du batchprocessen **Återställ brutna mallar från intern säkerhetskopia av databas** på sidan **Batch-jobb**.

![Sidan Batchjobb](./media/GER-BackupTemplates-3.png)

Körningsloggen för slutförd batch-process **Återställ brutna mallar från intern säkerhetskopia av databas** omfattar information om mallarna som har återställts från säkerhetskopians lagringsplats till den primära lagringsplatsen.

![Sidan för historik över batchjobb](./media/GER-BackupTemplates-4.png)

Som standard är processen för automatisk generering av säkerhetskopior av mallar i inställningar för ER-format aktiverad. Om du vill sluta göra säkerhetskopior av mallar anger du alternativet **Sluta skapa säkerhetskopior av mall** till **Ja** på fliken **bifogade filer** på sidan **parametrar för elektronisk rapportering**. Du kan öppna den här sidan från arbetsytan **elektronisk rapportering**.

Om du ställer in alternativet **sluta skapa säkerhets kopior av mallar** till **ja** och inte vill behålla de säkerhets kopior som tidigare gjorts för mallar väljer du **rensa säkerhets kopierings lagring** på sidan **parametrar för elektronisk rapportering**.

Om du uppgraderade miljön till Finance and Operations version 10.0.5 (oktober 2019) och vill migrera till en ny miljö som innehåller körbara ER-formatkonfigurationer, väljer du **Fyll i säkerhetslagring** på sidan **Parametrar för elektronisk rapportering** innan migreringen sker. Med den här knappen börjar du skapa säkerhetskopior av alla tillgängliga mallar, så att de kan lagras i lagringsplatsen för ER-säkerhetskopiering för mallar.

![Sida för parametrar för elektronisk rapportering](./media/GER-BackupTemplates-5.png)

## <a name="manual-recovery"></a>Manuell återställning

Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Återställ skadade mallar** för att manuellt initiera processen att återställa ER-mallar från säkerhetskopians lagringsplats till den primära lagringsplatsen. Innan du startar den här processen kan du på sidan **Återställ skadade mallar** ange om den ska utföras interaktivt, eller om du vill att batchprocessen ska schemaläggas för detta.

## <a name="supported-deployments"></a>Distributioner som stöds

I Finance and Operations version 10.0.5 är säkerhetslagring av funktionen ER-mallar endast tillgänglig i molndistributioner.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[Konfigurera ramverket för elektronisk rapportering (ER)](electronic-reporting-er-configure-parameters.md)
