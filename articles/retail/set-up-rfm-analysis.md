---
title: "Ställ in aktualitets-, frekvens- och monetär (RFM) analys"
description: "Det här avsnittet innehåller information om hur du ställer in recency, frekvens och monetär analys (RFM) för dina kunder."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRRFMDefinition
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 4314c81823940ce3192da23dfdf777e8ebf781f2
ms.contentlocale: sv-se
ms.lasthandoff: 01/04/2019

---

# <a name="set-up-recency-frequency-and-monetary-rfm-analysis"></a>Ställ in aktualitets-, frekvens- och monetär (RFM) analys

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller information om hur du ställer in recency, frekvens och monetär analys (RFM) för dina kunder.

Aktualitet, frekvens och monetär (RFM) analys är ett marknadsföringsverktyg som din organisation kan använda för att utvärdera de data som skapas av kundens inköp. När du har ställt in RFM-analys tilldelas kunderna en beräknad RFM-poäng när de gör inköp. RFM-poängen kan vara en tresiffrig klassificering eller ett aggregerat tal, beroende på hur din organisation har konfigurerat RFM-analysen. Så här fungerar värderingen om organisationen använder en tresiffrig klassificering för poängresultat:

- Den första siffran är kundens aktualitetsklassificering, d.v.s. hur nyligen kunden gjorde ett inköp från din organisation.
- Den andra siffran är kundens frekvensbedömning, d.v.s. hur ofta kunden gör inköp från din organisation.
- Den tredje siffran är kundens monetära värdering, d.v.s. hur mycket kunden spenderar när den gör inköp från din organisation.

Till exempel, din organisation har satt betyg på en skala från 1 till 5, där 5 är högsta betyg. I detta fall en kund värdering av 535 berättar dig följande information om kunden:

- **Aktualitet värdering av 5** – kunden har nyligen gjort ett köp.
- **Bedömning av frekvens av 3** – Kunden köper produkter från din organisation måttligt ofta.
- **Monetär värdering 5** – När kunden gör ett köp spenderar den en avsevärd summa pengar.

Om din organisation använder en sammanlagd siffra för tjoget, den individuella betyg läggs ihop. För samma exempel, kunden har en värdering av 13 (5 + 3 + 5).

## <a name="to-set-up-rfm-analysis-for-the-customers-in-your-organization"></a>Ställ in RFM-analys för kunderna i din organisation.

1. Gå till **Kundtjänst** \> **Periodisk** \> **RFM-analys**.
2. Välj **Ny** på sidan **RFM-analys**. Ange ett beskrivande namn på RFM-definitionen i fältet **RFM-definition**. Du kan till exempel kalla definitionen RFM-A.
3. Ange start- och slutdatum för den här RFM-definitionen.
4. Gör följande på snabbfliken **Allmänt**:

    - Om varje del av RFM-poängen måste innehålla ett likvärdigt antal kunder markerar du kryssrutan **Jämn distribution**.
    - Markera kryssrutan **Lägg till poäng** om du vill lägga samman de tre poängen. Detta ger till exempel en kund en RFM-poäng på 13 istället för 535.
    - Markera kryssrutan **Spara historik** om du vill att systemet ska spara statistiska uppgifter för kunder, så att dessa kan användas för att beräkna RFM-poäng.

5. Gör följande på snabbfliken **Aktualitet**:

    - Ange antalet avdelningar, eller grupper, som ska användas för att beräkna poängen recency för kunder i fältet **Indelningar**. Om du till exempel har 100 kunder innebär en indelning i 5 att det finns 20 kunder för varje poäng. 20 kunder som har gjort inköp helt nyligen har aktualitetspoäng 5. Nästa 20 kunder har en aktualitetspoäng på 4 osv. Om du har 50 kunder, har 10 kunder en recencyställning på 5, 10 har en recencyställning på 4, och så vidare.
    - I fältet **Prioritet** väljer du hur stor viktning parametern recency ska ha i förhållande till de andra parametrarna när RFM-poängen beräknas för en kund. Du kan till exempel lägga mer värde på recencypoängen än på den monetära poängen.
    - I fältet **Multiplikator** anger du det värde som aktualitetspoängen ska multipliceras med. Om du inte anger något värde kommer poängen inte att multipliceras.
    - Välj den tidsperiod för vilken aktualitetspoängen beräknas i fältet **Period**. Till exempel per vecka eller per månad.

6. Gör följande på snabbfliken **Frekvens**:

    - Ange antalet avdelningar, eller grupper, som ska användas för att beräkna frekvenspoängen för kunder i fältet **Indelningar**.
    - I fältet **Prioritet** väljer du hur stor viktning frekvensparametern ska ha i förhållande till de andra när RFM-poängen beräknas för en kund.
    - I fältet **Multiplikator** anger du det värde som frekvenspoängen ska multipliceras med. Om du inte anger något värde kommer poängen inte att multipliceras.

7. Gör följande på snabbfliken **Monetär**:

    - Ange antalet avdelningar, eller grupper, som ska användas för att beräkna monetär poäng för kunder i fältet **Indelningar**.
    - I fältet **Prioritet** väljer du hur stor viktning monetärparametern ska ha i förhållande till de andra när RFM-poängen beräknas för en kund.
    - I fältet **Multiplikator** anger du det värde som monetära poäng ska multipliceras med. Om du inte anger något värde kommer poängen inte att multipliceras.
    - I fältet **Brutto/netto** anger du om kundens monetära poäng ska beräknas genom att använda brutto- eller nettofakturabeloppet.
    - Om en kunds returbelopp ska dras från kundens totala fakturaberäkning markerar du kryssrutan **Subtrahera returer**.

## <a name="view-a-customers-rfm-score"></a>Visa en kunds RFM-poäng

Använd den här proceduren när du vill visa en kunds RFM-poäng.

1. Gå till **Kundtjänst** \> **Journaler** \> **Kundtjänst**.
2. På sidan **Kundtjänst** i fönstret **Kundtjänst** väljer du nyckelordtypen du vill söka på och anger sedan söktexten i sökfälten.
3. Välj **Sök**.
4. På sidan **Kundtjänst** markera kundposten som du vill använda och klicka sedan på **Välj kund**.

RFM-poängen visas i gruppen **Orderhistorik** till höger på sidan **Kundtjänst**.

## <a name="view-or-clear-the-history-of-an-rfm-analysis-record"></a>Visa eller ta bort historik för en RFM-analyspost

Använd den här proceduren när du vill visa eller ta bort historik för en RFM-post.

1. Gå till **Kundtjänst** \> **Periodisk** \> **RFM-analys**.
2. På sidan **RFM-analys**, välj den post som du vill visa.
3. Klicka på snabbfliken **Historik** om du vill visa posthistoriken.
4. Klicka på snabbfliken **Rensa historik** om du vill rensa posthistoriken.

