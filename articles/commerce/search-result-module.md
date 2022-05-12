---
title: Sökresultatmodul
description: Detta ämne handlar om moduler för sökresultat och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/21/2022
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
ms.openlocfilehash: 15b3bb50eb0b75fa19ac8e136da83cb362b4cec6
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644936"
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

Kunder förväntar sig vanligtvis att en e-handelsplats är lagermedveten via webbupplevelsen, så att de kan bestämma vad de ska göra om det inte finns något lager för en produkt. Sökresultatmodulen kan konfigureras för att inkludera lagerdata och ger följande erfarenheter:

- Visa en lagertillgänglighetsetikett tillsammans med produkten.
- Dölj produkter som inte finns i lager från produktlistan.
- Visa produkter som inte finns i lager i slutet av produktlistan.
- Filtrera produkter i sökresultat efter lagernivå.

Om du vill aktivera dessa erfarenheter måste du först aktivera funktionen **Utökad identifiering av näthandelsprodukt att bli lagermedveten** i arbetsytan **Funktionshantering**.

> [!NOTE]
> Funktionen **utökad identifiering av näthandelsprodukt att bli lagermedveten** är tillgänglig i Commerce version 10.0.20 och senare.

Lagermedveten produktsökning använder produktattribut för att få information om lagertillgänglighet. En förutsättning för funktionen är att dedikerade produktattribut ska skapas, lagerdata måste anges för dem och de måste läggas till i online-kanalen. 

Följ dessa steg för att skapa dedikerade produktattribut för att stödja den lagermedvetna sökresultatmodulen.

1. Gå till **Retail och Commerce \> Retail och Commerce IT \> Produkter och lager**.
1. Välj och öppna **Fyll i produktattribut med lagernivå**.
1. Ange följande information i dialogrutan:

    1. I fältet **Produktattribut och typnamn** anger du ett namn för det dedikerade produktattribut som kommer att skapas för att fånga in lagertillgänglighet.
    1. I fältet **Lagertillgänglighet grundad på** den kvantitetstyp som lagernivåberäkningen ska baseras på (t.ex. **Fysiskt disponibelt**). 

1. Kör jobbet i bakgrunden. Eftersom produktlager ständigt förändras i en miljö i flera kanaler, rekommenderar vi starkt att du schemalägger det här jobbet som en batchprocess.

> [!NOTE]
> För konsekvent beräkning av lagernivå över sidor och moduler på din e-handelswebbplats, se till att välja samma kvantitetstyp för både inställningen **Lagertillgänglighet grundad på** i Commerce-administration och inställningen **Lagernivå grundad på** i Commerce webbplatsskaparen. För information om hur du använder lagerinställningar i webbplatsskaparen, se [tillämpa lagerinställningar](inventory-settings.md).

Konfigurera produktattributen för en onlinekanal genom att följa dessa steg. 

1. Gå till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.
2. Välj en onlinekanal för att aktivera den lagermedvetna sökresultatmodulen för.
3. Markera och öppna en associerad attributgrupp, lägg till det nya produktattributet.
4. För Commerce versioner före 10.0.27, välj **Ange attributmetadata**, välj det nya produktattributet och aktivera sedan alternativet **Visa attribut på kanal**, **Hämtningsbar**, **Kan förfinas** och K **an frågas**.
5. Gå till **Butik och handel \> Butik och handel IT \> Distributionsschema** och kör jobbet **1150 (katalog)**. Om du schemalägger jobbet **Fyll i produktattribut med lagernivå** är en batchprocess rekommenderar vi att du också schemalägger 1150-jobbet som en batchprocess som körs med samma frekvens.

> [!NOTE]
> För produkter som visas i sökresultatmodulen visas lagernivån på huvudproduktnivå i stället för den enskilda variantnivån. Det har bara två möjliga värden: "tillgänglig" och "lagerförd". Den faktiska etiketten för värdet hämtas från definitionen [lagernivåprofil](inventory-buffers-levels.md). En huvudprodukt anses endast vara i lager när alla varianter av den inte finns i lager.

När alla föregående konfigurationssteg har utförts kommer anvisningarna på sökresultatsidorna att visa ett lagerbaserat filter och sökresultatmodulen hämtar lagerdata bakom den föregående konfigurationen. Du kan sedan konfigurera **lagerinställningarna för produktlistesidor** i Commerce webbplatsskaparen för att styra hur sökresultatsmodulen visar produkter som inte finns i lager. Mer information om [Använd lagerinställningar](inventory-settings.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över standardkategorilandningssida och sida för sökresultat](category-search-page-overview.md)

[Modulbibliotek – översikt](starter-kit-overview.md)

[Snabbvisningsmodul](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
