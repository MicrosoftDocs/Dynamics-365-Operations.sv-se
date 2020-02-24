---
title: Kreditgränsjusteringar
description: I det här avsnittet beskrivs hur du ställer in och lägger till justeringar av kreditgränser.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: f5e2fbe74d24c729711c6b96d5ff2b7f0c82922c
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015400"
---
# <a name="credit-limit-adjustments"></a>Kreditgränsjusteringar 

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Kreditgränsjusteringar gör att kreditchefer uppdaterar kreditgränserna och utgångsdatum för en enskild kund, en grupp med kunder eller alla kunder via en bokföringsprocess. Du kan lägga till poster för kreditgränsjustering för att uppdatera kunder och kundkreditgrupper, eller så kan du använda dem för att beräkna automatiska kreditgränser. Posterna kan sedan granskas, skickas för godkännande genom ett arbetsflöde och bokföras på kundkontona.

## <a name="set-up-credit-limit-adjustments"></a>Ange justering av kreditgräns

Du kan skapa poster i journalen för kreditgränsjustering på sidan **kreditgränsjustering** (**kredithantering \> kreditgränsjusteringar \> kreditgränsjusteringar**).

1. Välj **Ny**. En ny grupp med poster skapas som har ett kreditgränsjusteringsnummer.
2. Välj typ av kreditgränsjustering:

    - Välj **kreditgräns** om du vill ändra kundens kreditgräns.
    - Välj **tillfällig kreditgräns** om du vill skapa en tillfällig kreditgräns istället för att ändra kundens aktuella kreditgräns. Tillfälliga kreditgränser åsidosätter kundens kreditgräns för angiven period. När perioden är slut används kundens kreditgräns på nytt.
3. Ange en beskrivning. 

Om kryssrutan **bokförda** är markerad används kreditgränsen. Fältet **godkännande status** anger journalens arbetsflödesstatus. Arbetsflödet är tillval.

### <a name="add-credit-limit-adjustments"></a>Lägg till justering av kreditgräns

Om du vill lägga till kreditgränsjusteringar manuellt markerar du **rader** och följer sedan de här stegen.

1. Om du vill lägga till en kreditgränsjustering för en kund använder du menyn **kundjusteringar**. Om du vill lägga till en kreditgräns för en kundkreditgrupp, välj **Justeringar av kundkreditgrupp**.
2. Ange ett kundkonto för det fakturakundkonto som ska uppdateras med den nya kreditgränsen. Om du har valt **Justeringar av kundkreditgrupp** i steg 1 anger du kundkreditgruppen. Du kan inte ange både ett kundkonto och ett kundkreditgrupp-ID på samma journalrad.

    Den aktuella kreditgränsen visas och namnet visas automatiskt.

3. Ange den nya kreditgränsen som ska ersätta den aktuella kreditgränsen när kreditgränsposten bokförs.
4. Ange ett datum för att definiera det nya utgångsdatumet för kundkreditgränsen. Du måste ange en kreditgräns som utgångsdatum när du skapar en kreditgränsjustering.

Fältet **godkännande status** anger journalradens arbetsflödesstatus.

Om du vill att kreditgränsjusteringarna ska genereras automatiskt kan du använda **generera**-menyn i åtgärdsfönstret.
 
### <a name="add-temporary-credit-limit-adjustments"></a>Lägg till tillfälliga justeringar av kreditgräns

Om du vill lägga till tillfälliga kreditgränsjusteringar manuellt följer du de här stegen för journalrader.

1. Om du vill lägga till en kreditgränsjustering för en kund använder du menyn **kundjusteringar**. Om du vill lägga till en kreditgräns för en kundkreditgrupp, välj **Justeringar av kundkreditgrupp**.
2. Ange ett kundkonto för det fakturakundkonto som ska uppdateras med den nya kreditgränsen. Om du har valt **Justeringar av kundkreditgrupp** i steg 1 anger du kundkreditgruppen. Du kan inte ange både ett kundkonto och ett kundkreditgrupp-ID på samma journalrad.

    Om en aktiv eller framtida kreditgräns redan finns visas aktuella tillfälliga kreditgränser och datumintervall för varje tillfällig kreditgräns. Namnet visas automatiskt.

3. Ange den nya kreditgränsen som ska ersätta den aktuella kreditgränsen.
4. I fälten **nytt från-datum** och **nytt till-datum** definierar du den period då den avancerade kreditgränsen är giltig. Du måste ange en kreditgräns som utgångsdatum när du skapar en journal för kreditgränsjustering.

Fältet **godkännande status** anger journalradens arbetsflödesstatus.

## <a name="generate-credit-limit-adjustments"></a>Generera justering av kreditgräns

Du kan också justera kreditgränserna automatiskt. I åtgärdsfönstret, välj **Generera** och välj sedan ett av följande alternativ:

- Från befintligt kund
- Från befintlig kundkreditgrupp
- Automatiska kreditgränser

### <a name="from-existing-customer"></a>Från befintligt kund

Du kan skapa journalrader utifrån befintliga kunder. När du väljer **generera \> från befintlig kund**, visas en dialogruta där du kan ange kriterier för val av kunder och beräkning av de nya gränserna.

1. Ange ett justeringsvärde om du vill lägga till eller dra ifrån ett belopp från kreditgränsen. Ange ett negativt värde om du vill minska den aktuella kreditgränsen eller ett positivt värde om du vill öka värdet.
2. I fältet **värdetyp** välj hur värdet som du angav i steg 1 ska användas för att beräkna den nya kreditgränsen:

    - Välj **fast värde** om du vill ändra kreditgränsen med ett belopp.
    - Välj **procent** om du vill ändra kreditgränsen med en procentsats.

3. Ange ett värde som används för att avrunda den beräknade kreditgränsen. Ange t.ex. **10,00** för att avrunda kreditgränsen till närmaste 10,00 valutaenhet.
4. Ange fältet **avrundningsformulär** för att ange om resten ska avrundas upp eller ner.
5. Välj den metod som används för att justera datum.

    - Om du väljer **absolut** kan du ange de datum som definierar datumintervallet för kreditgränserna.
    - Om du väljer **relativ** kan du ange förskjutningsdatum för intervallet. Det aktuella datumintervallet för kreditgränsen kommer att justeras efter förskjutningen.

6. Använd snabbfliken **Poster att inkludera** för att filtrera listan med kunder som ingår. Om du inte inkluderar filter genereras kreditgränsposter för alla kunder.
7. Klicka på **OK** om du vill skapa poster för kreditgränsjustering.

### <a name="from-existing-customer-credit-group"></a>Från befintlig kundkreditgrupp

Du kan skapa journalrader utifrån befintliga kundkreditgrupper. När du väljer **generera \> från befintlig kund**, visas en dialogruta för kreditgrupp där du kan ange kriterier för val av kundkreditgrupper och beräkning av de nya gränserna. Kriterierna är samma kriterier som används för att skapa journalrader från befintliga kunder. Se stegen i föregående avsnitt.

### <a name="automatic-credit-limits"></a>Automatiska kreditgränser

Du kan skapa automatiska kreditgränser för att definiera och uppdatera kundkreditgränser. De automatiska kreditgränserna skapas för en riskgrupp och baseras på specifika värden som används i poänggrupperna. Du kan använda dessa automatiska kreditgränser för att generera kreditgränsposter. Om en kund har tilldelats en specifik riskgrupp och kundens kreditinformation matchar kriterierna för en automatisk kreditgräns, skapas en justeringspost för kreditgräns.

#### <a name="create-automatic-credit-limits"></a>Skapa automatiska kreditgränser

Du skapar automatiskt kreditgränser genom att använda kreditgränsjusteringar. När du väljer **generera \> automatiska kreditgränser** visas en dialogruta där du kan ställa in ett utgångsdatum för de nya kreditgränser som ska skapas utifrån de riskgrupper som kunder tilldelas till. När du är klar väljer du **OK** för att skapa justeringsraderna för kreditgränsen.

### <a name="post-adjustments"></a>Bokföringsjusteringar

När du har skapat justeringsrader för kreditgräns kan du använda knappen **bokför** i åtgärdsfönstret för att bokföra transaktionerna och uppdatera kundens kreditgränser. Om du har ställt in ett arbetsflöde måste du emellertid välja **arbetsflöde \> skicka** i åtgärdsfönstret för att skicka journal till godkännande.

### <a name="credit-limit-adjustments-workflows"></a>Arbetsflöden för justering av kreditgräns

Arbetsflödet **justering av kreditgräns** kan användas för att skicka kreditgränsjusteringar via ett arbetsflödes godkännandeprocess. Du kan skapa två arbetsflöden på sidan **Arbetsflöde för kredithantering** (**kredithantering \> inställningar \> arbetsflöde för kredithantering**):

- **Kreditgränsjusteringar** – det här arbetsflödet kan användas för att godkänna poster på rubriknivå.
- **Rad för kreditgränsjusteringar** – det här arbetsflödet kan användas för att godkänna justeringsposterna så att transaktionerna kan godkännas av olika personer, baserat på kriterierna i arbetsflödet.

> [!NOTE]
> När du skapar arbetsflödet **kreditgränsjusteringar** kan du ställa in det så att justeringarna bokförs automatiskt när raderna har godkänts. Ta bara med **bokföra journalen automatiskt** i arbetsflödet.
