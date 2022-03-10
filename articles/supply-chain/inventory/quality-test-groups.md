---
title: Testgrupper för kvalitetshantering
description: I det här avsnittet beskrivs hur du skapar testgrupper så att flera tester kan användas med kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 230e402c322509f3ea89d4f1dccb5555828377ff
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578402"
---
# <a name="quality-management-test-groups"></a>Testgrupper för kvalitetshantering

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar testgrupper så att flera tester kan användas med kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.

Du använder sidan **Testgrupper** för att ställa in, redigera och visa testgrupper och enskilda tester som har tilldelats dem. På sidans övre del visas testgrupperna, och på den nedre visas de tester som har tilldelats en vald testgrupp.

Du kan tilldela flera policyer till en testgrupp, till exempel en samplingsplan, en godtagbar kvalitetsnivå och behovet av destruktiv testning. När du sedan tilldelar ett enskilt test till en testgrupp definierar du ytterligare information, till exempel sekvensen, dokument och giltighetsdatum. För ett kvantitativt test innehåller informationen som du anger även acceptabla mätvärden. För ett kvalitativt test innehåller informationen testvariabeln och standardresultatet.

Den testgrupp som har tilldelats till en kvalitetsorder definierar standarduppsättningen med test som måste utföras på den angivna artikeln. Du kan dock lägga till, ta bort eller ändra tester för kvalitetsordern. Testresultaten rapporteras för varje test på en kvalitetsorder.

När du definierar en testgrupp kan du om du vill ange en artikelsampling. Artikelsampling används för att definiera den produktmängd som måste testas. Mer information finns i [Artikelsampling för kvalitetshantering](quality-item-sampling.md). Du kan även ange om testerna i en testgrupp är destruktiva. I ett destruktivt test förstörs artikelsamplingen och kvantiteten tas bort från lagerbehållningen.

## <a name="example-of-a-test-group"></a>Exempel på en testgrupp

Ett tillverkningsföretag definierar en testgrupp för varje variant av sina kvalitetsriktlinjer. De olika testgrupperna återspeglar skillnaderna i samplingsplanerna, uppsättningarna med tester som måste utföras tillsammans, den godtagbara kvalitetsnivån och andra faktorer. För kvantitativa tester finns det också skillnader i de godtagbara måttvärdena. För att framtvinga sina kvalitetsriktlinjer tilldelar företaget en testgrupp till respektive regel som används för att automatiskt generera kvalitetsorder på sidan **Kvalitetskopplingar**. En testgrupp tilldelas också kvalitetsorder som skapas manuellt.

## <a name="create-a-test-group"></a>Skapa en testgrupp

Gör så här om du vill skapa en testgrupp:

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Testgrupper**.
1. I åtgärdsfönstret väljer du **Ny** för att lägga till en rad i rutnätet på sidans övre del. Ange sedan följande fält för den nya raden:

    - **Testgrupp** – Ange ett unikt ID eller namn för testgruppen.
    - **Beskrivning** – Ange en detaljerad beskrivning av testgruppen.
    - **Godtagbar kvalitetsnivå** – Ange den totala procentandel av testresultaten som måste vara godkänd för att testgruppen ska betraktas som godkänd.
    - **Artikelsampling** – Välj en artikelsampling. Mer information finns i [Artikelsampling för kvalitetshantering](quality-item-sampling.md).
    - **Destruktiv** – Markera den här kryssrutan för att ange att testgruppen ska förstöra de artiklar som testas.

1. När den nya raden fortfarande är markerad väljer du fliken **Allmänt** på den övre delen av sidan. Vissa av inställningarna för testgruppen som valts på fliken **Översikt** upprepas här. Du kan dessutom ställa in följande fält för gruppen:

    - **Uppdatera batchattribut för lager** – När du ställer in alternativet som *Ja* här ställs det automatiskt in på *Ja* för varje nytt test som läggs till i testgruppen på den nedre delen av sidan.
    - **Uppdatera batchdisposition** – När du ställer in det här alternativet på *Ja* uppdateras batchdispositionen automatiskt med värdet som valts i fältet **Disposition för orderbatch med icke-godkänd kvalitet** eller **Disposition för orderbatch med godkänd kvalitet**, detta om den artikel som testas är batchkontrollerad.
    - **Disposition för orderbatch med icke-godkänd kvalitet** – Välj den batchdispositionskod som ska tilldelas när en kvalitetsorder som inkluderar den här testgruppen misslyckas eftersom den inte uppfyller den godtagbara kvalitetsnivån.
    - **Disposition för orderbatch med godkänd kvalitet** – Välj den batchdispositionskod som ska tilldelas när en kvalitetsorder som inkluderar den här testgruppen godkänns eftersom den uppfyller den godtagbara kvalitetsnivån.
    - **Uppdatera lagerstatus** – När du ställer in det här alternativet som *Ja* kommer, om **Lagerstatus** har aktiverats i lagerdimensionsgruppen för den artikel som testas, statusen att uppdateras automatiskt med den status som har valts i fältet **Icke-godkänd kvalitetsstatus** eller **Godkänd kvalitetsstatus**.
    - **Icke-godkänd kvalitetsstatus** – Välj den lagerstatus som ska tilldelas artikeln när en kvalitetsorder som omfattar denna testgrupp misslyckas eftersom den inte uppfyller den godtagbara kvalitetsnivån.
    - **Godkänd kvalitetsstatus** – Välj den lagerstatus som ska tilldelas artikeln när en kvalitetsorder som omfattar denna testgrupp godkänns eftersom den uppfyller den godtagbara kvalitetsnivån.

## <a name="add-a-qualitative-test-to-a-test-group"></a>Lägga till ett kvalitativt test i en testgrupp

Gör på följande sätt om du vill lägga till ett kvalitativt test i en testgrupp.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Testgrupper**.
1. Välj den testgrupp som du vill lägga till ett test i på fliken **Översikt** på den övre delen av sidan.
1. I fliken **Översikt** på sidans nedre del väljer du **Lägg till** i verktygsfältet för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Serienummer** – Ange ett heltal för att ange i vilken ordning testerna ska utföras. Tester som har mindre sekvensnummer körs före tester som har större sekvensnummer.

        > [!NOTE]
        > Vi rekommenderar att du lämnar en lucka mellan numren. Ställ till exempel in fältet **Serienummer** som *10* för ditt första test och öka sedan värdet med 10 för varje ytterligare test. På det här sättet kan du lägga till nya tester senare utan att behöva radera och skapa om raderna så att de ligger i önskad ordning.

    - **Test** – Välj det test du vill utföra. För att få ett kvalitativt test väljer du ett test där fältet **Typ** är inställt på *Alternativ*.
    - **Gäller från** – Välj det första datumet när testet är giltigt. Om detta fält lämnas tomt finns ingen gräns.
    - **Gäller till** – Välj det sista datumet när testet är giltigt. Om du lämnar detta fältet tomt eller ställer in det på *Aldrig* finns ingen gräns.
    - **Bestämning av testvärde** – Välj hur en godtagbar kvalitet bör fastställas när flera resultat registreras för samma test. För ett kvalitativt test kan endast *Manuell* väljas. Om du väljer något av de andra värdena (*Medel*, *Lägsta* eller *Högsta*) visas ett felmeddelande när du sparar testgruppen.
    - **Attribut** – Om du vill registrera testresultat för ett batchattribut väljer du attributet här och markerar kryssrutan **Uppdatera batchattribut för lager**.
    - **Uppdatera attribut för lagerbatch** – Markera denna kryssruta om du vill registrera testresultat för det batchattribut som valts i fältet **Attribut**.

1. Välj fliken **Allmänt** på den nedre delen av sidan. Vissa av inställningarna för testet som valts på fliken **Översikt** upprepas här. Du kan dessutom ställa in följande fält för testet:

    - **Analyscertifikatrapport** – Ange det här alternativet som *Ja* för att ange att testresultatet ska skrivas ut på analyscertifikatet. Rapporten kan genereras från kvalitetsordern.
    - **Åtgärd vid fel** – Välj antingen *Godkänn* eller *Underkänn* för att ange huruvida testet ska godkännas eller inte om dess analyscertifikat ej uppfylls.
    - **Godtagbar kvalitetsnivå** – Ange den totala procentandel av testresultaten som måste vara godkänd för att testet ska betraktas som godkänt.

1. Ställ in följande fält på fliken **Test** på den nedre delen av sidan:

    - **Variabel** – Välj den testvariabel som kvalitativa testresultat ska registreras för.
    - **Standardresultat** – Välj det standardresultat som ska registreras för testresultaten.
    - **Testinstrument** – Välj den enhet som ska användas för testet. Om ett testinstrument har definierats anges det automatiskt för testet i testgruppen.

1. Stäng sidan.

## <a name="add-a-quantitative-test-to-a-test-group"></a>Lägga till ett kvantitativt test i en testgrupp

Gör på följande sätt om du vill lägga till ett kvantitativt test i en testgrupp.

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Testgrupper**.
1. Välj den testgrupp som du vill lägga till ett test i på fliken **Översikt** på den övre delen av sidan.
1. I fliken **Översikt** på sidans nedre del väljer du **Lägg till** i verktygsfältet för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Serienummer** – Ange ett heltal för att ange i vilken ordning testerna ska utföras. Tester som har mindre sekvensnummer körs före tester som har större sekvensnummer.

        > [!NOTE]
        > Vi rekommenderar att du lämnar en lucka mellan numren. Ställ till exempel in fältet **Serienummer** som *10* för ditt första test och öka sedan värdet med 10 för varje ytterligare test. På det här sättet kan du lägga till nya tester senare utan att behöva radera och skapa om raderna så att de ligger i önskad ordning.

    - **Test** – Välj det test du vill utföra. För att få ett kvantitativt test väljer du ett test där fältet **Typ** är inställt på *Del* eller *Heltal*.
    - **Gäller från** – Välj det första datumet när testet är giltigt. Om detta fält lämnas tomt finns ingen gräns.
    - **Gäller till** – Välj det sista datumet när testet är giltigt. Om du lämnar detta fältet tomt eller ställer in det på *Aldrig* finns ingen gräns.
    - **Bestämning av testvärde** – Välj hur en godtagbar kvalitet bör fastställas när flera resultat registreras för samma test. De tillgängliga alternativen är *Medel*, *Lägst*, *Högst* och *Manuellt*.
    - **Attribut** – Om du vill registrera testresultat för ett batchattribut väljer du attributet här och markerar kryssrutan **Uppdatera batchattribut för lager**.
    - **Uppdatera attribut för lagerbatch** – Markera denna kryssruta om du vill registrera testresultat för det batchattribut som valts i fältet **Attribut**.

1. Välj fliken **Allmänt** på den nedre delen av sidan. Vissa av inställningarna för testet som valts på fliken **Översikt** upprepas här. Du kan dessutom ställa in följande fält för testet:

    - **Analyscertifikatrapport** – Ange det här alternativet som *Ja* för att ange att testresultatet ska skrivas ut på analyscertifikatet. Rapporten kan genereras från kvalitetsordern.
    - **Åtgärd vid fel** – Välj antingen *Godkänn* eller *Underkänn* för att ange huruvida testet ska godkännas eller inte om dess analyscertifikat ej uppfylls.
    - **Godtagbar kvalitetsnivå** – Ange den totala procentandel av testresultaten som måste vara godkänd för att testet ska betraktas som godkänt.

1. Ställ in följande fält på fliken **Test** på den nedre delen av sidan:

    - **Standard** – Ange det belopp (heltal eller del) som förväntas för testresultatet. Det värde du anger anges som standard i testresultatet. Dessutom anges det automatiskt som standardvärde i fälten **Min** och **Max**.
    - **Min** – Ange det lägsta tillåtna värdet för testresultatet. Värdet du anger måste vara lägre än det belopp som har angetts i fältet **Standard**. När du uppdaterar fältet **Min** uppdateras fältet **Lägsta tolerans (%)** automatiskt. När du uppdaterar fältet **Lägsta tolerans (%)** kommer på liknande sätt fältet **Lägsta** att uppdateras automatiskt.
    - **Max** – Ange det högsta tillåtna värdet för testresultatet. Värdet du anger måste vara högre än det belopp som har angetts i fältet **Standard**. När du uppdaterar fältet **Max** uppdateras fältet **Högsta tolerans (%)** automatiskt. När du uppdaterar fältet **Högsta tolerans (%)** kommer på liknande sätt fältet **Max** att uppdateras automatiskt.
    - **Testinstrument** – Välj den enhet som ska användas för testet. Om ett testinstrument har definierats anges det automatiskt för testet i testgruppen.

1. Stäng sidan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Testinstrument för kvalitetshantering](quality-management-processes.md)
- [Kvalitetshanteringstester](quality-management-processes.md)
- [Testvariabler för kvalitetshantering](quality-management-processes.md)
- [Kvalitetsassociationer](quality-management-processes.md)
- [Batchattribut](/supply-chain/production-control/batch-attributes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
