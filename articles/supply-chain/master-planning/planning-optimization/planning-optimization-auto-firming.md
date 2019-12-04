---
title: Automatisk bekräftelse med planeringsoptimering
description: I det här avsnittet beskrivs hur du använder automatisk bekräftelse för planeringsoptimering.
author: ChristianRytt
manager: AnnBe
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 90319222e7357d7c54243faa8c64575377348467
ms.sourcegitcommit: 0138b6c108a10f2bcb90c91205da8092917160d8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2783163"
---
# <a name="auto-firming-with-planning-optimization"></a>Automatisk bekräftelse med planeringsoptimering

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

Med automatisk bekräftelse kan du bekräfta (dvs frisläppa) planerade order som en del av huvudplaneringsprocessen. När planerade order bekräftas omvandlas de till faktiska inköpsorder, överföringsorder eller tillverkningsorder. När planeringsoptimering används bekräftas planerade order under en huvudplaneringskörning när orderdatumet (startdatumet) ligger inom tidsgränsen för bekräftelse.

> [!NOTE]
> Automatisk bekräftelse av en planerad inköpsorder kan endast äga rum om artikel kopplades till en leverantör.

## <a name="turn-on-auto-firming"></a>Aktivera automatisk bekräftelse

Så här aktiverar du automatisk bekräftelse.

1. I arbetsytan **Funktionshantering** på fliken **Ny**, välj **Automatisk bekräftelse för planeringsoptimering** i listan. Om funktionen inte visas på fliken **Ny** tittar du på flikarna **Ej aktiverad** och **Alla**.
1. Välj **Aktivera nu**. Du kan också välja **schema**och sedan välja den tidpunkt då funktionen ska aktiveras.

## <a name="set-up-the-firming-time-fence"></a>Ställ in bekräftad tidsgräns

Bekräftad tidsgräns beräknas framåt från körningsdatumet för huvudplaneringen. Det definieras av antalet dagar som du anger. Du kan kontrollera bekräftad tidsgräns på följande sätt:

- Om du vill definiera standard bekräftad tidsgräns för en disponeringsgrupp går du till **Huvudplanering** \> **Inställningar** \> **Disponering** \> **Disponeringsgrupper** och väljer en disponeringsgrupp. Ange sedan antalet dagar på snabbfliken **övrigt** i fältet **Automatisk bekräftelse av tidsgräns (dagar)**.
- Om du vill skriva över den bekräftelse av tidsgräns som har definierats för disponeringsgruppen för en viss artikel går du till **produktinformationshantering** \> **frisläppta produkter**, sedan från åtgärdsfönstret väljer du **Plan** och sedan **artikeldisponering**. Sedan på fliken **Allmänt** väljer du **Åsidosätt tidsgränser** och i fältet **Automatisk bekräftelse av tidsgräns (dagar)** anger du antalet dagar.
- Om du vill skriva över den bekräftelse av tidsgräns som har definierats för disponeringsgruppen och artikeldisponering för en viss huvudplan går du till **Huvudplanering** \> **Inställningar** \> **Huvudplaner** och välj en huvudplan. Sedan på snabbfliken **tidsgräns i dagar** ange **Frys** till **Ja** och ange antalet dagar.

Om automatisk bekräftelse aktiveras för en huvudplaneringskörning där planeringsoptimering används, utförs automatiskt bekräftelseprocess enligt inställningen för automatisk bekräftelse. Om automatisk bekräftelse inte är aktiverad eller om planeringen startas från sidan **nettobehov** hoppas den automatiska bekräftelseprocessen över.

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a>Planeringsoptimering jämfört med den inbyggda planeringsmotorn för Supply Chain Management

Både planeringsoptimering och planeringsmotorn som är inbyggd i Microsoft Dynamics 365 Supply Chain Management kan användas för att automatiskt bekräfta planerade order. Det finns emellertid några viktiga skillnader. Exempel: planeringsoptimering använder orderdatum (dvs. startdatum) för att avgöra vilka planerade order som ska bekräftas, den inbyggda planeringsmotorn för Supply Chain Management använder behovsdatum (dvs. slutdatumet). Här följer en sammanfattning av skillnaderna.

**Planeringsoptimering**

- Automatisk bekräftelse baseras på orderdatumet (startdatum).
- Eftersom orderdatumet (startdatum) utlöser bekräftelsen behöver du inte tänka på produktionstiden som en del av den bekräftade tidsgränsen.
- Om du vill bekräfta alla order som måste påbörjas under den aktuella veckan måste den bekräftade tidsgränsen vara en vecka.

**Inbyggd planeringsmotor för Supply Chain Management**

- Automatisk bekräftelse baseras på behovsdatum (slutdatum).
- För att garantera att order bekräftas i tid måste den bekräftade tidsgränsen vara längre än produktionstiden.
- Om du vill bekräfta alla order som måste påbörjas under den aktuella veckan måste den bekräftade produktionstid plus en vecka.
