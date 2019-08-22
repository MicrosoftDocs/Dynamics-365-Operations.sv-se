---
title: Ställa in policyer för lagerarbete (ansökan, maj 2016 )
description: Lagerställeprocesser inkluderar inte alltid lagerarbete.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 23ad33a2f070a33e4e658870561406c4604f4dce
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847073"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a>Ställa in policyer för lagerarbete (ansökan, maj 2016 )

[!include [task guide banner](../../includes/task-guide-banner.md)]

Lagerställeprocesser inkluderar inte alltid lagerarbete. Genom att definiera en arbetspolicy kan du förhindra skapande av arbete för råmaterialhämtning och inlagring av färdiga varor för en uppsättning av produkter på specifika platser. Det USMF-demonstrationsdataföretag användes för att skapa den här registreringen. Den här uppgiftsguiden kräver Dynamics AX program 7.0.1 eller senare.

1. Gå till Lagerstyrning > Inställningar > Arbete > Arbetspolicyer.
2. Klicka på Ny.
3. Skriv in "Inget inlagrat arbete" i fältet Namn på arbetspolicy.
4. Klicka på Spara.
5. Klicka på Lägg till.
6. Markera vald rad i listan.
7. Skriv in "Plats för slutförda varor" i fältet Typ av arbetsorder.
8. Klicka på Lägg till.
9. Markera vald rad i listan.
10. Välj ”Plats för samprodukt och biprodukt” i fältet Typ arbetsorder.
11. Visa avsnittet Lagerplatser.
12. Klicka på Lägg till.
13. Markera vald rad i listan.
14. Ange ”51" i lagerställets lista.
15. Ange eller välj "001" i fältet Plats.
16. Expandera avsnittet Produkter.
17. Välj "Markerad" i fältet Produktval.
18. Klicka på Lägg till.
19. Markera vald rad i listan.
20. Ange eller välj "L0101" i fältet Artikelnummer.
21. Klicka på Spara.

