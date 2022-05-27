---
title: Intäktsallokering
description: Detta ämne beskriver hur du använder intäktsallokering i prenumerationsfakturering.
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
ms.openlocfilehash: 09d3e9295f1fb753156aa603b00372316173721e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695258"
---
# <a name="revenue-allocation"></a>Intäktsallokering

Detta ämne beskriver hur du ställer in intäktsallokeringsparametrar för ett faktureringsschema. Du kan ställa in eller redigera intäktsallokering när du skapar faktureringsschemat. När du öppnar sidan **Intäktsallokering** för ett aktivt eller uppsagt faktureringsschema är fälten skrivskyddade.

## <a name="specify-the-revenue-allocation-for-a-billing-schedule"></a>Ange intäktsallokering för en faktureringsplan

För att ange intäktsallokering för en faktureringsschemarad följer du dessa steg.

1. På listsidan **Alla/aktiva faktureringsscheman** eller välj befintligt faktureringsschema eller faktureringsschemarader.
2. På fliken **Intäktsallokering** längst upp på sidan, välj **Intäktsallokering**.
3. I fältet **Ordningstyp för flera element**, välj typ av system med flera element (MEA).
4. I fältet **Ordningsnummer för flera element** ange MEA-nummer. I fältet **Intäktskonto för periodiserat kontrakt** ange intäktskonto för periodiserat kontrakt.

    Om du ställer in fältet **Ordningstyp för flera element** till **Enkel**, kommer samma värden för **Ordningsnummer för flera element** and **Intäktskonto för periodiserat kontrakt** tillämpas på varje rad. Om du ställer in fältet **Ordningstyp för flera element** till **Flera**, kan du ange olika värden för **Ordningsnummer för flera element** and **Intäktskonto för periodiserat kontrakt** varje rad.
    
    Ett MEA-nummer kan bara tilldelas två eller flera artiklar. En enskild rad får inte ha ett eget MEA-nummer.

5. Välj **Spara**.

### <a name="fields"></a>Fält

Sidan **Ordning för flera element** innehåller följande fält.

| Fält | Beskrivning |
|---|---| 
| Ordningstyp för flera element | <p>Välj MEA-typ för transaktionen:</p><ul><li>**Flera** – Radartiklarna i transaktionen är en del av MEA-avtalet, eller finns det fler än en ordning.</li><li>**Ingen** – Transaktionen är en standardtransaktion som inte har någon intäktsallokering.</li><li>**Enkelt** – Alla artiklar i transaktionen ingår i en enda MEA.</li></ul> |
| Ordningsnummer för flera element | <p>MEA-numret för raden. Detta fält är tillgängligt om fältet **Ordningstyp för flera element** anges till **Flera**.</p><p>Om det här fältet är tomt, och du tilldelar ett MEA-nummer kommer fälten **Ursprungligt fristående försäljningspris** och **Fristående försäljningspris** uppdateras automatiskt baserat på värdena från sidan **Fristående försäljningspris för artikel**. Endast MEA-nummer som tilldelats andra rader på försäljningsordern är tillgängliga.</p> |
| Intäktskonto för periodiserat kontrakt | Ange vilket konto som ska användas för journalposter när en MEA-kontraktsfaktura skapas. Detta fält är tillgängligt när fakturering av återkommande kontrakt används. |
| **Rader** | |
| Variantnummer | Variantnumret från försäljningsordern. |
| Artikelnummer | Artikelnumret från försäljningsordern. |
| Faktureringsfrekvens | Frekvensen för intäktsfördelningen: **Dagligen**, **Månadsvis**, **Kvartalsvis**, **Halvårsvis** eller **Årligen**. |
| Antal | Värdet kommer från försäljningsordern. |
| Kontraktsvärde | Kontraktsvärdet. |
| Ordningsnummer för flera element | <p>MEA-numret för raden. Detta fält är tillgängligt om fältet **Ordningstyp för flera element** anges till **Flera**.</p><p>Om det här fältet är tomt, och du tilldelar ett MEA-nummer kommer fälten **Ursprungligt fristående försäljningspris** och **Fristående försäljningspris** uppdateras automatiskt baserat på värdena från sidan **Fristående försäljningspris för artikel**. Endast MEA-nummer som tilldelats andra rader på försäljningsordern är tillgängliga. Om dessa värden inte ställs in för artikeln används värdena från sidan **Intäktsallokeringsparametrar för flera element**.</p> | 
| Ursprungligt fristående försäljningspris | <p>Ursprung för det fristående försäljningspriset:</p><ul><li>**Belopp** – Det fristående försäljningspriset är ett belopp som du anger och som är mer än 0 (noll). Beloppet konverteras mellan de funktionella och ursprungliga valutorna efter behov.</li><li>**Basförsäljningspris** – Det fristående försäljningspriset matchar artikelns basförsäljningspris.</li><li>**Fakturapris** – Det fristående försäljningspriset matchar artikelns fakturapris.</li><li>**Procentandel av artikel** – Det fristående försäljningspriset anges som ett procentvärde och beräknas baserat på artikelns pris. Om du väljer detta alternativ anger du förvalt procentvärde.</li><li>**Allokera restbelopp** – Ursprunget till det fristående försäljningspriset beräknas som *Totalt kontraktsvärde för överordnad artike* – *Totalt fristående försäljningspris för underordnade artiklar*:</p><ul><li>*Det totala kontraktsvärdet för den överordnade artikeln* är nettobeloppet eller fakturerat belopp.</li><li>*Totalt fristående försäljningspris för underordnade artiklar* är summan av det utökade eller kontraktsfristående försäljningspriset för alla underordnade artiklar, förutom den underordnade artikel som använder detta ursprungliga fristående försäljningspris.</li></ul><p>Om det beräknade beloppet är ett negativt värde sätts beloppet till 0 (noll).</p><p>**OBS:** Detta alternativ kan bara väljas för en (1) underordnad artikel i intäktsdelningen.</p></li><li>**Ingen** – Ursprunget till det fristående försäljningspriset baseras på de underordnade artiklarna. Detta alternativ gäller för artiklar som har definierats som överordnade artiklar i en mall för intäktsdelning. Om kryssrutan **Intäktsdelning** är markerad markeras detta alternativ automatiskt, och inställningen kan inte ändras.</li><li>**Procent för överordnat fakturapris** – Ursprunget till det fristående försäljningspriset är en procentandel av fakturapriset för den överordnade artikeln. Detta alternativ är endast tillgängligt för överordnade artiklar i mallar för intäktsdelning.</li><li>**Procent för överordnat standardpris** – Ursprunget till det fristående försäljningspriset är en procentandel av standardpriset för den överordnade artikeln. Detta alternativ är endast tillgängligt för överordnade artiklar i mallar för intäktsdelning. När alternativet för en underordnad artikel ändras från **Procent för överordnat standardpris** till **Procent för överordnat fakturapris**, eller från **Procent av överordnat fakturapris** till **Procent av överordnat standardpris** uppdateras även de beräknade värdena.</li></ul> |
| Fristående försäljningspris | <p>Det fristående försäljningspriset för raden i transaktionsvalutan.</p><p>Värdet i fältet **Belopp** anges eller beräknas.</p> |
| Fristående försäljningspris för kontrakt | Fristående försäljningspris för kontrakt. |
| Resterande kontraktsintäkt | Återstående intäktsbelopp för kontraktet. Det här beloppet är summan av alla rader som fakturor inte har skapats för än. |
| Total kontraktsintäkt | Det totala kontraktintäktsbeloppet för raden. Det här beloppet är summan av alla rader, oavsett om det har skapats fakturor för dem. |
| Intäktskonto för periodiserat kontrakt | <p>Ange vilket konto som ska användas för journalposter när en MEA-kontraktsfaktura skapas.</p><p>Detta fält är tillgängligt när fakturering av återkommande kontrakt används.</p> |
| Fel | Eventuella fel som har inträffat för intäktsallokeringen. |

## <a name="use-revenue-allocation-on-a-sales-order"></a>Använd intäktsallokering på en försäljningsorder

Följ de här stegen om du vill använda intäktsallokeringsfunktionen för en försäljningsorder.

1. På sidan **Alla försäljningsorder** skapar du en försäljningsorder som har artiklar.
2. På fliken **Faktura**, under **Intäktsallokering**, väljer du **Intäktsallokering** .
3. I fältet **Ordningstyp för flera element** välj MEA-typ.
4. I fältet **Ordningsnummer för flera element** ange MEA-nummer.
5. Om fältet **Ordningstyp för flera element** anges till **Flera**, välj de rader du vill ha och välj sedan **Använd i markerade**.
6. Välj **Spara**.

Om du använder periodisering av intäkt och utgift skapas periodiseringsschemat automatiskt. Du kan visa det på sidan **Alla periodiserade tidsplaner**.
