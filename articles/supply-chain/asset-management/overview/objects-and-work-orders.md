---
title: Tillgångar och arbetsorder
description: Det här avsnittet beskriver tillgångar och arbetsorder i tillgångshantering.
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
ms.openlocfilehash: 5bd55988578be2b0287b399549f17642bfb1693b
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783596"
---
# <a name="assets-and-work-orders"></a>Tillgångar och arbetsorder

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Det här avsnittet beskriver tillgångar och arbetsorder i tillgångshantering. Tillgångar och arbetsorder är de centrala delarna i funktionshanteraren. En *tillgång* är en maskin- eller maskindel som kräver kontinuerlig underhåll och service. Tillgångar kan skapas i en hierarkisk struktur och de kan relateras till funktionsplatser. Underhållsjobb kan planeras på alla nivåer i tillgångsstrukturen.

Olika data, till exempel produktinformation och tillgångsspecifikation och nödvändiga underhållsplaner ställs in för varje tillgång. Följande illustration visar en översikt över tillgångsdata och anslutning av tillgångar till jobbtyper. Röd text används för exempel som visar arv och beroenden.

![Figur 1](media/05-overview-image.png)

Varje arbetsorder har en arbetsordertyp, sådant förebyggande underhåll, avhjälpande underhåll eller inspektion. Arbetsordern innehåller ett eller flera arbetsorderjobb. Varje arbetsorderjobb definierar ett jobb som måste utföras på en tillgång och en relaterad jobbtyp. Exempel på relaterade jobbtyper är 10 000 km, 50 000 km, 1-års översyn och säkerhetsinspektion. En arbetsorder kan relateras till flera tillgångar.

Följande illustration visar en översikt över nyckeldata i en arbetsorder.

![Figur 2](media/06-overview-image.png)

En arbetsorder kan relateras till en annan arbetsorder och jobbtyper kan innehålla efterföljande jobb som skapar en arbetsorder. I allmänhet finns det inga beroenden mellan arbetsorder. Därför kan de ändra sitt livscykeltillstånd för arbetsorder och kan schemaläggas oberoende av varandra.

Arbetsorder kan skapas på olika sätt som är relaterade till korrigerande, förebyggande eller reaktivt underhåll. Du kan också skapa arbetsorder manuellt. Följande illustration visar en översikt över processen för automatisk eller manuell generering av arbetsorder.

![Figur 3](media/07-overview-image.png)

Flera steg måste slutföras när du vill schemalägga och köra ett underhållsjobb på en arbetsorder. Följande illustration visar en översikt över bearbetning för en arbetsorder.

![Figur 4](media/08-overview-image.png)

> [!NOTE]
> I allmänhet när du arbetar i Microsoft Dynamics 365 for Finance and Operations och modulen **tillgångshantering** väljer du **Ny** för att skapa en ny post, väljer **redigera** för att uppdatera en befintlig post och väljer **Spara** för att spara nya eller redigerade data.
