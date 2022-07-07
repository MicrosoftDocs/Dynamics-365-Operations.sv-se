---
title: Skapa och bearbeta påfyllnad
description: Denna artikel beskriver hur du skapar, bearbetar och frisläpper en påfyllnad för att skapa plockningsarbete för en last, försändelse, tillverkningsorder eller kanbanorder.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, WHSParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage, WHSProdWaveTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 60bf4ab6944bd982e022ead6431adae417ddfb43
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014631"
---
# <a name="wave-creation-and-processing"></a>Skapa och bearbeta påfyllnad

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur du skapar, bearbetar och frisläpper en påfyllnad för att skapa plockningsarbete för en last, försändelse, tillverkningsorder eller kanbanorder. Du kan skapa påfyllnader av följande ordertyper:

- **Försäljningsorder** – Använd leveranspåfyllnader för att inkludera rader från försäljningsorder. När en försäljningsorder frisläpps till lagerstället, kan försäljningsorderraderna inkluderas i påfyllnaden.
- **Produktionsorder** – Använd produktionspåfyllnader om du vill inkludera rader i strukturlistan (BOM) för produkten.
- **Kanban-ordrar** – kanban-påfyllnader inkluderar plocklisterader från kanban-ordrar.

För försäljnings - och kanbanorder måste lager reserveras om ordern har frisläppts till lagerstället. Annars kan artiklarna eller allokeringsraderna inte bearbetas i en påfyllnad. Tillverkningsorder är dock något mer flexibla. För tillverkningsorder kan du välja något av följande alternativ:

- Begär att alla material ska reserveras innan en order kan frisläppas till lagerstället.
- Tillåt att produktionsorder frisläpps till lagerstället trots att allt material inte kan reserveras. Om du markerar det här alternativet måste du upprepa frisläppningen till lagerprocess när ytterligare material blir tillgängliga. Detta är till exempel praktiskt om du har material som behövs för att starta en produktion, och kan vänta tills ytterligare material är tillgängligt.

Du kan ange vilket av dessa tillverkningsorderalternativ som ska användas som standard med hjälp av fältet **Behov för materialreservation** på sidan **Parametrar för produktionskontroll**. Du kan dock ändra den här inställningen för en viss produktionsorder när som helst. Mer information finns i [Lagerställeparametrar för påfyllnadsbearbetning](wave-warehouse-parameters.md).

## <a name="create-and-process-a-wave"></a>Skapa och bearbeta en påfyllnad

I bilden nedan visas flödet för hur leveranspåfyllnad skapas, bearbetas och frisläpps. Numren motsvarar de avsnitt som beskrivs senare i det här avsnittet.

![Process för att skapa en påfyllnad.](media/wave-processing-diagram.png "Process för att skapa en påfyllnad")

### <a name="prerequisites"></a>Förutsättningar

Innan du börjar måste en påfyllnadsmall vara tillgänglig för den typ av påfyllnad du vill skapa (leverans, produktion eller kanban). Påfyllnadsmallen förnyar många inställningar för hur påfyllnad ska genereras och bearbetas, bland annat vilka steg som måste utföras manuellt och som utförs automatiskt. Mer information finns i [Påfyllnadsmallar](wave-templates.md).

### <a name="create-a-wave"></a>Skapa en påfyllnad

#### <a name="automatically-create-waves-based-on-warehouse-and-order-type"></a>Skapa påfyllnad automatiskt baserat på lagerställe och ordertyp

Om du vill skapa påfyllnader automatiskt ställer du in [Påfyllnadsmallar](wave-templates.md) som gäller för varje relevant ordertyp och lagerställe. Se till att varje mall har alternativet **Automatisera skapande av påfyllnad** inställt på *Ja*.

#### <a name="manually-create-waves"></a>Manuellt skapa påfyllnader

Gör så här om du vill skapa en påfyllnad manuellt:

1. Se till att de relevanta [Påfyllnadsmallarna](wave-templates.md) inte är inställda på att automatiskt skapa en påfyllnad för lager- och ordertyperna där du vill göra det manuellt.
1. Klicka på något av följande, beroende på vilken typ av påfyllnad du ska skapa:

    - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Leveranspåfyllningar** \> **Alla påfyllningar**. Klicka på **påfyllning** i åtgärdsfönstret.
    - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Produktionspåfyllningar** \> **Alla produktionspåfyllningar**. Klicka på **Produktionspåfyllning** i åtgärdsfönstret.
    - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Kanban-påfyllningar** \> **Alla Kanban-påfyllningar**. Klicka på **Skapa påfyllning** i åtgärdsfönstret.

1. I fältet **Beskrivning** ange en kort beskrivning av påfyllnaden. Procentsatsen bör ange vad du bearbetar i påfyllnaden.

1. I fältet **Namn på påfyllnadsmall** välj påfyllnadsmall för typen av påfyllnad som ska skapas. Påfyllnadsmallen innehåller påfyllnadsmetoder som ska utföra sådana åtgärder som att skapa arbete för påfyllnaden. Påfyllnadsmallen för leveranspåfyllnader kan till exempel innehålla metoder för att skapa laster, allokera rader till påfyllnader, skapa lagerpåfyllnad och skapa plockningsarbete för påfyllnaden.

1. Om du vill använda påfyllnadsattribut som ytterligare frågekriterier för påfyllnaden väljer du attributen i fälten **påfyllnadsattribut**.

### <a name="specify-what-to-include-in-a-wave"></a>Ange vad som ska ingå i en påfyllnad

När en påfyllnad har skapats är du redo att börja lägga till innehåll i den.

> [!NOTE]
> Om det behövs kan du lägga till rader till en påfyllnad även efter det att den har bearbetats så länge den inte har frisläppts.

#### <a name="automatically-specify-what-to-include-in-a-wave"></a>Ange automatiskt vad som ska ingå i en påfyllnad

Om du vill skapa påfyllnader automatiskt ställer du in [Påfyllnadsmallar](wave-templates.md) som gäller för varje relevant ordertyp och lagerställe. Se till att varje mall har alternativet **Automatisera skapande av påfyllnad** inställt på *Ja*. Alternativt kan din mall automatiskt tilldela rader till alla kvalificerade öppna påfyllnader om alternativet **Tilldela öpppna påfyllnader** anges till *Ja*.

#### <a name="manually-specify-what-to-include-in-a-wave"></a>Ange manuellt vad som ska ingå i en påfyllnad

När en påfyllnad har skapats men ännu inte frisläppts kan du manuellt ange vad du vill ta med i den. Så här lägger du till rader i en påfyllnad manuellt:

1. Gör ett av följande, beroende på vilken typ av påfyllnad du ska lägga till rader för:

    - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Leveranspåfyllningar** \> **Alla påfyllningar**. Klicka på **påfyllning** i åtgärdsfönstret.
    - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Produktionspåfyllningar** \> **Alla produktionspåfyllningar**. Klicka på **Produktionspåfyllning** i åtgärdsfönstret.
    - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Kanban-påfyllningar** \> **Alla Kanban-påfyllningar**. Klicka på **Skapa påfyllning** i åtgärdsfönstret.

1. Välj påfyllnad. Gör något av följande i åtgärdsfönstret:

      - **Underhåll leveranser**
      - **Underhåll produktioner**
      - **Underhåll plocklistor för kanban-jobb**

1. Markera i den övre delen av fönstret den rad som ska läggas till påfyllnaden och klicka sedan på **Lägg till påfyllnad**. Raden flyttas till snabbfliken **påfyllnadsrader**.

    Upprepa det här steget för varje rad som du vill lägga till. Om du vill lägga till alla rader väljer du **Lägg till alla**.

    > [!TIP]
    > För försändelsepåfyllnader kan du snabbt hitta en viss order genom att välja ett anpassat filter i fältet **Kod för påfyllnadsfilter**. Koder för påfyllnadsfilter innehåller frågekriterier för leveranser, som skapas i formuläret **Påfyllnadsfilter**. Det här fältet är inte tillgängligt för produktionspåfyllnader eller kanban-påfyllnader.
    > En grön bockmarkering i kolumnen **I påfyllnad** kolumnen visar att leveransen har lagts till i påfyllnaden.

### <a name="process-the-wave-to-create-the-picking-work"></a>Bearbeta påfyllnaden om du vill skapa plockningsarbetet

När en påfyllnad har skapats och innehåller alla rader som behövs är du klar att bearbeta den för att skapa motsvarande plockningsarbete.

#### <a name="automatically-process-a-wave"></a>Bearbeta automatiskt en påfyllnad

Om du vill bearbeta en påfyllnad automatiskt ställer du in relevanta [påfyllnadsmallar](wave-templates.md) med de automatiska bearbetningsalternativen som krävs.

#### <a name="manually-process-a-wave"></a>Bearbeta en påfyllnad manuellt

Du kan endast bearbeta en påfyllnad om **Påfyllnadsstatus** är *Skapad*. När du har bearbetat en påfyllnad, **Påfyllnadsstatus** ändras till *Hållen*.

Gör på följande sätt om du vill bearbeta en påfyllnad manuellt som har allt det innehåll som krävs:

1. Gör något av följande, beroende på vilken typ av påfyllnad du ska bearbeta:

    - Välj **Lagerstyrning** \> **utgående påfyllningar** \> **leveranspåfyllningar** \> **alla påfyllningar**. Klicka på **påfyllning** i åtgärdsfönstret.
    - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Produktionspåfyllningar** \> **Alla produktionspåfyllningar**. Klicka på **Produktionspåfyllning** i åtgärdsfönstret.
    - Välj **Lagerstyrning** \> **Utgående påfyllningar** \> **Kanban-påfyllningar** \> **Alla Kanban-påfyllningar**. Klicka på **Skapa påfyllning** i åtgärdsfönstret.

1. Välj den påfyllnad som ska bearbetas. Välj **Process** i åtgärdsfönstret.

### <a name="release-the-wave-to-the-warehouse-to-start-picking-and-packing"></a>Frisläpp påfyllnad till lagerstället för att börja plocka och packa

Du måste bearbeta en påfyllnad innan du kan frisläppa den. När du frisläpper påfyllnaden är plockningsarbetet tillgängligt i lagerstället. Du kan avbryta en påfyllnad, efter att den har frisläppts, och lägga till mer rader, men du kan inte ändra raderna.

#### <a name="automatically-release-a-wave"></a>Frisläpp automatiskt en påfyllnad

Om du vill bearbeta en påfyllnad automatiskt ställer du in relevanta [påfyllnadsmallar](wave-templates.md) med de automatiska bearbetningsalternativen som krävs.

#### <a name="manually-release-a-wave"></a>Frisläpp en påfyllnad manuellt

Gör så här om du vill frisläppa en påfyllnad manuellt:

1. Gör något av följande, beroende på vilken typ av frisläppande du ska bearbeta:

      - Välj **Lagerstyrning** \> **utgående påfyllningar** \> **leveranspåfyllningar** \> **alla påfyllningar**. Klicka på **påfyllning** i åtgärdsfönstret.
      - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Produktionspåfyllningar** \> **Alla produktionspåfyllningar**. Klicka på **Produktionspåfyllning** i åtgärdsfönstret.
      - Välj **Lagerstyrning** \> **Utgående påfyllningar** \> **Kanban-påfyllningar** \> **Alla Kanban-påfyllningar**. Klicka på **Skapa påfyllning** i åtgärdsfönstret.

1. Välj den påfyllnad som ska frisläppas. Klicka på **Frisläpp påfyllning** i åtgärdsfönstret.

## <a name="containerize-a-wave"></a>Skapa behållare för påfyllnad

Med automatiskt skapande av behållare skapas behållare och plockarbete för leveranser när en påfyllnad bearbetas. Mer information om hur du konfigurerar den finns i [Behållaranpassning](wave-containerization.md).

## <a name="work-with-the-scheduled-work-creation"></a>Arbeta med det planerade arbetet som skapas

När funktionen *Schemalägga arbetsskapande* är aktiverad kommer påfyllnadsbehandling att skapa planerat arbete, som så småningom kommer att användas av den nya arbetsskapande processen. När arbetet skapas spärras arbetet med funktionen *Arbetsspärr för hela organisationen*. Mer information finns i [Planera skapande av arbete under påfyllnad](configure-wave-schedule-work-creation.md).

Flödesschemat nedan visar hur planerat arbete skapas under påfyllnadsbearbetning.

![Skapa tidsplan för arbete.](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Planerat arbete

Sidan **Information om planerat arbete** (**Lagerstyrning \> Arbete \> Information om planerat arbete**) visar information om det planerade arbetet som ursprungligen skapas under påfyllnadsbehandling. Följande värden för **Processtatus** finns:

- **Köad** - Det planerade arbetet väntar på att användas för att skapa arbete.
- **Slutfört** - Det planerade arbetet har använts för att skapa arbete.
- **Misslyckat** - påfyllnadsbearbetningen har misslyckats. Observera att det planerade arbetet kan vara i **misslyckat** läge med eller utan relaterat faktiskt arbete. När den faktiska processen för att skapa arbete misslyckas, kvarstår det faktiska arbetet med status *Annullerat*.

### <a name="batch-job-for-the-work-creation-process"></a>Batchjobb för att skapa arbete

Om du vill visa batchjobben för påfyllnadsbearbetning, välj **batchjobb** i åtgärdsfönstret på sidan **Alla påfyllnader**.

Här kan du visa alla batchuppgiftsdetaljer för varje batchjobb-ID.

## <a name="cancel-a-wave"></a>Avbryt en påfyllnad

Om det behövs kan du avbryta en påfyllnad som har bearbetats. Om du vill annullera påfyllnads- och plockarbete som skapats följ stegen nedan:

1. Gör något av följande, beroende på vilken typ av annullering du ska bearbeta:

      - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Leveranspåfyllningar** \> **Alla påfyllningar**.
      - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Produktionspåfyllningar** \> **Alla produktionspåfyllningar**.
      - Gå till **Lagerstyrning** \> **Utgående påfyllningar** \> **Kanban-påfyllningar** \> **Alla Kanban-påfyllningar**.

1. Välj den påfyllnad som ska avbrytas. I åtgärdsfönstret på fliken **Arbete** välj **Avbryt**.

## <a name="review-wave-batch-job-details"></a>Granska detaljer om batchjobb för påfyllnad

Använd sidan **Detaljer om batchjobb för påfyllnad** för att inspektera batchjobb och relaterade uppgifter som är associerade med alla påfyllnader. Detta är särskilt användbart vid felsökning av en påfyllnad som har misslyckats. Om den här funktionen inte har den här funktionen har endast administratörer vanligtvis åtkomst till batchjobbinformation. Sidan **Detaljer om batchjobb för påfyllnad** kan göras tillgänglig för användare som inte är administratörer och ger en skrivskyddad bild av batchjobb och relaterade uppgifter.

### <a name="turn-the-wave-batch-job-details-page-on-or-off"></a>Aktivera eller inaktivera sidan detaljer om batchjobb för påfyllnad

Från och med version 10.0.25 av Supply Chain Management aktiveras sidan **Information om påfyllnadsbatchjobb** som standard. Administratörer kan aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Information om påfyllnadsbatchjobb* i arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="use-the-wave-batch-job-details-page"></a>Använd sidan detaljer om batchjobb för påfyllnad

Sidan **Detaljer om batchjobb för påfyllnad** kombinerar batchjobb och batchjobbuppgifter, som låter dig undersöka alla påfyllnadsstegen utan att behöva navigera fram och tillbaka mellan ett enda batchjobb och batchuppgiftslistan. Sidan ger också åtkomst till batchloggen och, om du har den behörighet som krävs, innehåller en länk till sidan **Batchjobb**.

För att öppna den här sidan, välj en påfyllnad på någon av flera olika påfyllnadssidor och välj sedan **Detaljer om batchjobb för påfyllnad** i åtgärdsfönstret.

## <a name="review-load-validation-and-error-messages"></a>Granska lastvalidering och felmeddelanden

Under påfyllnadsbearbetning valideras och visar status för varje beläggningsrad i påfyllnad. Om inga varningar visas fortsätter den till nästa påfyllnadssteg. Om varningar förekommer visar det istället följande fel när det är klart att hela påfyllnaden ska valideras:

> Hittade ogiltiga beläggningsrader i påfyllnad. Ta bort de ogiltiga lastraderna.

Du kan sedan granska den slutliga statusen för varje beläggningsrad i påfyllnad och korrigera alla varningar innan du försöker igen. På så sätt kan du ta upp alla varningar samtidigt innan du bearbetar om påfyllnad. (I tidigare versioner slutade systemet att bearbeta påfyllnaden efter den första varningen, så du kan bara åtgärda varningar en åt gången.)

Hur dina statusmeddelanden för påfyllnadsbearbetning visas beror på hur du har ställt in alternativet **Skapa logg för påfyllnadbearbetningshistorik** på sidan **Lagerstyrningsparametrar**.

- När **Skapa logg för påfyllnadbearbetningshistorik** anges till *Nej*, visar lastraden statusmeddelanden i **informationsloggen**.
- När **Skapa logg för påfyllnadbearbetningshistorik** anges till *Ja*, visar lastraden statusmeddelanden på sidan **påfyllnadsbearbetning historiklogg**. Om du vill visa loggen går du till **Lagerstyrning \> Utgående påfyllnader \> Påfyllnadsbearbetning historiklogg**.

## <a name="additional-resources"></a>Ytterligare resurser

- [Konfigurera påfyllnadsbearbetning, exempel](tasks/configure-wave-processing.md)
- [Påfyllnadsmallar](wave-templates.md)
- [Skapande av fraktbehållare](wave-containerization.md)