---
title: Skapa en strukturlistemall
description: Du kan skapa en strukturlistemall med följande metoder.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 89c5d45ac27a8678c51fb63c0326c2802a094596
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566609"
---
# <a name="create-a-template-bom"></a>Skapa en strukturlistemall   

[!include [banner](../includes/banner.md)]


Du kan skapa en strukturlistemall med följande metoder. För samtliga metoder gäller att fälten **Från datum** och **Till datum** är valfria och endast till för information.

## <a name="create-a-template-bom-manually"></a>Skapa en strukturlistemall manuellt

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.

2.  Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.

3.  Under **Kopiera strukturlisterader från referens**markerar du alternativ **manuell**.

4.  I fältet **Artikelnummer** anger du en artikel av typen **Strukturlista**.

5.  Ange ett namn för mallen i fältet **Namn**.

6.  I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.

7.  Klicka på **OK**.

En ny tom strukturlistemall skapas.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Skapa en strukturlistemall som baseras på en annan strukturlistemall

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.

2.  Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.

3.  Under **Kopiera strukturlisterader från referens**markerar du alternativ **Mallstrukturlista**.

4.  I fältet **Referensnummer** väljer du en befintlig strukturlistemall att kopiera till din nya strukturlistemall.

5.  Ange ett namn för mallen i fältet **Namn**.

6.  I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.

7.  Klicka på **OK**.

En ny strukturlistemall skapas med rader som motsvarar raderna i den ursprungliga strukturlistemallen.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Skapa en strukturlistemall som baseras på en artikelstrukturlista

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.

2.  Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.

3.  Under **Kopiera strukturlisterader från referens** väljer du **Strukturlista**.

4.  I fältet **referensnummer** väljer du en strukturlisteversion. En artikel av typen Strukturlista kopieras till **artikelnummer**.

5.  Ange ett namn för mallen i fältet **Namn**.

6.  I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.

7.  Klicka på **OK**.

En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlistor**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Skapa en strukturlistemall som baseras på en produktionsstrukturlista

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.

2.  Tryck på CTRL+N om du vill öppna formuläret **Skapa mallstrukturlista**.

3.  Under **Kopiera strukturlisterader från referens** väljer du **Produktion**.

4.  I fältet **referensnummer** väljer du en produktionsstrukturlista.

5.  Ange ett namn för mallen i fältet **Namn**.

6.  I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.

7.  Klicka på **OK**.

En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlista**.

## <a name="see-also"></a>Se även

[Strukturlistemallar ](template-boms.md)

  


