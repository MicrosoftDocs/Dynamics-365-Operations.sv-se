---
title: Arbetsorderpooler
description: I det här avsnittet beskrivs hur du arbetar med arbetsorderpooler i Tillgångshantering.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7b0e3e5b25a291517d5ccefa1ed25b20255be187
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356059"
---
# <a name="work-order-pools"></a>Arbetsorderpooler

[!include [banner](../../includes/banner.md)]


Du kan använda arbetsorderpooler för att gruppera arbetsorder som har något gemensamt. Här följer några exempel på vad du kan skapa arbetsorderpooler för:

- Arbetslag, t.ex. underhållslag A eller underhållslag B  

- Yrkesfärdigheter, t.ex. elektriker eller rörmokare  

- Fysiska platser  

- Tidsscheman, t.ex. veckor eller andra perioder  

När du behöver kan du placera en arbetsorder i flera arbetsorderpooler.


## <a name="create-a-work-order-pool"></a>Skapa en arbetsorderpool

På listsidan **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler** kan du få en översikt över dina arbetsorderpooler och skapa nya pooler.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler**.

2. Välj **Ny**.

3. I fältet **Pool** anger du ett ID för arbetsorderpoolen.

4. Ange sedan ett namn i fältet **Namn**.

5. Ange alternativet **Aktiv** till **Ja** om du vill ange att arbetsorderpoolen är aktiv.

6. Ange alternativet **Ta bort arbetsorderrelationer** till **Ja** om du vill att arbetsorder automatiskt ska tas bort från arbetsorderpoolen.

7. I fältet **Ta bort livscykeltillstånd** väljer du arbetsorderns livscykeltillstånd. Livscykeltillståndet för arbetsordern för att slutföra en arbetsorder kan t.ex. ställas in för att automatiskt ta bort relationer till arbetsorderpooler.

    Du kan börja lägga till arbetsorder till din arbetsorderpool omedelbart.

8. På snabbfliken **Arbetsorder** klickar du på **Lägg till rad**.

9. Välj en arbetsorder i fältet **Arbetsorder**. Det relaterade fälten uppdateras automatiskt.

10. Upprepa steg 8 till och med 9 om du vill lägga till fler arbetsorder.

11. Om de arbetsorder som du la till ska utföras i en specifik ordning kan du i fältet **sorteringsordning** kan du ange siffrorna **1**, **2**, **3** osv för att ange den ordningen.

12. Om du vill visa en lista med alla arbetsorder som har inkluderats i arbetsordern går du till åtgärdsfönstret på fliken **Arbetsorderpool** i gruppen **Visa arbetsorderpoolrelaterad** och välj **arbetsorder** för att öppna listsidan **alla arbetsorder**.

13. För att beräkna och visa kapacitetsbelastning för underhållsschemat, ej tidsplanerade arbetsorder och tidsplanerade arbetsordrar, i åtgärdsfönstret, på fliken **Arbetsorderpool** i gruppen **Visa arbetsorderpoolrelaterad**, välj **Artikelprognoser** för att öppna dialogrutan **Beräkna artikelprognoser**.

14. För att beräkna och visa prognoser för artiklar (reservdelar och andra obligatoriska artiklar) som är relaterade till underhållsschema, ej tidsplanerade arbetsorder och tidsplanerade arbetsordrar, i åtgärdsfönstret, på **Arbetsorderpool** i gruppen **Visa arbetsorderpoolrelaterad**, välj **Artikelprognoser** för att öppna **Beräkna artikelprognoser**.

15. För att se en lista över inköpskrav som är relaterade till arbetsordrarna i arbetsorderpoolen, i åtgärdsfönstret, på **Arbetsorderpool** i gruppen **Anskaffning**, välj **Inköp för arbetsorder** för att öppna listsidan **Inköp för arbetsorder**.

16. För att se en lista över inköpskrav som är relaterade till arbetsordrarna i arbetsorderpoolen, i åtgärdsfönstret, på **Arbetsorderpool** i gruppen **Anskaffning**, välj **Inköpsrekvisition för arbetsorder** för att öppna listsidan **Inköpsrekvisition för arbetsorder**.

>[!NOTE]
>När en arbetsorderpool inte längre är relevant för din arbetsplanering ställer du in alternativet **Aktiv** för den poolen till **Nej** i listvyn på sidan **Arbetsorderpool**.

Om du vill radera alla arbetsorderrader anger du alternativet **Ta bort arbetsorderrelationer** till **Ja**. Det här alternativet är användbart om du t.ex. vill skapa en tom pool som du kan använda senare för andra arbetsorder. När du är redo att använda arbetsorderpoolen för att skapa nya arbetsordrelationer senare, kom ihåg att ställa in alternativet **Ta bort arbetsorderrelationer** till **Nej**.

I bilden nedan visas ett exempel på listsidan **Arbetsorderpool**.

![Figur 1.](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a>Lägga till en arbetsorder i en arbetsorderpool

Som beskrivs i avsnittet ovan kan du lägga till arbetsorder till en arbetsorderpool när du skapar poolen. Du kan också lägga till arbetsorder till en arbetsorderpool på listsidan **Alla arbetsorder** eller **Aktiva arbetsorder**.

1. Välj arbetsorder och sedan i åtgärdsfönstret på fliken **Arbetsorder** i gruppen **Underhåll** väljer du **Arbetsorderpool**.

2. Välj arbetsorder i listan och klicka på **Arbetsorderpool**.

3. I dialogrutan **Underhåll arbetsorderpool** i fältet **Lägg till/ta bort** väljer du **Lägg till**.

4. Välj arbetsorderpoolen i fältet **Pool**.

5. Välj **OK**.

6. Om du vill placera arbetsordern som du la till i en viss ordning i arbetsorderpoolen, på listsidan **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler** väljer du poolen och väljer sedan **redigera**. På sidan **Arbetsorderpool** på snabbfliken **Arbetsorder** kan du använda fältet **Sorteringsorder** för att justera sorteringsordningen för de arbetsorder som ingår i poolen.

Om du vill ta bort en arbetsorder från en arbetsorderpool, upprepa dessa steg men välj **Ta bort** i steg 3.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]