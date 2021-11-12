---
title: Sökresultatmodul
description: Detta ämne handlar om moduler för sökresultat och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: dc4a01e520379a74ca3b21c1d588531412e762be
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647522"
---
# <a name="search-results-module"></a>Sökresultatmodul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Detta ämne handlar om moduler för sökresultat och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

I modulen Sökresultat returneras produktsökningsresultat och en lista över tillämpliga förfiningar för produkterna. Sökresultatmoduler på Dynamics 365 Commerce-webbplatser kan användas för att återge sidor för följande scenarier:

- Sökresultat som initieras av en användarsökning
- Sökresultat som visar en specifik uppsättning produkter, t.ex. "Shop similar looks" ("sök efter liknande")
- Listor med produkter som tillhör en kategori

Mer information om kategori- och sökresultatsidor finns i [Standardkategorins landningssida och översikt över sökresultatsidor](category-search-page-overview.md).

Följande illustration visar ett exempel på en sökresultatsida för en kategori på Fabrikams webbplats.

![Exempel på en sökresultatsida på webbplatsen Fabrikam.](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a>Egenskaper för sökresultatmodul

I följande tabell visas egenskaperna för sökresultatmodulerna tillsammans med deras värden och beskrivningar.

| Egenskap | Värden | beskrivning |
|----------|--------|-------------|
| Artiklar per sida | Heltal | Antalet objekt som ska visas på respektive sida. |
| Tillåt bakåt i PDP | **Sant** eller **falskt** | Om denna egenskap är inställd på **Sant** kommer navigeringen av säkerhetsdetaljer på produktinformationssidan (PDP) länken "Tillbaka till resultat" när en användare väljer en produkt på sökresultatsidan. |
| Visa förfiningar | **Alla**, **1**, **2**, **3** eller **4** | Antalet toppförfinare som ska utvidgas när en sida läses in. Om egenskapen exempelvis är inställd på **3** expanderas de första tre förfinarna på sidan. |
| Dölj visning av kategorihierarki | **Sant** eller **falskt** | Om egenskapen har angetts som **Sant** döljs den kategorihierarki som visas på sidan. Denna egenskap ska vara **True** om du använder [modulen för navigeringssökväg](add-breadcrumb.md) för att visa kategorihierarkin.|
| Inkludera produktattribut i sökresultat | **Sant** eller **falskt** | Om egenskapen anges som **Sant** returneras attributen för produkterna i sökresultatet. Även om dessa attribut kan visas på en Commerce-webbplats krävs ett tillägg.|
| Visa anknytningspriser | **Sant** eller **falskt** | Om denna egenskap är inställd på **Sant** visas anknytningspriser för produkter i sökresultaten när en inloggad användare bläddrar på sidan. |
| Uppdatera förfiningspanel | **Sant** eller **falskt** | Om egenskapen har satts till **Sant** uppdateras förfiningspanelen när förfining väljs. I det här läget kommer vissa flervalsförfinare att bete sig som envalsförfinare när förfiningspanelen uppdateras. |

> [!IMPORTANT]
> I  Commerce version 10.0.16 och senare kan konfigurationen **Visa anknytningspriser** användas för att visa anknytningspriser på sidan.
>
> I Commerce version 10.0.20 frisläppning och senare kan konfigurationen **Uppdatera förfiningspanel** användas för att uppdatera förfiningspanelen under val av förfining.

## <a name="supported-modules"></a>Moduler som stöds

Modulen för sökresultat stöder [snabbvisningsmodulen](quick-view-module.md), där användarna kan visa produktinformation och lägga till artiklar i kundvagnen från sökresultatsidan.

## <a name="add-a-search-results-module-to-a-category-page"></a>Lägg till en sökresultatmodul på en kategorisida

För att lägga till en sökresultatmodul på en kategorisida, följ dessa steg.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mall** anger du namnet **Sökresultat** och väljer sedan **OK**.
1. I fältet **Brödtext** väljer du ellipsen (...) och sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.
1. I fältet **Huvud** i modulen **Standardsida** väljer du ellipsen (...) och sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I fältet **Behållare** väljer du ellipsen (...) och sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **navigeringssökväg** och klicka sedan på **OK**.
1. I egenskapsfönstret för **Navigering** anger du värdet **1** för **Min. träffar**.
1. I fältet **Behållare** väljer du ellipsen (...) och sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** väljer du modulen **Sökresultat** och sedan **OK**.
1. I egenskapsfönstret **Sökresultat** anger du värdet **1** för **Min. träffar** och anger sedan övriga erforderliga egenskaper för sökresultatmodulen. Genom att ange dessa egenskaper i mallen säkerställer du att alla anpassningar till en viss kategorisida automatiskt inkluderar dessa inställningar.
1. Välj **Slutför redigering** och välj sedan **Publicera** för att publicera mallen.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du den **Sökresultat**-mall som du skapade, anger sedan **Kategorisida** för **Sidnamn** och väljer sedan **OK**. Eftersom alla värden har angetts i mallen är sidan klar att publiceras.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="enable-inventory-awareness-for-the-search-results-module"></a>Aktivera kunskap om lager för modulen sökresultat

Kunder förväntar sig vanligtvis att en e-handelsplats är lagermedveten via webbupplevelsen, så att de kan bestämma vad de ska göra om det inte finns något lager för en produkt. Sökresultatmodulen kan förbättras så att den innehåller lagerdata och ger följande erfarenheter:

- Visa en lagertillgänglighetsetikett tillsammans med produkter.
- Dölj produkter som inte finns i lager.
- Visa produkter som inte finns i lager i slutet av sökresultatlistan.
    
Om du vill aktivera dessa erfarenheter måste du konfigurera följande nödvändiga inställningar i Commerce-administration.

### <a name="enable-the-enhanced-e-commerce-product-discovery-to-be-inventory-aware-feature"></a>Aktivera funktionen utökad identifiering av näthandelsprodukt att bli lagermedveten

> [!NOTE]
> Funktionen **utökad identifiering av näthandelsprodukt att bli lagermedveten** är tillgänglig i Commerce version 10.0.20.

För att aktivera funktionen **utökad identifiering av näthandelsprodukt att bli lagermedveten** i Commerce-administration följer du stegen nedan.

1. Gå till **Arbetsytor \> Funktionshantering**.
1. Sök efter funktionen **utökad identifiering av näthandelsprodukt att bli lagermedveten** och aktivera den sedan.

### <a name="configure-the-populate-product-attributes-with-inventory-level-job"></a>Konfigurera jobbet Fyll i produktattribut med lagernivå

Jobbet **Fyll i produktattribut med lagernivå** skapar ett nytt produktattribut för att fånga lagertillgänglighet och ställer sedan in det attributet till det senaste lagernivåvärdet för varje huvudprodukt. Eftersom lagertillgängligheten för en produkt eller ett sortiment som säljs ändras rekommenderar vi starkt att du tidsplanera jobbet som en batchprocess.

Konfigurera jobb **Fyll i produktattribut med lagernivå** i Commerce-administration, följ dessa steg.

1. Gå till **Retail och Commerce \> Retail och Commerce IT \> Produkter och lager**.
1. Välj **Fyll i produktattribut med lagernivå**.
1. Gör på följande sätt i dialogrutan **Fyll i produktattribut med lagernivå**:

    1. Under **Parametrar** i fältet **Produktattribut och typnamn** anger du ett namn för det dedikerade produktattribut som kommer att skapas för att fånga in lagertillgänglighet.
    1. Under **Parametrar**, väljer du i fältet **Lagertillgänglighet grundad på** den kvantitet som lagernivåberäkningen ska baseras på (t.ex. **Fysiskt disponibelt**).
    1. Under **Kör i bakgrunden** konfigurerar du jobbet som ska köras i bakgrunden och aktiverar eventuellt alternativet **batchbearbetning**. 

> [!NOTE]
> För konsekvent beräkning av lagernivå över PDP:er och produktlistsidor på din e-handelswebbplats, se till att välja samma kvantitetsalternativ för både inställningen **Lagertillgänglighet grundad på** i Commerce-administration och inställningen **Lagernivå grundad på** i Commerce webbplatsskaparen. För information om hur du använder lagerinställningar i webbplatsskaparen, se [tillämpa lagerinställningar](inventory-settings.md).

### <a name="configure-the-new-product-attribute"></a>Konfigurera det nya produktattributet

När jobbet **Fyll i produktattribut med lagernivå** körs måste du konfigurera det nyskapade produktattributet på e-handelsplatsen där du vill aktivera lagermedvetenhet för sökresultatmodulen.

Följ dessa steg för att konfigurera attributet ny produkt i Commerce-administrationen.

1. Gå till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut** och välj näthandelsplats.
1. Markera och öppna en associerad attributgrupp, lägg till det nya produktattributet och stäng sedan sidan.
1. Välj **Ange attributmetadata**, välj det nya produktattributet och aktivera sedan alternativet **Visa attribut på kanal**, **Hämtningsbar**, **Kan förfinas** och K **an frågas**.

> [!NOTE]
> För produkter som visas i sökresultatmodulen anges lagernivån på huvudproduktnivå i stället för den enskilda variantnivån. Det har bara två möjliga värden: "tillgänglig" och "lagerförd". Den faktiska texten för värdena hämtas från definitionen [lagernivåprofil](inventory-buffers-levels.md). En huvudprodukt anses endast vara i lager när alla varianter av den inte finns i lager. Lagernivån för en variant bestäms utifrån produktens profildefinition på lagernivå. 

När alla föregående konfigurationssteg har utförts kommer anvisningarna på sökresultatsidorna att visa ett lagerbaserat filter och sökresultatmodulen hämtar lagerdata bakom den föregående konfigurationen. Du kan sedan konfigurera **lagerinställningarna för produktlistesidor** i Commerce webbplatsskaparen för att styra hur sökresultatsmodulen visar produkter som inte finns i lager. Mer information om [Använd lagerinställningar](inventory-settings.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över standardkategorilandningssida och sida för sökresultat](category-search-page-overview.md)

[Modulbibliotek – översikt](starter-kit-overview.md)

[Snabbvisningsmodul](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
