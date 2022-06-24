---
title: Periodiseringstidsplaner i intäkts- och utgiftsperiodiseringar
description: Detta ämne beskriver periodiseringstidsplaner i intäkts- och utgiftsperiodiseringar.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 093005f9b66d7ce741689b55612f006fa5123910
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903375"
---
# <a name="deferral-schedules"></a>Periodisringsplaner

Periodiseringstidsplaner skapas efter att en transaktion har bokförts.

På sidorna **Alla periodiseringstidsplaner** och **Aktiva periodiseringstidsplaner** kan du visa all information om ett periodiseringsschema. Vilken information som visas beror på typen av periodiseringsschema (linjär eller händelsebaserad) samt transaktionstypen. Den omfattar de tidsplansraderna för periodisering samt totalbeloppen för periodiseringstidsplanen. Du kan använda sidan för att redigera periodiseringstidsplanen.

## <a name="recognize-revenue"></a>Beakta intäkt

> [!NOTE]
> - Om du vill beakta intäkt för en periodiseringstidsplan börjar du med steg 1.
> - Om du vill beakta intäkt för flera periodiseringstidsplaner börjar du med steg 2.

1. På sidan **Alla periodiseringstidsplaner**, i rutnätet **Tidsplansrader**, väljer du de rader du vill beakta och sedan **Beakta**.
2. på sidan **redovisningsbearbetning** anger du fältet **redovisningsåtgärd** som **Skapa redovisningsjournal**.
3. I fältet **Slutdatum** väljer du slutdatum. Bearbetningen kommer endast att innehålla rader där slutdatumet är tidigare än eller samma som det valda slutdatumet.
4. Välj **Filter** och lägg till datafilter så att listan bara visar det postintervall du vill ha.
5. Välj **Visa förhandsgranskning** om du vill visa raderna.
6. Markera de rader som du inte vill bearbeta i listan med rader och välj sedan **Ta bort**.
7. Välj om du vill sammanfatta redovisningsjournalposten.
8. I avsnittet **Transaktionsdatum** kan du åsidosätta transaktionsdatumet med ett visst datum för att bearbeta transaktionen. Transaktionsdatumet kan anges för stängda perioder.
9. Om du vill bearbeta som en del av ett batchjobb väljer du **Batch**. i dialogrutan **Batchbearbetning** anger du parametrarna för batchen och väljer sedan **OK** för att återgå till sidan **redovisningsbearbetning**. Intäktsredovisningen bearbetas senare, när batchen bearbetas.
10. Välj **Process**. Om du inte lagt till transaktionen i ett batchjobb bearbetas alla rader omedelbart. Annars bearbetas raderna när batchen bearbetas.

## <a name="modify-a-schedule"></a>Ändra en tidsplan

För att redigera en periodiseringstidsplan, följ dessa steg.

1. På sidan **Alla periodiseringstidsplaner** väljer du periodiseringsschemat och sedan **Redovisning \> Ändra tidsplan**.
2. På sidan **Ändra tidsplan** redigerar du de alternativ du vill ändra. Beroende på tidsplaneringsschema kan du inte ändra samtliga alternativ.
3. Välj **Förhandsversion** för att granska periodiseringstidsplanen.
4. Välj **OK**.

### <a name="straight-line-deferral-schedules"></a>Linjöra periodiseringstidsplaner

Om periodiseringstidsplanen inte har några redovisade eller externt bokförda rader kan du ändra hela periodiseringstidsplanen, inklusive startdatumet.

Om periodiseringstidsplanen har några redovisade eller externt bokförda rader och du ändrar periodiseringstidsplanen, beror resultatet av periodiseringstidsplanen på omberäkningsdatumet och periodiseringsslutdatumet för redovisade rader. Som standard bestäms periodiseringens slutdatum av den första period som inte redovisats.

Om du vill använda redovisningsdatumet väljer du ett av följande värden i fältet **Start för tidsplan**: 
- **Kompensation** – Kvarvarande belopp efter att alla redovisade rader har omberäknats.
- **Återföring** – Alla rader efter omberäkningsdatumet återförs med det angivna journalnamnet och bokföringsdatumet. Beloppet efter omberäkningsdatumet beräknas sedan om.

Om en mall används ignoreras de ignorerade perioderna, och mallen används bara för att beräkna slutdatumet.

### <a name="event-based-deferral-schedules"></a>Händelsebaserade periodiseringstidsplaner

För en händelsebaserad periodiseringstidsplan kan du ändra alla icke-identifierade rader.

Om periodiseringstidsplanen har några redovisade eller externt bokförda rader kan du inte ändra mall och tilldelningstyp för periodiseringstidsplanen. När du ändrar ett befintligt periodiseringsschema kan du inte ändra värdet för fältet **Skapa separata händelser per enhet**.

Om en rad har redovisats eller bokförts externt, markeras kryssrutan **Redovisad**.

## <a name="modify-a-deferral-or-recognition-account"></a>Ändra ett periodiserings- eller redovisningskonto

Följ de här stegen om du vill ändra periodiserings- eller redovisningskonto för en periodiseringstidsplan.

1. På sidan **Alla periodiseringstidsplaner** väljer du periodiseringstidsplanen och därefter **Redovisning \> Ändra konto**.
2. På sidan **Ändra konto** väljer du det konto som du vill ändra (periodisering, kortfristigt eller redovisning).
3. I fältet **Nytt konto** markerar du ett nytt konto.
4. Välj om ändringar i kontot ska skapa justeringsjournalposter.
5. Om du ställer in alternativet som **Ja** i föregående steg ska du välja journalnamnet i fältet **Journalnamn** och ange transaktionsdatumet i fältet **Transaktionsdatum**.
6. Välj **OK**.

## <a name="put-a-deferral-schedule-on-hold"></a>Spärra en periodiseringstidsplan

Följ dessa steg för att spärra en periodiseringstidsplan.

1. På sidan **Alla periodiseringstidsplaner** väljer du periodiseringstidsplanen och därefter **Spärra \> Placera spärr**.
2. På sidan **Placera spärr** väljer du om du vill överföra saldot från periodiseringskontot eller spärrkontot.
3. Om du vill överföra balansen väljer du journalnamnet i fältet **Journalnamn** väljer du spärrkontot i fältet **Spärrkonto** och sedan transaktionsdatumet i fältet **Transaktionsdatum**.
4. Välj **OK**.

## <a name="remove-a-hold-from-a-deferral-schedule"></a>Ta bort en spärr från en periodiseringstidsplan

Om du vill ta bort en spärr från en periodiseringstidsplan följer du dessa steg.

1. I listan **Alla periodiseringstidsplaner** väljer du periodiseringstidsplanen och därefter **Spärra \> Ta bort spärr**.
2. I fältet **Journalnamn** väljer du journalnamnet.
3. I fältet **Transaktionsdatum** anger du transaktionsdatumet.
4. Välj **OK**.

## <a name="cancel-unrecognized-amounts"></a>Annullera icke-beaktade belopp

> [!NOTE]
> Alla rader som redan har bokförts eller bokförts externt exkluderas från denna process.

Följ dessa steg för att avbryta icke-redovisade belopp i en periodiseringstidsplan.

1. På sidan **Alla periodiseringstidsplaner** väljer du periodiseringsschemat och sedan **Avbryt \> Icke-redovisade belopp**.
2. På sidan **Annullera icke-redovisade belopp** väljer du om du vill skapa annuleringsposter.
3. Om du valt att skapa annulleringsposter väljer du journalnamnet i fältet **Journalnamn** väljer annulleringskontot i fältet **Annulleringskonto** och därefter transaktionsdatumet i fältet **Transaktionsdatum**.
4. Välj **OK**.

## <a name="cancel-a-completed-schedule"></a>Annullera en slutförd tidsplan

Använd sidan **Alla periodiseringstidsplaner** för att återföra redovisade eller externt bokförda belopp och annullera periodiseringstidsplanen i syfte att förhindra ytterligare redovisning.

Följ dessa steg för att annullera en hel periodiseringstidsplan.

1. På sidan **Alla periodiseringstidsplaner** väljer du periodiseringstidsplanen och sedan **Annullera \> Slutförd tidsplan**.
2. På sidan **Annullera slutförd tidsplan** väljer du om du vill skapa annuleringsposter.
3. Om du valt att skapa annulleringsposter väljer du journalnamnet i fältet **Journalnamn** väljer kontot i fältet **Annulleringskonto** och därefter transaktionsdatumet i fältet **Transaktionsdatum**.
4. Välj **OK**.

## <a name="reverse-transactions"></a>Återför transaktioner

> [!NOTE]
> - Om du vill återföra intäktsredovisning för en periodiseringstidsplan börjar du med steg 1.
> - Om du vill återföra intäktsredovisning för flera tidsplaner börjar du med steg 2.

1. På sidan **Alla periodiseringstidsplaner**, i rutnätet **Tidsplansrader**, väljer du de rader du inte vill redovisa och väljer sedan **Återför**.
2. På sidan **Igenkänningsbearbetning** anger du fältet **Igenkänningsåtgärd** som **Återför redovisningsjournal**.
3. I fältet **Slutdatum** väljer du slutdatum. Bearbetningen kommer endast att innehålla rader där slutdatumet är tidigare än eller samma som det angivna slutdatumet.
4. Välj **Filter** och lägg till datafilter så att listan bara visar det postintervall du vill ha.
5. Välj **Visa förhandsgranskning** om du vill visa raderna.
6. Markera de rader som du inte vill bearbeta i listan med rader och välj sedan **Ta bort**.
7. Fälten **Namn** och **Beskrivning** uppdateras automatiskt med standardjournalnamnet och standardbeskrivningen. Du kan emelelrtid ändra värdena som du vill. Du kan även välja om du vill sammanfatta igenkänningsjournalposten.
8. I avsnittet **Transaktionsdatum** kan du åsidosätta transaktionsdatumet med ett visst datum för att bearbeta transaktionen. Transaktionsdatumet kan anges för stängda perioder.
9. Om du vill bearbeta som en del av ett batchjobb väljer du **Batch**. i dialogrutan **Batchbearbetning** anger du parametrarna för batchen och väljer sedan **OK** för att återgå till sidan **redovisningsbearbetning**. Redovisningen för återförda intäkter bearbetas senare, när batchen bearbetas.
10. Välj **OK**. Om du inte lagt till transaktionen i ett batchjobb bearbetas alla rader omedelbart. Annars bearbetas raderna när batchen bearbetas.

## <a name="apply-or-unapply-a-credit-note"></a>Tillämpa eller ta bort tillämpningen för en kreditfaktura

Gör så här om du vill tillämpa en kreditfaktura.

> [!NOTE]
> När du skapar en kreditfaktura från sidan **Periodisering för försäljningsordertransaktion** och anger alternativet **Justera befintlig tidsplan** som **Ja** tillämpas kreditfakturan automatiskt på tidsplanen när kreditfakturan bokförs.

1. På sidan **Alla periodiserade tidsplaner** väljer du periodiseringsschemat.
2. I listan **Kreditjusteringar** markerar du en rad och väljer sedan **Verkställ**.
3. På sidan **Använd kreditfaktura (periodiseringar)** anger du datumet för omberäkningen i fältet **Datum för omberäkning** och slutdatumet i fältet **Slutdatum**.
4. I listan **Sidhuvud** markerar du den **Försäljningsorder** som har kreditfakturor.
5. Markera raden i listan **Rader**.
6. Välj **OK**.
7. Välj **Ja**.

> [!NOTE]
> Om du vill använda en kreditfaktura för flera enskilda artiklar från olika fakturor måste du upprepa proceduren.

Gör så här om du vill ta bort tillämpningen för en kreditfaktura.

1. På sidan **Alla periodiserade tidsplaner** väljer du periodiseringsschemat.
2. I listan **Kreditjusteringar** markerar du fakturan och väljer sedan **Ta bort tillämpning**.
3. Välj **Ja**.

## <a name="fields"></a>Fält

Sidan **Alla periodiseringstidsplaner** innehåller följande fält.

| Fält | Beskrivning |
|--------|-------------|
| **Siduvud** | |
| **Tidsplan** | |
| Allokeringstyp | Allokeringstypen för händelsebaserade periodiseringar: **procentsats** eller **belopp**. |
| Omklassificeringsdatum | <p>Det senaste datumet när den kortfristiga omklassificeringen för ett periodiseringsschema bearbetades. Detta datum uppdateras varje gång **Kortfristig omklassificering för händelse** används för periodiseringsschemat.</p>Detta fält är endast tillgängligt om den rullande perioden eller den fasta metoden för korttida periodisering används. |
| **Konto** | |
| Periodiseringskonto | Kontot som används för periodiseringsbeloppet. |
| Redovisningskonto | Kontot som används för redovisningsbeloppet. |
| Redovisningstyp | Redovisningstypen. |
| Distributionstyp | Distributionstypen. |
| **Transaktion** | |
| Källa för skapande | Den källa som transaktionen skapades ur. |
| Transaktionstyp | Transaktionstypen. |
| Försäljningsorder | Försäljningsordernumret. |
| Faktura | Fakturanumret. |
| Objekt | Artikelnummer. |
| **Fakturaschema** | |
| Fakturaschemanummer | Numret för motsvarande faktureringstidsplan. |
| Status för faktureringsrad | Status för radartikel för motsvarande faktureringstidsplan. |
| Externa referenser | Information om externa referenser från faktureringsplanen: **Externt** och **Radnummer**. |
| Summor | <p>Beloppssummor för periodiseringsschemat:</p><ul><li>**Långfristiga** – Summan av långfristiga periodiseringsbelopp. Detta värde är endast tillgängligt när fältet **Kortfristig periodiseringsmetod** anges som **Ingen** på sidan **Periodiseringsparametrar för intäkt och utgift**, eller också är det kortfristiga beloppet mer än 0 (noll).</li><li>**Kortfristig** – Summan av kortfristiga periodiseringsbelopp. Detta värde är endast tillgängligt när fältet **Kortfristig periodiseringsmetod** anges som **Ingen** på sidan **Periodiseringsparametrar för intäkt och utgift**, eller också är det kortfristiga beloppet mer än 0 (noll).</li><li>**Ej redovisade** – Summan av icke-redovisade belopp för alla rader.</li><li>**Lagrade** – Summan av externt bokförda belopp för alla rader.</li><li>**Redovisade** – Summan av redovisade belopp för alla rader.</li><li>**Externt bokförda och redovisade** – Summan av externt bokförda och redovisade belopp för alla rader.</li><li>**Totalt belopp** – Summan av beloppen för alla rader.</li></ul> |
| **Schemarader** | |
| Rad | Sekvensnummer för rad. |
| Startdatum för periodisering | Startdatum för periodiseringstidsplanen. |
| Periodiseringsslutdatum | Slutdatum för periodiseringstidsplanen. |
| Belopp | Periodiseringsbeloppet. |
| Extern bokföring | Ett värde som anger om raden har bokförts externt. |
| Beaktade | Ett värde som anger om en raden har beaktats. |
| Journalbatchnummer | Det batchnummer där beloppet beaktades. |
| Händelsebeskrivning | En beskrivning av händelsen. Detta fält är bara tillgängligt för händelsebaserade periodiseringstidsplaner. |
| **Kreditjusteringar** | |
| Faktura | <p>Fakturanumret.</p><p>Värdet anger fakturan för kreditfakturajusteringen som redan har tillämpats på periodiseringstidsplanen.</p> |
| Tillämpat belopp | Det kreditjusteringsbelopp som redan har tillämpats på periodiseringstidsplanen. |
| Tillämpningsdatum | Det datum då kreditjusteringen tillämpades. |
| **Justering** | Justeringsvärdena visas bara om en kreditfaktura har bearbetats för periodiseringstidsplanen. Om ingen kreditfaktura har bearbetats är dessa värden dolda. |
| Justeringsbelopp | Det totala justeringsbeloppet, beräknat som *Ursprungligt belopp* – *Tidsplaneringsbelopp*. |
| Ursprungligt slutdatum | Det ursprungliga slutdatumet för periodiseringstidsplanen. |
| Ursprungligt schemabelopp | Summan för den ursprungliga periodiseringstidsplanen. |
