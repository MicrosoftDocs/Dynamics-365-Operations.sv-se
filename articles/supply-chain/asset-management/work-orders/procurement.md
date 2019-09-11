---
title: Anskaffning
description: I det här avsnittet beskrivs anskaffning i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1678dbe2432e4be46aebb40a12e73dfd695c3e77
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875901"
---
# <a name="procurement"></a>Anskaffning


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I Tillgångshantering kan du få en översikt över inköpsrekvisitioner och inköpsorder relaterade till arbetsorder. Det går också att skapa en inköpsorder eller en inköpsrekvisition från en arbetsorder.

I listan **Inköpsrekvisition för arbetsorder** (**Tillgångshantering** > **Allmänt** > **Anskaffning** > **Inköpsrekvisition för arbetsorder**) visas en lista över inköpsrekvisitioner som är relaterade till arbetsorder.

- Välj ett arbetsorderjobb i listan **Inköpsrekvisition för arbetsorder** och klicka på knappen **Inköpsrekvisition** för att öppna den relaterade inköpsrekvisitionen.  
- Välj ett arbetsorderjobb i listan **Inköpsrekvisition för arbetsorder** och klicka på knappen **Arbetsorder** för att öppna den relaterade arbetsordern.  
- Välj ett arbetsorderjobb i listan **Inköpsrekvisition för arbetsorder** och klicka på knappen **Artikel där den används** om du vill få en översikt över var artikeln på den valda raden används i Tillgångshantering, i relation till tillgångar, standardvärden för underhållsjobbtyper, reservdelar och arbetsorder. 

![Figur 1](media/08-work-orders.png)


I listan **Inköpsrekvisition för arbetsorder** (**Hantering av företagstillgångar** > **Allmänt** > **Anskaffning** > **Arbetsorderinköp**) visas en lista över inköpsorder som är relaterade till arbetsorder.

- Välj ett arbetsorderjobb i listan **Inköpsrekvisition för arbetsorder** och klicka på knappen **Inköpsorder** för att öppna den relaterade inköpsordern.  
- Välj ett arbetsorderjobb i listan **Arbetsorderinköp** och klicka på knappen **Arbetsorder** för att öppna den relaterade arbetsordern.  
- Välj ett arbetsorderjobb i inköpslistan **Arbetsorder** och klicka på knappen **Artikel där den används** om du vill få en översikt över var artikeln på den valda raden används i Tillgångshantering, i relation till tillgångar, standardvärden för underhållsjobbtyper, reservdelar och arbetsorder. 

![Figur 2](media/09-work-orders.png)


I de listor som visas ovan placeras en ikon för kontroll av leveransdatum till höger på varje rad. Om ikonen visar ett utropstecken i en röd cirkel, innebär det att leveransen på den relaterade inköpsrekvisitionen eller inköpsordern kan vara försenad.

På en inköpsrekvisition finns det datum som används för att beräkna möjlig försening i formuläret **Inköpsrekvisitioner** > snabbfliken **Inköpsrekvisitionshuvud** > fältet **Begärt datum**. Detta datum jämförs med det tillgängliga datumet på arbetsordern eller arbetsorderjobbet på samma sätt som inköpsorderdatumet.

På en inköpsorder är det datum som används för att beräkna möjlig försening det datum som är relaterat till inköpsorderraden, som visas i formuläret **Inköpsorder** > välj inköpsorderrad snabbfliken **Radinformation** > fliken **Inställningar** > fältet **Bekräftat leveransdatum**. Om fältet inte är ifyllt används datumet i fältet **Leveransdatum** på snabbfliken **Inköpsorderhuvud**. Ett av dessa datum jämförs med det tillgängliga datumet på arbetsordern eller arbetsorderjobbet i följande ordning:

- Faktiskt startdatum på arbetsordern, eller  

- Tidsplanerat startdatum för det relaterade arbetsorderjobbet, eller  

- Tidsplanerat startdatum på arbetsordern, eller  

- Förväntat startdatum på arbetsordern, eller  


## <a name="create-purchase-order-from-a-work-order"></a>Skapa inköpsorder från en arbetsorder

I **Alla arbetsorder** väljer du ett arbetsorderjobb och skapar en relaterad inköpsorder eller inköpsrekvisition. Detta görs för att säkerställa projektrelationer mellan inköpsordern eller inköpsrekvisitionen och arbetsordern.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Markera i listan **Alla arbetsorder** eller **Aktiva arbetsorder** den arbetsorder som du vill skapa en inköpsorder för och klicka på **Redigera**.

3. I formuläret **Arbetsorder** > snabbfliken **Underhållsjobb för arbetsorder** väljer du det arbetsorderjobb som du vill skapa inköpsordern för.

4. Klicka på **Artikeluppgifter** > **Inköpsorder från arbetsorderjobb**.

5. På listsidan **Projektinköpsorder**, klicka på **Ny**.

6. Skapa inköpsordern.

>[!NOTE]
>Att skapa en inköpsrekvisition är nästan identiskt med att skapa en inköpsorder. Den enda skillnaden är att i proceduren ovan klickar du på **Artikeluppgifter** > **Inköpsrekvisition från arbetsorderjobb** i steg 2.

## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Projektrelation mellan arbetsorder och inköpsorder eller inköpsrekvisition

En inköpsorderrad eller inköpsrekvisitionsrad är relaterad till ett arbetsorderjobb via arbetsorderprojekt och det relaterade projektaktivitetsnumret. När du skapar en inköpsorder eller inköpsrekvisition från ett arbetsorderjobb är det relaterade projektaktivitetsnumret obligatoriskt. Projektaktivitetsnumret infogas automatiskt på en inköpsorder eller inköpsrekvisition om motsvarande arbetsorder innehåller arbetsorderjobb som alla använder samma typ av underhållsjobb. Om arbetsorderjobben innehåller olika underhållsjobbtyper måste projektaktivitetsnumret infogas manuellt.

Om du vill visa eller infoga aktivitetsnumret som hör till en inköpsorderrad öppnar du **Arbetsorderinköp** > väljer inköpsorderposten > klickar på inköpsorder i kolumnen **Inköpsorder** > snabbfliken **Radinformation** > fliken **Projekt** > fältet **Aktivitetsnummer**.


![Figur 3](media/10-work-orders.png)


På samma sätt, om du vill visa eller infoga aktivitetsnumret som hör till en inköpsrekvisitionsrad för arbetsorder öppnar du **Inköpsrekvisition för arbetsorder** > väljer inköpsrekvisitionsposten > klickar på inköpsrekvisitionen i kolumnen **Inköpsrekvisition** > snabbfliken **Radinformation** > fliken **Projekt** > fältet **Aktivitetsnummer**.

