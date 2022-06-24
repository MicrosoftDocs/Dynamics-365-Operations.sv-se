---
title: Serviceintervall
description: Denna artikel innehåller en översikt över hur du arbetar med serviceintervall. Serviceavtalsintervallet anger den frekvens med vilken serviceorderrader skapas för serviceavtalsrader när du skapar serviceorder automatiskt.
author: sorenva
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62708258ac3dca9ac03b44efdc96e3bfd643a255
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887237"
---
# <a name="service-intervals"></a>Serviceintervall

[!include [banner](../includes/banner.md)]

Serviceavtalsintervallet anger den frekvens med vilken serviceorderrader skapas för serviceavtalsrader när du skapar serviceorder automatiskt.

När du skapar serviceorder automatiskt, skapas serviceorderrader i enlighet med det intervall du har angett för serviceavtalsraden från avtalsradens startdatum.

Om fältet för **intervall** på en serviceavtalsrad på sidan **serviceavtal** är blank, förekommer raden en gång och den används inte för att skapa serviceorder vid flera tillfällen.

## <a name="example"></a>Exempel

Det här exemplet illustrerar hur ett serviceintervall påverkar serviceavtalsrader och serviceorderrader på en serviceorder.

### <a name="create-a-service-agreement"></a>Skapa ett serviceavtal

Först skapar du ett serviceavtal och anger **med serviceavtal** för alternativet **kombinera serviceorder**.

1. Klicka på **Serviceavtal**
2. För att skapa ett nytt serviceavtal använd **åtgärdsfönstret** på fliken **serviceavtal** och klicka på **serviceavtal** i gruppen för **nytt**.
3. Ange en beskrivning, välj ett projekt i fältet **projekt-ID** och ange ett datum i fältet **startdatum**.
4. I fältet **kombinera serviceorder** väljer du **med serviceavtal**.

Nu har du skapat följande serviceavtal:

| Project      | Startdatum                                                                         |
|--------------|------------------------------------------------------------------------------------|
| Ditt projekt | Det angivna datumet för projektet. I det här exemplet används dagens datum. |

### <a name="create-a-service-agreement-line"></a>Skapa en serviceavtalsrad

Nu ska du skapa en serviceavtalsrad med transaktionstypen **timme**.

För att slutföra den här delen av exemplet måste du skapa ett serviceintervall på 10 dagar på sidan för **serviceintervall**. 

1. Markera det serviceavtal du just skapat. 
2. I snabbfliken för **rader** klickar du på knappen som **lägger till** för att skapa en ny rad i det nedre fönstret på sidan för **serviceavtal**.
3. Välj **timme** i fältet för **transaktionstyp**.
4. I fältet för **medarbetare** välj den medarbetare som ska leverera tjänsten.
5. I fältet för **serviceintervall** väljer du 10-dagarsintervall.

Nu har du skapat en serviceavtalsrad med följande information:

| transaktionstyp | Startdatum                               | Serviceintervall |
|------------------|------------------------------------------|------------------|
| Timme             | Aktuellt datum.                        | Var 10:e dag    |
| Arbetare           | Den medarbetare som ska utföra servicen. |                  |

Inget tidsfönster har angetts för denna rad. 

### <a name="create-planned-service-orders"></a>Skapa planerade serviceorder

Nu kan du skapa planerade serviceorder och serviceorderrader för kommande månad.

1. På sidan för **serviceavtal** klickar du på **planerade serviceorder** på fliken **leverera** i **åtgärdsfönstret**.
2. På sidan för att **skapa serviceorder** anger du det aktuella datumet i fältet **från datum** och ett datum som infaller en månad från det aktuella datumet i fältet **till datum**.
3. Ställ skjutreglaget för **timme** på **Ja**. 
4. Klicka på **OK**.

Eftersom det inte finns någon gruppering på serviceordern (definierad av alternativet **med serviceavtal** i fältet **kombinera serviceorder**), skapas en serviceorderrad per serviceorder.

### <a name="service-orders-created"></a>Skapade serviceorder

Tre serviceorderrader har skapats inom den tidsram som du angav i dialogrutan för att **skapa serviceorder**. Du kan se serviceorderraderna på sidan för **serviceavtal** (**åtgärdsfönstret**\>**leverera**-fliken \>**visa** -knappen).

## <a name="related-articles"></a>Relaterade artiklar

[Ställ in serviceintervall](set-up-service-intervals.md)  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]