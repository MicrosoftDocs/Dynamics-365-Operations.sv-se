---
title: Konfigurera intäktsallokering för flera element
description: Detta ämne beskriver hur du konfigurerar parametrar för allokering av intäkter från flera element i Prenumerationsfakturering.
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
ms.openlocfilehash: bb5b220dd941cbb9f1fda5d0eb821a86a9135309
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685811"
---
# <a name="set-up-multiple-element-revenue-allocation"></a>Konfigurera intäktsallokering för flera element

Allokering av intäkter med flera element låter dig ställa in olika mallar som används för att beräkna och fördela intäkter över flera artiklar. Med den här funktionen kan du följa kodifieringsämne 606 för redovisningsstandarder (ASC 606) och/eller International Financial Reporting Standard 15 (IFRS 15).

## <a name="multiple-element-revenue-allocation-parameters"></a>Intäktsallokeringsparametrar för flera element

Använd sidan **Allokeringsparametrar för intäkter från flera element** för att konfigurera parametrar intäktsallokering för flera element.

### <a name="standalone-selling-price-origin"></a>Ursprungligt fristående försäljningspris

Fältet **Ursprung för fristående försäljningspris** avgör varifrån det fristående försäljningspriset kommer. Du kan uppdatera värdet på sidan **Försljningspris för fristående artikel** samt på transaktionen. Följande alternativ är tillgängliga.

| Alternativ | Beskrivning |
|--------|-------------|
| Belopp | Det fristående försäljningspriset är ett belopp som du anger och som är mer än 0 (noll). Beloppet konverteras mellan de funktionella och ursprungliga valutorna efter behov. |
| Basförsäljningspris | Det fristående försäljningspriset matchar artikelns basförsäljningspris. |
| Fakturapris | Det fristående försäljningspriset matchar artikelns fakturapris. |
| Procent av artikel | Det fristående försäljningspriset anges som ett procentvärde och beräknas baserat på artikelns pris. Om du väljer detta alternativ anger du förvalt procentvärde. |
| Allokera restbelopp | <p>Ursprunget till det fristående försäljningspriset beräknas som *Totalt kontraktsvärde för överordnad artikel* – *Totalt fristående försäljningspris för underordnade artiklar*:</p><ul><li>*Det totala kontraktsvärdet för den överordnade artikeln* är nettobeloppet eller fakturerat belopp.</li><li>*Totalt fristående försäljningspris för underordnade artiklar* är summan av det utökade eller kontraktsfristående försäljningspriset för alla underordnade artiklar, förutom den underordnade artikel som använder detta ursprungliga fristående försäljningspris.</li></ul><p>Om det beräknade beloppet är ett negativt värde sätts beloppet till 0 (noll).</p><p>**OBS:** Detta alternativ kan bara väljas för en (1) underordnad artikel i intäktsdelningen.</p> |
| Inget | Ursprunget till det fristående försäljningspriset baseras på de underordnade artiklarna. Detta alternativ gäller för artiklar som har definierats som överordnade artiklar i en mall för intäktsdelning. Om kryssrutan **Intäktsdelning** är markerad markeras detta alternativ automatiskt, och inställningen kan inte ändras. |
| Procent av överordnat fakturapris | Ursprunget till det fristående försäljningspriset är en procentandel av fakturapriset för den överordnade artikeln. Du kan ändra standardvärdet. Detta alternativ är endast tillgängligt för överordnade artiklar i mallar för intäktsdelning. |
| Procent av överordnat standardpris | Ursprunget till det fristående försäljningspriset är en procentandel av standardpriset för den överordnade artikeln. Du kan ändra standardvärdet. Detta alternativ är endast tillgängligt för överordnade artiklar i mallar för intäktsdelning. Det är standardalternativet för underordnade artiklar. När alternativet för en underordnad artikel ändras från **Procent för överordnat standardpris** till **Procent för överordnat fakturapris**, eller från **Procent av överordnat fakturapris** till **Procent av överordnat standardpris** uppdateras även de beräknade värdena. |

### <a name="account-for-revenue-allocation-rounding-differences"></a>Konto för avrundningsdifferenser vid intäktsallokering

Fältet **Konto för avrundningsdifferenser för intäktsallokering** anger det konto som används för att registrera eventuella avrundningsjusteringar i ett intäktsbelopp i kontrakt. Detta är tillgängligt när återkommande fakturering av kontrakt används.

## <a name="item-standalone-selling-price"></a>Fristående försäljningspris för artikel

Använd sidan **Artikelns fristående försäljningspris** om du vill ange ursprung och fristående försäljningspris för en artikel. Värdena som anges på den här sidan används som standardvärden på sidan **Intäktsallokering** i flera allokeringar för elementintäkt och fakturering av återkommande kontrakt.

### <a name="specify-item-standalone-selling-price"></a>Ange fristående försäljningspris för artikel

Följ de här stegen om du vill ange det fristående priset för en artikel.

1. På sidan **Fristående försäljningspris för artikel**, i fältet **Ursprung för fristående försäljningspris** väljer du ursprunget till det fristående försäljningspriset.
2. Gör något av följande, beroende på vilket värde du valt i fältet **ursprung för fristående försäljningspris**:

    * Om du har valt **Procent av artikel** anger du procentsatsen i fältet **Procent**.
    * Om du har valt **Belopp** anger du beloppet i fältet **Fristående försäljningspris**.

2. Välj **Lägg till** för respektive artikel som du vill lägga till i listan.
3. I fältet **Artikelkod** väljer du artikelkoden. I fältet **Artikelrelation** väljer du artikelrelationen. För artiklar där kryssrutan **Intäktsdelning** är avmarkerad måste den valda kombinationen för en artikelkod och en artikelrelation vara unik.
4. Ändra standardvärdet för det **fristående försäljningsprisets ursprung**, **fristående försäljningspris** eller **Procent** efter behov.
5. Välj **Lägg till** för respektive överordnad artikel som du vill lägga till i listan.
6. I fältet **Artikelkod** väljer du artikelkoden. I fältet **Artikelrelation** väljer du artikelrelationen.
7. Välj kryssrutan **Intäktsdelning**.
8. I fältet **Artikelrelation** väljer du artikelrelationen. Listan uppdateras med den överordnade artikeln och alla underordnade artiklar.
9. För den underordnade artikeln ska du ändra standardvärdet för fälten **Fristående försäljningsprisets ursprung**, **Procent för överordnat standardpris**, **Procent av överordnat fakturapris** eller **Allokera restbelopp** efter behov.
10. Välj **Lägg till artiklar** för att lägga till flera artiklar samtidigt.
11. Uppdatera frågan för att markera den artikelgrupp som du vill lägga till.
12. Välj **OK**, granska listan över artiklar som du har lagt till och välj **OK**.

### <a name="fields"></a>Fält

Sidan **Försäljningspris för fristående artikel** innehåller följande fält.

| Fält | Beskrivning |
|-------|-------------|
| Ursprungligt fristående försäljningspris | <p>Välj ursprung för det fristående försäljningspriset:</p><ul><li>**Belopp** – Det fristående försäljningspriset är ett belopp som du anger och som är mer än 0 (noll). Beloppet konverteras mellan de funktionella och ursprungliga valutorna efter behov.</li><li>**Basförsäljningspris** – Det fristående försäljningspriset matchar artikelns basförsäljningspris.</li><li>**Fakturapris** – Det fristående försäljningspriset matchar artikelns fakturapris.</li><li>**Procentandel av artikel** – Det fristående försäljningspriset anges som ett procentvärde och beräknas baserat på artikelns pris. Om du väljer detta alternativ anger du förvalt procentvärde.</li></ul>**Allokera restbelopp** – Ursprunget till det fristående försäljningspriset beräknas som *Totalt kontraktsvärde för överordnad artike* – *Totalt fristående försäljningspris för underordnade artiklar*:</p><ul><li>*Det totala kontraktsvärdet för den överordnade artikeln* är nettobeloppet eller fakturerat belopp.</li><li>*Totalt fristående försäljningspris för underordnade artiklar* är summan av det utökade eller kontraktsfristående försäljningspriset för alla underordnade artiklar, förutom den underordnade artikel som använder detta ursprungliga fristående försäljningspris.</li></ul><p>Om det beräknade beloppet är ett negativt värde sätts beloppet till 0 (noll).</p><p>**OBS:** Detta alternativ kan bara väljas för en (1) underordnad artikel i intäktsdelningen.</p></li><li>**Ingen** – Ursprunget till det fristående försäljningspriset baseras på de underordnade artiklarna. Detta alternativ gäller för artiklar som har definierats som överordnade artiklar i en mall för intäktsdelning. Om kryssrutan **Intäktsdelning** är markerad markeras detta alternativ automatiskt, och inställningen kan inte ändras.</li><li>**Procent för överordnat fakturapris** – Ursprunget till det fristående försäljningspriset är en procentandel av fakturapriset för den överordnade artikeln. Du kan ändra standardvärdet. Detta alternativ är endast tillgängligt för överordnade artiklar i mallar för intäktsdelning.</li><li>**Procent för överordnat standardpris** – Ursprunget till det fristående försäljningspriset är en procentandel av standardpriset för den överordnade artikeln. Du kan ändra standardvärdet. Detta alternativ är endast tillgängligt för överordnade artiklar i mallar för intäktsdelning. Det är standardalternativet för underordnade artiklar. När alternativet för en underordnad artikel ändras från **Procent för överordnat standardpris** till **Procent för överordnat fakturapris**, eller från **Procent av överordnat fakturapris** till **Procent av överordnat standardpris** uppdateras även de beräknade värdena.</li></ul> |
| Fristående försäljningspris | Ange det fristående försäljningspriset för artikeln. Detta fält är tillgängligt när fältet **Ursprungligt fristående försäljningspris** är inställt på **Belopp**. |
| Procentandel | Ange procentsats för det fristående försäljningspriset. Detta fält är tillgängligt när fältet **Ursprungligt fristående försäljningspris** har angetts som **Procent av artikel**, **Procent av överordnat fakturapris** eller **Procent av överordnat standardpris**. |
| Intäktsdelning | <p>Ange om en rad använder intäktsdelning:</p><ul><li>**Markerat** – Det är bara artiklar som en intäktsdelningsmall har konfigurerats för som kan väljas i fältet **Artikelrelation**. Du kan endast välja denna kryssruta för överordnade artiklar tillhörande en mall för intäktsdelning.</li><li>**Avmarkerad** – Artikeln är en standardartikel som inte använder intäktsdelning.</li></ul> |
| Relation | En symbol anger om artikeln är en överordnad eller underordnad artikel i en intäktsdelning. |
| Artikelkod | <p>Välj artikelkod **Tabell** eller **Grupp**.</p><p>Om kryssrutan **Intäktsdelning** har markerats anges detta fält som **Tabell**, och värdet kan inte ändras.</p> |
| Artikelrelation | <p>Välj ett artikelnummer.</p><p>Om kryssrutan **Intäktsdelning** har markerats går det bara att välja artiklar som är överordnade artiklar som har ställts in för intäktsdelningsmall. När den överordnade artikeln markeras uppdateras listan automatiskt med de underordnade artiklarna tillhörande den överordnade artikeln.</p> |
| Överordnad artikel | Detta fält visar artikelnumret för den överordnade artikeln. För underordnade artiklar i en intäktsdelning visas artikelnumret för den överordnade artikeln. |

## <a name="mea-templates"></a>MEA-mallar

Använd sidan **MEA-mallar** om du vill skapa och redigera mallidentifierare för arrangemang med flera element (MEA). Dessa identifierar används på sidan **Intäktsallokering** i syfte att gruppera ihop artiklar.

### <a name="create-a-template"></a>Skapar en mall

Följ dessa steg för att konfigurera en MEA-mall.

1. På sidan **MEA-mallar** väljer du **Ny**.
1. Ange ett unikt ID i fältet **Mall-ID för MEA**.
1. Ange en beskrivning i fältet **beskrivning**.
1. I fältet **Intäktskonto för periodiserat kontrakt** väljer du det konto som du vill använda för journalposter när en faktura för MEA-kontrakt skapas. Detta fält är tillgängligt när fakturering av återkommande kontrakt aktiveras och används.
1. Välj **Spara**.
