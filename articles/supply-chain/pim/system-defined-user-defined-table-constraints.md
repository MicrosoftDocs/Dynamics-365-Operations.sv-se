---
title: Systemdefinierade och användardefinierade registerbegränsningar
description: Denna artikel förklarar de två typerna av registerbegränsningar för komponenter i en produktkonfigurationsmodell - användardefinierade och systemdefinierade. Registerbegränsningar representerar matriser för de tillåtna attributkombinationerna, där varje rad anger en uppsättning möjliga attributvärden.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3fb1395859b5abd06539e07ada3d968b2e9c9147
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986537"
---
# <a name="system-defined-and-user-defined-table-constraints"></a>Systemdefinierade och användardefinierade registerbegränsningar

[!include [banner](../includes/banner.md)]

Denna artikel förklarar de två typerna av registerbegränsningar för komponenter i en produktkonfigurationsmodell - användardefinierade och systemdefinierade. Registerbegränsningar representerar matriser för de tillåtna attributkombinationerna, där varje rad anger en uppsättning möjliga attributvärden.

Registerbegränsningar representerar matriser av kombinationer av attribut som tillåts för komponenter i en produktkonfigurationsmodell. Varje rad i registeren definierar en uppsättning möjliga attributvärden. Du kan ange två typer av begränsningar i en produktkonfigurationsmodell:

-   **Uttryckbegränsning** – Skapa ett uttryck som definierar relationer mellan attribut som garanterar att endast kompatibla värden kan markeras under produktkonfiguration.
-   **registerbegränsning** – Skapa ett register som definierar alla kombinationer, som tillåts för en viss uppsättning attribut. Två typer av registerbegränsningar finns: användardefinierade registerbegränsningar och systemdefinierade registerbegränsningar.

Denna artikel beskriver användardefinierade och systemdefinierade registerbegränsningar för komponenter i en produktkonfigurationsmodell.

## <a name="user-defined-table-constraints"></a>Användardefinierad registerbegränsning
En användardefinierad registerbegränsning är en sorts matris som kan användas för att beskriva uppsättningen kombinationer vilka definieras av attributtyper. Om du till exempel tillverkar högtalare, kan du inkludera kolumner för kabinettfinish och frontgaller i den användardefinierade registerbegränsningen. Attributtypen för det kabinettfinish har fyra värden, och attributtypen för frontgaller har tre värden. Därför om begränsningar inte används finns det 4 × 3 = 12 möjliga kombinationer. Men i det här exemplet tillåts bara sex kombinationer, som visas i följande register. Informationen visas på fliken **Tillåtna kombinationer** på sidan **Redigera registerbegränsning**.

| Kabinettfinish | Frontgaller |
|----------------|-------------|
| Svart          | Svart       |
| Svart          | Metall       |
| Ek            | Svart       |
| Rosenträ       | Vit       |
| Vit          | Svart       |
| Vit          | Vit       |

Användardefinierade registerbegränsningar definieras av statisk streckkodsindata som fungerar på samma sätt som en uttrycksbegränsning. När du använder en användardefinierad registerbegränsning, är fördelen att registerer är ofta enklare att skapa och underhåla än långa uttryckbegränsningar.

## <a name="system-defined-table-constraints"></a>Systemdefinierad registerbegränsning
En systemdefinierad registerbegränsning skapar en dynamisk mappning mellan en attributtyp och ett fält i ett register. När en systemdefinierad registerbegränsning inkluderas i en produktkonfigurationsmodell garanterar mappningen att data i registret visas i stället för attributtypens värden. Resultatet är en dynamisk begränsning, eftersom registerinnehållen kan ändras (exempelvis efter andra moduler.)  

När du skapar en systemdefinierad registerbegränsning, väljer du ett register, definierar valfritt frågan som ska användas, och sedan associerar du attributtyper i fälten i det valda registret. Dessa fälttyper måste matcha attributtyperna.  

Innan ett register kan tillämpas på en modell för produktkonfiguration måste registerbegränsningen inkluderas i en begränsning av en av modellens komponenter. Proceduren är att skapa en ny begränsning, markera typen av begränsning och välj den definition av registerbegränsning som ska användas. Så småningom måste alla fält i registerbegränsningen mappas till attribut i produktkonfigurationsmodellen.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Översikt över produktkonfigurationsmodeller](product-configuration-models.md)



