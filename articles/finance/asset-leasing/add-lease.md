---
title: Lägga till och kopiera leasing (förhandsversion)
description: I det här ämnet beskrivs hur du skapar en ny leasing genom att ange information om den i Leasing av tillgångar, eller genom att kopiera information från en befintlig leasing.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b09a87c7d4f5ba076647218c3586d17a13e6c558
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967936"
---
# <a name="add-or-copy-leases-preview"></a>Lägga till och kopiera leasing (förhandsversion)

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du skapar en leasing från grunden i Leasing av tillgångar och hur du skapar en leasing genom att kopiera en befintlig leasing. Processen att skapa en leasing från grunden omfattar att ange information för den nya leasingen och sedan skapa en leasingplan. När minst en leasing har konfigurerats kan det vara enklare att kopiera informationen från en befintlig leasing och sedan redigera informationen efter behov för att skapa en ny leasing.

## <a name="create-a-lease"></a>Skapa en leasing

Följ dessa steg för att skapa en leasing i Leasing av tillgångar.

1. På sidan **Sammanfattning av leasing** i åtgärdsfönstret väljer du **Ny**.
2. Ange information om leasingen. Obligatoriska fält har röda kantlinjer.

Startdatumet för leasingbetalningen får inte vara tidigare än leasingavtalets startdatum. Om du anger ett startdatum för leasingbetalningen som är tidigare än startdatumet för leasingavtalet får du ett felmeddelande.

Alternativet **Fördelningsbelopp** på snabbfliken **Allmänt** på sidan **Leasingdetaljer** anges till **Nej** om alternativet **Tillåt betalningsuppdelning** på sidan **Parametrar för tillgångsleasing** anges till **Ja**. 

Om alternativet **Uppdelning av betalningsbelopp** anges till **Ja** kommer fältet **Betalningsbelopp** på snabbfliken **Betalningsplanrader** att låsas. Det ställs in på summan av betalningsbeloppen som registreras senare i katalogen för **Uppdelning av betalningsbelopp**. 

Välj **Uppdelning av betalningsbelopp** om du vill öppna en sida där du kan lägga till de specificerade betalningstyperna. Knappen **Lägg till summor i betalningsbelopp** flyttar summorna till fältet **Betalningsbelopp**.

> [!NOTE]
> Om du lägger till ett specificerat betalningsbelopp och sedan väljer **Esc** läggs de angivna beloppen inte till i fältet **Betalningsbelopp** på snabbfliken **Betalningsplanrader**. De lagras i stället i dialogrutan **Uppdelning av betalningsbelopp**. Om du vill att dialogrutan ska visa totalsumman markerar du kolumnen **Belopp**, markerar och håller ned (eller högerklickar) och väljer sedan **Summa den här kolumnen**. 

Knappen **Kopiera rad** kopierar den specificerade betalningsuppdelningen.

## <a name="create-a-lease-schedule"></a>Skapa en leasingplan

När du har angett all information för leasingen skapar du leasingplanen genom att följa stegen nedan.

> [!NOTE]
> De ekonomiska dimensionerna kan ändras baserat på anpassade ekonomiska dimensioner.

1. Välj **Skapa scheman** för att generera leasingböckerna. Leasingböckerna inkluderar planer för betalning, amortering, avskrivning och utgifts.
2. Välj fliken **Böcker** för att få tillgång till leasingböcker och visa de nya planer som skapats.

    På sidan **Information om bok** visas hur leasingen redovisas av de böcker som har tilldelats till den. Härifrån kan du visa leasingplaner.

    Betalningsplanen innehåller inmatningar från fliken **Betalningsplanrader** på sidan **Lägg till leasing**. Du kan fortfarande ändra varje betalningsbelopp och variabel betalning. Leasingskulden beräknas utifrån det ändrade betalningsplanen.

    > [!NOTE]
    > Startdatumet för leasingbetalningen måste vara detsamma eller ett senare datum än leasingavtalets startdatum. Du får ett felmeddelande om startdatumet för betalningen är tidigare än startdatumet för leasingen. 

4. När du är klar med granskningen av betalningsplanen väljer du **Bekräfta plan**. När planen har bekräftats går det inte längre att redigera leasingen.

    > [!NOTE]
    > Leasingperioden beräknas automatiskt från betalningsplanraderna på sidan **Lägg till leasing**.
    >
    > Om du vill beräkna leasingperioden i månader hittar systemet skillnaden mellan start- och slutdatum för en viss betalningsplanrad. Därefter flyttas du till nästa betalningsplanrad och hittar differensen igen. Slutligen summerar systemet alla belopp för att bestämma leasingperioden i månader.

5. Om du vill visa de beräknade räntekostnaden för perioden öppnar du sidan **Plan för amortering av skuld**. Om du vill visa beräknad linjär avskrivning öppnar du sidan **Avskrivningsplan för tillgången**.
6. När du har granskat det beräknade beloppet kan du skapa den första bokföringsjournalposten på sidan **Första redovisningstillfälle**. Ett meddelande visas om att journalen har skapats.

    > [!NOTE]
    > Journalposten bokförs inte i redovisningen förrän du har bokfört transaktionen manuellt.

7. Om du vill granska den föreslagna redovisningstransaktionen innan du bokför den väljer du **Journal för leasing av tillgång**.

    > [!NOTE]
    > Det går inte att skapa till journalen för leasing av tillgång manuellt. Den skapas automatiskt när leasingplanerna skapas.

8. När du är klar med granskningen av den journalposten för det första bokföringstillfället och du är redo att bokföra den, väljer du **Bokför** för att redovisa ROU-tillgången och leasingskulden i redovisningen.

## <a name="copy-a-lease"></a>Kopiera leasing

Med Leasing av tillgångar kan du kopiera informationen om en leasing för att skapa en ny leasing med samma information. Du kan sedan ändra leasingfälten innan du skapar planerna för den kopierade leasingen.

1. På sidan **Sammanfattning av leasing** väljer du leasingen som ska kopieras och i åtgärdsfönstret väljer du sedan **Kopiera leasing**.

    > [!NOTE]
    > Om parametern **Manuell** är inaktiverad för nummerserien för leasing-ID:n, genereras nästa nummer i serien automatiskt som leasing-ID för den kopierade leasingen. Om parametern **Manuell** är aktiverad visas ett meddelande där du uppmanas att ange leasing-ID innan du kan fortsätta kopiera leasingen.

2. Välj **Kopiera**. Leasinginformationen från den valda leasingen kopieras till en ny leasing. Du kan sedan redigera informationen om den nya leasingen innan du sparar den och skapar leasingplanerna.

## <a name="asset-leasing-journal"></a>Journal för leasing av tillgång

Alla journalposter som skapas i Leasing av tillgång ingår i journalen för leasing av tillgång. På sidan **Journal för leasing av tillgång** (**Leasing av tillgångar \> Journalposter \> Journal för leasing av tillgång**) kan du filtrera efter bokföringsstatus, visa specifika journalposter och verifikationerna och bokföra ej bokförda journalposter.

> [!NOTE]
> Det går inte att skapa till journalen för leasing av tillgång manuellt. Den skapas automatiskt när leasingplanerna skapas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
