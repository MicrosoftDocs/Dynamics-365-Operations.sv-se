---
title: Konfigurera ett dotterbolag som juridik person för konsolidering
description: I detta ämne beskrivs hur du arbetar med kontoplanerna för konsolideringsföretag.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 44bd184514b24a816cc83f6b0070a5e08163921b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204819"
---
# <a name="set-up-a-subsidiary-legal-entity-for-consolidation"></a>Konfigurera ett dotterbolag som juridik person för konsolidering

[!include [banner](../includes/banner.md)]

Metoden som du använder för att förbereda dotterbolagskonton för konsolidering beror delvis på den omfattning som strukturen i kontoplanen i dotterbolagets juridiska person återspeglar kontoplanen i den konsoliderade juridiska personen.

Innan du påbörjar en konsolidering när en period avslutas ska du utföra förberedelser för periodstängning, men inte stänga dotterbolagskontona förrän konsolideringen är slutförd. Mer information om stängning i samband med periodavslut finns i [Stäng redovisningen vid periodslut](close-general-ledger-at-period-end.md) och [Avsluta bokföringsår](tasks/close-fiscal-year.md).

> [!NOTE]
>  Vi rekommenderar att du använder Management Reporter för Microsoft Dynamics 365 Finance för att kombinera ekonomiska resultat för flera juridiska personer i ett konsoliderat format. I Management Reporter kan du skapa konsoliderade ekonomiska rapporter för juridiska personer, använda Excel för att importera konsolideringsdata från andra källor, samt översätta belopp till valfritt antal rapporteringsvalutor utan att behöva köra konsolideringsprocessen i Dynamics 365 Finance.

## <a name="map-subsidiary-main-accounts-to-consolidated-main-accounts"></a>Mappa dotterbolagets huvudkonton till de konsoliderade huvudkontona

Om kontoplanen i dotterbolagets juridiska person inte följer kontoplanen i den konsoliderade juridiska personen, kan du mappa huvudkontona i dotterbolaget till huvudkontona i den konsoliderade juridiska personen.

1. I *entiteten för juridisk person* går du till **Redovisning \> Inställningar** \> **Kontoplan \> Kontoplaner**.
2. Välj en kontoplan. På snabbfliken **Huvudkonton** väljer du ett huvudkonto och sedan **Redigera**.
3. Markera de huvudkonton för dotterbolags som ska mappas till ett konsoliderat huvudkonto. I snabbfliken **Allmänt**, i fältet **Konsolideringskonto**, anger du kontot i den konsoliderade juridiska person som saldot eller överföringarna för huvudkontot för valt dotterbolag måste överföras till. Du kan ange samma konsoliderade huvudkonto för flera olika dotterbolagskonton.

    > [!NOTE]
    > Om huvudkontotyperna för de dotterbolagskonton som mappas skiljer sig från huvudkontotyperna i den konsoliderade juridiska personen, skrivs värdena för konton med huvudkontotypen **Summa** öve ri samband med konsolidering.

4. Förbered rapporter och bokslut för den konsoliderade juridiska personen som baseras på ekonomiska dimensioner. Följ dessa steg om du vill mappa de ekonomiska dimensioner som används i dotterbolagskontona till de ekonomiska dimensionerna i den konsoliderade juridiska personen:

    1. I *Juridisk person för dotterbolag* går du till **Redovisning \> Inställningar \> Ekonomiska dimensioner \> Ekonomiska dimensioner**, väljer en ekonomisk dimension och sedan **Värden för ekonomisk dimension**.
    2. Välj värdet för den ekonomiska dimension som ska mappas till ett annat värde för ekonomisk dimension i den konsoliderade juridiska personen.
    3. På snabbfliken **Allmänt**, i fältet **Gruppdimension**, anger du den ekonomiska dimensionen i den konsoliderade juridiska personen. Under konsolideringen kommer denna ekonomisk dimension att tilldelas till transaktioner och saldon som använder den valda ekonomiska dimensionen i dotterbolagets juridiska person. Ekonomiska dimensioner som du anger här måste användas i den konsoliderade juridiska personen. Du kan tilldela den ekonomiska dimension som används som gruppens ekonomiska dimension i flera dotterbolags ekonomiska dimensioner.

5. Om du utför en konsolidering online följer du dessa steg för att säkerställa att överföringarna sker enligt ditt syfte:

    1. I den *konsoliderade juridiska personen* går du till **Redovisning \> Periodisk \> Konsolidera \> Konsolidera \[Exportera till\]** för att öppna sidan **Konsolidera \[online\]**.
    2. I fliken **Kriterier** väljer du kryssrutan **Använd konsolideringskonto**.
    3. I fliken **Ekonomiska dimensioner** väljer du lämpliga ekonomiska dimensioner.
    4. För respektive ekonomisk dimension som du väljer anger du ett värde i fältet **Segmentordning** för att indikera den ordning i vilken dimensionerna ska visas.

## <a name="maintain-the-same-chart-of-accounts-in-the-subsidiary-and-consolidated-legal-entities"></a>Underhålla samma kontoplan i dotterbolaget och konsoliderade juridiska personer

Huvudkonton i dotterbolagets juridiska person kan ha samma kontonummer och samma struktur för kontoplanen som huvudkontona i den konsoliderade juridiska personen. I det här fallet behöver du inte mappa huvudkonton i dotterbolaget manuellt till huvudkonton i den konsoliderade juridiska personen.

Innan du startar konsolideringen följer du dessa steg.

1. I den *konsoliderade juridiska personen* går du till **Redovisning \> Periodisk \> Konsolidera \> Konsolidera \[Exportera till\]** för att öppna sidan **Konsolidera \[online\]**.
2. Markera rutan **Använd konsolideringskonto**. Överföringen av transaktioner och saldon sker automatiskt till rätt konton under konsolideringen.

> [!NOTE]
> Om kontona inte stämmer överens stoppas konsolideringen och ett meddelande visas.

## <a name="create-a-chart-of-accounts-for-the-consolidated-legal-entity-based-on-an-existing-chart-of-accounts"></a>Skapa en kontoplan för den konsoliderade juridiska personen som baseras på en befintlig kontoplan

Du kan utföra en konsolidering även om en kontoplan inte redan har skapats i den konsoliderade juridiska personen.

- Om du har planerat kontostrukturen som du vill använda i den konsoliderade juridiska personen, kan du mappa dotterbolagets konton till den här strukturen.
- Om du inte mappar några dotterbolagskonton skapas det konsoliderade företagets konton automatiskt när dotterbolagsdata överförs till den konsoliderade juridiska personen. Dessa konton baseras på huvudkontot. Efterföljande data sammanställas i konton hos den konsoliderade juridiska person som har samma kontonummer som dotterbolagets konton.

Oavsett om du har mappat konton eller inte ska du avmarkera kryssrutan **Använd konsolideringskonto** på sidan **Konsolidera** i konsoliderad juridisk person innan du kör den här typen av konsolidering.

> [!NOTE]
> Du bör använda den här metoden när du skapar en kontoplan i den konsoliderade juridiska personen utifrån kontoplanerna i en av dotterbolagets juridiska personer. (Mer information finns i [Konsolideringskontogrupper och ytterligare konsolideringskonton](../budgeting/consolidation-account-groups-consolidation-accounts.md) .) Tilldela sedan lämplig konsolideringskonverteringsprincip till respektive konsoliderat huvudkonto och kör sedan konsolideringen för alla juridiska personer i dotterbolaget.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]