---
title: Frisläppning i batch av delvis reserverade överföringsorder
description: Detta avsnitt beskriver hur du ställer in och använder batchfrisläppning av delvis reserverade överföringsorder från en mobil enhet.
author: pjacobse
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7807ae109a4a708f3530112feed1a4fb210a30ef
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016304"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>Frisläppning i batch av delvis reserverade överföringsorder

[!include [banner](../includes/banner.md)]

Funktionerna för batchfrisläppande av delvis reserverade överföringsorder gör att du delvis kan frisläppa överföringsorder till ett lager med hjälp av ett batchjobb.
Eftersom du kan välja att frisläppa en delkvantitet behöver du inte vänta på att hela orderkvantiteten ska vara tillgänglig i distributionslagret innan du frisläpper en order.

Frisläppandet av order till ett lagerställe är en avancerad lagerhanteringsprocess. Denna process involverar aktiviteter, till exempel plockning, paketering och frakt, som en lagerarbetare kan utföra med en mobil enhet.

## <a name="where-it-applies"></a>Tillämpning

För den här funktionen frisläpps överföringsorder till ett lagerställe med hjälp av ett batchjobb. Denna funktion är användbar när det inte finns tillräckligt mycket lager men du ändå vill överföra artiklar från ett lagerställe till ett annat.

## <a name="how-it-is-set-up"></a>Inställningar

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>Ange uppfyllandevillkor för överförings- och försäljningsorder

Innan en order kan delvis frisläppas till ett lager som en batch, måste uppfyllandevillkoret uppfyllas. Dessa uppfyllandekriterier utförande bestäms av uppfyllandepolicyn.

Uppfyllandepolicyer för överförings- och försäljningsorder anges på företagsnivå. Beroende på inställningarna för uppfyllandepolicyn kommer orderfrisläppandet i batch att godtas eller avvisas. Alla order kommer sedan att behandlas därefter.

-   Om du vill skapa uppfyllandepolicyer för överförings- och försäljningsorder klickar du på **Lagerstyrning** \> **Inställningar** \> **Frisläpp till lagerställe** \> **Uppfyllelsepolicy** , och skapar sedan en uppfyllandepolicy genom att ange ett namn och en beskrivning.

-   Om du vill ange en uppfyllandekvot, en värdetyp samt det meddelande som ska visas om uppfyllandepolicyn överträds klickar du på **Lagerstyrning** \> **Inställningar** \> **Frisläpp till lagerställe** \> **Uppfyllandepolicy** , och fyller sedan i fälten **Uppfyllandekvot** , **Värdetyp** och **Meddelande om brott mot uppfyllande**.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>Ange uppfyllandevillkoren för överförings- och försäljningsorder

-   Om du vill ange villkoren för överföringsorder klickar du på **Lagerstyrning** \> **Inställningar** \> **Parametrar för lager och lagerstyrning** \> **Överföringsorder** \> **Lagerstyrning** , och väljer sedan uppfyllelsevillkor för överföringsorder.

-   Om du vill ange uppfyllelsevillkor för försäljningsorder klickar du på **Kundreskontra** \> **Inställningar** \> **Parametrar för kundreskontra** \> **Lagerstyrning** och väljer sedan villkor för uppfyllandet av försäljningsorder.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a>Tillåt frisläpp i batch, och ange den kvantitet som ska frisläppas i batch

Ett batch-jobb används för att frisläppa order till ett lager i batch. De parametrar som särskiljer de order som ska köras i ett batchjobb anges i själva batchjobbet.

Parametern **Kvantitet** anger om hela kvantiteten eller den fysiskt reserverade kvantiteten ska frisläppas i batchen. Parametern **Tillåt frisläppning av delvis frisläppta order** avgör om order i batchen godkänns eller avvisas om de tidigare delvis har frisläppts.

-   För att ange parametrarna **Kvantitet** och **Tillåt frisläpp av delvis frisläppta order** för överföringsorder klickar du på **Lagerstyrning** \> **Frisläpp till lagerställe** \> **Automatisk frisläppning av överföringsorder**.

-   För att ange parametrarna **Kvantitet** och **Tillåt frisläppning av delvis frisläppta order** för försäljningsorder klickar du på **Lagerstyrning** \> **Frisläpp till lagerställe** \> **Automatisk frisläppning av försäljningsorder**.
