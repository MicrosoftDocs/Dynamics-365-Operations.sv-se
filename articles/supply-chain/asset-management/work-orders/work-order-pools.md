---
title: Arbetsorderpooler
description: I det här avsnittet beskrivs hur du arbetar med arbetsorderpooler i Tillgångshantering.
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
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875904"
---
# <a name="work-order-pools"></a>Arbetsorderpooler


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Du kan använda arbetsorderpooler för att gruppera arbetsorder som har något gemensamt. Du kan till exempel skapa pooler för arbetsorder för

- arbetslag, t.ex. underhållslag A, underhållslag B  

- yrkesfärdigheter, t ex. elektriker eller rörmokare  

- fysiska platser  

- tidsscheman, t. ex. veckor eller andra perioder  


Vid behov kan en arbetsorder placeras i flera av arbetsorderpoolerna.


## <a name="create-work-order-pool"></a>Skapa arbetsorderpool

I **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler** kan du få en översikt över dina arbetsorderpooler och skapa nya pooler.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler**.

2. Klicka på **Ny**.

3. Infoga ett ID för arbetsorderpool i fältet **Pool** och ett namn i fältet **Namn**.

4. Välj "Ja" på växlingsknappen **Aktiv** om du vill ange att arbetsorderpoolen är aktiv.

5. Välj "Ja" på växlingsknappen **Ta bort arbetsorderrelationer** om du vill att arbetsorder automatiskt ska tas bort från arbetsorderpoolen.

6. I fältet **Ta bort livscykeltillstånd** väljer du arbetsorderns livscykeltillstånd. Livscykeltillståndet för arbetsordern för att slutföra en arbetsorder kan t.ex. ställas in för att automatiskt ta bort relationer till arbetsorderpooler.

7. Du kan börja lägga till arbetsorder till din arbetsorderpool omedelbart. På snabbfliken **Arbetsorder** klickar du på **Lägg till rad**.

8. Välj en arbetsorder i fältet **Arbetsorder**. Det relaterade fälten uppdateras automatiskt.

9. Upprepa steg 7-8 om du vill lägga till fler arbetsorder.

10. I fältet **Sorteringsordning** kan du ange om arbetsorder ska utföras i en viss ordning. Infoga nummer 1, 2, 3 och så vidare för att ange en specifik sekvens för de valda arbetsorderna.

11. Klicka på knappen **Arbetsorder** om du vill visa en lista över alla arbetsorder som ingår i arbetsorderpoolen.

12. Klicka på knappen **Kapacitetsbeläggning** för att öppna **Kapacitetsbeläggning** för att beräkna och visa kapacitetsbeläggning för underhållsschema, ej tidsplanerade arbetsorder och tidsplanerade arbetsorder.

13. Klicka på knappen **Artikelprognos** om du öppna **Artikelprognos** för att beräkna och visa prognoser för artiklar (reservdelar och andra nödvändiga artiklar) relaterade till ett underhållsschema, ej tidsplanerade arbetsorder och tidsplanerade arbetsorder.

14. Klicka på knappen **Inköpsrekvisition för arbetsorder** för att öppna listan **Inköpsrekvisition för arbetsorder** och visa en lista med inköpsrekvisitioner relaterade till arbetsorderna i arbetsorderpoolen.

15. Klicka på knappen **Arbetsorderinköp** för att öppna listan **Arbetsorderinköp** och visa en lista med inköpsorder relaterade till arbetsorderna i arbetsorderpoolen.

>[!NOTE]
>När en arbetsorderpool inte längre är relevant för din arbetsplanering ställer du in kryssrutan **Aktiv** för den poolen till "Nej" i listvyn **Arbetsorderpool**.

Markera kryssrutan **Ta bort arbetsorderrelationer** om du vill ta bort alla arbetsorderrader, t.ex. för att skapa en tom pool som du senare kan använda för andra arbetsorder. Kom ihåg att avmarkera **Ta bort arbetsorderrelationer** om du vill använda arbetsorderpoolen för att skapa nya arbetsorderrelationer senare.


![Figur 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a>Lägga till arbetsorder i en arbetsorderpool

Som beskrivs i avsnittet ovan kan du lägga till arbetsorder till en arbetsorderpool när du skapar poolen. Du kan också lägga till en arbetsorder till en arbetsorderpool från en listorna **Alla arbetsorder**.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsorder i listan och klicka på **Arbetsorderpool**.

3. Välj "Lägg till" i fältet **Lägg till/ta bort**.

4. Välj arbetsorderpoolen i fältet **Pool**.

5. Klicka på **OK**.

6. När du har lagt till en arbetsorder i en arbetsorderpool, och vill placera arbetsordern i en viss serie i poolen: öppna en av listsidorna för arbetsorderpooler, välj poolen och klicka på **Redigera** och justera sorteringsordningen för arbetsorderna som ingår i poolen i formuläret **Arbetsorderpool** > snabbfliken **Arbetsorder** > fältet **Sorteringsordning**.

Om du vill ta bort den valda arbetsordern från en arbetsorderpool väljer du "Ta bort" i steg 3.

