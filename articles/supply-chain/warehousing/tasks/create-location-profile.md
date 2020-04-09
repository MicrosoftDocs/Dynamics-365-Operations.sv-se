---
title: Skapa en platsprofil
description: Det här avsnittet innehåller information om hur du skapar en platsprofil i Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 764d1dc1d7fb54e0fa14a681d6d3cdb1d829aa57
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146133"
---
# <a name="create-a-location-profile"></a>Skapa en platsprofil

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller information om hur du skapar en platsprofil i Dynamics 365 Supply Chain Management. Varje plats på lagerstället måste ha en platsprofil associerad som beskriver egenskaperna för platsen, till exempel om blandade artiklar tillåts för platsen. I den här proceduren skapar vi en profil för en plats som inte kräver kontroll av registreringsskylt. Vi ska aktivera blandade artiklar och blandad lagerstatus, samt tillåta rullande inventering. Du kan använda den här proceduren i demonstrationsdataföretaget USMF.


1. I navigeringsfönstret, gå till **Moduler > Lagerstyrning > Inställningar > Lagerställe > Platsprofiler**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Platsprofil-ID.**
4. Skriv ett värde i fältet **Namn**.
5. Ange eller välj ett värde i fältet **Platsformat.**
6. Ange eller välj ett värde i fältet **Platstyp.**
7. Ange eller välj ett värde i fältet **ID för lastkajshanteringsprofil**.
8. Välj **Ja** i fältet **Tillåt blandade artiklar**.
9. Välj **Ja** i fältet **Tillåt blandade lagerstatusar**.
10. Välj **Ja** i fältet **Tillåt rullande inventering**.
11. Välj **Spara**.

