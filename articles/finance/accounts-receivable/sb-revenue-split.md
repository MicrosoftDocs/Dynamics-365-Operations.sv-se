---
title: Intäktsdelningsmallar i prenumerationsfakturering
description: I det här avsnittet beskrivs hur du ställer in mallar för intäktsdelning för artiklar som säljs som buntar.
author: JodiChristiansen
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 73dbc2242639a54d687506e7c325fec4b9a95d12
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770166"
---
# <a name="revenue-split-templates-in-subscription-billing"></a>Intäktsdelningsmallar i prenumerationsfakturering

Använd sidan **Mall för intäktsdelning** för att sätta upp mallar för intäktsfördelning. Intäktsdelningen består av en överordnad artikel som har underordnade artiklar. Den här typen av artikel säljs ofta till kunder som en enskild artikel eller bunt.

En datorartikel kan till exempel skapas på följande sätt:

- **Överordnad artikel:** Abonnemang Silver
- **Radartiklar (underordnad):**

    - Support
    - Bibehåll
    - Licens

När du skapar en överordnad artikel ska du tänka på följande begränsningar:

- En artikel kan bara anges som överordnad artikel en gång.
- Den överordnade artikeln kan väljas som underordnad artikel i samma mall.
- För en giltig mall krävs det minst en underordnad artikel.
- En artikel kan anges som underordnad artikel för mer än en buntartikel.
- Varje överordnad-underordnad relation måste vara unik.

## <a name="create-a-parent-item-that-has-child-items"></a>Skapa en överordnad artikel som har underordnade artiklar

Följ dessa steg för att skapa ett överordnat objekt som har underordnade objekt.

1. På sidan **Mall för intäktsdelning** välj **Ny**.
1. Välj en överordnad artikel i fältet **Överordnad artikel**. Fältet **Variantnummer** uppdateras automatiskt. Du kan dock ändra värdet som du vill.
1. I fältet **Allokeringsmetod** välj allokeringsmetod.
1. I listan **Komponentartiklar**, välj **Lägg till** för att lägga till underordnade artiklar.
1. Om du har valt **Procent** i fältet **Allokeringsmetod** anger du en procentsats i fältet **Procent**.

    - Om du väljer **Lika mycket** i fältet **Allokeringsmetod** uppdateras fältet **Procent** automatiskt så att alla artiklar har samma procentsats.
    - Om du har valt **Variabelt belopp**, **Noll överordnat belopp** eller **Noll belopp** i fältet **Allokeringsmetod** kommer värdet i fältet **Procent** vara **0** (noll) och kan inte ändras.

1. Välj **Spara**.

## <a name="fields"></a>Fält

Sidan **mall för intäktsdelning** innehåller följande fält.

| Fält | Beskrivning |
|-------|-------------|
| Överordnad artikel | Välj ett artikelnummer. Denna artikel blir överordnad artikel för buntartikeln du skapar. |
| Produktnamn | Produktnamnet. |
| Allokeringsmetod | <p>Välj tilldelningsmetod:</p><ul><li>**Lika med belopp** – allokeringsprocenten beräknas automatiskt och delas lika mellan artiklarna i mallen.</li><li>**Procent** – Du kan ange ett procentbelopp för allokeringen. Summan av alla procentsatser måste vara lika med 100.</li><li>**Variabelt belopp** – Underordnade artiklar som läggs till har ett nettobelopp på 0 (noll). Priset på de underordnade artiklarna måste anges på transaktionsnivå.</li><li>**Nollbelopp** – Den överordnade artikeln behåller priset per enhet och nettobeloppet. Alla underordnade artiklar har nettobeloppet 0 (noll).</li><li>**Noll överordnat belopp** – Den överordnade artikeln har ett fast nettobelopp på 0 (noll). Alla underordnade artiklar behandlas som standardartiklar. Ingen validering görs för att verifiera att summan av underordnade artikelbelopp är lika med det överordnade artikelbeloppet.</li></ul> |
| **Komponentartiklar** | |
| Komponentartikel | Välj ett artikelnummer. Denna artikel är underordnad en artikel. |
| Variantnummer | Välj variantnummer för artikeln. |
| Produktnamn | Produktnamnet. |
| Procentsats | <p>Allokeringsprocent för milstolpen:</p><ul><li>Om fältet **Allokeringsmetod** är inställt på **Procent** kan du ange du procentsatsen.</li><li>Om fältet **Allokeringsmetod** ställs in på **Lika med belopp**, delas procenten automatiskt beräknas så att varje artikel i mallen har en lika stor procentandel.</li><li>Om fältet **Allokeringsmetod** anges till **Variabelt belopp**, **Noll överordnat belopp** eller **Nollbelopp**, är procentsatsen 0 (noll) och kan inte redigeras.</li></ul><p>Värdet i det här fältet kan vara vilket positivt tal som helst mellan 0 (noll) och 100. Summan av alla procentsatser måste vara lika med 100.</p> |
| Total procent | <p>Summan av värdena i kolumnen **procent**.</p><ul><li>Om fältet **Allokeringsmetod** anges till **Lika med belopp** eller **Procent**, summan av alla procentsatser måste vara 100.</li><li>Om fältet **Allokeringsmetod** anges till **Variabelt belopp**, **Noll överordnat belopp** eller **Nollbelopp**, är den totala procentsatsen 0 (noll).</li></ul> |

## <a name="revenue-split-on-a-sales-order"></a>Intäktsdelning på en försäljningsorder

För att skapa en försäljningsorder som har en artikel som är inställd för intäktsdelning, följ dessa steg.

1. På sidan **Försäljningsorder** skapar du en försäljningsorder.
2. På raden för varje artikel som är inställd för intäktsdelning markerar du kryssrutan **Intäktsdelning**. Den artikeln blir överordnad artikel. Om mallen redan är inställd visas de underordnade artiklarna automatiskt i listan.
3. Om du vill lägga till fler underordnade artiklar, väljer du **Lägg till underordnade intäkter** och väljer den underordnade artikel som du vill lägga till.
4. Spara ordern.

## <a name="revenue-split-with-billing-schedules"></a>Intäktsdelning med faktureringsscheman

För att skapa ett faktureringsschema som har en artikel som är inställd för intäktsdelning, följ dessa steg.

1. På sidan **Alla/aktiva faktureringsscheman** skapar du ett faktureringsschema.
2. På raden för varje artikel som är inställd för intäktsdelning markerar du kryssrutan **Intäktsdelning**. Den artikeln blir överordnad artikel. Om mallen redan är inställd visas de underordnade artiklarna automatiskt i listan.
3. Om du vill lägga till fler underordnade artiklar, väljer du **Lägg till underordnade intäkter** och väljer den underordnade artikel som du vill lägga till.
4. Fortsätt med stegen när du vill arbeta med faktureringsschemat.

> [!NOTE]
> Om alternativet **Skapa intäktsdelning automatiskt** ställs in på **Ja** på sidan **Faktureringsparametrar för återkommande kontrakt** inträffar följande åtgärder:
>
> - Om raden är inställd som den överordnade posten i en intäktsfördelningsmall, markeras kryssrutan **Intäktsdelning** automatiskt.
> - De underordnade artiklarna registreras automatiskt på raden för försäljningsorder eller faktureringsschema.
>
> Om alternativet **Automatiskt skapa intäktsdelning** har ställts in på **Nej**, förklaras beteendet som tidigare.

## <a name="additional-revenue-split-information"></a>Ytterligare information om intäktsdelning

När du lägger till en artikel som ingår i en intäktsdelning ska du observera följande information: 

- Det överordnade beloppet kan inte skjutas upp.
- Startdatum, slutdatum, kvantitet, enhet, webbplats och lagerställevärden för underordnade artiklar baseras på den överordnade artikeln. De här värdena kan inte ändras för de underordnade artiklarna. Alla ändringar måste göras av den överordnade artikeln. 
- Prissättningsmetoden är **Fast** och kan inte ändras.
- Underordnade artiklar kan läggas till eller tas bort.
- Samma artikelgrupp måste användas för överordnade och underordnade artiklar. 
- Underordnade artiklar kan ha någon av följande inställningar:

    - Fälten **Faktureringsfrekvens** och **Faktureringsintervall** ställs in på samma värde som den överordnade artikeln. 
    - Ställ in fältet **Faktureringsfrekvens** på **En gång**. I det här fallet ställs fältet **Faktureringsintervall** automatiskt in på **1**. 

- Summan av nettobeloppen för de underordnade artiklarna är lika med det överordnade beloppet. Om allokeringsmetoden är **Nollbelopp** är både summan av de underordnade artikelbeloppen och det överordnade beloppet 0 (noll). 

    > [!NOTE]
    > Om allokeringsmetoden är **Noll** överordnat belopp är inte summan (icke-noll) för de underordnade artiklarna lika med det överordnade beloppet, vilket är 0 (noll). Den här allokeringsmetoden används för interna syften, så att medarbetare kan se de underordnade artiklarna. Kunderna kan bara se den överordnade artikeln.

- Om försäljningsorderns flera elementavtalstyp (MEA) är **Enstaka**, skapas motsvarande rad för flera element intäktsallokering transaktioner när de överordnade och underordnade artiklarna läggs till. 
- Om allokeringsmetoden för en intäktsdelning är **Lika med belopp**, och det överordnade beloppet ändras, omberäknas beloppen för alla underordnade rader. 
- För en intäktsdelning där allokeringsmetoden är **Variabelt belopp** inträffar följande:

    - Nettobeloppet för den överordnade artikeln visas i kolumnen **Överordnat belopp**. Det här värdet kan redigeras. Priset per enhet, nettobeloppet och rabatten är dock 0 (noll) och kan inte redigeras.
    - Priset per enhet för underordnade artiklar är 0 (noll). Du kan redigera priset per enhet eller nettobeloppet. När du redigerar ett värde uppdateras det andra värdet automatiskt.

- För en intäktsdelning där allokeringsmetoden är **Procentsats** inträffar följande:

    - Nettobeloppet för den överordnade artikeln visas i kolumnen **Överordnat belopp**. Det här värdet kan redigeras. Priset per enhet, nettobeloppet och rabatten är dock 0 (noll) och kan inte redigeras. 
    - Nettobeloppet för underordnade artiklar beräknas som *Procentsats* &times; *Överordnat belopp*.

- För en intäktsdelning där allokeringsmetoden är **Lika med belopp** inträffar följande:

    - Nettobeloppet för den överordnade artikeln visas i kolumnen **Överordnat belopp**. Det här värdet kan redigeras. Priset per enhet, nettobeloppet och rabatten är dock 0 (noll) och kan inte redigeras. 
    - Nettobeloppet för underordnade artiklar beräknas genom att dela det överordnade beloppet jämnt mellan alla underordnade artiklar. 
    - Om underordnade artiklar tas bort eller läggs till omberäknas nettobeloppet och priset per enhet så att alla underordnade rader har samma belopp. 
    - Om det överordnade beloppet inte kan delas jämnt, kan nettobeloppet och enhetspriset för den sista underordnade artikeln vara något högre eller lägre än nettobeloppet och enhetspriset för de andra underordnade artiklarna. 

- För en intäktsdelning där allokeringsmetoden är **Nollbelopp** inträffar följande:

    - Priset per enhet, nettobeloppet och rabatten kan ändras. Det överordnade beloppet är 0 (noll) och går inte att redigera. 
    - Kvantitet, enhet, webbplats och lagerställevärden för underordnade artiklar baseras på den överordnade artikeln. Du kan inte ändra de här värdena för de underordnade artiklarna. Alla ändringar måste göras av den överordnade artikeln. 
    - Enhetspriset och nettopriset för underordnade artiklar är 0 (noll) och går inte att redigera. 

- För en intäktsdelning där allokeringsmetoden är **Noll överordnat belopp** inträffar följande:

    - Enhetspriset, överordnat belopp och nettobelopp för överordnade artikeln är 0 (noll).
    - I ett faktureringsschema visas de underordnade raderna som om de lagts till manuellt och alla värden uppdateras baserat på den valda faktureringsschemagruppen. Dessa värden kan inte redigeras. För underordnade artiklar kan du få åtkomst till alternativen **Eskalering och rabatt** och **Avancerad prissättning** genom att använda fälten **Kvantitet har angetts**, **Enhetspris**, **Rabatt** och **Nettobelopp** i **Visa faktureringsinformation**. 
    - På en försäljningsorder har de underordnade raderna en rabatt och en rabattprocent på 0 (noll). 
    - Faktureringsfrekvensen för den överordnade och de underordnade artiklarna kan ändras och varje rad kan ha olika frekvens. Den överordnade artikeln uppdateras dock automatiskt så att den använder den kortaste frekvensen från de underordnade raderna. En intäktsdelning har till exempel två underordnade artiklar, varav en använder faktureringsfrekvensen **Månadsvis** och den andra använder faktureringsfrekvensen **Årligen**. I det här fallet uppdateras faktureringsfrekvensen för den överordnade artikeln till **Månadsvis**.
