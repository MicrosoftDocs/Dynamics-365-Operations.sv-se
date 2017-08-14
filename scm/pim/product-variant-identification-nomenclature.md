---
title: "Terminologi för produktvariantnummer och namn"
description: "Det här avsnittet beskriver hur du ställer in en produktnummerterminologi för att ersätta det fasta formatet [Produktmallsnummer - Konfiguration - Storlek - Färg - Stil]. Den nya terminologin har ett riktat format som innehåller produktmallsnummer, aktiva produktdimensioner och valfria textavgränsare. Du kan också skapa en terminologi för produktnamn. Slutligen kan du också skapa en terminologi för att identifiera konfigurationer som skapas av den begränsningsbaserade produktkonfiguratorn. Dessa nomenklaturer kan innehålla valfria attribut."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 0c3c1a3e64b016aa72e933f4d6cba854549ff13a
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a>Terminologi för produktvariantnummer och namn

Det här avsnittet beskriver hur du ställer in en produktnummerterminologi för att ersätta det fasta formatet [Produktmallsnummer - Konfiguration - Storlek - Färg - Stil]. Den nya terminologin har ett riktat format som innehåller produktmallsnummer, aktiva produktdimensioner och valfria textavgränsare. Du kan också skapa en terminologi för produktnamn. Slutligen kan du också skapa en terminologi för att identifiera konfigurationer som skapas av den begränsningsbaserade produktkonfiguratorn. Dessa nomenklaturer kan innehålla valfria attribut.

Med nya terminologier för produktvariantnummer och produktvariantnamn kan du inkludera segment i identifierarna för produktvarianter. Dessa segment kan innehålla produktmallsnummer och -namn, ID för produktdimensioner, nummerserier, textkonstanter och attribut. Med denna funktion kan du snabbt hitta en specifik produktvariant när du skapar en försäljningsorder eller inköpsorder. Du skapar terminologier för både produktvariantnummer och produktvariantnamn via sidan **Produktterminologi**. För att öppna denna sida klickar du på **Produktinformationshantering** &gt; **Inställningar**.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenklatur för fördefinierade produktvarianter
Produktvarianter genereras för produktmallar enligt en av tre konfigurationstekniker:

-   Fördefinierade varianter
-   Begränsningsbaserad
-   Dimensionsbaserad

Varje produktvariant har ett nummer och ett namn, och med identifieringsterminologin för produktvariant kan du välja de segment som ska inkluderas i respektive produktvariantnummer eller -namn. Du kan välja följande segment på sidan **Produktterminologi**:

-   Produktmallsnummer
-   Namn på produktmall
-   Nummersekvensvärde
-   Textkonstant
-   Produktdimensioner
    -   Konfigurations-ID eller -namn
    -   Färg-ID eller namn
    -   Storleks-ID eller namn
    -   Stil-ID eller namn

När du anger en identifieringsnummerterminologi för produktvariant kan du koppla den till en produktdimensionsgrupp. Alla produktmallar som refererar till denna produktdimensionsgrupp kommer sedan att tilldelas produktvariantnummer enligt terminologin. Produktvariantens namnterminologier kan dock inte associeras med produktdimensionsgrupper. Du kan också tilldela en identifieringsterminologi för produktvariant direkt till en produktmall. I det här fallet tilldelas de produktvarianter som tillhör produktmallen produktvariantnummer och namn i enlighet med terminologierna.

### <a name="example"></a>Exempel

En T-shirt (TS1234) skapas i tre olika storlekar (S, M, L), fyra olika färger (röd, grön, blå, gul) och två olika format (Polo, V). Därför är 24 produktvarianter möjliga (= 2 × 4 × 3). Du kan skapa en nummerterminologi för produktvariant med följande segment:

1.  Produktmallsnummer
2.  Textkonstant: "-"
3.  Färg
4.  Textkonstant: "-"
5.  Storlek
6.  Textkonstant: "-"
7.  Stil

I detta fall blir produktvariantnumret för en röd polo-T-shirt i storlek S: TS1234-Red-Small-T-shirt.

## <a name="nomenclature-of-constraintbased-configurations"></a>Nomenklatur för begränsningsbaserade konfigurationer
För begränsningsbaserade konfigurationer kan du skapa en särskild terminologi för konfigurationsproduktdimensionen. Du kan välja följande segment på sidan **Produktterminologi**:

-   Nummersekvensvärde
-   Textkonstant
-   Attributvärde

Varje komponent i en modell för produktkonfiguration kan ha sin egen konfigurationsnomenklatur. Endast attribut som tillhör komponenten kan användas. Attribut från delkomponenter eller användarkrav får inte användas.

### <a name="example"></a>Exempel

En produktkonfigurationsmodell har en rotkomponent med två attribut:

-   Material (plast, trä, stål)
-   Längd (10...100)

Du kan skapa en nummerterminologi för konfiguration med följande segment:

1.  Attributvärde: Material
2.  Textkonstant: "AAA"
3.  Attributvärde: Längd

I detta fall blir konfigurations-ID för trämaterial med en längd på 78 då WoodAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Nomenklatur för dimensionsbaserade konfigurationer
För dimensionsbaserade konfigurationer kan du skapa en särskilt avsedd terminologi för konfigurationsproduktdimensionen. Du kan välja följande segment på sidan **Produktterminologi**:

-   Nummersekvensvärde
-   Textkonstant
-   Konfigurationsgruppartikel

Du kan definiera en konfigurationsterminologi för en strukturlista (BOM).

### <a name="example"></a>Exempel

En strukturlista har fyra strukturlisterader som är uppdelade i två konfigurationsgrupper:

-   Strukturlisterad: M0007, standardkabinett
    -   Konfigurationsgrupp: Kabinett
-   Strukturlisterad: M0008, avancerat kabinett
    -   Konfigurationsgrupp: Kabinett
-   Strukturlisterad: M0021, framgallerduk
    -   Konfigurationsgrupp: Framgaller
-   Strukturlisterad: M0022, framgallermetall
    -   Konfigurationsgrupp: Framgaller

Du kan skapa en nummerterminologi för konfiguration med följande segment:

1.  Konfigurationsgrupp: Kabinett
2.  Textkonstant: "&"
3.  Konfigurationsgrupp: Framgaller

I detta fall blir konfigurations-ID för ett standardkabinett som har ett dukframgaller: M0007&M0021.

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a>Terminologi för en kombination av produktvarianter och konfigurationer
När du använder antingen begränsningsbaserad eller dimensionsbaserad konfigurationsteknik för att konfigurera produktvarianter för en produktmall, kan produktvarianternas produktvariantnummer innehålla terminologin från konfigurationsdimensionen. Om du vill konfigurera varianter, följ dessa steg.

1.  Definiera en nummerterminologi för produktvarianter som innehåller konfigurationsdimensionen på sidan **Produktterminologi**.
2.  Tilldela terminologin till en produktdimensionsgrupp med konfigurationsdimension.
3.  Definiera en konfigurationsterminologi för de komponenter eller strukturlistor som ska användas för att konfigurera produktvarianterna.

Du kan också skapa terminologier för produktvariantnamn. Produktvariantnamnen kan konfigureras att omfatta konfigurations-ID eller namn.

### <a name="example-for-constraint-based-configurations"></a>Exempel på konstantbaserade konfigurationer

I det här exemplet använder du en nummerterminologi för produktvariant som består av följande segment:

1.  Produktmallsnummer
2.  Textkonstant "\_"
3.  Inställningar

Konfigurationsterminologin består av följande segment:

1.  Attributvärde: Material
2.  Textkonstant: "AAA"
3.  Attributvärde: Längd

Du kan ange följande värden för segment:

-   Produktmallsnummer = **M0099**
-   Material = **Plast**
-   Längd = **12**

I detta fall blir produktvariantnumret M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Exempel på dimensionsbaserade konfigurationer

I det här exemplet använder du en nummerterminologi för produktvariant som består av följande segment:

1.  Produktmallsnummer
2.  Textkonstant "//"
3.  Inställningar

Konfigurationsterminologin består av följande segment:

1.  Konfigurationsgrupp: Kabinett
2.  Textkonstant: "&"
3.  Konfigurationsgrupp: Framgaller

Du kan ange följande värden för segment:

-   Produktmallsnummer = **D0123**
-   Kabinett = **M0008**
-   Frontgaller = **M0022**

I detta fall blir produktvariantnumret D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Nummerkonflikter
I vissa fall kan ett produktvariantnummer som du skapar komma att inte framställa unika produktvariantnummer. Till exempel kommer produktvarianten inte att vara unika om en aktiv produktdimension inte inkluderas i terminologin för en produktmall som använder den fördefinierade variantkonfigurationstekniken. Hur konflikter hanteras varierar beroende på inställningen för konfigurationsteknik.

### <a name="predefined-variants"></a>Fördefinierade varianter

Ett fel uppstår om du manuellt skapar eller automatiskt försöker generera produktvarianter , och mer än en produktvariant erhåller samma produktvariantnummer. För att undvika detta bör du använda alla aktiva produktdimensioner i produktdimensionsgruppen. Alternativt kan du inkludera en nummerserie för att garantera att produktvariantnumren är unika.

### <a name="constraint-based-configurations"></a>Begränsningsbaserade konfigurationer

Beroende på terminologin kan systemet komma att försöka tilldela ett icke-unikt produktvariantnummer till en konfiguration. I så fall kommer systemet att använda nummerserien för konfigurationsdimensionen som produktvariantnummer istället. Om detta händer får du ett varningsmeddelande. För att undvika detta scenario bör du inkludera tillräckligt med attribut i terminologin för att garantera unika produktvariantnummer. Du bör också se till att alternativet **Återanvänd** aktiveras för komponenten.

### <a name="dimension-based-configurations"></a>Dimensionsbaserade konfigurationer

Under ett steg under konfigurationsprocessen föreslår systemet ett konfigurationsvärde enligt terminologin. I detta steg kan du ändra konfigurationsvärdet manuellt. När du sparar konfigurationen kommer systemet att bekräfta att konfigurationsvärdet är unikt. Du får ett felmeddelande om värdet som du angett inte är unikt. Du måste ange ett unikt konfigurationsvärde för att spara konfigurationen.

<a name="see-also"></a>Se även
--------

[Skapa en produktnummerterminologi för fördefinierade produktvarianter](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-predefined-variants-2016-11)

[Skapa en produktnummerterminologi för konfigurerade produktvarianter](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-product-variants_2016_11)


