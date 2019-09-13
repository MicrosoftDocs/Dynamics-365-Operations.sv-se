---
title: Skapa en ny layout för lagerställe
description: I det här avsnittet beskrivs hur du ställer in information om platser i ett lagerställe.
author: perlynne
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 302c028a93dfdb57972e4759abbbc4fdedabbd17
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867255"
---
# <a name="create-a-new-warehouse-layout"></a>Skapa en ny layout för lagerställe

[!include [task guide banner](../../includes/task-guide-banner.md)]

I det här avsnittet beskrivs hur du ställer in information om platser i ett lagerställe. Detta gäller endast lagerställen som skapats med hjälp av ”grundläggande lagerstyrning” i lagerhanteringmodulen och inte för lagerställen som skapats i lagerstyrningsmodulen. Du kan använda den här proceduren i demonstrationsföretaget USMF eller med dina egna data.


## <a name="set-the-default-location-capacity"></a>Ange standardplatskapaciteten
1. I navigeringsfönstret, gå till **Moduler > Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning**.
2. Välj fliken **Platser**.
3. Välj ett nummer i fältet **Standardbredd.**
4. Välj ett nummer i fältet **Standarddjup.**
5. Välj ett nummer i fältet **Standardhöjd.**
6. Välj **Spara**.
7. Stäng sidan.

## <a name="define-the-location-name-format"></a>Definiera platsnamnformatet
1. I navigeringsfönstret, gå till **Moduler > Lagerhantering > Inställningar > Lagerindelning > Lagerställen**.
2. Välj **Ny**.
3. Ange ett värde i fältet **Lagerställe**.
4. Skriv ett värde i fältet **Namn**.
5. På fält **Plats** klicka på önskad post från sökningen.
6. Växla utökningen av avsnittet **Platsnamn**. Alternativen i detta avsnitt definierar standardformatet på platsnamn. I vårt exempel ska vi inkludera gångnummer, ställningsnummer och hyllnummer.  
7. Ange alternativet **Inkludera gång** till **Ja**.
8. Ange alternativet **Inkludera ställning** till **Ja**. 
9. I fältet **Format** skriver du in ett värde för ställningen.
10. Ange alternativet **Inkludera hylla** till **Ja**.
11. I fältet **Format** skriver du in ett värde för hyllan.

## <a name="define-warehouse-locations"></a>Definiera lagerställesplatser
1. Klicka på **Lagerställe** i åtgärdsfönstret.
2. Välj **Platsguide**.
3. Välj **Nästa**.
4. Avmarkera alternativet **Utlastningsplatser**
5. Avmarkera alternativet **Bulkplatser**
6. Välj **Nästa** tills du kommer till det här alternativet för att välja **Slutför**.
7. Stäng sidan.
8. Uppdatera sidan.

