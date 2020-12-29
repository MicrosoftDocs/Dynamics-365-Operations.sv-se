---
title: Uppdatering av standardkostnader i en icke-tillverkningsmiljö
description: Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader i en icke-tillverkningsmiljö.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09dca3012952b739a75a6930908752fba73a4550
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437616"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a>Uppdatering av standardkostnader i en icke-tillverkningsmiljö

[!include [banner](../includes/banner.md)]

Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader i en icke-tillverkningsmiljö.

I följande riktlinjer förutsätts det att du bara använder tvåversionssättet när du vill uppdatera standardkostnad. I den här metoden, en kostnadsredovisningsversion innehåller standardkostnader som ursprungligen angetts för den frysta perioden, och den andra kostnadsredovisningsversion innehåller de inkrementella uppdateringarna. Varje uppdatering anges som en kostnadspost som bifogas i den andra kostnadsredovisningsversionen och slutligen har aktiverats. Ett alternativ, enversionssättet, använder standardkostnadsuppsättningen som ursprungligen angetts. Tvåversionssättet innebär att du definierar en andra kostnadsredovisningsversion. Här följer riktlinjerna om hur du definierar denna kostnadsredovisningsversion:

-   Tilldela en kostnadskalkyleringstyp för **Standardkostnader**.
-   Tilldela ett meningsfullt ID som anger innehållet för kostnadsredovisningsversionen, till exempel **2016-UPPDATERINGAR**.
-   Kontrollera att innehållet inkluderar kostnadsposter.
-   Tillåt att kostnadsposter anges för alla platser. Om du anger en plats, kan kostnadsposter anges endast för den platsen.
-   Ange reservprincipen **Ingen**. Reservprincipen gäller endast för kostnadsberäkningar av tillverkade artiklar.

Utför följande steg om du vill korrigera, justera eller uppdatera standardkostnader för nya artiklar:

1.  Använd **Kostnadsredovisningsversion** **inställningar**-sidan för att möjliggöra att kostnadsdata kan anges i den andra kostnadsredovisningsversionen. Du kan även välja att förhindra att pågående kostnader aktiveras, så att aktiveringen tillåts när de pågående kostnaderna har definierats fullständigt och korrekt. Du kan också kan ange ett datum i **Från datum**-fältet. Som en allmän riktlinje bör du använda det datum då du tänker aktivera de stegvisa uppdateringarna. Du kan även lämna fältet **Från datum** tomt för kostnadsredovisningsversionen och sedan ange ett datum i fältet **Från datum** för varje kostnadspost.
2.  Använd **Artikelpris**-sidan för att ange uppdateringar som artikelkostnadsposter som bifogas i den andra kostnadsredovisningsversionen.
3.  Använd **Artikelpriser**-rapporten för att kontrollera att de artikelkostnadsposter som bifogas i den andra kostnadsredovisningsversionen är slutförda och korrekta.
4.  Använd **Underhåll av kostnadsredovisningsversion**-sidan för att ändra spärrflaggan för att tillåta aktivering av de väntande kostnadsposter som bifogas i den andra kostnadsredovisningsversionen.
5.  Använd **Aktivera priser**-sidan (som du öppnar från sidan **Underhåll av kostnadsredovisningsversion**) för att aktivera alla väntande artikelkostnadsposter som bifogas i den andra kostnadsredovisningsversionen. Du kan även aktivera de väntande kostnadsposterna för enskilda artiklar genom att klicka på knappen **Aktivera väntande pris** på sidan **Artikelpris**.
6.  För att förhindra ytterligare dataunderhåll, använd **Inställningar för kostnadsredovisningsversion**-sidan för att ändra spärrflaggorna som bifogas i den andra kostnadsredovisningsversionen. Spärrprinciperna förhindrar registrering av nya pågående kostnader samt aktivering av pågående kostnader.




