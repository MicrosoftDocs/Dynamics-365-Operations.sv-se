---
title: Skapa funktionsplatser
description: I det här avsnittet beskrivs hur du skapar en funktionsplats i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8ba905224fbbcc5db95820e2b228a0d478e6146
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205424"
---
# <a name="create-functional-locations"></a>Skapa funktionsplatser

[!include [banner](../../includes/banner.md)]

 

I det här avsnittet beskrivs hur du skapar en funktionsplats i Tillgångshantering.

När du skapar en funktionsplatsstruktur bör du vara medveten om att när du har skapat en funktionsplats kan du inte flytta den från den ursprungliga platsen. Det innebär att du noggrant bör överväga strukturen för dina funktionsplatser innan du börjar skapa dem i Tillgångshantering. Om du ångrar en funktionsplats kan du ta bort den, förutsatt att den ännu inte har tagits i bruk.

För att kunna arbeta med funktionsplatser börjar du med att skapa två "kategorier" av funktionsplatser:

- Skapa *en* standardfunktionsplats med utan underplatser. Den här funktionella platsen används endast som standardplats för tillgångar när du skapar nya tillgångar.  
- Skapa de funktionella platsstrukturer som krävs för att hantera underhållsjobb i företaget.

## <a name="create-a-default-functional-location"></a>Skapa en funktionell standardplats

När du använder funktionsplatser börjar du med att skapa en standardplats som ska användas när du skapar nya tillgångar. Den här funktionella platsen är den du väljer i fältet **tillgångshantering** > **inställningar** > **parametrar för tillgångshantering** > **tillgångar** länk > **funktionella standardplatser**. Den funktionella standardplatsen kan användas när du skapar nya tillgångar och du ännu inte har ställt in en funktionsplatsstruktur för dessa tillgångar.

1. Välj **tillgångshantering** > **allmänt** > **funktionsplatser** > **alla funktionsplatser**.  
2. I **alla funktionsplatser**väljer du **ny**.
3. Infoga ett ID i fältet **funktionsplats**, till exempel "0000" eller "standard", för att indikera att detta är en speciell funktionsplats.
4. Infoga namn för den funktionella standardplatsen i fältet **namn**.
5. Välj *inte* en överordnad i fältet **överordnad** – lämna fältet tomt.
6. I fältet **funktionsplatstyp** välj den typ av funktionsplats som ska användas för den funktionella standardplatsen. Se [Typer av funktionsplats](../setup-for-functional-locations/functional-location-types.md) för mer information om hur du ställer in typer av funktionsplats.
7. Välj **OK**. Du bör inte lägga till ytterligare data till den här funktionella platsen eftersom den endast används som en tillfällig plats för nya tillgångar tills du installerar tillgångarna på de funktionsplatser som används av ditt företag.

## <a name="create-functional-locations"></a>Skapa funktionsplatser

Följande procedur beskriver hur du skapar de funktionsplatser som krävs för underhållshantering i ditt företag.

1. Välj **tillgångshantering** > **allmänt** > **funktionsplatser** > **alla funktionsplatser**. Du kan skapa en funktionsplats från rutnätsvy eller detaljerad vy.
2. Välj knappen **Ny**.
3. Infoga ett ID i fältet **funktionsplats**.
4. Infoga ett namn för den funktionella standardplatsen i fältet **namn**.
5. Om den funktionella platsen är en underplats i en struktur, väljer du den överordnade platsen i fältet **överordnad**.
6. Välj en typ i fältet **Typ av funktionsplats**.
7. Välj **OK**.
8. Välj den funktionella platsen och klicka på knappen **redigera** för att lägga till ytterligare information.

>[!NOTE]
>Beroende på din inställning av livscykeltillstånd för funktionsplats kan du behöva skapa alla underplatser för en funktionsplats och sedan ändra livscykeltillståndet för funktionsplats innan du kan börja installera tillgångar. Se [installera tillgångar på funktionsplatser](../functional-locations/install-objects-on-functional-locations.md) för mer information om installation av tillgångar. Se [livscykeltillstånd för funktionsplats](../setup-for-functional-locations/functional-location-stages.md) om du vill veta mer om inställningar för livscykeltillstånd för funktionsplats.

I informationsvyn kommer du att se snabbflikar där du kan lägga till och redigera information om den funktionella platsen.

## <a name="general-information"></a>Allmän information

Det här avsnittet innehåller en översikt över överordnad och underordnad information i den funktionella platsstrukturen. I avsnittet **information** kan du se antalet tillgångsattribut, underhållsplaner och tillgångar som är relaterade till den funktionella platsen. I avsnittet **lager** kan du välja den plats och det lagerställe som den funktionella platsen är relaterad till. Plats och lagerställe används i samband med artikelprognoser för arbetsorder. När du skapar en artikelprognos används automatiskt plats- och lagerställeinformation för tillgångens funktionella plats. I avsnittet **livscykeltillstånd** visas information om livscykeltillståndet för funktionsplats.

## <a name="installed-assets"></a>Installerade tillgångar

Se [installera tillgångar på funktionsplatser](../functional-locations/install-objects-on-functional-locations.md) för mer information om installation av tillgångar. Du kan använda knappen **Visa** på den här snabbfliken om du vill visa fler fält på snabbfliken. Fälten **giltig från** och **undertillgång** kan visas i rutnätet.

## <a name="asset-attribute-requirements"></a>Krav för tillgångsattribut

På den här snabbfliken kan du lägga till specifika attributkrav för de tillgångar som du installerar på den funktionella platsen. Dessa krav är endast i informationssyfte. De hindrar dig inte från att installera tillgångar med andra attributkrav. Välj **Lägg till rad** och välj attributtypen. Sedan infogar du **relevant värde**, väljer ett tröskelvärde i fältet **tröskelvärdekriterier** och sparar posten.

## <a name="maintenance-plans-and-maintenance-rounds"></a>Underhållsplaner och underhållsomgångar

Här kan du lägga till underhållsplaner och underhållsomgångar till den funktionella platsen, inklusive ett startdatum. De tillgångar som är installerade på en funktionsplats kan ha andra underhållsplaner inställda. Alla underhållsplaner och underhållsomgångar kan användas för att schemalägga tillgångskalenderposter för en funktionsplats och det är för närvarande installerade tillgångar.

>[!NOTE]
>Om du uppdaterar inställningarna för tillgångstyper, tillgångsmärken och tillgångsmodeller på underhållsplaner i detaljvyn **alla funktionsplatser**, snabbfliken **underhållsplaner** när du har planerat underhållsplaner, kommer befintliga underhållsschemaposter som är relaterade till den funktionella platsen att raderas automatiskt. Om du vill skapa nya schemaposter, som motsvarar den uppdaterade underhållsplaninställningen på den funktionella platsen, måste du köra ett nytt schema för underhållsplanen för den funktionella platsen. 

## <a name="address"></a>Adress

Infoga adressen för funktionsplats på snabbfliken **adress**. Adresser på funktionsplatser ärvs, vilket innebär att om en underplats inte har någon adress definierad, används adressen till den överordnade platsen.

## <a name="workers"></a>Arbetare

På den här snabbfliken kan du lägga till arbetare som är anslutna till den funktionella platsen och du kan välja en funktionsplats som primär för arbetaren. 

## <a name="attributes"></a>Attribut

På den här snabbfliken kan du ange värden för funktionella platsattribut. Dessa attribut kan användas för att beskriva egenskaper som är relevanta för den funktionella platsen, till exempel strukturella egenskaper, byggnadstyp, områdesbeskrivningar eller plats ovanför eller under jord.

Välj **Lägg till rad** och välj attributtypen. Därefter infogar du **värdet** som är relaterat till attributtypen och sparar posten.

## <a name="financial-dimensions"></a>Ekonomiska dimensioner

Du kan välja ekonomiska dimensioner för den funktionella platsen. [Typer av funktionsplats](../setup-for-functional-locations/functional-location-types.md) kan ställas in så att de tillåter automatisk uppdatering av ekonomiska dimensioner från en funktionsplats. Det innebär att tillgångar som är installerade på en ekonomisk dimension automatiskt får de ekonomiska dimensionerna för den funktionella platsen. Detta är användbart om du vill ha olika kostnadsställen, beroende på platser.

När data om **plats**, **lagerställe**, **adress** och **ekonomiska dimensioner** uppdateras på en överordnad funktionsplats, kan relaterade funktionella underplatser uppdateras om du gör det valet under uppdateringen. En dialogruta öppnas och ger dig uppdateringsalternativen.

## <a name="copy-a-functional-location-structure"></a>Kopiera en funktionsplatsstruktur

Om ditt företag har flera funktionsplatser med liknande platsstrukturer, kan du använda funktionen Kopiera i Tillgångshantering för att snabbt skapa ett antal liknande platshierarkier. När du kopierar en specifik funktionsplats eller en hel struktur har den nya platsen eller strukturen samma namn som den du kopierade. När kopieringen är klar kan du enkelt ändra namnet eller andra inställningar på den nya funktionella platsen, förutsatt att livscykeltillståndet för den funktionella platsen som valts för den nya funktionella platsen tillåter det.

1. I **alla funktionsplatser**väljer du den funktionella plats som du vill kopiera. Du kan till exempel välja en övre plats (överordnad) om du vill kopiera hela funktionella platsstrukturen inklusive underplatser.
2. Välj knappen **kopiera funktionsplatsstruktur**. Den plats du valde på listsidan visas i fältet **kopiera från**.
3. Infoga namnet på den nya platsen i fältet **ny funktionsplats**.
4. I fältet **överordnad att klistra in under** kan du bara infoga ett överordnat ID om den plats du skapar ska ingå i en befintlig funktionsplatsstruktur.
5. Klicka på **OK**. Den nya funktionella platsstrukturen visas på **alla funktionsplatser**.

>[!NOTE]
>När du kopierar en funktionsplatsstruktur anges livscykeltillståndet för funktionsplatser i den nya strukturen till "första tillstånd" som du har skapat för funktionsplatser. Om du kan byta namn på eller ta bort en funktionsplats med knapparna **byt namn** och **ta bort** i **alla funktionsplatser** beror på det aktuella livscykeltillståndet för den funktionella platsen.

## <a name="delete-a-functional-location"></a>Ta bort en funktionsplats

En funktionsplats med relaterade underplatser kan tas bort om inga tillgångar har installerats på någon av de funktionsplatser som du försöker ta bort och om det aktuella livscykeltillståndet för funktionsplats tillåter det.

1. I **alla funktionsplatser**väljer du den funktionella plats som du vill ta bort.
2. Om det behövs, uppdatera den funktionella platsen till ett livscykeltillstånd för funktionsplats som tillåter borttagning av en funktionsplats.
3. Välj **Ta bort**.

>[!NOTE]
>Om du inte kan ta bort en funktionsplats kan du i stället hantera borttagningen genom att ställa in ett livscykeltillstånd för funktionsplats för detta ändamål. Du kan till exempel ställa in ett "kasserat" eller "borttaget" stadium, som inte ska vara en aktiv fas, i formuläret **livscykeltillstånd för funktionsplats**.
