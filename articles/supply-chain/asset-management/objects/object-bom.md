---
title: Tillgångsstrukturer
description: Denna artikel beskriver tillgångsstrukturer i Tillgångshanteraren.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetStandardSparePartsItemGroup, EntAssetObjectBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 665c705e3ffb617fc159a1223cb3f776878d5cd2
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016258"
---
# <a name="asset-boms"></a>Tillgångsstrukturer

[!include [banner](../../includes/banner.md)]

 

Denna artikel beskriver tillgångsstrukturer i Tillgångshanteraren. Sidan **Tillgångsstrukturer** visar en lista över alla artiklar (reservdelar och andra artiklar) som används på en tillgång under hela dess livstid. När du skapar en ny tillgång bör du överväga att konfigurera en tillgångsstruktur som en del av inställningsproceduren. På så sätt kan du spåra artikelhistoriken för tillgången från datumet för skapandet.

När du har slutfört ett underhållsjobb och artikelförbrukning har registrerats på en arbetsorder kan du spåra förbrukning av reservdelar och andra artiklar som används på tillgången. Den här funktionen kan du behålla en fullständig artikelförbrukningspost för alla dina tillgångar. Du kan till exempel använda posten för att övervaka om en viss reservdel ofta ersätts eller för att hålla reda på de reservdelar eller andra artiklar som för närvarande används på en tillgång.

> [!NOTE]
> På en arbetsorder kan artikelförbrukning innehålla både reservdelar och andra, ytterligare artiklar, till exempel smörjmedel, bultar och packningar.

En tillgångsstruktur kan uppdateras automatiskt baserat på inställningarna i tillgångshanteraren. Om ett livscykeltillstånd för arbetsorder har skapats för att hantera färdiga eller slutförda arbetsorder och alternativet **uppdatera tillgångsstruktur** för den arbetsorderns livscykeltillstånd anges till **Ja** i **livscykeltillstånd för arbetsorder** kommer alla artiklar som används på den arbetsordern att uppdateras automatiskt på sidan **tillgångsstruktur** när arbetsordern uppdateras till det livscykeltillståndet. 


Du kan också manuellt uppdatera en tillgångsstruktur genom att skapa nya artikelrader på sidan **tillgångsstruktur**.

På sidan **tillgångsstruktur** kan du spåra reservdelshistorik för tillgångar när artikelförbrukningen har registrerats på en arbetsorder. Om du vill använda den här funktionen måste du välja de artikelgrupper som ska användas för reservdelsregistrering på sidan **artikelgrupper för reservdelar**.

Om du vill använda funktionen för tillgångsstruktur måste du först konfigurera nödvändiga artikelgrupper för reservdelar. Om du vill att tillgångsstrukturen ska uppdateras automatiskt när en arbetsorder slutförs, kan du konfigurera ett livscykeltillstånd för arbetsorder för att hantera uppdateringen. 


## <a name="set-up-spare-parts-item-groups"></a>Ställ in artikelgrupper för reservdelar

Inställningen av reservdelshistoriken baseras på artikelgrupper som skapas i modulen **hantering av lager och lagerställe**. I Tillgångshantering ställer du in artikelgrupper så att du kan spåra reservdelshistorik för artiklarna i de valda artikelgrupperna.

1. Välj **Tillgångshantering** \> **inställningar** \> **tillgång** \> **artikelgrupper för reservdelar**.
2. Välj **ny** om du vill konfigurera en artikelgrupp.
3. I fältet **artikelgrupp** väljer du gruppen. Namnet på gruppen anges automatiskt i fältet **Namn**.

## <a name="view-and-update-asset-boms"></a>Visa och uppdatera tillgångsstrukturlistor

När du bokför artikelförbrukning på en arbetsorder kan du visa den registrerade artikelförbrukningen på sidan **tillgångsstruktur**.

1. Gå till **Tillgångshantering** \> **Tillgångar** \> **Aktiva tillgångar**. Välj tillgången i listan och välj sedan **tillgångsstruktur**.

    > [!NOTE]
    > Om du vill visa alla artikelförbrukningsregistreringar på alla tillgångar, välj **Tillgångshantering** \> **förfrågningar** \> **tillgångar** \> **tillgångsstruktur**.

2. Välj **uppdatera tillgångsstruktur**. Du kan lägga till tillgångar, tillgångstyper och resurser till uppdateringen som du behöver genom att välja **Välj**. Starta uppdateringen genom att välja **OK**, Du kan också konfigurera uppdateringsfunktionen som ett batchjobb.
3. Om du vill se mer information som är relaterad till artiklarna kan du lägga till lagerdimensioner. Välj **Lager** \> **Dimensionsvisning** och markera sedan kryssrutorna för de dimensioner som du vill visa. Om du vill behålla den här inställningen för alla **tillgångsstrukturer** anger du alternativet **spara inställningar** till **Ja**.
4. Om du vill få en översikt över var i Tillgångshantering som artikeln på den valda raden används, i relation till tillgångar, jobbtypstandard, reservdelar och arbetsorder väljer du **artikel där den används**. 
5. Om du bara vill visa aktiva artikelrader väljer du **visa** \> **aktuell**. Om du vill visa alla artikelrader, inklusive rader där förfallodatumet infaller tidigare än det aktuella datumet väljer du **Visa** \> **Alla**.

> [!NOTE]
> När du har slutfört en arbetsorder, om vissa artiklar eller reservdelar som är relaterade till den relaterade tillgången har upphört att gälla eller har ersatts av andra artiklar eller reservdelar, rekommenderar vi att du uppdaterar tillgångsstrukturen i enlighet med detta.

## <a name="create-a-new-item-line-in-an-asset-bom"></a>Skapa en ny artikelrad i en tillgångsstruktur

Du kan manuellt skapa artikelrader för tillgångar.

1. Välj **Nytt** på sidan **Tillgångsstruktur**.
2. I fältet **Tillgång** väljer du den tillgång du vill lägga till en artikelrad för.
3. Ange ett sekventiellt radnummer i fältet **Radnummer**.
4. Ange ett startdatum för artikeln i fältet **Giltighet**.
5. Om artikeln upphör att gälla anger du ett slutdatum i fältet **förfallodatum**.
6. Välj en artikel i fältet **Artikelnummer**. Namnet anges automatiskt i fältet **Produktnamn**.
7. I fältet **Kvantitet** anger du kvantiteten som används. Fältet **Enhet** uppdateras automatiskt.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]