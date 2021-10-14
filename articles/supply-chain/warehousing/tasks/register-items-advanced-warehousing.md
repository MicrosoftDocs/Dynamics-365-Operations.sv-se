---
title: Registrera artiklar för en artikel som är aktiverad för avancerad distributionslagerhantering med hjälp av en artikelinförseljournal
description: Det här ämnet presenterar ett scenario som visar hur du registrerar artiklar via artikelinförseljournalen när du använder avancerade processer för lagerstyrning.
author: Mirzaab
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e753897d1e21ffebbcbfac48abab4b0549c3553f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565265"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Registrera artiklar för en artikel som är aktiverad för avancerad distributionslagerhantering med hjälp av en artikelinförseljournal

[!include [banner](../../includes/banner.md)]

Det här ämnet presenterar ett scenario som visar hur du registrerar artiklar via artikelinförseljournalen när du använder avancerade processer för lagerstyrning. Detta görs vanligtvis av en inleveransansvarig.

## <a name="enable-sample-data"></a>Aktivera exempeldata

Om du vill gå igenom det här scenariot med hjälp av de exempelposter och värden som anges i det här avsnittet måste du använda ett system där standard demodata är installerad och du måste välja den juridiska personen *USMF* innan du börjar.

Du kan istället arbeta dig igenom det här scenariot genom att använda värderingsvärden från dina egna data under förutsättning att du har följande tillgängliga data:

- Du måste ha en bekräftad inköpsorder med en öppen inköpsorderrad.
- Artikeln på raden måste lagras. Den får inte använda produktvarianter och får inte ha spårningsdimensioner.
- Objektet måste associeras med en lagringsdimensionsgrupp som har lagerhanteringsprocessen aktiverad.
- Lagerstället som används måste aktiveras för lagerstyrningsprocesser och lagerplatsen som du använder för inleveranser måste vara id-nummerstyrd.

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a>Skapa en journalrubrik för artikelinförleverans som använder lagerstyrning

I följande scenario visas hur du skapar en artikelinföringsjournalrubrik där lagerstyrning används:

1. Kontrollera att systemet innehåller en bekräftad inköpsorder som uppfyller kraven i det föregående avsnittet. I det här scenariot används en inköpsorder för företaget *USMF*, leverantörskonto *1001*, lagerställe *51* med en orderrad för *10 PL* (10 lastpallar) för artikelnummer *M9200*.
1. Anteckna inköpsordernumret som du vill använda.
1. Gå till **Lagerhantering \> Poster i redovisningsjournal \> Artikelinförsel \> Artikelinförsel**.
1. Välj **Ny** i åtgärdsfönstret.
1. Dialogrutan **Skapa lagerhanteringsjournal** öppnas. Välj ett journalnamn i fältet **Namn**.
    - Om du använder exempeldata för *USMF*, välj *WHS*.
    - Om du använder dina egna uppgifter måste den journal du väljer ha **Kontrollera plockplats** inställt på *Nej* och **Karantänhantering** anges till *Nej*.
1. Ange **Referens** till *Inköpsorder*.
1. Ange **Kontonummer** till *1001*.
1. Ange **Nummer** till numret inköpsordern som du identifierade i det här arbetet.

    ![Artikelinförselsjournal.](../media/item-arrival-journal-header.png "Artikelinförseljournal")

1. Välj **OK** för att skapa journalrubriken.
1. I avsnittet **Journalrader**, välj **Lägg till rad** och ange följande data:
    - **Artikelnummer** – Ange till *M9200*. **Webbplatsen**, **lagerstället** och **kvantiteten** kommer att ställas in baserat på lagertransaktionsdata för de 10 lastpallar (1000 st).
    - **Plats** – Ställ in på *001*. Den här platsen spårar inte licensinnehavare.

    ![Artikelinförselsjournalrad.](../media/item-arrival-journal-line.png "Artikelinförseljournalrad")

    > [!NOTE]
    > Fältet **Datum** bestämmer datumet då lagerbehållningen för artikeln ska registreras i lagret.  
    >
    > **Parti-ID** fylls i av systemet, om det kan identifieras av den tillhandahållna informationen. Annars måste du ange det manuellt. Detta är ett obligatoriskt fält, som kopplar den här registreringen till en viss källdokumentrad.  

1. Välj **Validera** i åtgärdsfönstret. Detta kontrollerar att journalen är klar att bokföras. Om valideringen misslyckas måste du korrigera felen innan du kan bokföra journalen.  
1. Dialogrutan **Kontrollera journal** öppnas. Välj **OK**.
1. Granska meddelandefältet. Det bör visas ett meddelande om att åtgärden lyckades.  
1. Klicka på **Bokföra** i åtgärdsfönstret.
1. Dialogrutan **Bokför journal** öppnas. Välj **OK**.
1. Granska meddelandefältet. Det bör visas ett meddelande om att åtgärden lyckades.
1. Välj **Funktioner > Produktinleverans** i åtgärdsfönstret om du vill uppdatera inköpsorderraden och bokföra en produktinleverans.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
