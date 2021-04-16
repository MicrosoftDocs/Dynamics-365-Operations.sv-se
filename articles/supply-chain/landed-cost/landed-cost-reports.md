---
title: Rapporter för hemtagningskostnad
description: I det här avsnittet beskrivs hur du söker efter och använder de olika rapporttyper som är tillgängliga för modulen hemtagningskostnad.
author: sherry-zheng
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 90630a29d8ad77931735a81ee152aa76514a387c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821091"
---
# <a name="landed-cost-reports"></a>Rapporter för hemtagningskostnad

[!include [banner](../../includes/banner.md)]

## <a name="outstanding-invoices"></a>Utestående fakturor

Rapporten utestående fakturor innehåller en lista över alla utestående fakturor för de olika kostnadsnivåerna som är associerade med varje färd. Den används för att med jämna mellanrum stämma av färd och färdkostnader för redovisningstransaktioner. När en omkostnad har fakturerats tas den bort från rapporten.

För att generera rapporten för utestående fakturor följ dessa steg.

1. Gå till **Hanteringskostnad \> Rapporter \> Spåra \> Utestående fakturor**.
1. I dialogrutan **Utestående fakturor** i fältet **Per datum** anger du ett datum. Fakturor som var utestående på eller före detta datum kommer att inkluderas i utleveransen.
1. Välj något av följande alternativ under **Visa**:

    - **Kostnad som inte fakturerats** – Inkludera kostnader för fakturerade försändelser som har ett uppskattat kostnadsvärde men ingen faktisk kostnad.
    - **Ej fakturerat lager** – Inkludera kostnader som har fakturerats, men som inköpsordern ännu inte har mottagits för.
    - **Alla som inte fakturerats** – Inkludera resultatet för både alternativet **Kostnad som inte fakturerats** och alternativet **Lager som inte fakturerats**.

1. Ställ in alternativet **Inkludera nya kostnader** till *Ja* för att inkludera kostnader som ännu inte har någon faktisk kostnad och som inte har erhållits för lager. Om du ställer in det till *Nej* kommer rapporten endast att inkludera kostnader som har fakturerats.
1. I avsnittet **Vy**, aktivera varje typ av detaljer som du vill inkludera i rapporten.
1. Som du gör för andra typer av rapporter i Microsoft Dynamics 365 Supply Chain Management, använd snabbfliken **Destination** för att välja utdataformat för rapporten.
1. Som du gör för andra typer av rapporter i Supply Chain Management, använd snabbflikarna **Poster som ska ingå** för att ytterligare begränsa de poster som kommer att ingå i rapporten.
1. Klicka på **OK** för att generera rapporten.

## <a name="activityprovider-analysis-reports"></a>Analys av aktivitet/leverantör, rapporter

Med analysrapporterna för aktiviteter/leverantörer kan du kontrollera att tidsuppskattningarna för respektive leverantör är korrekta.

För att generera analysrapporten för aktivitet/leverantör följ dessa steg.

1. Följ ett av följande steg, beroende på vilken typ av rapport du vill skapa:

    - Gå till **Hemtagningskostnad \> Rapporter \> Analys av aktivitet/leverantör efter aktivitet**. I det här fallet grupperas tidsuppskattningarna efter aktivitet.
    - Gå till **Hemtagningskostnad \> Rapporter \> Analys av aktivitet/leverantör efter leverantör**. I det här fallet grupperas tidsuppskattningarna efter leverantör.

    Antingen dialogrutan **Analys av aktivitet/leverantör efter aktivitet** eller dialogrutan **Analys av aktivitet/leverantör efter leverantör** visas. Samma alternativ finns i båda dialogrutorna.

1. Som du gör för andra typer av rapporter i Supply Chain Management , använd snabbfliken **Destination** för att välja utdataformat för rapporten.
1. Som du gör för andra typer av rapporter i Supply Chain Management, använd snabbflikarna **Poster som ska ingå** för att ytterligare begränsa de poster som kommer att ingå i rapporten.
1. Klicka på **OK** för att generera rapporten.

## <a name="voyage-costing-reports"></a>Kostnadsredovisningsrapporter för färd

I kostnadsredovisningsrapporter för färd visas kostnaden för artiklarna och importkostnaderna per år, leveransbehållare eller underhåll, beroende på vilka alternativ du väljer när du genererar rapporten. Varje kostnadsrapport för färd gör att du kan visa den uppskattade kostnaden för en kostnad jämfört med den faktiska kostnaden, och den kan delas upp med flera identifierande faktorer.

För att generera kostnadsredovisningsrapporter för färd, följ dessa steg.

1. Följ ett av följande steg, beroende på vilken typ av rapport du vill skapa:

    - Gå till **Hemtagningskostnad \> Rapporter \> Kostnadsredovisning \> Färdkostnad efter individuell kostnad**. I det här fallet visar det enskilda kostnadsalternativet importkostnader per kostnadsområde per kostnadstypkod.
    - Gå till **Hemtagningskostnad \> Rapporter \> Kostnadsredovisning \> Färdkostnad efter rapporteringskategori**. I det här fallet delas importkostnaden upp i olika rapporteringskategorier. Kostnadstyper grupperas efter rapportkategorier.

    Antingen dialogrutan **Färdkostnad per enskild kostnad** eller dialogrutan **Färdkostnad efter rapporteringskategori** visas. Dessa dialogrutor liknar varandra. Alla skillnader noteras under resten av den här proceduren.

1. Om du har öppnat dialogrutan **Färdkostnad efter rapporteringskategori** i fältet **Kostnad** väljer du ett av följande värden:

    - **Kostnadsvärde** – Värdet beräknas antingen genom att använda automatisk kostnader eller skapas manuellt i kostnadsområdet.
    - **Uppskattat** – När varorna har inkommit ställs den uppskattade kostnaden in.
    - **Utfall** – När ordern har fakturerats ställs den faktiska kostnaden in på kostnaden på fakturan.
    - **Bäst** – Systemet använder det som av de föregående tre alternativen är mest korrekt. (Vi rekommenderar att du väljer detta alternativ.)

1. Ställ in alternativet **Per artikel** till *Ja* för att visa kostnaden för respektive artikel. Ställ in den till *Nej* för att visa kostnader per färd.
1. I avsnittet **Vy** välj de kategorier som kostnaden ska delas upp i.
1. I avsnittet **Dimensioner**, välj de dimensioner som ska inkluderas i rapporten.
1. Som du gör för andra typer av rapporter i Supply Chain Management , använd snabbfliken **Destination** för att välja utdataformat för rapporten.
1. Som du gör för andra typer av rapporter i Supply Chain Management, använd snabbflikarna **Poster som ska ingå** för att ytterligare begränsa de poster som kommer att ingå i rapporten.
1. Klicka på **OK** för att generera rapporten.

## <a name="shipping-container-receipts-list"></a>Inleveranslista för fraktcontainer

Inleveranslistan för leveransbehållare innehåller alla ej inlevererade kvantiteter som förfaller på eller före ett förväntat datum. Lagerställepersonal kan använda den här rapporten för att identifiera de förväntade varorna i en leveransbehållare. Det kan också användas för att manuellt validera varor som in kommer in på en leveransbehållare.

Följ de här stegen om du vill generera en inleveranslista för en leveransbehållare.

1. Gå till **Hemtagningskostnad \> Rapporter \> Spårning \> Inleveranslistan för leveransbehållare**.
1. I dialogrutan **Inleveranslistan för leveransbehållare** för fältet **Förväntat datum** anger du ett datum. Alla kvantiteter ej inlevererats på eller före detta datum kommer att inkluderas i utleveransen.
1. I avsnittet **Dimensioner**, välj de dimensioner som ska inkluderas i rapporten.
1. Som du gör för andra typer av rapporter i Supply Chain Management , använd snabbfliken **Destination** för att välja utdataformat för rapporten.
1. Som du gör för andra typer av rapporter i Supply Chain Management, använd snabbflikarna **Poster som ska ingå** för att ytterligare begränsa de poster som kommer att ingå i rapporten.
1. Klicka på **OK** för att generera rapporten.

## <a name="expected-delivery-report"></a>Rapport för förväntad leverans

Den förväntade leveransrapporten innehåller grundläggande information om färden, leveransbehållare, folio, artiklar och förväntat leveransdatum.

För att generera en rapport för förväntad leverans följ dessa steg.

1. Gå till **Hanteringskostnad \> Rapporter \> Spåra \> Förväntad leverans**.
1. I dialogrutan **Förväntad leverans** i fältet **Förväntat datum** välj datum då leverans av varor till slutliga destinationslagerstället förväntas. Alla färdrader som har ett förväntat datum på eller före detta datum, och som ännu inte har inkommit, inkluderas i utleveransen.
1. Valfritt: I fältet **leverantörskonto**, välj ett leverantörskonto för att endast inkludera leveranser från en specifik leverantör.
1. I avsnittet **Dimensioner**, välj de dimensioner som ska inkluderas i rapporten.
1. Som du gör för andra typer av rapporter i Supply Chain Management , använd snabbfliken **Destination** för att välja utdataformat för rapporten.
1. Som du gör för andra typer av rapporter i Supply Chain Management, använd snabbflikarna **Poster som ska ingå** för att ytterligare begränsa de poster som kommer att ingå i rapporten.
1. Klicka på **OK** för att generera rapporten.
