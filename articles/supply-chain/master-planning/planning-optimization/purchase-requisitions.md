---
title: Inköpsrekvisitioner
description: Den här artikeln beskriver inköpsrekvisitioner.
author: t-benebo
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: d9d55186307b18f4c3be78ae0828b08d3c987aad
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740695"
---
# <a name="purchase-requisitions"></a>Inköpsrekvisitioner

[!include [banner](../../includes/banner.md)]

Huvudplaneringen kan fylla på godkända inköpsrekvisitioner. För att täcka inköpsrekvisitioner behöver därför användarna inte använda ett arbetsflöde för att skapa inköpsorder. I stället kan inköpsrekvisitioner täckas av huvudplaneringen. På grund av den här funktionen kan en inköpsrekvisition producera en inköpsorder, en överföringsorder eller en tillverkningsorder, beroende på värdet för **Planerad ordertyp** som har angetts för den relaterade produkten.

## <a name="enable-master-plans-to-include-requisitions"></a>Aktivera huvudplaner för att inkludera rekvisitioner

Följ de här stegen om du vill ta med rekvisitioner under disponeringsberäkningen för en huvudplan.

1. Gå till **Huvudplanering** \> **Inställningar** \> **Planer** \> **Huvudplaner**.
1. Skapa eller välj huvudplan.
1. På snabbfliken **allmänt** anger du alternativet **Inkludera rekvisitioner** till *Ja*.
1. Upprepa steg 2 och 3 för varje ytterligare huvudplan där du vill ta med rekvisitioner.

## <a name="approved-requisitions-time-fence"></a>Godkänd rekvisitionstidsgräns

Den *godkända rekvisitionstidsgränsen* anger hur långt tillbaka (i dagar) en huvudplan kommer att omfatta efterfrågan från godkända påfyllnadsrekvisitioner. Du kan konfigurera en godkänd rekvisitionstidsgräns på både disponeringsgruppnivå och huvudplansnivå.

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a>Ställa in tidsgräns för godkända rekvisitioner för en disponeringsgrupp

1. Gå till **huvudplanering** \> **inställningar** \> **täckning** \> **disponeringsgrupper**.
1. Skapa eller välj en disponeringsgrupp.
1. På snabbfliken **Annat** anger du **tidsgränsen för godkända rekvisitioner (dagar)** till antalet dagar som ska inkluderas i tidsgränsen.
1. Upprepa steg 2 och 3 för varje ytterligare disponeringsgrupp där du vill konfigurera en godkänd tidsgräns för rekvisitioner.

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a>Ställa in tidsgräns för godkända rekvisitioner för en individuell huvudplan

När du anger en godkänd rekvisitionstidsgräns för en enskild huvudplan åsidosätter inställningen tidsgränsinställningen för disponeringsgruppen.

1. Gå till **Huvudplanering** \> **Inställningar** \> **Planer** \> **Huvudplaner**.
1. Skapa eller välj huvudplan.
1. På snabbfliken **Tidsgräns i dagar** anger du **tidsgränsen för godkända rekvisitioner (dagar)** till antalet dagar som ska inkluderas i tidsgränsen.
1. Upprepa steg 2 och 3 för varje ytterligare huvudplan där du vill konfigurera en godkänd tidsgräns för rekvisitioner.

> [!IMPORTANT]
> Godkända rekvisitioner tidsgränser stöds inte för Planeringsoptimering. Till dess att de stöds ignoreras alla värden som du anger i fältet **tidsgränsen för godkända rekvisitioner (dagar)**.

## <a name="independent-supply-regardless-of-coverage-code"></a>Oberoende leverans, oavsett disponeringskod

Inköpsrekvisitioner omfattas alltid av oberoende planerade order, oavsett disponeringskod. Detta garanterar en tydlig spårning och arbetsflöden mellan inköpsrekvisitioner och påfyllnadsorder.

### <a name="example-1"></a>Exempel 1

En produkt ställs in så att den har ett **disponeringskodsvärde** för *Min/max*. Det har följande status för lager och rekvisitioner:

- Lagerbehållningskvantitet = 10.
- Minsta lagerkvantitet = 15.
- Maximal lagerkvantitet = 20.
- Det finns en inköpsrekvisition för en del. Det har ett begärt datum för idag.

När huvudplaneringen körs skapas två planerade order: en för tio enheter för att fylla på lagret till den största kvantiteten och en för en del för att fylla på inköpsrekvisitionen.

### <a name="example-2"></a>Exempel 2

En produkt ställs in så att den har ett **disponeringskodsvärde** för *Min/max*. Det har följande status för lager och rekvisitioner:

- Lagerbehållningskvantitet = 17.
- Minsta lagerkvantitet = 15.
- Maximal lagerkvantitet = 20.
- Det finns en inköpsrekvisition för en del. Det har ett begärt datum för idag.

När huvudplaneringen körs skapas en planerad order för en del för att fylla på inköpsrekvisitionen.

### <a name="example-3"></a>Exempel 3

En produkt ställs in så att den har ett **disponeringskodvärde** för *Period* och en periodlängd på sju dagar. Den har följande status för lager, försäljningsorder och rekvisitioner:

- Lagerbehållningskvantitet = 0.
- Det finns en försäljningsorder med fem enheter. Den har ett förväntat transportdatum för idag plus en dag.
- Det finns en inköpsrekvisition för tre delar. Det har ett begärt datum för idag plus tre dagar.

När huvudplaneringen körs skapas två planerade order: en för tre delar för att fylla på inköpsrekvisitionen och en för fem för att fylla på efterfrågan på försäljningsordern.

> [!NOTE]
> När en planerad order som är pegging till en inköpsrekvisition har bekräftats, behåller planeringsmotorn peggingen på inköpsrekvisitionen. Om den bekräftade ordern senare visar sig sakna en viss kvantitet som krävs för att uppfylla inköpsrekvisitionen, skapas en ny planerad order för differensen.

Mer information om inköpsrekvisitioner finns i [översikten över inköpsrekvisitioner](../../procurement/purchase-requisitions-overview.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]