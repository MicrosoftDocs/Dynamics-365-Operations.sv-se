---
title: Skapa en strukturlistemall
description: Du kan skapa en strukturlistemall med följande metoder.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 781df7611ec1e3ee9d3013f971232700df38ada0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836312"
---
# <a name="create-a-template-bom"></a>Skapa en strukturlistemall   

[!include [banner](../includes/banner.md)]


Du kan skapa en strukturlistemall med följande metoder. För samtliga metoder gäller att fälten **Från datum** och **Till datum** är valfria och endast till för information.

## <a name="create-a-template-bom-manually"></a>Skapa en strukturlistemall manuellt

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.

2.  Välj **Ny** om du vill öppna formuläret **Skapa mallstrukturlista**.

3.  Under **Kopiera strukturlisterader från referens** markerar du alternativ **manuell**.

4.  I fältet **Artikelnummer** anger du en artikel av typen **Strukturlista**.

5.  Ange ett namn för mallen i fältet **Namn**.

6.  I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.

7.  Välj **OK**.

En ny tom strukturlistemall skapas.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Skapa en strukturlistemall som baseras på en annan strukturlistemall

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.

2.  Välj **Ny** om du vill öppna formuläret **Skapa mallstrukturlista**.

3.  Under **Kopiera strukturlisterader från referens** markerar du alternativ **Mallstrukturlista**.

4.  I fältet **Referensnummer** väljer du en befintlig strukturlistemall att kopiera till din nya strukturlistemall.

5.  Ange ett namn för mallen i fältet **Namn**.

6.  I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.

7.  Välj **OK**.

En ny strukturlistemall skapas med rader som motsvarar raderna i den ursprungliga strukturlistemallen.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Skapa en strukturlistemall som baseras på en artikelstrukturlista

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.

2.  Välj **Ny** om du vill öppna formuläret **Skapa mallstrukturlista**.

3.  Under **Kopiera strukturlisterader från referens** väljer du **Strukturlista**.

4.  I fältet **referensnummer** väljer du en strukturlisteversion. En artikel av typen Strukturlista kopieras till **artikelnummer**.

5.  Ange ett namn för mallen i fältet **Namn**.

6.  I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.

7.  Välj **OK**.

En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlistor**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Skapa en strukturlistemall som baseras på en produktionsstrukturlista

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceobjekt**\>**Mallstrukturlista**.

2.  Välj **Ny** om du vill öppna formuläret **Skapa mallstrukturlista**.

3.  Under **Kopiera strukturlisterader från referens** väljer du **Produktion**.

4.  I fältet **referensnummer** väljer du en produktionsstrukturlista.

5.  Ange ett namn för mallen i fältet **Namn**.

6.  I fälten **Från datum** och **Till datum** anger du ett datumintervall under vilket strukturlistemallen är aktiv.

7.  Välj **OK**.

En ny strukturlistemall skapas med hjälp av rader motsvarande raderna i den strukturlista som listas i **strukturlista**.

## <a name="see-also"></a>Se även

[Strukturlistemallar ](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]