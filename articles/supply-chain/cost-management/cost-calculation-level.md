---
title: Kostnadsberäkningsnivå
description: I denna artikel beskrivs den strukturlistenivå som kallas Kostnadsberäkningsnivå. Denna strukturlistenivå omfattar inte produktions- och batchorder från beräkningar.
author: JennySong-SH
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 647ef4b13b864cfdbb7905fe7a0d340e85f6c1e6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850885"
---
# <a name="cost-calculation-level"></a>Kostnadsberäkningsnivå

[!include [banner](../includes/banner.md)]

Den strukturlistenivå som har den namngivna **kostnadsberäknings nivån** utesluter produktionsorder och batchorder från sina beräkningar. Systemet använder den här nivån när kostnadsberäkningar i kostnadsversioner körs. I processer som omberäkningar och lagerstängningar använder systemet strukturlistenivån **Kostnadsnivå** i stället.

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