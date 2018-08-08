---
title: "Uppdatera standardkostnader för en ny tillverkad artikel"
description: "Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader för en ny tillverkad artikel."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79693
ms.assetid: ba64b70f-3f4c-4373-9a7d-8fd07c45a8cf
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1cfb04a98f7d01f7766bea97157ca3c44c51e326
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="update-standard-costs-for-a-new-manufactured-item"></a>Uppdatera standardkostnader för en ny tillverkad artikel

[!include [banner](../includes/banner.md)]

Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader för en ny tillverkad artikel. 

I följande riktlinjer förutsätts det att du bara använder tvåversionssättet när du vill uppdatera standardkostnader. I den här metoden, en kostnadsredovisningsversion innehåller standardkostnader som ursprungligen angetts för den frysta perioden, och den andra kostnadsredovisningsversion innehåller de inkrementella uppdateringarna som hör till de nya tillverkade artiklarna. De stegvisa uppdateringarna registreras som kostnadsposter i den andra kostnadsversionen, och aktiveras sedan slutligen. Tvåversionssättet innebär att du definierar en andra kostnadsredovisningsversion. Här följer riktlinjerna om hur du definierar denna kostnadsredovisningsversion:

-   Tilldela en kostnadskalkyleringstyp för **Standardkostnad**.
-   Tilldela ett unikt ID som anger innehållet för kostnadsredovisningsversionen, till exempel **2016-UPPDATERINGAR**.
-   I fältgruppen **Tillåt pristyper**, kontrollera att **Självkostnad** är inställd på **Ja**.
-   Tillåt att kostnadsposter anges för alla platser (d.v.s. lämnar **Plats**-fältet tomt). Om du anger en plats, kan kostnadsposter anges endast för den platsen.
-   Använd en reservprincip för **Aktiv**.

Följ dessa steg för att lägga till tillverkade artiklar under den låsta perioden.

1.  Använd **Kostnadsredovisningsversion**-sidan för att möjliggöra att kostnadsposter kan anges i den andra kostnadsredovisningsversionen som innehåller de inkrementella uppdateringarna. Förhindra aktivering av väntande kostnader, där aktivering tillåts när väntande kostnader har definierats på rätt sätt. Ange ett tomt fråndatum som princip i kostnadsversionen, och ange sedan fråndatumet när du registrerar respektive kostnadspost. Fråndatumet bör representera ett datum som infaller innan nya artiklar köps in eller tillverkas.
2.  Använd sidan **Artikelpris** för att registrera kostnadsposter för nya inköpta artiklar. För varje kostnadspost registrerar du kostnadsredovisningsversionen som innehåller stegvisa uppdateringar, och använder ett fråndatum som infaller före det förväntade tillverkningsdatumet för nya tillverkade artiklar.
3.  Beräkna kostnaden för nya tillverkade artiklar genom att använda sidan **Beräkning**. Öppna **Beräkning**-sidan från **Underhåll av kostnadsredovisningsversion**-sidan och välj sedan kostnadsredovisningsversionen som innehåller de inkrementella uppdateringarna. Använd urvalsvillkoret för att ange den nya tillverkade artikeln och dess tillverkade komponenter. I en produktstruktur med flera nivåer måste du kanske även identifiera alla överordnade artiklar som innehåller de nya tillverkade artiklarna som en komponent. Ange ett fråndatum för strukturlisteberäkningen som motsvarar startdatumet för tillverkningen av de nya tillverkade artiklarna. Fråndatumet måste finnas inom giltighetstiden för artikelns strukturlisteversion och flödesversion. **Obs!** En saknad kostnadspost kan ange en ny tillverkad artikel. Strukturlisteberäkningar kan begränsas till artiklar med saknade kostnader.
4.  Kontrollera att beräkningen av kostnaderna för nya tillverkade artiklar är korrekt och slutförd. Använd sidan **Slutfört** för att granska de beräknade kostnaderna för respektive artikelkostnadspost och även granska eventuella varningsmeddelanden i informationsloggen. Alternativt kan du använda sidan **Beräkning** om du vill granska de beräknade kostnaderna.
5.  Använd **Inställningar för kostnadsredovisningsversion**-sidan för att ändra spärrflaggan för att tillåta aktivering av de väntande kostnadsposterna i den andra kostnadsredovisningsversionen.
6.  Använd **Aktivera priser**-sidan (som du öppnar från sidan **Underhåll av kostnadsredovisningsversion**) för att aktivera alla väntande kostnadsposter i den andra kostnadsredovisningsversionen. Du kan även aktivera de väntande kostnadsposterna för enskilda artiklar genom att klicka på knappen **Aktivera** på sidan **Artikelpris**.
7.  För att förhindra ytterligare dataunderhåll, använd **Inställningar för kostnadsredovisningsversion**-sidan för att ändra spärrflaggorna i den andra kostnadsredovisningsversionen. Spärrprinciperna förhindrar registrering av nya pågående kostnader samt aktivering av pågående kostnader.





