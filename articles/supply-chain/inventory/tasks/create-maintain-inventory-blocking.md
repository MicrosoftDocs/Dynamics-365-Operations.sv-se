---
title: Skapa och underhålla en lagerspärr
description: I den här proceduren visas hur du kan förhindra den fysiska lagerbehållningen från att reserveras av andra utgående källdokument genom att använda lagerspärren.
author: perlynne
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12c6e047e15aaab157e6de70f4a09f500af2965f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437934"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Skapa och underhålla en lagerspärr

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du kan förhindra den fysiska lagerbehållningen från att reserveras av andra utgående källdokument genom att använda lagerspärren. Du kan köra proceduren i demonstrationsdataföretaget USMF med hjälp av exempelvärdena som visas. Du behöver ha en artikel med fysisk lagerbehållning tillgänglig innan du startar den här proceduren.


## <a name="create-an-inventory-blocking"></a>Skapa en lagerspärr
1. I **navigeringsfönstret**, gå till **Moduler > Lagerhantering >Periodiska uppgifter > Lagerspärr**.
2. Klicka på **Ny**.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelnummer**.
4. Välj den artikel som du vill ha i listan. Välj ett artikelnummer med fysisk lagerbehållning som du vill spärra. Om du använder USMF kan du välja artikeln M9201.  
5. Ange ett nummer i fältet **Kvantitet**. Om du använder artikeln M9201 måste du välja lägre än 200.
6. Expandera snabbfliken **Lagerdimensioner.**
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagerställe**.
8. Hitta och markera önskad post i listan. Om du använder artikeln M9201 kan du välja lager 51.  
9. Klicka på **Spara**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Uppdatera villkoren för lagerspärrren
1. Ange ett nummer på snabbfliken **Allmänt**, i fältet **Kvantitet**. Uppdatera lagerkvantitetsfältet som speglar kvantiteten som ska spärras.  
2. Ange ett datum i fältet **Förväntat datum.** Du kanske vill ange när det spärrade lagret förväntas bli tillgängligt för reservation genom att tilldela ett förväntat datum. Om du väljer alternativet Förväntade inleveranser för lagerspärren som anges som standard när du skapar en spärr manuellt, kommer detta datum visas på den förväntade transaktionen.  
3. Klicka på **Spara**.

## <a name="remove-the-inventory-blocking"></a>Ta bort lagerspärren
1. Klicka på **Ta bort** i **åtgärdsfönstret**.
2. Klicka på **Ja**.
3. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]