---
title: Tillgångar och arbetsorder
description: Denna artikel beskriver tillgångar och arbetsorder i Tillgångshantering.
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
ms.openlocfilehash: df2d0fcc5162900ad2ad67f2629d14015f694bd4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869703"
---
# <a name="assets-and-work-orders"></a>Tillgångar och arbetsorder

[!include [banner](../../includes/banner.md)]

 

Denna artikel beskriver tillgångar och arbetsorder i Tillgångshantering. Tillgångar och arbetsorder är de centrala delarna i funktionshanteraren. En *tillgång* är en maskin- eller maskindel som kräver kontinuerlig underhåll och service. Tillgångar kan skapas i en hierarkisk struktur och de kan relateras till funktionsplatser. Underhållsjobb kan planeras på alla nivåer i tillgångsstrukturen.

Olika data, till exempel produktinformation och tillgångsspecifikation och nödvändiga underhållsplaner ställs in för varje tillgång. Följande illustration visar en översikt över tillgångsdata och anslutning av tillgångar till jobbtyper. Röd text används för exempel som visar arv och beroenden.

![Diagram som visar tillgångsdata relaterade till jobbtyper.](media/05-overview-image.png)

Varje arbetsorder har en arbetsordertyp, sådant förebyggande underhåll, avhjälpande underhåll eller inspektion. Arbetsordern innehåller ett eller flera arbetsorderjobb. Varje arbetsorderjobb definierar ett jobb som måste utföras på en tillgång och en relaterad jobbtyp. Exempel på relaterade jobbtyper är 10 000 km, 50 000 km, 1-års översyn och säkerhetsinspektion. En arbetsorder kan relateras till flera tillgångar.

Följande illustration visar en översikt över nyckeldata i en arbetsorder.

![Diagram som visar nyckeldata i en arbetsorder.](media/06-overview-image.png)

En arbetsorder kan relateras till en annan arbetsorder och jobbtyper kan innehålla efterföljande jobb som skapar en arbetsorder. I allmänhet finns det inga beroenden mellan arbetsorder. Därför kan de ändra sitt livscykeltillstånd för arbetsorder och kan schemaläggas oberoende av varandra.

Arbetsorder kan skapas på olika sätt som är relaterade till korrigerande, förebyggande eller reaktivt underhåll. Du kan också skapa arbetsorder manuellt. Följande illustration visar en översikt över processen för automatisk eller manuell generering av arbetsorder.

![Diagram som visar automatisk eller manuell generering av arbetsorder.](media/07-overview-image.png)

Flera steg måste slutföras när du vill schemalägga och köra ett underhållsjobb på en arbetsorder. Följande illustration visar en översikt över bearbetning för en arbetsorder.

![Diagram som visar översikt över bearbetning av en arbetsorder.](media/08-overview-image.png)

> [!NOTE]
> I allmänhet när du arbetar i Dynamics 365 Supply Chain Management och modulen **Tillgångshantering** väljer du **Ny** för att skapa en ny post, väljer **redigera** för att uppdatera en befintlig post och väljer **Spara** för att spara nya eller redigerade data.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]