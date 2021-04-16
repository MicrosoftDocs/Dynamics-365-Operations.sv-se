---
title: Arbetspolicyer
description: Det här avsnittet innehåller information om hur du ställer in arbetspolicyer.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 39a9ba00763fac220eff16bdd42aa07cc8e35ba4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838140"
---
# <a name="work-policies"></a>Arbetspolicyer

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in systemet och mobilappen för distributionslagerhantering så att de stöder arbetspolicyer. Du kan använda den här funktionen för att snabbt registrera lager utan att skapa inlagringsarbete när du tar emot inköps- eller överföringsorder, eller när du avslutar tillverkningsprocesser. Det här avsnittet innehåller allmän information. Detaljerad information som är relaterad till det mottagna ID-numret finns i [Inleverans av ID-nummer som erhålls via mobilappen för distributionslagerhantering](warehousing-mobile-device-app-license-plate-receiving.md).

En arbetspolicy styr om lagerarbete ska skapas när en tillverkad artikel rapporteras som färdig eller när varor tas emot med hjälp av mobilappen för distributionslagerhantering. Du ställer in varje arbetspolicy genom att definiera villkoren där den gäller: arbetsordertyper och processer, lagerstället och (valfritt) produkterna. En inköpsorder för produkt *A0001* måste tas emot på plats *RECV* i lagerstället *24*. Senare förbrukas produkten i en annan process vid platsen *RECV*. I det här fallet kan du ställa in en arbetspolicy för att förhindra att inlagringsarbete skapas när en arbetare rapporterar produkt *A0001* som inlevererad på plats *RECV*.

> [!NOTE]
> - Om en arbetspolicy ska vara aktiv måste du definiera minst en plats för den på snabbfliken **lagerplatser** på sidan **Arbetspolicyer**. 
> - Du kan inte ange samma plats för flera arbetspolicyer.
> - Alternativet **Skriv ut etikett** för menyalternativ för mobila enheter kommer inte att skriva ut en ID-nummeretikett om inte ett arbete skapas.

## <a name="activate-the-features-in-your-system"></a>Aktivera funktionerna i systemet

Om du vill göra alla funktioner som beskrivs i det här avsnittet tillgängliga i systemet aktiverar du följande två funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Förbättrad mottagning av registreringsskylt
- Arbetspolicyförbättringar för inkommande arbete

## <a name="the-work-policies-page"></a>Sidan arbetspolicyer

Om du vill ställa in arbetspolicyer går du till **Hantering av distributionslager \> inställningar \> arbete \> arbetspolicyer**. Ställ sedan in fälten enligt beskrivningen i följande underavsnitt på varje snabbflik.

### <a name="the-work-order-types-fasttab"></a>Snabbfliken arbetsordertyper

På snabbfliken **arbetsordertyper** kan du lägga till alla arbetsordertyper och relaterade arbetsprocesser som arbetspolicyn gäller för. Följande arbetsordertyper och relaterade arbetsprocesser stöds för arbetspolicyer.

| Typ av arbetsorder | Arbetsprocess |
|---|---|
| Råmaterialhämtning| Alla relaterade processer |
| Plats för samprodukt och biprodukt | Alla relaterade processer |
| Plats för slutförda varor | Alla relaterade processer |
| Överföringsinleverans | Plats och mottagning av registreringsskylt |
| Inköpsorder | <ul><li>Plats och mottagning av registreringsskylt</li><li>Mottagande och inleverans av lastartikel</li><li>Inköpsorderrad har inlevererats och inlagrats</li><li>Inleverans och inlagring av inköpsorderartikel</li></ul> |

Om du vill ställa in en arbetspolicy så att den gäller för flera arbetsprocesser av samma arbetsordertyp, lägger du till en separat rad för varje arbetsprocess i rutnätet.

För varje rad i rutnätet anger du fältet **Metod för att skapa arbete** till ett av följande värden:

- **Aldrig** – Arbetspolicyn förhindrar att arbetsuppgifter på lagerstället skapas för vald arbetsordertyp och relaterade arbetsprocesser.
- **Direktutleverans** – Arbetspolicyn kommer att skapa direktutleverans med hjälp av den policy du väljer i fältet **Direktleveranspolicynamn**.

### <a name="the-inventory-locations-fasttab"></a>Snabbfliken lagerplatser

På snabbfliken **lagerplatser** lägger du till alla platser där den här arbetspolicyn ska användas. Om ingen plats finns associerad med en arbetspolicy, gäller inte arbetspolicyn för några processer.

Du kan inte ange samma plats för flera arbetspolicyer.

Det går att använda ett lagerställe som är tilldelat till en platsprofil även om **Använd spårning av ID-nummer** inte är aktiverad. I det här fallet registrerar arbetare direkt lagerbehållningen.

### <a name="the-products-fasttab"></a>Snabbfliken produkter

På fliken **produkter** ställer du in fältet **produktval** så att du kan kontrollera vilka produkter policyn ska gälla för:

- **Alla** – policyn ska gälla för alla produkter.
- **Markerad** – policyn ska bara gälla för produkter som visas i rutnätet. Använd verktygsfältet på snabbfliken **produkter** om du vill lägga till produkter i rutnätet eller ta bort dem från rutnätet.

## <a name="default-and-custom-to-locations"></a>Standard och anpassade till platser

> [!NOTE]
> Om du vill göra funktionen som beskrivs i det här avsnittet tillgänglig i ditt system, måste du aktivera funktionerna *Förbättringar av inleverans av ID-nummer* och *Förbättringar av arbetspolicy för inkommande arbete* i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Tidigare har systemet endast tagit emot den standardplats som har definierats för varje lagerställe. Menyalternativen för mobila enheter som använder följande processer för arbetsskapande har nu alternativet **Använd standarddata**. Med det här alternativet kan du tilldela en anpassad "till"-plats till ett eller flera menyalternativ. (Det här alternativet är redan tillgängligt för andra typer av menyalternativ.)

- Plats och mottagning av registreringsskylt
- Mottagande och inleverans av lastartikel
- Inköpsorderrad har inlevererats och inlagrats
- Inleverans och inlagring av inköpsorderartikel

Inställningen **Till plats** för ett menyalternativ åsidosätter standard mottagningsplatsen för lagerstället, för alla order som bearbetas med hjälp av det menyalternativet.

Gör så här om du vill konfigurera ett menyalternativ för mobila enheter för att stödja mottagning på en vald plats:

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Välj eller skapa ett menyalternativ som använder en av arbetsprocesserna som listas tidigare i det här avsnittet.
1. På snabbfliken **allmänt** anger du alternativet **Använd standarddata** till **Ja**.
1. I åtgärdsfönstret, välj **Standarddata**.
1. Ange följande värden på sidan **Standarddata**:

    - **Standarddatafält:** Ange det här fältet till *till plats*.
    - **Lagerställe:** Välj det lagerställe vid destinationen som ska användas för menyartikeln.
    - **Plats:** i det här fältet visas en lista över de plats-ID:n som är tillgängliga för det valda lagerstället. Inställningen av det här fältet har dock ingen effekt. Därför kan du lämna det tomt. Du kan dock använda listan för att bekräfta det ID som du måste ange i fältet **Hårdkodat värde**.
    - **Hårdkodat värde:** Ange plats-ID för mottagningsplatsen som gäller för det här menyalternativet.

> [!TIP]
> En arbetspolicy kan bara användas om alla mottagande platser anges i de relevanta inställningarna för arbetspolicy. Detta krav gäller oavsett om du använder standardplatsen för lagermottagning eller en anpassad "till"-plats.

## <a name="example-scenario-warehouse-receiving"></a>Exempelscenario: inleverans av lager

Alla produkter som tas emot av processen *Inleverans och inlagring av inköpsorderartikel* måste registreras på platsen *FL-001* och de måste vara tillgängliga i lagerstället *24*. Arbete ska dock inte skapas. Produkter som tas emot av någon annan process (dvs. genom att använda andra menyartiklar för mobila enheter) registreras på standardplatsen för inleverans av lager (*RECV*) och arbete ska skapas som vanligt. (Det här scenariot visar inte standardinställningarna för mottagning.)

Det här scenariot kräver följande element:

- En arbetspolicy för processen *Inleverans och inlagring av inköpsorderartikel* på platsen *FL-001* för alla produkter
- En menyartikel på en mobil enhet som har standarddata och som anger fältet **Till plats** till *FL-001*

### <a name="prerequisites"></a>Förutsättningar

Om du vill göra funktionen som beskrivs i det här scenariot tillgänglig i ditt system, måste du aktivera funktionerna *Förbättringar av inleverans av ID-nummer* och *Förbättringar av arbetspolicy för inkommande arbete* i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Den här scenariot använder sig av standard demodata. Därför, om du vill arbeta igenom scenariot genom att använda värdena som ges här måste du arbeta på ett system där demodata är installerat. Dessutom måste du välja den **USMF** juridiska personen.

### <a name="set-up-a-work-policy"></a>Konfigurera en arbetspolicy

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetspolicyer**.
1. Välj **Ny**.
1. I fältet the **Arbetspolicynamn** anger du *Ingen inköpspost för inlagringsarbete*.
1. Välj **Spara**.
1. På snabbfliken **Arbetsordertyper** väljer du **Lägg till** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:

    - **Arbetsordertyp:** *inköpsorder*
    - **Arbetsprocess:** *Inköpsorderpost har inlevererats och inlagrats*
    - **Arbetsskapande metod:** *aldrig*
    - **Direktleveranspolicynamn:** Lämna det här fältet tomt.

1. På snabbfliken **Lagerplatser** väljer du **Lägg till** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:

    - **Lagerställe:** *24*
    - **Plats:** *FL-001*

1. På snabbfliken **produkter** ställer du in fältet **produktval** till *alla*.
1. Välj **Spara**.

### <a name="set-up-a-mobile-device-menu-item-to-change-the-receiving-location"></a>Ställ in ett menyalternativ för mobila enheter för att ändra mottagningsplats

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I vänster ruta, välj befintligt menyalternativ **inleverans av inköp**.
1. På snabbfliken **allmänt** anger du alternativet **Använd standarddata** till *Ja*.
1. Välj **Spara**.
1. I åtgärdsfönstret, välj **Standarddata**.
1. På sidan **Standarddata** i åtgärdsfönstret väljer du **Ny** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:

    - **Standarddatafält:** *till plats*
    - **Lagerställe:** *24*
    - **Plats:** lämna det här fältet tomt.
    - **Hårdkodat värde:** *FL-001*

1. Välj **Spara**.

### <a name="receive-a-purchase-order-without-creating-work"></a>Ta emot en inköpsorder utan att skapa arbete

Exemplet i det här avsnittet visar hur du tar emot en inköpsorderartikel, men utan att skapa arbete på en plats som skiljer sig från den standardplats för inleverans som har ställts in för lagerstället. I det här exemplet används arbetspolicyn och objektet i den mobila enheten som du skapade tidigare i det här scenariot.

#### <a name="create-a-purchase-order"></a>Skapa en inköpsorder

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Välj **Ny**.
1. I dialogrutan **Skapa inköpsorder** ställ in följande värden:

    - **Leverantörskonto:** *US-101*
    - **Plats:** *2*
    - **Lagerställe:** *24*

1. Välj **OK** för att stänga dialogrutan och öppna den nya inköpsordern.
1. På snabbfliken **inköpsorderrader** anger du följande värden för den tomma raden:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *1*

1. Välj **Spara**.
1. Anteckna inköpsordernumret.

#### <a name="receive-a-purchase-order"></a>Få en inköpsorder

1. På den mobila enheten logga in på lagerställe *24* med hjälp av *24* som användar-ID och *1* som lösenord.
1. Välj **Ankommande**.
1. Välj **inköpsmottagare**. Fältet **Plats** fältet ska ställas in på *FL-001*.
1. Ange inköpsordernumret för inköpsordern som du skapade i den föregående proceduren.
1. I fältet **artikelnummer** ange *A0001*.
1. Välj **OK**.
1. I fältet **Kvantitet**, ange *1*.
1. Välj **OK**.

Inköpsordern tas nu emot, men inget arbete associeras med den. Lagerbehållningen har uppdaterats och kvantiteten *1* av artikel *A0001* finns nu tillgänglig på platsen *FL-001*.

## <a name="example-scenario-manufacturing"></a>Exempelscenario: tillverkning

I följande exempel finns det två produktionsorder *PRD-001* och *PRD-002*. Produktionsorder *PRD-001* har en åtgärd med namnet *Sammansättning*, där produkten *SC1* rapporterats som färdig till plats *001*. Produktionsorder *PRD-002* har en åtgärd med namnet *Målar* och förbrukar produkten *SC1* från platsen *001*. Produktionsorder *PRD-002* förbrukar även råmaterial *RM1* från platsen *001*. Råmaterial *RM1* lagras på lagerställeplats och *BULK-001* plockas till platsen *001* av lagerställets arbetsuppgift för plockning av råmaterial. Plockningsarbetet skapas när produktion *PRD-002* frisläpps.

[![Policyer för distributionslagerarbete](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)

När du planerar att konfigurera en arbetspolicy för detta scenario på lagerstället, bör du beakta följande punkter:

- Arbetsuppgifter för förvaring av färdiga varor på lagerställen krävs inte när du rapporterar produkten *SC1* som färdig från produktionsorder *PRD-001* till platsen *001*. Detta eftersom åtgärden *Målar* för produktionsorder *PRD-002* förbrukar produkten *SC1* på samma plats.
- Lagerställearbete för plockning av råmaterial krävs för att flytta råmaterialet *RM1* från lagerplats *BULK-001* till plats *001*.

Här följer ett exempel på en arbetspolicy som du kan ställa in, baserat på dessa överväganden:

- **Namn på arbetspolicy:** *inget inlagringsarbete*
- **Arbetsordertyper:** *Plats för slutförda varor* och *Plats för samprodukt och biprodukt*
- **Lagerställen:** lagerställe *51* och plats *001*
- **Produkter:** *SC1*

Följande exempelscenario ger steg-för-steg-instruktioner om hur du ställer in arbetspolicyn för lagerstället för detta scenario.

## <a name="example-scenario-report-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Exempelscenario: Rapportera en produktionsorder som slutförd till en plats som inte kontrolleras via registreringsskylt

Detta scenario visar ett exempel som visar hur du rapporterar en produktionsorder som slutförd till en plats som inte kontrolleras via registreringsskylt.

Den här scenariot använder sig av standard demodata. Därför, om du vill arbeta igenom scenariot genom att använda värdena som ges här måste du arbeta på ett system där demodata är installerat. Dessutom måste du välja den **USMF** juridiska personen.

### <a name="set-up-a-warehouse-work-policy"></a>Konfigurera en policy för lagerarbete

Lagerställeprocesser inkluderar inte alltid lagerarbete. Genom att definiera en arbetspolicy kan du förhindra skapande av arbete för råmaterialhämtning och inlagring av färdiga varor för en uppsättning av produkter på specifika platser.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetspolicyer**.
1. Välj **Ny**.
1. I fältet **Arbetspolicynamn** anger du *Inget inlagringsarbete*.
1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Arbetsordertyper** väljer du **Lägg till** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:

    - **Arbetsordertyp:** *Plats för slutförda varor*
    - **Arbetsprocess:** *Alla relaterade arbetsprocesser*
    - **Arbetsskapande metod:** *aldrig*
    - **Direktleveranspolicynamn:** Lämna det här fältet tomt.

1. Välj **Lägg till** igen om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:

    - **Arbetsordertyp:** *Plats för samprodukt och biprodukt*
    - **Arbetsprocess:** *Alla relaterade arbetsprocesser*
    - **Arbetsskapande metod:** *aldrig*
    - **Direktleveranspolicynamn:** Lämna det här fältet tomt.

1. På snabbfliken **Lagerplatser** väljer du **Lägg till** om du vill lägga till en rad i rutnätet och sedan ange följande värden för den nya raden:

    - **Lagerställe:** *51*
    - **Plats:** *001*

1. På snabbfliken **produkter** ställer du in fältet **produktval** till *valda*.
1. På snabbfliken **produkter**, välj **Lägg till** om du vill lägga till rutnätet.
1. I nya rader, ange fältet **Artikelnummer** till *L0101*.
1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-an-output-location"></a>Ställ in en utleveransplats

1. Gå till **Organisationsadministration \> Resurser \> Resursgrupper**.
1. I det vänstra fönstret, välj resursgrupp **5102**.
1. Ange följande värden på snabbfliken **Allmänt**:

    - **Utleveranslagerställe:** *51*
    - **Utleveransplats:** *001*

1. Klicka på **Spara** i åtgärdsfönstret.

> [!NOTE]
> Plats *001* är en ej ID-nummerstyrd plats. Du kan ställa in en utgående plats som inte är ID-nummerstyrd utleveransplats bara om en lämplig arbetspolicy finns för platsen.

### <a name="create-a-production-order-and-report-it-as-finished"></a>Skapa en produktionsorder och rapportera den som färdig.

1. Gå till **Produktionskontroll \> Produktionsorder \> Alla produktionsorder**.
1. Välj **Ny produktionsorder** i åtgärdsfönstret.
1. I dialogrutan **Skapa produktionsorder** ange fältet **Artikelnummer** till *L0101*.
1. Välj **Skapa** för att skapa den försäljningsordern och stänga dialogrutan.

    En ny tillverkningsorder läggs till i rutnätet på sidan **Alla produktionsorder**.

    Behåll den nya produktionsordern vald.

1. I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Process**, markerar du **Uppskatta**.
1. I dialogrutan **uppskattningen** läs uppskattningen och välj sedan **OK** för att stänga dialogrutan.
1. I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Process**, markerar du **Start**.
1. I dialogrutan **Start** på fliken **Allmänt** anger du fältet **automatisk strukturlisteförbrukning** till *Aldrig*.
1. Välj **OK** om du vill spara inställningarna och stänga dialogrutan.
1. I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Process**, markerar du **Rapportera som slutförd**.
1. I dialogrutan **Rapportera som slutförd** på fliken **Allmänt** anger du alternativet **Acceptera fel** till *Ja*.
1. Välj **OK** om du vill spara inställningarna och stänga dialogrutan.
1. I åtgärdsfönstret, på fliken **Lagerställe**, i gruppen **Allmänt**, väljer du **Arbetsdetaljer**.

När tillverkningsordern rapporterades som färdig, genererades inget arbete för plats. Detta beteende inträffar, eftersom en arbetspolicy definieras som hindrar arbete från att genereras när produkten *L0101* rapporterats som färdig till plats *001*.

## <a name="more-information"></a>Mer information

Mer information om menyartiklar för mobila enheter finns i [ställa in mobila enheter för lagerarbete](configure-mobile-devices-warehouse.md).

Detaljerad information om det mottagna ID-numret och arbetspolicyer finns i [Inleverans av ID-nummer som erhålls via mobilappen för distributionslagerhantering](warehousing-mobile-device-app-license-plate-receiving.md).

Mer information om inkommande belastningshantering finns i [Lagerhantering av inkommande laster för inköpsorder](inbound-load-handling.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]