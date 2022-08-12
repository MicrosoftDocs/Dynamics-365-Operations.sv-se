---
title: Funktionsplatser och tillgångar
description: Denna artikel beskriver funktionsplatser och tillgångar i Tillgångshantering. Tillgångshantering är en avancerad modul för hantering av tillgångar och underhållsjobb i Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d8d155b8bbf981408f6f15e914fc3bb1da25c9c
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111089"
---
# <a name="functional-locations-and-assets"></a>Funktionsplatser och tillgångar

[!include [banner](../../includes/banner.md)]

 

Denna artikel beskriver funktionsplatser och tillgångar i Tillgångshantering. Tillgångshantering är en avancerad modul för hantering av tillgångar och underhållsjobb i Dynamics 365 Supply Chain Management.

## <a name="overview"></a>Översikt

Tillgångshantering integreras sömlöst med flera moduler med andra appar för ekonomi och drift. Följande illustration visar gränssnitten med andra moduler.

![Diagram som visar hur Tillgångshantering samarbetar med andra moduler.](media/01-overview-image.png)

Med Tillgångshantering kan du effektivt hantera och utföra alla uppgifter som är relaterade till hantering och underhåll av många typer av utrustning i företaget. Denna utrustning omfattar maskiner, produktionsutrustning och fordon. Tillgångshantering stödjer även lösningar inom många branscher.

Följande illustration visar en översikt över de viktigaste funktionerna som täcks av Tillgångshantering.

![Diagram som visar huvudfunktionerna i Tillgångshanteringen.](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Funktionsplatser och tillgångar

Funktionsplatser används för att hantera tillgångar på platser. I den här hanteringen ingår spårning av tillgångskostnader på funktionsplatser. Funktionsplatser struktureras hierarkiskt och platser kan ha underordnade platser. Strukturen på funktionsplatser är statisk. Med andra ord kan platser inte ändra plats. Tillgångar kan installeras på funktionsplatser och kan, efter behov, installeras på andra funktionsplatser senare.

Tillgångskostnader följer alltid placeringen av tillgången. Med andra ord, om du installerar en tillgång på en ny funktionsplats, använder tillgången automatiskt de ekonomiska dimensionerna som är relaterade till den nya funktionsplatsen. Därför är tillgångskostnader alltid relaterade till den funktionsplats som tillgången är installerad på. Denna automatiska hantering av ekonomiska dimensioner hjälper till att garantera fullständig spårning av kostnader när ditt företag utför projektstyrning och rapportering på funktionsplatser.

Hur du bygger din hierarki av funktionsplatser beror på ditt företags krav på underhåll av intern utrustning eller service av kundutrustning. Följande bild visar ett exempel på funktionsplatser som är baserade på geografiska platser.

![Diagram som visar funktionella platser baserat på geografiska platser.](media/03-overview-image.png)

Följande bild visar ett exempel på funktionsplatser som är baserade på kunder.

![Diagram som visar funktionella platser baserat på kunder.](media/04-overview-image.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
