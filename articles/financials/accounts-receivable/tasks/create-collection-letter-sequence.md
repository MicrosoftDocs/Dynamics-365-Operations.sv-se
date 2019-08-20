---
title: Skapa in en kravbrevsserie
description: Använd den här uppgifthandbok om du vill skapa ett kravbrev sekvens.
author: mikefalkner
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a317fba4f30ab9fefe6b12637d53fda141d354bf
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843035"
---
# <a name="create-a-collection-letter-sequence"></a>Skapa in en kravbrevsserie

[!include [task guide banner](../../includes/task-guide-banner.md)]

Använd den här uppgifthandbok om du vill skapa ett kravbrev sekvens. I den här uppgiften används demonstrationsföretaget USMF.

1. I navigeringsfönstret, gå till **Moduler > Kredit och inkasso > Inställningar > Ställ in kravbrevsserier**.
2. Klicka på **Ny**.
3. Ange sekvens-ID för att representera sekvensen i fältet **Kravbrevsserie**. Detta kan användas, när du ställer in en bokföringsprofil.
4. I fältet **Beskrivning** anger du ett värde.  Betalningsvillkoren är valfri. Om du anger ett värde här, ska kravbrevsavgift fakturan använda dessa betalningsvillkor istället för de betalningsvillkor som lagras med kunden.  
5. I fältet **kravbrevskod** väljer du koden för det första kravbrev som du vill skicka. Det första kravbrevet skapas med hjälp av förfallodatumet på fakturan, det värde som du anger för respitperioden i fältet och den information som du anger på denna rad.  
6. I fältet **Beskrivning** anger du ett värde. Valutan för avgiften anpassas till kundens valuta. Denna valutakod kan skilja sig från fakturavalutan.  
7. Klicka på **Lägg till** om du vill lägga till nästa kravbrev som ska skickas i sekvensen I många fall är det första kravbrevet bara en varning. Du kan lägga till tillägg, om det behövs.  
8. Välj kod för nästa kravbrev som du vill skicka i sekvensen.
9. I fältet **Beskrivning** anger du ett värde.
10. Välj intäktskontot som ska användas för tillägg i fältet **huvudkonto**.
11. Ange den avgift som debiteras kravbrev, när den bokförs.
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelmomsgrupp**. Ange en artikelmomsgrupp, om moms måste beräknas på avgiften.  
13. Klicka på länken på den valda raden i listan.
14. I fältet **Minsta förfallet saldo** anger du det minsta förfallna saldot som krävs innan ett kravbrev skickas.
15. I fältet **Dagar** ange antalet respitdagar som tillåts. Detta är antal dagar efter förfallodatumet att ett kravbrev kan genereras. Förfallodatumet, som används för beräkning, beror på positionen för kravbrevet i kravbrevsekvensen:
    - Respitperioden för kravbrev 1 är relativ till förfallodatumet på fakturan.
    - Respitperioden för kravbrev 2 och högre är relativ till datum, att föregående kravbrevet bokförs eller skriva ut, beroende på vad som valts i fältet för uppdateringkravbrevkoden i kundreskontraparametersidan.  
16. Klicka på **Lägg till** om du vill lägga till det sista kravbrevet i sekvensen. Du kan lägga till upp till fem kravbrevskoder för en kravbrevsserie.  
17. I fältet **kravbrevskod** väljer du nästa kravbrev som du vill skicka i sekvensen.
18. I fältet **Beskrivning** anger du ett värde.
19. Ange önskade värden i fältet **Huvudkonto**.
20. Ange ett nummer i fältet **Avgift i valuta**.
21. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelmomsgrupp**.
22. Klicka på länken på den valda raden i listan.
23. Ange ett värde i fältet **Minsta förfallet saldo**.
24. Välj ett tal i fältet **Dagar**.
25. Markera kryssrutan **Spärra** om du vill stoppa ytterligare leveranser till och fakturering av kunden. Om du vill ta bort spärren från kontot väljer du **Nej** i fältet Spärrad fakturering och leverans på sidan Kunder.  
26. Expandera snabbfliken **Anmärkning**.
27. Ange den text som ska visas i kravbrevet för den valda kravbrevskoden. Du kan översätta den här texten in på språk med hjälp av översättningsmenyn över anmärkningsasken.  

