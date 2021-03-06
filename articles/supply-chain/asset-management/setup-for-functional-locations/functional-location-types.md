---
title: Funktionsplatstyper
description: I det här avsnittet beskriver hur du skapar funktionsplatstyper i Tillgångshantering.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 708c27dbf568ca8bea6ec0b775afac9b80759581
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837739"
---
# <a name="functional-location-types"></a>Funktionsplatstyper

[!include [banner](../../includes/banner.md)]

 

I det här avsnittet beskriver hur du skapar funktionsplatstyper i Tillgångshantering. Funktionsplatstyper används för att hantera krav för funktionsplatser, inklusive hur tillgångar installeras på en funktionsplats. Du kan ställa in tillgångstyper, underhållsplaner, funktionsplatsattribut och tillgångsattributkrav som ska användas på en funktionsplats som använder den specifika funktionsplatstypen. När du skapar en funktionsplats är funktionsplatstypen obligatorisk.

>[!NOTE] 
>För att fungera med funktionsplatser måste du skapa en standardfunktionsplatser som ska användas endast för att skapa nya tillgångar. För standardfunktionsplatsen bör du skapa en standardfunktionsplatstyp som är väldigt enkel och tillåter att flera tillgångar installeras på standardfunktionsplatsen. Se [Skapa funktionsplatser](../functional-locations/create-functional-locations.md) för mer information om hur du ställer in typer av funktionsplatser.

## <a name="create-a-default-functional-location-type"></a>Skapa en standardfunktionsplatstyp

I den här proceduren visas hur du skapar en standardfunktionsplatstyp som ska användas för en standardfunktionsplats.

1. Välj **tillgångshantering** > **inställningar** > **funktionsplatser** > **funktionsplatstyper**.
2. Välj **Ny** för att skapa en ny funktionsplatstyp.
3. Infoga ett funktionsplatstyp-ID i fältet **funktionsplatstyp**, till exempel "standard" och ett namn i fältet **namn**.
4. Välj en livscykelmodell i fältet **Livscykelmodell för funktionsplats**.
5. Välj "Ja" på växlingsknappen **flera tillgångar** för att tillåta att flera tillgångar installeras på en funktionsplats (standardfunktionsplats) med den här typen.

Standardfunktionsplatstypen som endast ska användas för en standardfunktionsplats skapas nu. Du bör inte lägga till några fler krav eller begränsningar för den här standardfunktionsplatstypen.


## <a name="create-functional-location-types"></a>Skapa funktionsplatstyper

1. Välj **tillgångshantering** > **inställningar** > **funktionsplatser** > **funktionsplatstyper**.
2. Välj **Ny** för att skapa en ny funktionsplatstyp.
3. Infoga ett funktionsplatstyp-ID i fältet **funktionsplatstyp** och ett namn i fältet **namn**.
4. Välj en livscykelmodell i fältet **Livscykelmodell för funktionsplats**. Referera till [livscykeltillstånd för funktionsplats](../setup-for-functional-locations/functional-location-stages.md) för mer information om livscykeltillstånd och livscykelmodeller för funktionsplats.
5. Välj "Ja" på växlingsknappen **flera tillgångar** om det ska vara möjligt att installera flera tillgångar på en funktionsplats med den här funktionsplatstypen. Om du väljer "nej" kan du bara installera *en* tillgång på en funktionsplats med den här funktionsplatstypen.
6. Välj "Ja" på växlingsknappen **Uppdatera tillgångsdimension** om du vill att tillgångar som är installerade på en funktionsplats av den här typen automatiskt ska använda de ekonomiska dimensionerna som är relaterade till den funktionsplatsen. Det innebär att om du ändrar ekonomiska dimensioner i formuläret [Skapa funktionsplatser](../functional-locations/create-functional-locations.md) och funktionsplatsen använder en funktionsplatstyp med den här växlingsknappen inställd på "Ja", uppdateras ekonomiska dimensioner automatiskt på alla tillgångar installerad på den funktionsplatsen.
7. Fältet **tillgångstyp** används om du vill skapa *en* tillgång automatiskt för funktionsplatsen med samma ID och namn som den funktionsplatsen som du skapar. Detta kan till exempel vara relevant om du skapar en statisk funktionsplatsen, till exempel en byggnad eller en pipeline. I så fall väljer du den tillgångstyp som du vill använda för den automatiskt skapade tillgången. Kom ihåg att om du gör ett val i det här fältet måste växlingsknappen **Flera tillgångar** vara inställd på "nej".
8. På snabbfliken **tillgångstyper** väljer du de tillgångstyper som ska relateras till funktionsplatstypen: Välj **Lägg till rad** och välj tillgångstypen. Om du lägger till tillgångstyper här kan endast tillgångar som använder dessa tillgångstyper installeras på en funktionsplats med den här funktionsplatstypen. Om inga tillgångstyper har valts på snabbfliken **tillgångstyper** kan alla tillgångstyper vara installerade.
9. På snabbfliken **underhållsplaner** väljer du de underhållsplaner som automatiskt ska ställas in på nya funktionsplatser med den här funktionsplatstypen. Välj **Lägg till rad** och välj underhållsplaner. Om du lägger till underhållsplaner här kan endast dessa planer användas på en funktionsplats med den här funktionsplatstypen.
10. På snabbfliken **Krav för tillgångsattribut** ställer du in de tillgångsattribut som automatiskt ska ställas in på nya funktionsplatser med den här funktionsplatstypen. Välj **Lägg till rad** och välj attribut. Dessa attributkrav fungerar som riktlinjer. De verifieras inte mot attribut som ställts in på en tillgång (**tillgångshantering** > **allmänt** > **tillgångar** > **alla tillgångar** > välj tillgång på listsidan > fliken **allmänt** > knappen **attribut**). Attributkrav visas när du installerar tillgångar på funktionsplatser.
11. På snabbfliken **tillåtna typer** väljer du de funktionsplatstyper som ska gälla för underfunktionsplatstyper som är relaterade till en överordnad funktionsplatstyp, som använder den valda funktionsplatstypen.
12. På snabbfliken **Attribut** väljer du de funktionsplatsattribut som automatiskt ska ställas in på funktionsplatser med den här funktionsplatstypen. Välj **Lägg till rad** och välj attribut.


>[!NOTE] 
>På snabbfliken **allmänt** kan du få en översikt över antalet tillgångstyper, underhållsplaner, tillgångsattributkrav, tillåtna typer, attribut och funktionsplatser som har ställts in på funktionsplatstypen. I fältet **funktionsplatser** visas antalet funktionsplatser som använder funktionsplatstypen. Du kan använda knappen **kopiera** för att kopiera inställningar från en funktionsplatstyp till den valda funktionsplatstypen.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]