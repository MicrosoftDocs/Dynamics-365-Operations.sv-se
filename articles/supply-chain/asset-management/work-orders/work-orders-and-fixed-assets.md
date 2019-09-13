---
title: Arbetsorder och anläggningstillgångar
description: Det här avsnittet innehåller förklaringar av arbetsorder och anläggningstillgångar i Tillgångshantering.
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
ms.openlocfilehash: f03b7fa073c4e5338b7b5681ba7b8c9fe00a657b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875897"
---
# <a name="work-orders-and-fixed-assets"></a>Arbetsorder och anläggningstillgångar


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


I Tillgångshantering kan tillgångar relateras till anläggningstillgångar och du kan skapa arbetsorder för dessa tillgångar. Om du använder den här funktionen kan du få en fullständig översikt över anläggningstillgångar, relaterade investeringsprojekt och de kostnader som registrerats för investeringsprojekt i modulen **Projekthantering och redovisning** och modulen **Anläggningstillgångar** i Dynamics 365 for Finance and Operations.

>[!NOTE]
>Fältet **Anläggningstillgångsnummer** fylls bara i på arbetsorderns jobbprojekt om typen "investering" väljs som projekttyp för arbetsorders jobbprojekt.

![Figur 1](media/24-work-orders.png)

Följande procedur beskriver relationen mellan tillgångar, arbetsorder, jobbprojekt för arbetsorder och anläggningstillgångar.

1. Du skapar en tillgång som du kopplar till en anläggningstill gång, som du ser i bilden nedan.

![Figur 2](media/25-work-orders.png)

2. När du ställer in arbetsordertyper (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Arbetsordertyper**) skapar du en arbetsordertyp för hantering av investeringar. Se även [Arbetsordertyper](../setup-for-work-orders/work-order-types.md).

![Figur 3](media/26-work-orders.png)

3. När du ställer in projektgrupper för arbetsorder (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Projektinställning** > **Projektgrupp**-länk), skapas en relation mellan arbetsordertypen som används för investeringar och projektetgruppen som skapas för investeringar i modulen **Projekthantering och redovisning** (**Projekthantering och redovisning** > **Inställningar** > **Bokför** > **Projektgrupper**).

![Figur 4](media/27-work-orders.png)

4. När du skapar en arbetsorder som hör till ett anläggningstillgångsobjekt väljer du den arbetsordertyp som används för att hantera investeringar, t. ex. "investeringar".

5. När arbetsordern skapas visas den relaterade arbetsordertypen i **Alla arbetsorder.**

![Figur 5](media/28-work-orders.png)

6. När arbetsordern skapas, skapas projektet som hör till arbetsordern i **Projekthantering och redovisning** > **Alla projekt**. Du kan se projektrelaterad information genom att klicka på **Projekt-ID**-länken på arbetsordern (i **Tillgångshantering**, öppna arbetsordern i informationsvyn > snabbfliken **Radinformation** > fliken **Allmänt**  > fältet **Projekt-ID**).

![Figur 6](media/29-work-orders.png)

7. I **Anläggningstillgångar** visas en översikt över de projekt som är kopplade till en anläggningstillgång (**Anläggningstillgångar** > **Anläggningstillgångar** > **Anläggningstillgångar** > klicka på anläggningstillgången i fältet **Anläggningstillgångens nummer** > visa innehållet i fönstret **Relaterad information** > avsnittet **Associerade projekt**).

