---
title: Ange ett tillägg till en anläggningstillgång
description: I den här proceduren visas hur du lägger till ett tillägg till en befintlig anläggningstillgång.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d23f60963466249b332b759ee72ebc8387aee4b
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713061"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a>Ange ett tillägg till en anläggningstillgång

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du lägger till ett tillägg till en befintlig anläggningstillgång. Syftet med tillägg till anläggningstillgång ska följa efter Artikeltillägg, underhåll eller förbättringar av en tillgång och är endast till för information. Ändringar i anläggningstillgångens värde eller tjänstelivstid ska göras separat.   

Här används revisorrollen och demonstrationdata för den juridiska personen USMF.

1. I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Anläggningstillgångar > Anläggningstillgångar**.
2. Hitta och välj den anläggningstillgång som ska läggas till.
3. Klicka på länken på den valda raden i listan.
4. Klicka på **Anläggningstillgång** i åtgärdsfönstret.
5. Klicka på **Tillägg till anläggningstillgång**.
6. Klicka på **Ny**.
7. Skriv ett värde i fältet **Namn**.
8. I fältet **anskaffningsdatum** anger du datumet för tilläggsinköpet eller tjänsten.
9. I fältet **Enhetskostnad** anger du kostnaden för artikeln eller underhållet eller ange en annan förbättring för tillgången.
10. Ange ett nummer i fältet **Kvantitet**. Det totala kostnaden har ingen inverkan på värdet på anläggningstillgången och är för att följa och informationsändamål. Om kostnaden ska vara skriven med versaler, måste en uppskrivning transaktion bokförs separat.  
11. Klicka på fliken **Allmänt**.

    * Ange **Ökar tjänstelivstiden** till **Ja** om tillägget förlänger anläggningstillgångens tjänstelivstid.  
    * Det här fältet är endast till för information. Ändra tjänstelivstiden i värdemodellerna och avskrivningsreglerna för tillgången att öka tjänstelivstid.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
