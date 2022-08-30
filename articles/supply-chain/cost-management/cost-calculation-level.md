---
title: Kostnadsberäkningsnivå
description: I denna artikel beskrivs den strukturlistenivå som kallas Kostnadsberäkningsnivå. Denna strukturlistenivå omfattar inte produktions- och batchorder från beräkningar.
author: JennySong-SH
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: e63a868696e36c1d4f5d19ea87bdf4d682c39f8c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334968"
---
# <a name="cost-calculation-level"></a>Kostnadsberäkningsnivå

[!include [banner](../includes/banner.md)]

Den strukturlistenivå som har den namngivna **kostnadsberäknings nivån** utesluter produktionsorder och batchorder från sina beräkningar. Systemet använder den här nivån när kostnadsberäkningar i kostnadsversioner körs. I processer som omberäkningar och lagerstängningar använder systemet strukturlistenivån **Kostnadsnivå** i stället.

## <a name="turn-the-cost-calculation-level-feature-on-or-off"></a>Aktivera eller inaktivera funktionen för kostnadsberäkningsnivå

Innan du kan använda funktionen måste den aktiveras i ditt system. Från och med version 10.0.29 av Supply Chain Management är denna funktion aktiverad som standard. Administratörer kan aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Kostnadsberäkningsnivå* i arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="example-scenario"></a>Exempelscenario

Följande enkla scenario visar skillnaderna mellan **kostnadsberäkningsnivån** och strukturnivån på **kostnadsnivån**.

Du har tre produkter: A, B och C. Produkt C är komponenten av produkt B och produkt B är komponenten av produkt A.

- **Kostnadsnivån** tilldelas följande strukturlistenivåer:

    - **Produkt A:** 0
    - **Produkt B:** 1
    - **Produkt C:** 2

- **Kostnadsberäkningsnivån** tilldelas följande strukturlistenivåer:

    - **Produkt A:** 0
    - **Produkt B:** 1
    - **Produkt C:** 2

En produktionsorder för produkt C skapas och produkt A läggs till i produktionsorderns strukturlista. När ordern har uppskattats uppdateras strukturnivåerna på följande sätt:

- **Kostnadsnivån** tilldelas följande strukturlistenivåer:

    - **Produkt B:** 1
    - **Produkt C:** 2
    - **Produkt A:** 3

- **Kostnadsberäkningsnivån** tilldelas följande strukturlistenivåer:

    - **Produkt A:** 0
    - **Produkt B:** 1
    - **Produkt C:** 2

Detta säkerställer att ändringar av strukturlistor för produktionsorder inte påverkar efterföljande kostnadsberäkningar.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]