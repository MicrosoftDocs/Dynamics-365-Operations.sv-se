---
title: Anskaffning
description: I denna artikel beskrivs anskaffning i Tillgångshantering.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderPurchaseListPagePreviewPane, EntAssetWorkOrderPurchaseListPage, EntAssetWorkOrderPurchaseLineAmountInfoPart, EntAssetWorkOrderPurchReqListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6e41a28ec922924b0ef86858a881280fd44bfe63
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014964"
---
# <a name="procurement"></a>Anskaffning

[!include [banner](../../includes/banner.md)]

I Tillgångshantering kan du få en översikt över inköpsrekvisitioner och inköpsorder relaterade till arbetsorder. Det går också att skapa en inköpsorder eller en inköpsrekvisition från en arbetsorder.

På listsidan **Inköpsrekvisition för arbetsorder** (**Tillgångshantering** > **Anskaffning** > **Inköpsrekvisition för arbetsorder**) visar en lista över inköpsrekvisitioner som är relaterade till arbetsorder. När du väljer ett jobb för arbetsorder på den här sidan kan du använda knapparna i gruppen **Visa** i åtgärdsfönstret **Inköpsrekvisition för arbetsorder** för att utföra olika åtgärder:

- Om du vill öppna den relaterade inköpsrekvisitionen, välj **inköpsrekvisition**. 
- Om du vill öppna en relaterad arbetsorder väljer du **arbetsorder**.
- Om du vill få en översikt som visar var artikeln på den valda raden används, i relation till tillgångar, underhållsjobbtypstandarder, reservdelar och arbetsorder i Tillgångshantering väljer du **artikel där den används**. Mer information om översikten finns i [Artikel där den används](../controlling-and-reporting/item-where-used.md).

I bilden nedan visas ett exempel på listsidan **Inköpsrekvisition för arbetsorder**.

![Figur 1.](media/08-work-orders.png)


På listsidan **Inköp för arbetsorder** (**Tillgångshantering** > **Anskaffning** > **Inköpsrekvisition för arbetsorder**) visas en lista över inköpsorder som är relaterade till arbetsorder. När du väljer ett jobb för arbetsorder på den här sidan kan du använda knapparna i gruppen **Visa** på fliken i åtgärdsfönstret **Inköpsrekvisition för arbetsorder** för att utföra olika åtgärder:

- Om du vill öppna en relaterad inköpsorder väljer du **inköpsorder**. 
- Om du vill öppna en relaterad arbetsorder väljer du **arbetsorder**.
- Om du vill få en översikt som visar var artikeln på den valda raden används, i relation till tillgångar, underhållsjobbtypstandarder, reservdelar och arbetsorder i Tillgångshantering väljer du **artikel där den används**. Mer information om översikten finns i [Artikel där den används](../controlling-and-reporting/item-where-used.md).

I bilden nedan visas ett exempel på listsidan **Inköp för arbetsorder**.

![Figur 2.](media/09-work-orders.png)


På listsidan **Inköp för arbetsorder** och **Inköpsrekvisition för arbetsorder** visas en symbol som är relaterad till kontrollen av leveransdatum till höger på varje rad. Om symbolen är ett utropstecken i en röd cirkel, innebär det att leveransen av den relaterade inköpsordern eller inköpsrekvisitionen kan vara försenad.

För en inköpsorder används det datum som är relaterat till inköpsorderraden för att beräkna en möjlig försening. Om du vill visa datumet väljer du inköpsorderraden på sidan **inköpsorder**. Datumet visas på fliken **Bekräftat leveransdatum** på fliken **Inställningar** på snabbfliken **Radinformation**. Om fältet **Bekräftat leveransdatum** inte har angetts används datumet i fältet **Leveransdatum** på snabbfliken **Inköpsorderrubrik** används för beräkningen. Ett av dessa datum jämförs med det tillgängliga datumet på arbetsordern eller arbetsorderjobbet i följande ordning:

1. Faktiskt startdatum på arbetsordern  

2. Tidsplanerat startdatum för det relaterade arbetsorderjobbet 

3. Tidsplanerat startdatum på arbetsordern 

4. Förväntat startdatum på arbetsordern, eller 

För en inköpsrekvisition används datumet i fältet **Begärt datum** på snabbfliken **Inköpsrekvisitionshuvud** på sidan **Inköpsrekvisitioner** för att beräkna en möjlig försening. Datumet i detta fält jämförs med det tillgängliga datumet på arbetsordern eller arbetsorderjobbet på samma order som används för inköpsorderdatumet.


## <a name="create-a-purchase-order-from-a-work-order"></a>Skapa en inköpsorder från en arbetsorder

På listsidan **Alla arbetsorder** kan du välja ett arbetsorderjobb och skapar sedan en relaterad inköpsorder eller relaterad inköpsrekvisition. Detta hjälper dig att säkerställa att projektrelationer finns mellan inköpsordern eller inköpsrekvisitionen och arbetsordern.

1. Klicka på **Tillgångshantering** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Markera arbetsordern som du vill skapa en inköpsorder för och välj sedan **redigera**.

3. På snabbfliken **Underhållsjobb för arbetsorder**, välj arbetsorderjobb att skapa arbetsordern för.

4. Klicka på **Artikeluppgifter** > **Inköpsorder från arbetsorderjobb**.

5. På listsidan **Projektinköpsorder**, klicka på **Ny**.

6. Skapa inköpsordern.

>[!NOTE]
>Gör på samma sätt för att skapa en relaterad inköpsrekvisition. Du kan dock välja **Artikeluppgifter** > **Inköpsrekvisition från arbetsorderjobb** i steg 4.


## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Projektrelation mellan arbetsorder och inköpsorder eller inköpsrekvisition

En inköpsorderrad eller inköpsrekvisitionsrad är relaterad till ett arbetsorderjobb via arbetsorderprojekt och det relaterade projektaktivitetsnumret. När du skapar en inköpsorder eller inköpsrekvisition från ett arbetsorderjobb är det relaterade projektaktivitetsnumret obligatoriskt. Projektaktivitetsnumret infogas automatiskt på en inköpsorder eller inköpsrekvisition om motsvarande arbetsorder innehåller arbetsorderjobb som alla använder samma typ av underhållsjobb. Om arbetsorderjobb har olika underhållsjobbtyper måste du manuellt ange projektaktivitetsnumret på inköpsorder eller inköpsrekvisition.

Om du vill visa eller ange aktivitetsnumret som hör till en inköpsorderrad, välj listsidan **Inköp för arbetsorder**, välj arbetsorderposten och välj sedan i kolumnen **inköpsorder** länken för inköpsordern. Du hittar fältet **aktivitetsnummer** på fliken **projekt** på snabbfliken **radinformation**.

Illustrationen nedan visar ett exempel på sidan **Inköpsorder** med fokus på **aktivitetsnummer**.

![Figur 3.](media/10-work-orders.png)

På samma sätt, för att visa eller ange det aktivitetsnummer som är relaterat till en rekvisitionsrad för arbetsorder på listsidan **Inköpsrekvisition för arbetsorder** välj inköpsrekvisitionsposten och sedan i kolumnen **inköpsrekvisition** väljer du länken för inköpsrekvisitionen. Du hittar fältet **aktivitetsnummer** på fliken **projekt** på snabbfliken **radinformation**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]