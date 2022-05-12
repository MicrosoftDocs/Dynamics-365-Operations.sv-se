---
title: Skapa handelskataloger för B2B-webbplatser
description: I detta ämne beskrivs hur du skapa handelskataloger för Microsoft Dynamics 365 Commerce B2B-webbplats (business-to-business).
author: ashishmsft
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 868f6bbeefeb1698bb136d52c09cebf293c95731
ms.sourcegitcommit: 0abc777986112ea2332f5bf0e815b303b952356c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2022
ms.locfileid: "8656862"
---
# <a name="create-commerce-catalogs-for-b2b-sites"></a>Skapa handelskataloger för B2B-webbplatser

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

I detta ämne beskrivs hur du skapa handelsproduktkataloger för Microsoft Dynamics 365 Commerce B2B-webbplats (business-to-business). Svar på vanliga frågor om handelskataloger för B2B-webbplatser finns i [Handelskataloger för B2B vanliga frågor](catalogs-b2b-sites-FAQ.md).

> [!NOTE]
> Detta ämne gäller Dynamics 365 Commerce-version 10.0.26 och senare versioner.

Du kan använda handelskataloger för att identifiera de produkter som du vill erbjuda i dina B2B onlinebutiker. När du skapar en katalog identifierar du onlinebutikerna som produkterna erbjuds i, lägger till de produkter du vill inkludera och ökar produkterbjudanden genom att lägga till marknadsföringsdetaljer. Du kan skapa flera kataloger för varje B2B-onlinebutik.

Med handelsproduktkataloger för handel kan du definiera följande information:

- **Katalogspecifik navigeringshierarki** – Organisationerna kan skapa en separat kategoristruktur för sin specifika katalog.
- **Katalogspecifik attributmetadata** – Attribut innehåller information om en produkt. Genom att tilldela attribut till en kategori i navigeringshierarkin kan du definiera värden för de attribut på produktnivå som tilldelats den kategorin. Organisationer kan sedan slutföra dessa uppgifter:

    - Definiera katalogspecifika attributvärden.
    - Kontrollera synligheten för attribut på katalognivå.
    - Välj de förfiningar som är specifika för en enskild katalog.

- **Kanaler** – Organisationer kan koppla mer än en B2B-onlinekanal till en katalog. Slutpunkt till slutpunkt-stöd för kataloger är för närvarande bara tillgängligt för B2B-onlinebutiker.
- **Kundhierarkier** – För en given B2B-kanal kan organisationer göra en specifik katalog tillgänglig för valda B2B-partner genom att associera kundhierarkier med den katalogen.
- **Prisgrupper** – Du kan konfigurera priser och erbjudanden som är specifika för en viss katalog. Den här kapaciteten är basorsaken när du definierar en katalog för en B2B-kanal. Med prisgrupper för kataloger kan organisationer göra produkter tillgängliga för de avsedda B2B-organisationerna och tillämpa sina prioriterade priser och rabatter. B2B-kunder som beställer från en konfigurerad katalog kan ha nytta av specialpriser och specialerbjudanden när de har loggat in på en Commerce B2B-webbplats. Om du vill konfigurera specifika priser väljer du **prisgrupper** från fliken **kataloger** för att länka en eller flera prisgrupper i katalogen. Alla handelsavtal, journaler för prisjusteringar och avancerade rabatter som har länkats till samma prisgrupp kommer att tillämpas när kunderna beställer från den här katalogen. (Avancerade rabatter inkluderar tröskel, kvantitet och mixa och matcha-rabatter.) Mer information om prisgrupper finns i [Prisgrupper](price-management.md#price-groups).

> [!NOTE]
> Den här funktionen är tillgänglig i Dynamics 365 Commerce version 10.0.26. För att konfigurera katalogspecifika konfigurationer som navigeringshierarkin och kundhierarkin, i Commerce-administration, öppna arbetsytan **Funktionshantering** (**Systemadministration \> Arbetsytor \> Funktionshantering**), aktivera funktionen **Aktivera användning av flera kataloger i butikskanaler** och kör sedan jobbet **1110 CDX**.

## <a name="catalog-process-flow"></a>Katalogprocessflöde

Processen för att skapa och bearbeta en katalog har fyra allmänna steg. Varje steg förklaras detaljerat i nästa avsnitt.

1. **[Konfiguration](#configure-the-catalog)**

    - Associera navigeringshierarkin.
    - Ange giltighetsdatum och utgångsdatum, om de är tillämpliga.
    - Lägg till och kategorisera produkter.
    - Associera prisgrupper.
    - Koppla en kundhierarki som är specifik för B2B-organisationerna. 
    - Associera standard dimensionsattributgrupp för förfiningar som storlek, stil och färg.
    - Ställ in attributmetadata.

1. **[Validering](#validate-the-catalog)** – I det här steget kör du valideringsregler som framtvingar ett specifikt beteende. Nedan följer några exempel:

    - Se till att det inte finns några okategoriserade produkter.
    - Kontrollera att alla artiklar som ingår i varje kanal är kopplade till en katalog.

1. **[Godkännande](#approve-the-catalog)**
1. **[Publicerar](#publish-the-catalog)**

## <a name="set-up-the-catalog"></a>Konfigurera katalogen

Använd informationen i det här avsnittet om du vill ställa in katalogen.

### <a name="configure-the-catalog"></a>Konfigurera katalogen

I Commerce-administration, gå till **Butik och handel \> Kataloger och sortiment \> Alla kataloger** för att konfigurera katalogen.

När du skapar en ny katalog måste du först koppla den till en eller flera kanaler. Endast artiklar som är kopplade till den valda kanalen [sortiment](/dynamics365/unified-operations/retail/assortments) kan användas när du skapar katalogen. Om du vill koppla katalogen till en eller flera kanaler väljer du **Lägg till** på snabbfliken **Handelskanaler** på sidan **kataloginställning**.

#### <a name="associate-the-navigation-hierarchy"></a>Associera navigeringshierarkin

Om du vill lägga till produkter i en katalog måste en navigeringshierarkin väljas. Kategoristrukturen stöder navigeringshierarkin för katalogen. Du måste välja en av navigeringshierarkierna som är associerade med kanalerna som du valde på snabbfliken **Handelskanaler** på sidan **kataloginställning**. Om du vill koppla en standardnavigeringshierarki till dina kanaler går du till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.

#### <a name="specify-time-effective-and-expiration-dates"></a>Ange giltighetsdatum och utgångsdatum

Om du vill ange giltighetsdatum och utgångsdatum för en katalog väljer du toppnoden i kataloghierarkin som ska återgå till huvudvyn för katalogrubriken. Sedan på snabbfliken **Allmänt** konfigurera giltighets- och utgångsdatum efter behov.

#### <a name="add-and-categorize-products"></a>Lägg till och kategorisera produkter

I Commerce-administration, gå till **Butik och handel \> Kataloger och sortiment \> Alla kataloger** för att konfigurera produkter att lägga till i katalogen. På fliken **Kataloger**, välj **Lägg till produkter**.

Du kan även välja en nod i navigeringshierarkin. Du kan sedan lägga till produkter direkt i en kategori i katalogen.

#### <a name="associate-price-groups"></a>Associera prisgrupper

Om du vill konfigurera katalogspecifika priser måste du koppla en eller flera prisgrupper till katalogen. För att koppla prisgrupper med en katalog, i Commerce-administration, gå till **Butik och handel \> Kataloger och sortiment \> Alla kataloger** för att konfigurera produkter att lägga till i katalogen. Sedan på fliken **Kataloger**, under **Priser**, välj **Prisgrupper**. Alla handelsavtal, journaler för prisjusteringar och avancerade rabatter (tröskelvärde, kvantitet, mixa och matcha rabatter) som har länkats till samma prisgrupp kommer att tillämpas när kunderna beställer från den här katalogen.

Mer information om prisgrupper finns i [Prisgrupper](price-management.md#price-groups).

> [!NOTE]
> Det går inte att skapa en ny prisgrupp från sidan **Alla kataloger**. I stället måste du skapa den från sidan **Alla prisgrupper**. Du måste sedan koppla den till katalogen på sidan **Alla kataloger**.

#### <a name="associate-a-customer-hierarchy"></a>Associera en kundhierarki

För att associera kundhierarkier, i Commerce-administration, gå till **Butik och handel \> Kataloger och sortiment \> Alla kataloger**. Sedan på fliken **Kataloger**, under **Kundhierarki**, välj **Tilldela hierarkier** för att länka en eller flera kundhierarkier till katalogen.

> [!NOTE]
> Det går inte att skapa en ny kundhierarki från sidan **Alla kataloger**. I stället måste du skapa den från sidan **Kundhierarkier**. Du måste sedan koppla den till katalogen på sidan **Alla kataloger**.

#### <a name="associate-default-dimension-attribute-group-for-refiners-such-as-size-style-and-color"></a>Associera standard dimensionsattributgrupp för förfiningar som storlek, stil och färg

För att associera en standarddimension attributgrupp för förfiningar som storlek, stil och färg, i Commerce-administration, gå till **Butik och handel \> Kataloger och sortiment \> Alla kataloger**. Sedan på fliken **Kataloger**, under **Attribut**, välj **Attributgrupper**.

#### <a name="set-attribute-metadata"></a>Ställ in attributmetadata

För att konfigurera attributmetadata, i Commerce-administration, gå till **Butik och handel \> Kataloger och sortiment \> Alla kataloger**. Sedan på fliken **Kataloger**, under **Attribut**, välj **Ställ in attributmetadata**. För att välja de attribut som ska vara synliga och förfina, välj en kategori i den tillhörande katalogspecifika navigeringshierarkin och sedan under **Katalogproduktattribut**, välj ett attribut. Välj sedan **Visa attribut för kanal**. Som standard kan alla visningsbara attribut också sökas. Om du vill göra attributen förfina, kan du välja **Kan finjusteras**.

### <a name="validate-the-catalog"></a>Validera katalogen

Innan du kan använda en ny katalog måste den valideras och publiceras.

Gör så här om du vill validera en katalog.

1. På fliken **Kataloger** på sidan **Alla kataloger** under **Validera** väljer du **Validera katalog** om du vill köra en validering. Detta steg är obligatoriskt. Det kommer att validera att den nödvändiga inställningen är korrekt.
1. Välj **Visa resultat** om du vill visa detaljer för valideringen. Om fel påträffas måste du korrigera data och köra sedan valideringen igen tills den går igenom.

### <a name="approve-the-catalog"></a>Godkänn katalogen

Efter att en katalog har validerats måste den godkännas.

Följ dessa steg för att starta arbetsflödet för kataloggodkännande.

1. I åtgärdsfönstret på sidan **Alla kataloger** välj **Arbetsflöde \> Skicka**.
1. Gå till **Butik och handel \> Administrationsinställning \> Handelsarbetsflöden** för att konfigurera stegen och behöriga användare för arbetsflödet. Arbetsflödet definierar de steg som krävs för att hämta katalogen till status **Godkänd**.

### <a name="publish-the-catalog"></a>Publicera katalogen

När en katalog har statusvärdet **Godkänt** kan du publicera den genom att välja **Publicera** på menyn **Kataloger** . När katalogen är i status **publicerad** kan den användas vid orderregistrering för kundtjänst och skicka katalogprocesser. Du kan publicera en katalog manuellt eller med hjälp av en batchprocess. Det giltighetsdatum du definierat för katalogen avgör när produkterna är tillgängliga i onlinebutiken. Utgångsdatumet som du definierar avgör när produkterna tas bort från onlinebutiken.

> [!NOTE]
> Du kan publicera en katalog som innehåller produkter som har varningar. Dessa produkter kommer dock inte att visas i onlinebutiken.

## <a name="additional-resources"></a>Ytterligare resurser

[Utvidgningar av handelskataloger för B2B-anpassningar](catalogs-b2b-sites-dev.md)

[Vanliga frågor om handelskataloger för B2B](catalogs-b2b-sites-FAQ.md)
