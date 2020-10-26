---
title: Serviceuppgifter – översikt
description: Använd serviceuppgifter om du vill beskriva den aktivitet som utförs under en serviceorder. Den här informationen är tillgänglig för både tekniker och kunder.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b433632523bfd64119fda62f8e4b108ff9b5dccd
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987315"
---
# <a name="service-tasks-overview"></a>Serviceuppgifter – översikt

[!include [banner](../includes/banner.md)]

Använd serviceuppgifter om du vill beskriva den aktivitet som utförs under en serviceorder.
Den här informationen är tillgänglig för både tekniker och kunder.

Skapa serviceuppgifter på sidan **serviceuppgifter** och associera serviceuppgifterna med ett specifikt serviceavtal eller en specifik serviceorder genom att skapa serviceuppgiftsrelationer. Varje gång du skapar en serviceuppgiftsrelation kan du skapa följande:

-  Interna anteckningar om uppgiften, som detaljerade tekniska beskrivningar för uppgiften som är viktiga för teknikern att känna till.

-  Externa anteckningar som kunden kan se. De här anteckningarna kan innehålla en enklare förklaring av den uppgift som utförs enligt avtalet mellan kunden och serviceföretaget.

När du har skapat en serviceuppgiftsrelation mellan en serviceuppgift och en serviceorder eller ett serviceavtal, kan du specificera denna serviceuppgift när du skapar serviceorderrader eller serviceavtalsrader för den aktuella serviceordern eller serviceavtalet.

När du genererar serviceorder från ett serviceavtal, kan du använda de serviceuppgifter som är tilldelade till respektive serviceavtalsrad för att gruppera serviceorderrader i serviceorder.

## <a name="create-a-service-task"></a>Skapa en serviceuppgift

1. Klicka på **servicehantering** \> **inställningar** \> **serviceuppgifter**.
2. Skapa en ny rad.
3. Ange service-ID och beskrivning.

## <a name="example"></a>Exempel

En tekniker måste utföra två jobb på en växellåda (serviceobjekt GB-1234) hos en kund. Ett serviceavtal skapas för kunden, och flera transaktioner associeras med jobben. Serviceavtalet och serviceavtalsraderna för de två jobben är enligt följande:

### <a name="service-agreement"></a>Serviceavtal

| Project | Serviceavtal | beskrivning                                  | Grupp   |
|---------|-------------------|----------------------------------------------|---------|
| 9012    | 000008\_001       | Inspektion och planerat byte – GB-1234 | Bonus |

### <a name="service-agreement-lines"></a>Serviceavtalsrader

| beskrivning             | transaktionstyp | Serviceobjekt | Serviceuppgift |
|-------------------------|------------------|----------------|--------------|
| Inspektion och rengöring | Timme             | GB-1234        | I/C - GB1234 |
| Resor                  | Expense          | GB-1234        | I/C - GB1234 |
| Material               | Artikel             | GB-1234        | I/C - GB1234 |
| Planerat byte     | Timme             | GB-1234        | RR - GB1234  |
| GR-1                    | Artikel             | GB-1234        | RR - GB1234  |
| GR-5                    | Artikel             | GB-1234        | RR - GB1234  |

Det finns två serviceuppgifter kopplade till serviceavtalsraderna för de två jobben. Serviceuppgifterna fastställer vilka transaktioner som tillhör respektive jobb. I det första fallet identifierar serviceuppgiften I/C - GB1234 alla serviceavtalsrader som ingår i inspektionen samt rengöring av objekt GB-1234. I det andra fallet identifierar serviceuppgiften RR - GB1234 alla serviceavtalsrader som ingår i ett jobb med planerade byten.

Följande serviceuppgiftsrelationer kopplar serviceuppgifterna till det specifika avtalet:

### <a name="service-tasks"></a>Serviceuppgifter

| Serviceuppgift | Beskrivning                             | Intern anteckning                                                                                                                 | Extern anteckning                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| I/C - GB1234 | Inspektion av växellåda GB-1234           | Visuell och mekanisk inspektion och rengöring av växellådan GB1234.                                                              | Rutininspektion av växellåda |
| RR - GB1234  | Planerat byte av delar i GB-1234 | Planerade servicebyten av komponenterna GR-1 och GR-5 (för växellådor som tillverkats före 2002, byt även komponenten GR-2) | Planerat byte av reservdelar  |

## <a name="group-service-orders"></a>Gruppera serviceorder

När du automatiskt skapar serviceorder kan du använda serviceuppgifter som ett grupperingskriterium. Om du vill gruppera serviceorder efter serviceuppgifter ska du på serviceavtalet definiera att serviceorder som baseras på serviceavtalet ska grupperas efter serviceuppgifts-ID som ursprungligt grupperingskriterium.

**Gruppera efter serviceuppgift**

1. Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.
2. På fliken **inställningar** välj **per serviceuppgift** i fältet för **kombinera serviceorder**.


