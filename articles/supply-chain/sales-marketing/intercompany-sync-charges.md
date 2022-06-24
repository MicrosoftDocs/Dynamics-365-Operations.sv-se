---
title: Synkronisera koncerninterna avgifter
description: Denna artikel förklarar synkronisering av koncerninterna avgifter
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: e7b3de3d7da7be6c1c8b5c3842862e7bccd78277
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857298"
---
# <a name="synchronize-intercompany-charges"></a>Synkronisera koncerninterna avgifter

[!include [banner](../../includes/banner.md)]

Avgifter synkroniseras endast mellan en koncernintern försäljningsorder och en koncernintern inköpsorder, och synkroniseringen genomförs alltid.

Om fältet **Tillåt prisredigering** har markerats på den koncerninterna inköpsordern eller den koncerninterna försäljningsordern kan du manuellt lägga till en avgift på försäljningsordern eller inköpsordern. Annars kan du inte.

Om fältet **Tillåt prisredigering** inte har markerats på den koncerninterna försäljningsordern kan du inte lägga till avgifter manuellt på försäljningsordern.

Om fältet **Tillåt prisredigering** inte har markerats på den koncerninterna inköpsordern kan du inte lägga till avgifter på inköpsordern.

Om fältet **Tillåt prisredigering** är aktiverat på både koncerninterna inköpsordern och koncerninterna försäljningsordern kan du lägga till avgifter manuellt på båda order. Detta kan dock leda till att många avgifter läggs till på fel sätt.

Den bästa metoden att undvika den här typen av konflikter är att tillåta att avgifter kan läggas till antingen på koncerninterna försäljningsorder eller på koncerninterna inköpsorder men inte på båda.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
