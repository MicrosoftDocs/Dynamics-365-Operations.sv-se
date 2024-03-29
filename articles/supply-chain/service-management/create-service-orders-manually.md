---
title: Skapa en serviceorder manuellt
description: Du kan skapa serviceorder manuellt med hjälp av ett serviceavtal eller med formuläret **Serviceorder**.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1764d97d4492e7b982a5d2c9f7e7f1c15380be1d
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014863"
---
# <a name="create-service-orders-manually"></a>Skapa en serviceorder manuellt    

[!include [banner](../includes/banner.md)]


Du kan skapa serviceorder manuellt med hjälp av ett serviceavtal eller med formuläret **Serviceorder**. Du kan även skapa en serviceorder från ett projekt.

> [!TIP]
> <P>Du kan använda automatiserade processer för att skapa serviceorder. 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>Skapa en serviceorder manuellt från serviceavtalet

1.  Gå till **servicehantering** \> **serviceavtal** \> **serviceavtal**.

2.  Välj ett serviceavtal eller skapa ett nytt.

3.  Klicka på fliken **leverera** och gruppen **skapa**, klicka **planerade serviceorder** för att öppna formuläret **skapa serviceorder**.

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>Skapa en serviceorder manuellt i formuläret för serviceorder

1.  Välj **Servicehantering** \> **Serviceorder** \> **Serviceorder**.

2.  Välj **Ny** för att skapa en ny serviceorder.

3.  Skapa serviceorderrader för serviceordern.

> [!NOTE]
> <P>Om kryssrutan <STRONG>Tillåt utan serviceavtal</STRONG> i formuläret <STRONG>Servicehanteringsparametrar</STRONG> är markerad kan du bokföra transaktionerna från serviceorderraderna utan att koppla serviceordern till ett serviceavtal. Om kryssrutan är avmarkerad måste du knyta den manuellt skapade serviceordern till ett projekt innan du kan bokföra serviceorderraderna.</P>

## <a name="create-a-service-order-from-a-project"></a>Skapa en serviceorder från Projekt

1.  Gå till **Projekthantering och redovisning** \> **Projekt** \> **Alla projekt**.

2.  I formuläret **Projekt** i **åtgärdsfönstret** klickar du på fliken **Hantera** \> och **Service** \> **Serviceorder**.

3.  Följ tidigare procedur för att skapa en serviceorder manuellt i formuläret **Serviceorder**. Fältet **Projekt-ID**, visar projektreferensen.

> [!NOTE]
> <P>Om kryssrutan <STRONG>Tillåt utan serviceavtal</STRONG> i formuläret <STRONG>Servicehanteringsparametrar</STRONG> är markerad kan du bokföra transaktionerna från serviceorderraderna utan att koppla serviceordern till ett serviceavtal. Om kryssrutan är avmarkerad måste du knyta den manuellt skapade serviceordern till ett projekt innan du kan bokföra serviceorderraderna.</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>Skapa serviceorder från en försäljningsorderformuläret

Du kan skapa en serviceorder från formuläret **försäljningsorder** genom att använda guiden **skapa en ny serviceorder baserat på försäljningsordern**.

1.  Gå till **Försäljning och marknadsföring** \> **Försäljningsorder** \> **Alla försäljningsorder**.

2.  Öppna relevant försäljningsordern.

3.  På fliken **försäljningsorder**, klicka på **Serviceorder** för att starta guiden **Skapa en ny serviceorder baserat på försäljningsordern**.

4.  Klicka på **nästa \>**, och gör sedan följande steg på sidan **Välj avtal för serviceorder**:
    
      - Använd fältet **Serviceavtal** för att välja det nya serviceavtal som den nya serviceordern ska kopplas till.
    
      - Valfritt: Använd fältet **Projekt-ID** och koppla serviceordern till ett projekt.

5.  Klicka på **nästa \>**, och gör sedan följande steg på sidan **Skapa serviceorder**:
    
      - Ange datum och tid då servicesamtalet ska inledas i fältet **Prioriterad servicetid**.
    
      - Valfritt: Ändra texten i fältet **Beskrivning**. Som standard innehåller detta fält en beskrivning av det serviceavtal som du valde på föregående sida.
    
      - I fältet **Ansvarig** väljer du sedan ID:t på den medarbetare som ansvarar för avtalet och, om du känner till det, ID:t på den tekniker som kunden vill ska genomföra servicesamtalet.
    
      - I fältet **Kontakt-ID** väljer du person i kundens företag som ska kontaktas för denna serviceorder.

6.  Välj **Nästa \>** och välj sedan **Slutför**.


## <a name="see-also"></a>Se även

[Serviceorder](service-orders.md)

[Skapa serviceorder automatiskt](create-service-orders-automatically.md)

[Skapa serviceorder (klassformulär)](https://technet.microsoft.com/library/aa553901\(v=ax.60\)) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]