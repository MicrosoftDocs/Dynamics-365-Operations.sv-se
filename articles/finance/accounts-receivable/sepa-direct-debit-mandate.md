---
title: Ställa in SEPA Autogiromedgivande
description: Ett SEPA-autogiro låter en fordringshavare ta ut medel från en kunds bankkonto, förutsatt att kunden har gett fordringshavaren en undertecknad fullmakt.
author: ShivamPandey-msft
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0bea974750a6ac62d8ddeea5d9d4457f4846cb79
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891650"
---
# <a name="set-up-sepa-direct-debit-mandate"></a>Ställa in SEPA Autogiromedgivande

[!include [banner](../includes/banner.md)]

Ett SEPA-autogiro låter en fordringshavare ta ut medel från en kunds bankkonto, förutsatt att kunden har gett fordringshavaren en undertecknad fullmakt. Kunden undertecknar en fullmakt som auktoriserar fordringsägaren till att inkassera en betalning och instruerar kundens bank att betala inkasseringen. Den här artikeln är organiserat för att visa processen för inställning av SEPA-autogiromedgivande.

## <a name="prerequisites"></a>Förutsättningar
Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar

| Kategori       | Förutsättning                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Land/region | Den primära adressen för den juridiska personen måste vara i följande länder/regioner: Österrike, Belgien, Tyskland, Spanien, Frankrike, Italien eller Nederländerna. |

1. Ställ in en nummerserie för autogiromedgivande. Varje autogiromedgivande måste ha ett unikt nummer. Använd sidan **Nummersekvenser** om du vill skapa en nummerserie för autogiromedgivanden. Du använder den här identifieraren för att tilldela nummerserien till systemet för autogiromedgivande på sidan **Parametrar för kundreskontra**.

2. Ställ in parametrar för kundreskontra för autogiromedgivande. Använd sidan **Parametrar för kundreskontra** om du vill ställa in parametrar för autogiromedgivande. Du ställer in dessa parametrar på fliken **Direktdebitering**. Ändra standardparametrarna som du vill. Klicka sedan på fliken **Nummerserier** och uppdatera fältet **ID för autogiromedgivande** med den nummerserie som du skapade tidigare.

3. Om du vill ställa in ett betalsätt för autogiromedgivanden måste du ställa in ett betalsätt för autogiromedgivanden. Du använder den här betalsättet om du vill fråga efter fakturor som du vill generera autogirobetalningar för. Betalsättet måste ställas in på sidan **Betalsätt**. Om du vill ställa in ett betalsätt för autogiromedgivanden måste du följa följande ytterligare steg för ett betalsätt:

-   Välj **Elektronisk betalning** i fältet **Betalningstyp**.
-   Valfritt: Om du förväntar dig att var och en av dina kunder har flera fullmakter, väljer du **Faktura** i fältet **Period**. En separat betalning skapas för varje faktura och varje betalning kommer att använda fullmakten som angetts för fakturan.
-   Välj alternativet **Kräv medgivande** för att skapa betalningar genom att använda autogiromedgivanden. Alternativet **Kräv medgivande** är endast tillgängligt om du väljer **Elektronisk betalning** i fältet **Betalningstyp**.

Ytterligare resurser

[Översikt över SEPA-autogiro](sepa-direct-debit-overview.md) 

[Skapa ett autogiromedgivande för en kund](tasks/create-direct-debit-mandate-customer.md) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
