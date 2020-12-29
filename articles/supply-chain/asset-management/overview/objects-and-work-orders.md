---
title: Tillgångar och arbetsorder
description: Det här avsnittet beskriver tillgångar och arbetsorder i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c2500a695fcffe0d60ac13b1b74cda4322b0e14
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437710"
---
# <a name="assets-and-work-orders"></a>Tillgångar och arbetsorder

[!include [banner](../../includes/banner.md)]

 

Det här avsnittet beskriver tillgångar och arbetsorder i tillgångshantering. Tillgångar och arbetsorder är de centrala delarna i funktionshanteraren. En *tillgång* är en maskin- eller maskindel som kräver kontinuerlig underhåll och service. Tillgångar kan skapas i en hierarkisk struktur och de kan relateras till funktionsplatser. Underhållsjobb kan planeras på alla nivåer i tillgångsstrukturen.

Olika data, till exempel produktinformation och tillgångsspecifikation och nödvändiga underhållsplaner ställs in för varje tillgång. Följande illustration visar en översikt över tillgångsdata och anslutning av tillgångar till jobbtyper. Röd text används för exempel som visar arv och beroenden.

![Diagram som visar tillgångsdata relaterade till jobbtyper](media/05-overview-image.png)

Varje arbetsorder har en arbetsordertyp, sådant förebyggande underhåll, avhjälpande underhåll eller inspektion. Arbetsordern innehåller ett eller flera arbetsorderjobb. Varje arbetsorderjobb definierar ett jobb som måste utföras på en tillgång och en relaterad jobbtyp. Exempel på relaterade jobbtyper är 10 000 km, 50 000 km, 1-års översyn och säkerhetsinspektion. En arbetsorder kan relateras till flera tillgångar.

Följande illustration visar en översikt över nyckeldata i en arbetsorder.

![Diagram som visar nyckeldata i en arbetsorder](media/06-overview-image.png)

En arbetsorder kan relateras till en annan arbetsorder och jobbtyper kan innehålla efterföljande jobb som skapar en arbetsorder. I allmänhet finns det inga beroenden mellan arbetsorder. Därför kan de ändra sitt livscykeltillstånd för arbetsorder och kan schemaläggas oberoende av varandra.

Arbetsorder kan skapas på olika sätt som är relaterade till korrigerande, förebyggande eller reaktivt underhåll. Du kan också skapa arbetsorder manuellt. Följande illustration visar en översikt över processen för automatisk eller manuell generering av arbetsorder.

![Diagram som visar automatisk eller manuell generering av arbetsorder](media/07-overview-image.png)

Flera steg måste slutföras när du vill schemalägga och köra ett underhållsjobb på en arbetsorder. Följande illustration visar en översikt över bearbetning för en arbetsorder.

![Diagram som visar översikt över bearbetning av en arbetsorder](media/08-overview-image.png)

> [!NOTE]
> I allmänhet när du arbetar i Dynamics 365 Supply Chain Management och modulen **tillgångshantering** väljer du **Ny** för att skapa en ny post, väljer **redigera** för att uppdatera en befintlig post och väljer **Spara** för att spara nya eller redigerade data.
