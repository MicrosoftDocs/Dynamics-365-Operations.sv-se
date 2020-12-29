---
title: Tekniska attribut och sökning efter tekniska attribut
description: I det här avsnittet beskrivs hur du kan använda tekniska attribut för att ange alla icke-standardvärden, för att se till att alla produkthuvuddata kan registreras i systemet. Det förklarar också hur du kan använda tekniska attributsökningar för att enkelt hitta produkter, baserat på de egenskaper som har registrerats.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductAttributeSearch, EngChgMaintainAttributeInheritance, EngChgAttribute
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 5a4f31af3f76c1af6a0f5546955e810bd1cca375
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438126"
---
# <a name="engineering-attributes-and-engineering-attribute-search"></a>Tekniska attribut och sökning efter tekniska attribut

[!include [banner](../includes/banner.md)]

För att säkerställa att alla produktmalldata kan registreras i systemet, bör du använda tekniska attribut för att ange alla icke-standardegenskaper. Du kan sen använda tekniska attributsökningar för att enkelt hitta produkter, baserat på de egenskaper som har registrerats.

## <a name="engineering-attributes"></a>Konstruktionsattribut

Vanligtvis har teknik produkter många egenskaper och egenskaper som du måste samla in. Även om du kan registrera vissa av egenskaperna med hjälp av standard produktfälten, kan du också skapa nya konstruktions egenskaper efter behov. Du kan definiera egna *tekniska attribut* och göra dem till en del av produktdefinitionen.

### <a name="create-engineering-attributes-and-attribute-types"></a>Skapa tekniska attribut och attributtyper

Varje attribut för teknik måste tillhöra en *attributtyp*. Det här kravet beror på att varje attribut för teknik måste ha en *datatyp* som definierar vilka typer av värden som kan rymmas. En typ av teknisk attribut kan vara en standardtyp (t.ex. fritext, heltal eller decimal) eller en anpassad typ (t.ex. text som har en specifik uppsättning värden att välja mellan). Du kan återanvända varje attributtyp med valfritt antal tekniska attribut.

#### <a name="set-up-engineering-attribute-types"></a>Ställ in tekniska attributtyper

Om du vill visa, skapa eller redigera en typ av teknisk attribut följer du dessa steg.

1. Gå till **Konstruktionsändringshantering \> Inställningar \> Attribut \> Attributtyper**.
1. Välj en befintlig attributtyp listvyn eller välj **ny** i åtgärdsfönstret för att skapa en ny attributtyp.
1. Ange följande fält.

    - I fältet **Attributtypnamn** - ange ett namn på attributtypen.
    - **Typ** – Välj en standard datatyp (*Valuta*, *DatumTid*, *Decimal*, *Heltal*, *Text*, *Boolesk* eller *Referens*).
    - **Fast lista** – det här alternativet är endast tillgängligt om du ställer in fältet **Typ** till *Text*. Ange värdet *Ja* för att definiera specifika värden för attribut av den här typen. I det här fallet skapas en nedrullningsbar lista. Med hjälp av snabbfliken **värde** kan du fastställa vilka värden som är tillgängliga för den här attributtypen. Ställ in det här alternativet på *Nej* om du vill att användarna ska kunna ange valfritt värde. I det här fallet skapas ett inmatningsfält.
    - **Värdeintervall** – det här alternativet är bara tillgängligt om du ställer in fältet **typ** till *heltal*, *decimal* eller *valuta*. Ange det till *Ja* för att fastställa minimi- och maximivärden som accepteras för attribut av denna typ. Du kan använda snabbfliken **intervall** för att fastställa minimi- och maximivärden och (för valuta) den valuta som gäller för de gränser som du anger. Ange det här alternativet till *Nej* om du accepterar något värde. 
    - **Måttenhet** – Det här fältet är endast tillgängligt om du ställer in **Typ** till *Heltal* eller *Decimal*. Välj den måttenhet som ska användas för den här attributtypen. Om ingen enhet krävs lämnar du det här fältet tomt.

#### <a name="set-up-engineering-attributes"></a>Ställ in tekniska attribut

Om du vill visa, skapa eller redigera av teknisk attribut följer du dessa steg.

1. Gå till **Konstruktionsändringshantering \> Inställningar \> Attribut \> Tekniska attribut**.
1. Välj en befintlig attribut listvyn eller välj **ny** i åtgärdsfönstret för att skapa en ny attribut.
1. Ange följande fält.

    - **Namn** – Ange ett namn för attribut. Namnet visas bara på sidan **tekniska attribut**. Överallt i systemet, värdet på fältet **Eget namn** visas vanligtvis för att identifiera attributet.
    - **Attributtyp** – Välj en attributtyp som du har definierat i det föregående avsnittet.
    - **Eget namn** – Ange ett namn som identifierar attributet i systemet (förutom på sidan **tekniska attribut**). 
    - **Beskrivning** – Ange en beskrivning av attributet.
    - **Hjälptext** – Ange hjälptexten som anger vad attributet används till för andra användare.
    - **Standardvärde** – Ange ett standardvärde för attributet. Vilka alternativ som visas beror på vilken attributtyp du har valt.
    - **Valuta** – om den attributtyp som du har valt är en valuta väljer du den valuta som attributet ska acceptera och visa värden i.

1. Om den attributtyp du valt är ett heltal eller en decimal visas snabbfliken **intervall**. På den här snabbfliken ställer du in följande fält efter behov:

    - **Toleransåtgärd** – Välj hur systemet ska svara om en användare anger ett värde utanför det angivna intervallet. Om du väljer *Varning* visas en varning men användaren kan spara värdet. Om du väljer *ej tillåtet* visas en varning och värdet kan inte sparas förrän användaren korrigerar det.
    - **Minimum** – Ange det lägsta rekommenderade eller godkända värdet.
    - **Maximum** – Ange det högsta rekommenderade eller godkända värdet.

### <a name="connect-engineering-attributes-to-an-engineering-product-category"></a>Ansluta tekniska attribut till en teknisk produktkategori

Vissa av de tekniska attributen gäller för alla produkter, medan andra är specifika för enskilda produkter eller produktkategorier. Elektriska attribut krävs till exempel inte för mekaniska produkter. Därför kan du ställa in *kategorier för konstruktionsprodukter*. En kategori för konstruktionsprodukter etablerar samlingen av tekniska attribut som måste ingå i definitionen för produkter som tillhör den kategorin. Du kan även ange vilka tekniska attribut som är obligatoriska och om det finns ett standardvärde.

Mer information om hur du arbetar med kategorier för konstruktionsprodukter inklusive information om hur du ansluter attribut till kategorier, finns i [tekniska versioner och kategorier för konstruktionsprodukter](engineering-versions-product-category.md).

### <a name="set-values-for-engineering-attributes"></a>Ställa in värden för tekniska attribut

De tekniska attribut som är anslutna till en teknisk produktkategori presenteras när du skapar en ny teknisk produkt som baseras på denna kategori. På den tiden kan du ange värden för attributen. Senare kan dessa värden ändras på sidan **teknisk version** eller som en del i hanteringen av konstruktionsändringshantering i en teknisk ändringsorder. För mer information, se [Hantera ändringar av konstruktionsprodukter](engineering-change-management.md).

### <a name="create-an-engineering-product"></a>Skapa en ny teknisk produkt

Om du vill skapa en teknisk produkt öppnar du sidan **frisläppta produkter**. Sedan i åtgärdsfönstret, på fliken **Produkt**, i gruppen **Ny**, markerar du sedan **Teknisk produkt**.

Du måste ange den tekniska kategori som produkten tillhör. Kategorin anger alla standardvärden och egenskaperna för produkten. Även de attribut som gäller för produkten anges. När du har valt kategorin anges värdena för attributen. Du kan sedan ändra dessa värden.

## <a name="search-for-products-by-using-engineering-attribute-values"></a>Sök efter produkter med hjälp av konstruktionsattributvärden

Du kan använda teknik för att söka efter produkter genom att söka efter deras tekniska attributvärden. Därför är det lätt att hitta tekniska produkter utifrån deras egenskaper. Du kan söka i de produkter som tillhör en teknisk produktkategori, eller söka bland alla tekniska produkter.

Sökningen är tillgänglig på sidor för produktmalldata och från transaktionsartiklar i systemet, t.ex. försäljningsorder. För en transaktionsartikel kan du använda sidan **Sökning efter tekniska attribut** för att söka efter en produkt. Du kan sedan använda knappen **Lägg till som ny rad** om du vill lägga till produkten på försäljningsorderraderna. Produkter i sökresultatet kan också läggas till direkt på ordern.
