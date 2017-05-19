---
title: "Nomenklatur för produktnummer"
description: "I det här avsnittet beskrivs hur du kan skapa en produktnummernomenklatur för att ersätta det fasta formatet, [Produktmallsnummer - Konfiguration - Storlek - Färg - Formatmall], med ett riktat format som innehåller de produktmallsnummer, aktiva produktdimensioner och textavgränsare du själv önskar. Du kan också skapa en nomenklatur för att identifiera konfigurationer som skapas av den begränsningsbaserade konfiguratorn. Dessa nomenklaturer kan innehålla valfria attribut."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220104
ms.assetid: 31c9efb4-b5f6-4af3-b884-8f1e128469bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: deda2b7986333e0d865aa87e6b34b6acdc8f6a6d
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="product-number-nomenclature"></a>Nomenklatur för produktnummer

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du kan skapa en produktnummernomenklatur för att ersätta det fasta formatet, [Produktmallsnummer - Konfiguration - Storlek - Färg - Formatmall], med ett riktat format som innehåller de produktmallsnummer, aktiva produktdimensioner och textavgränsare du själv önskar. Du kan också skapa en nomenklatur för att identifiera konfigurationer som skapas av den begränsningsbaserade konfiguratorn. Dessa nomenklaturer kan innehålla valfria attribut.

Den nya varianten för produktnummernomenklatur gör att du kan inkludera segment i dina produktvariantidentifierare. Dessa segment kan innehålla produktmallsnummer, produktdimensioner, nummerserier, textkonstanter och attribut. Med denna funktion kan du snabbt hitta en specifik produktvariant när du skapar en försäljningsorder eller inköpsorder.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenklatur för fördefinierade produktvarianter
Produktvarianter genereras för produktmallar enligt en av tre konfigurationstekniker:

-   Fördefinierade varianter
-   Begränsningsbaserad
-   Dimensionsbaserad

Varje produktvariant har ett nummer, och med identifieringsnomenklaturen för produktvariant kan du välja de segment som ska inkluderas i respektive produktvariantnummer. Du kan välja följande segment på sidan **Produktnomenklatur**.

-   Produktmallsnummer
-   Nummersekvensvärde
-   Textkonstant
-   Produktdimensioner
    -   Inställningar
    -   Färg
    -   Storlek
    -   Stil

När en identifieringsnomenklatur för produktvariant har definierats, kan den kopplas till en produktdimensionsgrupp. Därför kommer alla produktmallar som refererar till denna produktdimensionsgrupp att tilldelas produktvariantnummer enligt nomenklaturen. Det går också att tilldela en identifieringsnomenklatur för produktvariant direkt till en produktmall. I så fall kommer de produktvarianter som tillhör denna mall att tilldelas produktvariantnummer enligt nomenklaturen.

### <a name="example"></a>Exempel

En T-tröja (TS1234) produceras i tre olika storlekar (S, M, L), i fyra olika färger (röd, grön, blå, gul) och i två olika utföranden (polo, V-neck), vilket innebär totalt 24 möjliga produktvarianter. En identifieringsnomenklatur för produktvariant skapas med följande segment:

1.  Produktmallsnummer
2.  Textkonstant: '-'
3.  Färg
4.  Textkonstant: '-'
5.  Storlek
6.  Textkonstant: '-'
7.  Stil

Produktvariantnumret för en röd polotröja i storlek S blir då: TS1234-Red-Small-Polo.

## <a name="nomenclature-of-constraintbased-configurations"></a>Nomenklatur för begränsningsbaserade konfigurationer
För begränsningsbaserade konfigurationer kan en särskild terminologi byggas för konfigurationsproduktdimensionen. Du kan välja följande segment på sidan **Produktnomenklatur**.

-   Nummersekvensvärde
-   Textkonstant
-   Attributvärde 

Varje komponent i en modell för produktkonfiguration kan ha sin egen konfigurationsnomenklatur. Endast attribut som tillhör komponenten kan användas. Attribut från delkomponenter eller användarkrav är inte tillgängliga.

### <a name="example"></a>Exempel

En produktkonfigurationsmodell har en rotkomponent med två attribut.

-   Material (plast, trä, stål)
-   Längd (10...100)

En konfigurationsnomenklatur definieras med hjälp av följande segment:

1.  Attributvärde: Material
2.  Textkonstant: 'AAA'
3.  Attributvärde: Längd

Konfigurations-ID för trämaterial med längden 78 får följande konfigurations-ID: WoodAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Nomenklatur för dimensionsbaserade konfigurationer
För dimensionsbaserade konfigurationer kan en särskild terminologi byggas för konfigurationsproduktdimensionen. Du kan välja följande segment på sidan **Produktnomenklatur**.

-   Nummersekvensvärde
-   Textkonstant
-   Konfigurationsgruppartikel

En konfigurationsnomenklatur kan definieras för en strukturlista (BOM).

### <a name="example"></a>Exempel

En strukturlista innehåller fyra strukturlisterader som delas in i två konfigurationsgrupper.

-   Strukturlisterad: M0007, standardkabinett
    -   Konfigurationsgrupp: Kabinett
-   Strukturlisterad: M0008, avancerat kabinett
    -   Konfigurationsgrupp: Kabinett
-   Strukturlisterad: M0021, framgallerduk
    -   Konfigurationsgrupp: Framgaller
-   Strukturlisterad: M0022, framgallermetall
    -   Konfigurationsgrupp: Framgaller

En konfigurationsnomenklatur definieras med hjälp av följande segment:

1.  Konfigurationsgrupp: Kabinett
2.  Textkonstant: '&'
3.  Konfigurationsgrupp: Framgaller

Konfigurations-ID för ett standardkabinett med dukframgaller blir: M0007&M0021.

## <a name="nomenclature-of-a-combination-of-product-variants-and-configurations"></a>Nomenklatur för en kombination av produktvarianter och konfigurationer
När du använder antingen begränsningsbaserad eller dimensionsbaserad konfigurationteknologi för att konfigurera produktvarianter för en produktmall, kan produktvarianterna få produktvariantnummer som innehåller nomenklaturen från konfigurationsdimensionen. Om du vill konfigurera varianter, följ dessa steg:

1.  Definiera en nummernomenklatur för produktvariant som innehåller konfigurationsdimensionen på sidan **Produktnomenklatur**.
2.  Tilldela denna nomenklatur till en produktdimensionsgrupp med konfigurationsdimensionen aktiverad.
3.  Definiera en konfigurationsnomenklatur för de komponenter eller strukturlistor som ska användas för att konfigurera produktvarianterna.

### <a name="example-for-constraint-based-configurations"></a>Exempel på konstantbaserade konfigurationer

I det här exemplet kan du använda en nummernomenklatur för produktvariant som består av följande segment:

1.  Produktmallsnummer
2.  Textkonstant \_
3.  Inställningar

Konfigurationsnomenklaturen kan bestå av följande segment:

1.  Attributvärde: Material
2.  Textkonstant: 'AAA'
3.  Attributvärde: Längd

Du kan ange följande värden för segment:

-   Produktmallsnummer = M0099
-   Material = Plast
-   Längd = 12

Produktvariantnumret blir: M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Exempel på dimensionsbaserade konfigurationer

I det här exemplet kan du använda en nummernomenklatur för produktvariant som består av följande segment:

1.  Produktmallsnummer
2.  Textkonstant '//'
3.  Inställningar

Konfigurationsnomenklaturen kan bestå av följande segment:

1.  Konfigurationsgrupp: Kabinett
2.  Textkonstant: '&'
3.  Konfigurationsgrupp: Framgaller

Du kan ange följande värden för segment:

-   Produktmallsnummer = D0123
-   Kabinett = M0008
-   Frontgaller = M0022

Produktvariantnumret blir: D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Nummerkonflikter
Det går att skapa nummernomenklaturer för produktvarianter som resulterar i icke-unika produktvariantnummer. Detta kan till exempel hända om en aktiv produktdimension inte inkluderas i nomenklaturen för en produktmall som använder den fördefinierade variantkonfigurationstekniken. Konflikter behandlas olika för de olika konfigurationsteknologierna.

### <a name="predefined-variants"></a>Fördefinierade varianter

Ett fel uppstår om du manuellt eller automatiskt försöker generera produktvarianter där en eller flera erhåller samma produktvariantnummer. För att undvika detta bör du använda alla aktiva produktdimensioner i produktdimensionsgruppen, eller inkludera en nummerserie för att säkerställa att produktvariantnumren är unika.

### <a name="constraint-based-configurations"></a>Begränsningsbaserade konfigurationer

Beroende på nomenklaturen kan systemet komma att försöka tilldela ett icke-unikt produktvariantnummer till en konfiguration. I så fall kommer systemet att använda nummerserien för konfigurationsdimensionen som produktvariantnummer istället. Om detta händer får du ett varningsmeddelande. För att undvika detta bör du inkludera tillräckligt med attribut i nomenklaturen för att säkerställa unika nummer, samt se till att alternativet **Återanvänd** aktiveras för komponenten.

### <a name="dimension-based-configurations"></a>Dimensionsbaserade konfigurationer

Konfigurationprocessen inkluderar ett steg där systemet föreslår ett konfigurationsvärde enligt nomenklaturen. I detta steg kan du ändra konfigurationsvärdet manuellt. När du sparar konfigurationen kommer systemet att kontrollera om konfigurationsvärdet är unikt. Om så inte är fallet, visas ett felmeddelande. Du måste ange ett unikt konfigurationvärde för att spara konfigurationen.



<a name="see-also"></a>Se även
--------

[Skapa en produktnummernomenklatur för fördefinierade produktvarianter (Uppgiftsguide)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-predefined-product-variants/)

[Skapa en produktnummernomenklatur för konfigurerade produktvarianter (Uppgiftsguide)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-configured-product-variants/)




