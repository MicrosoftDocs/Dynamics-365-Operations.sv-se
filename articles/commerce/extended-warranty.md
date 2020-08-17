---
title: Skapa och konfigurera utökade garantier
description: Det här avsnittet omfattar utökade garantier och beskriver hur du skapar och konfigurerar dem i Microsoft Dynamics 365 Commerce.
author: sijoshi
manager: annbe
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: sijoshi
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a875343d9b93f5ebf2c2992fba8b2f182310461e
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621203"
---
# <a name="create-and-configure-extended-warranties"></a>Skapa och konfigurera utökade garantier

[!include [banner](includes/banner.md)]

Det här avsnittet omfattar utökade garantier och beskriver hur du skapar och konfigurerar dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Kunderna väljer i allt större utsträckning support och tjänster när de köper produkter, särskilt konsumentprodukter som säljs till en premium-prispunkter, t.ex. telefoner och datorer. Genom att tillhandahålla utökade garantier för inköp kan återförsäljare hjälpa till att skapa kundlojalitet. Utökade garantier gör det möjligt för kunderna att veta var de kan gå till service och support. Därför kan de vara övertygade om att deras problem kommer att hanteras effektivt.

Utökade garantier kan säljas till kunder i en återförsäljarkanal under det initiala produktinköpet. De kan också säljas under en begränsad tid efter den första inköpet.

### <a name="warranty-item-setup"></a>Inställning av garantiartikel

Dynamics 365 Commerce tillhandahåller funktioner som gör att du kan skapa en garantiartikel och ange attribut för den. Dessa attribut inkluderar associationen mellan en produkt och en garantiartikel, priset på garantin och garantins giltighetstid. När en garantiartikel har konfigurerats och frisläppts till organisationsenheten kan en återförsäljare sälja garantier via en Modern Point of Sale (MPOS), onlinebutiker och andra återförsäljarkanaler.

### <a name="warranty-item-sales"></a>Försäljning av garantiartikel

Utökade garantier säljs i en återförsäljarkanal under det initiala produktinköpet. De kan också säljas under en begränsad tid efter den första inköpet.

I kassan (POS) ber säljaren att lägga till en utökad garanti när en relaterad produkt läggs till i en kundvagn. Därför presenteras en affärsmöjlighet med försäljning och merförsäljning till säljare som en del av försäljningsflödet.

Kunder kan också returnera senare och köpa en utökat garanti för en produkt som de tidigare har köpt. I dessa fall kan en säljare söka efter den ursprungliga transaktionen och sälja kunden den relaterade utökade garantiartikeln.

### <a name="warranty-terminology"></a>Garantiterminologi

I följande tabell definieras vissa garantier som är relaterade till garantin.

| Villkor | beskrivning |
|------------------------------|--------------|
| Utökad garanti/garanti | En *utökad garanti* refererar till ett serviceavtal eller kontrakt som ger en långvarig garanti till kunder. Den utökade garantin omfattar den ytterligare tjänsten för utbyte av eller reparerade varor under den utökade garantins täckningsperiod. |
| Tillverkarens garanti | En *tillverkares garanti* (kallas ofta för *begränsad garanti*) är den garanti som kunderna får när de köper en produkt. Här följer några av funktionerna för tillverkarens garanti:<ul><li>Garantikostnaden ingår i kostnaden för produkten. Kunderna behöver inte betala något ytterligare belopp för tillverkarens garanti.</li><li>Beroende på produktkategori är tillverkarens garanti vanligtvis 30 dagar, sex månader eller ett år. (För de flesta hemelektronikprodukter varar garantin i ett år).</li><li>Garantin täcker alla fel som orsakas av mekaniska eller elektriska fel. Täckningen är begränsad och den omfattar inte olycksskador på den köpta produkten. Kunder som vill skydda produkterna som de köper från vardagliga skador bör investera i en utökad garanti. Utökade garantier varar i två till tio år, beroende på produktkategori. De har också större täckning och täcker varje vardagliga missöden, t.ex. fall, spill och fläckar.</li></ul> |
| Garantiartikel | En *garantiartikel* är en utökad garantiartikel som säljs för en garantiberättigad artikel. Ett exempel är en två års olycksskyddsplan för bärbara datorer. |
| Garantiberättigad artikel | En *garantiberättigad artikel* är en serialiserad produkt som en garanti säljs för. En bärbar dator är till exempel en garantiberättigad artikel som kan säljas till två år och tre års utökad garanti. |
| Garantigrupp | En *garantigrupp* är en relation mellan garantiartiklar och garantiberättigad artiklar. Kassan använder garantigrupper för att fastställa vilka garantiartiklar som säljare ska föreslå att lägga till när en garantiberättigad artikel läggs till i en kundvagn. |
| Garantipolicy | En *garantipolicy* är en entitet som skapas i Commerce när en garantipolicy säljs. En garantipolicy omfattar information som start- och slutdatum för den inköpta garantiartikeln, villkoren och villkoren samt serienumret för den motiverade produkten. Garantipolicynummer kan delas med kunder så att de har en referens till den utökade garanti artikeln som de köpt. |

## <a name="create-a-warranty-item"></a>Skapa en garantiartikel

Följ de här stegen om du vill skapa en garantiartikel i Commerce.

1. Gå till **Retail och Commerce \> Produkter och kategorier \> Produkter**.
1. Välj **Nytt** för att skapa en garantiartikel.
1. I dialogrutan **Ny produkt** i fältet **Produkttyp** väljer du **Tjänst**.
1. I fältet **Delprodukttyp** väljer du **Produkt**.
1. I fältet **Produkttjänsttyp** väljer du **Tjänst**.
1. I fältet **Produktnamn** anger du ett produktnamn.
1. I fältet **butikskategori** väljer du ett värde i listrutan och väljer sedan **OK**.
1. I fältet **Produktnummer** anger du ett produktnummer.
1. Välj **OK**.
1. På snabbfliken **Produktdetaljer** på snabbfliken **Garanti**, ange fältet **Tidsenhet** och **Tidslängd**.

    | Fältnamn | Värde | beskrivning |
    |------------|-------|-------------|
    | Tidsenhet | **Dagar**, **veckor**, **månader** eller **År** | Det här fältet innehåller den tidsenhet som används för garantin. |
    | Tidslängd | Ett positivt heltalsvärde | I det här fältet anges garantins giltighetstid för den valda tidsenheten. |

    Om du till exempel vill ha en två års garanti ställer du in fältet **tidsenhet** på **År** och fältet **tidslängd** på **2**. Du kan också ställa in värdet för fältet **Tidsenhet** till **Månader** och fältet **Tidslängd** till **24**, som visas i bilden nedan.

    ![Produktinformationssida för en garantiartikel](./media/ew-time-properties.png)

1. Välj **Spara** för att spara garantiartikeln.
1. Frisläpp garantiprodukten till företaget så att den kan säljas. För mer information, se [Ställ in butiksprodukter](set-up-retail-products.md).
1. På sidan **Frisläppt produkt information** på snabbfliken **Garanti** anger du fälten **Bas för prisintervall**, **Nedre gräns** och **Övre gräns**.

    | Fältnamn | Värde | beskrivning |
    |------------|-------|-------------|
    | Bas för prisintervall | **Inget**, **Grundpris** eller **Försäljningspris** | <ul><li>**Ingen** – Värdena **Nedre gräns** och **Övre gräns** för prisintervall är inte tillämpliga.</li><li>**Grundpris** – En given garanti kommer att tillämpas om grundpriset (dvs. priset utan rabatter) för den garanterade artikeln ligger mellan värdena **Nedre gränsen** och den **Övre gränsen** som anges här, baserat på priset för den motiverade artikeln.</li><li>**Försäljningspris** – detta värde är reserverat för framtida användning.</li></ul> |
    | Nedre gräns, övre gräns | Ett positivt heltalsvärde | Dessa fält definierar de övre och nedre prisgränserna för den artikel som är berättigad och hur den aktuella garantiartikeln kan användas för den garantiberättigade artikeln. Dessa gränser kan baseras på den motiverade artikelns grundpris (även kallad tillverkarens föreslagna butikspris \[MSRP\]). Om fältet **Bas för prisintervall** anges till endast **Grundpris**, kommer endast en garantiberättigad artikel (produkt) som har ett grundpris mellan värdena **nedre gräns** och **övre gräns** kommer att utlösa en uppmaning om att lägga till garantiposten i kassan. |

    I följande bild visas till exempel fältet **Bas för prisintervall** som anges till **Grundpris**, fältet **nedre gräns** anges till 500 $ och fältet **övre gräns** anges till 1 000 $.
    
    ![Informationssida för frisläppt produkt för en garantiartikel](./media/ew-release-product-details.png)

1. Sortera garantiartikeln till den kanal där den ska säljas. Mer information finns i [Ställ in sortiment](set-up-assortments.md).

### <a name="example"></a>Exempel

En produkt som kan vara föremål för en bärbar dator (produkt) har ett grundpris på 999 $ och det finns två garantiberättigade artiklar för bärbar dator:

- Garanti\_1 har en nedre gräns för 500 $ och en övre gräns på 1 000 $ och **Bas för prisintervall** är inställt på **grundpris**.
- Garanti\_2 har en nedre gräns på 1 001 $ och en övre gräns på 2 000 $ och **Bas för prisintervall** är inställt på **grundpris**.

När den bärbara datorn läggs till i en kundvagn visas i så fall en uppmaning att lägga till garanti\_1 i kassan, eftersom priset på den bärbara datorn ligger mellan det nedre och övre gräns värdet för garanti\_1.

> [!NOTE]
> Om du till exempel vill att frågor ska visas både om garanti\_1 och garanti\_2, oavsett pris på garantiberättigad artikel, ställer du in fältet **Bas för prisintervall** till **ingen**.

## <a name="configure-channel-specific-settings"></a>Konfigurera kanalspecifika inställningar

Med kanalspecifika inställningar kan du ange om en fråga ska läggas till om en garantiartikel ska visas i kassan när en garantiberättigad artikel läggs till i en kundvagn.

Om du vill konfigurera kanalspecifik inställning i Commerce följer du stegen nedan.

1. Gå till **Retail och Commerce \> Produkter och kategorier \> Garanti \> Garantiinställningar**.
1. På fliken **Kanalspecifik** i kolumnen **Fråga efter garanti** för din kanal, följ ett av stegen nedan:

    - Markera kryssrutan om en fråga om garantiartikeln ska visas i kassan när en berättigad artikel läggs till i kundvagnen.
    - Avmarkera kryssrutan om ingen fråga om garantiartikeln ska visas i kassan när en berättigad artikel läggs till i kundvagnen.

1. Kör **1070** jobbet för att synkronisera data till kanalen.

## <a name="configure-a-number-sequence-for-warranty-policies"></a>Konfigurera en nummerserie för garantipolicyer

Varje garantipolicy identifieras unikt av ett garantipolicynummer som genereras av en nummerserie. Mer information om nummerserier, se [Översikt över nummerserier](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Följ de här stegen om du vill konfigurera en nummerserie för garantipolicyn i Commerce.

1. Gå till **Retail och Commerce \> Produkter och kategorier \> Garanti \> Garantiinställningar**.
1. På fliken **Nummerserier** i raden för referensen **Garantipolicy** ange eller välj ett värde i fältet **Nummerseriekod**.

## <a name="set-up-a-warranty-group"></a>Ställ in en garantigrupp

En garantigrupp är en relation mellan garantiartiklar och garantiberättigad artiklar. Kassan använder garantigrupper för att fastställa vilka garantiartiklar som säljare ska föreslå att lägga till när en garantiberättigad artikel läggs till i en kundvagn.

Så här ställer du in en garantigrupp i Commerce.

1. Gå till  **Retail och Commerce \> Produkter och kategorier \> Garanti \> Garantigrupper**.
1. Välj **Nytt** för att skapa en garantigrupp.
1. Ange ett unikt namn för den nya gruppen i fältet **Namn**.
1. På snabbfliken **Allmänt** i fältet **Beskrivning** anger du en beskrivning för gruppen.
1. På snabbfliken **garantiprodukter** väljer du **Lägg till rad** för att lägga till en garantiartikel.
1. I fältet **visningsordning** anger du ett nummer som rangordnar garantigruppen vid kassan. I kassan visas garantiartiklar i stigande rangordning i garantitolken.
1. På snabbfliken **garantiberättigade produkter** väljer du **Lägg till rad** för att lägga till garantiberättigade produkter.
1. Om garantiartikeln gäller för en hel kategori av garantiberättigade artiklar (produkter) väljer du kategorin i fältet **kategori**. Om garantiartikeln gäller för en specifik artikel (produkt) väljer du produkten i fältet **produkt**.
1. På snabbfliken **Tillämpliga kanaler** väljer du **Lägg till rad** om du vill lägga till kanalen där garantiartikeln ska säljas.
1. Välj **Spara** för att spara konfiguration.
1. Välj **publicera** om du vill publicera garantigruppen.
1. Kör **1040** jobbet för att synkronisera data till kanalen.

## <a name="sell-warranty-items-at-the-pos"></a>Sälj garantiartiklar i kassan

Två kassaåtgärder gör det möjligt för säljare att sälja garantiartiklar under arbetsflödet för kundinköp:

- **Lägg till garanti** – den här åtgärden utlöser en ledtext som visar tillämpliga garantier för en motiverad artikel som väljs i kundvagnen.
- **Lägg till garanti i befintlig transaktion** – den här åtgärden gör att säljaren säljer garantier för de artiklar som tidigare har sålts. Säljare kan hitta den ursprungliga transaktionen för en garantiartikel genom att ange kvittonumret för transaktionen.

I följande illustration visas ett exempel på ett kassaterminalfönster med en uppmaning att lägga till en garantiartikel för det aktuella inköpet av en artikel som kan vara berättigad.

![Exempel på en fråga om du vill lägga till en garantiartikel för det aktuella inköpet](./media/ew-sell-warranty.png)

I följande illustration visas ett exempel på funktionen för att lägga till en garantiartikel för en motiverad artikel som tidigare har sålts.

![Exempel på funktionen för att lägga till en garantiartikel för en tidigare såld artikel](./media/ew-add-warranty-existing.png)

## <a name="process-warranty-transactions"></a>Bearbeta garantitransaktioner

När garantier säljs i hämtköpstransaktioner, efter det att transaktionerna har bokförts i Commerce-administration kan Commerce-användare köra jobbet **Bearbeta garantitransaktioner** för att bearbeta garantitransaktionerna och skapa garantipolicy.

Följ de här stegen för att hantera garantitransaktioner i Commerce-administration.

1. Gå till **Retail och Commerce \> Produkter och kategorier \> Garanti \> Bearbeta garantitransaktioner**.
1. I dialogrutan **Välj organisationsnoder** i fältet **Organisationshierarki** välj ett värde.
1. I listan **tillgängliga organisationsnoder** väljer du antingen en enskild butik eller, om du vill skapa batchjobbet för en grupp med butiker, en nod.
1. Välj högerpilen för att lägga till ditt val i listan **Valda organisationsnoder**.
1. Välj fliken **Kör i bakgrunden**.
1. Ställ in alternativet **Batchbearbetning** på **Ja** och välj sedan **återkommande**.
1. I dialogrutan **Definiera resurser** i fältet **Startdatum** väljer eller anger du ett startdatum för upprepningen.
1. I fältet **starttid** väljer eller anger du en starttid för upprepningen.
1. Gör något av följande:

    - Välj alternativet **inget slutdatum** om upprepningen aldrig ska sluta.
    - Välj alternativet **slut efter** om upprepningen ska avslutas efter ett visst antal körningar. Om du väljer det här alternativet ska du ange antalet körningar.
    - Välj alternativet **Sluta den** om upprepningen bör sluta ett visst datum. Om du väljer det här alternativet ska du välja eller ange datumet.

1. Välj **OK**.
1. Välj **OK**.

## <a name="warranty-policies"></a>Garantipolicy

När en utökad garanti säljs skapas automatiskt en entitet för garantipolicy. Garantipolicynummer kan delas med kunder så att de har en referens till garantiartikeln som de köpt. Egenskaperna för garantipolicyerna inkluderar det effektiva startdatumet och utgångsdatumet för garantin, villkoren samt serienumret på den garantiberättigade artikeln som garantin såldes för.

> [!NOTE]
> Egenskaper för garantipolicy skapas automatiskt när entiteterna för garantipolicy skapas. De kan för närvarande inte konfigureras manuellt eller redigeras.

I följande tabell beskrivs egenskaperna för garantipolicy och deras värden. I Commerce-administration heter databasregistret WARRANTYPOLICY.

| Egenskapsnamn | Värde | beskrivning |
|---------------|-------|-------------|
| PolicyNumber | En teckensträng (högst 20 tecken) | Garantipolicynumret |
| WarrantiedItemId | En teckensträng (högst 20 tecken) | ID för den garantiberättigade artikeln |
| WarrantiedInventoryLotId | En teckensträng (högst 20 tecken) | Lagerparti-ID för den garantiberättigade artikeln |
| WarrantiedSerialNumber | En teckensträng (högst 20 tecken) | Serienummer för den garantiberättigade artikeln |
| WarrantiedFulfilledDate | Ett datum | Uppfyllelsedatumet för den garantiberättigade artikeln |
| WarrantyItemId | En teckensträng (högst 20 tecken) | ID för garantiartikeln |
| WarrantyInventoryLotId | En teckensträng (högst 20 tecken) | Lagerparti-ID för den garantiartikeln |
| WarrantySalesDate | Ett datum | Försäljningsdatum för garantiartikeln |
| WarrantyEffectiveDate | Ett datum | Giltighetsdatum för garantipolicyn |
| WarrantyExpirationDate | Ett datum | Utgångsdatumet för garantipolicyn |
| CustAccount | En teckensträng (högst 20 tecken) | Kundkontonummer |
| Status | **Skapad**, **Annullerad**, **Giltig** eller **Förfallen** | Status för garantipolicyn |
| Anteckningar | En teckensträng (högst 255 tecken) | Anteckningar om garantipolicyn, t.ex. villkor |

## <a name="frequently-asked-questions-faq"></a>Vanliga frågor

**Varför ser jag inte någon garantifråga i kassan?**

Se till att garantiartikeln är utvald för kanalen. Kontrollera också att garantigruppen har konfigurerats så att den innehåller relevant kanal.

**När jag försöker lägga till en garanti i en befintlig transaktion och ange kundens kvittonummer för order, varför ser jag inte några transaktionsradartiklar?**

Kvitton kan bara hittas om ett dragjobb (P-jobb) körs för att överföra inleveranserna till Commerce-administration. För att köra P-jobb, gå till **Retail och Commerce \> Retail och Commerce IT \> Distributionsschema**, välj **P-0001** jobb och välj sedan **Kör nu**.

**Varför gäller endast garantifunktionen för serialiserade produkter?**

En garanti är en tjänst som tillhandahålls för en specifik, unik produkt. I Dynamics 365 kan en produkt identifieras unikt av ett serienummer.

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in butiksprodukter](set-up-retail-products.md)

[Ställa in sortiment](set-up-assortments.md)

[Nummerserier – översikt](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)
