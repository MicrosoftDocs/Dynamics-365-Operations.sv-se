---
title: Funktionsplatser och tillgångar
description: Det här avsnittet beskriver funktionsplats och tillgångar i tillgångshantering. Tillgångshantering är en avancerad modul för hantering av tillgångar och underhållsjobb i Microsoft Dynamics 365 for Finance and Operations.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 351e27dfbbd5227a9642f14a48afe194c447a0f3
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783614"
---
# <a name="functional-locations-and-assets"></a>Funktionsplatser och tillgångar

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Det här avsnittet beskriver funktionsplats och tillgångar i tillgångshantering. Tillgångshantering är en avancerad modul för hantering av tillgångar och underhållsjobb i Microsoft Dynamics 365 for Finance and Operations.

## <a name="overview"></a>Översikt

Tillgångshantering integreras sömlöst med flera moduler i Finance and Operations. Följande illustration visar gränssnitten med andra moduler.

![Figur 1](media/01-overview-image.png)

Med tillgångshantering kan du effektivt hantera och utföra alla uppgifter som är relaterade till hantering och underhåll av många typer av utrustning i företaget. Denna utrustning omfattar maskiner, produktionsutrustning och fordon. Tillgångshantering stödjer även lösningar inom många branscher.

Följande illustration visar en översikt över de viktigaste funktionerna som täcks av tillgångshantering.

![Figur 2](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Funktionsplatser och tillgångar

Funktionsplatser används för att hantera tillgångar på platser. I den här hanteringen ingår spårning av tillgångskostnader på funktionsplatser. Funktionsplatser struktureras hierarkiskt och platser kan ha underordnade platser. Strukturen på funktionsplatser är statisk. Med andra ord kan platser inte ändra plats. Tillgångar kan installeras på funktionsplatser och kan, efter behov, installeras på andra funktionsplatser senare.

Tillgångskostnader följer alltid placeringen av tillgången. Med andra ord, om du installerar en tillgång på en ny funktionsplats, använder tillgången automatiskt de ekonomiska dimensionerna som är relaterade till den nya funktionsplatsen. Därför är tillgångskostnader alltid relaterade till den funktionsplats som tillgången är installerad på. Denna automatiska hantering av ekonomiska dimensioner hjälper till att garantera fullständig spårning av kostnader när ditt företag utför projektstyrning och rapportering på funktionsplatser.

Hur du bygger din hierarki av funktionsplatser beror på ditt företags krav på underhåll av intern utrustning eller service av kundutrustning. Följande bild visar ett exempel på funktionsplatser som är baserade på geografiska platser.

![Figur 3](media/03-overview-image.png)

Följande bild visar ett exempel på funktionsplatser som är baserade på kunder.

![Figur 4](media/04-overview-image.png)
