---
title: Skapa rapporter genom att lägga till innehåll som råa XML-dokument
description: Du kan utforma elektronisk rapportering (ER)-format som skapar utgående dokument i XML-format.
author: kfend
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: 87b70d5893d71e5022205a2f39f8263edf6d5280
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277555"
---
# <a name="generate-reports-by-adding-content-as-raw-xml"></a>Skapa rapporter genom att lägga till innehåll som råa XML-data

[!include[banner](../includes/banner.md)]

Du kan använda **RÅA XML**-formatelement för att utforma format för elektronisk rapportering (ER) som skapar utgående dokument i XML-format. I vissa fall kanske du vill lägga till obearbetad XML-data i dessa rapporter av en eller flera av följande orsaker:

- Det är bekvämare att använda råa XML-dokument för den ursprungliga designen och löpande underhåll av en rapport eftersom XML-strukturen kan skapas automatiskt genom att köra ett uttryck för körning. Därför måste inte flera bindningar fastställas för flera formatelement när du designar. Det är möjligt när du använder datakällor som innehåller information som kan användas för att göra XML-element medan rapporten skapas.
- Ingen annan metod kan användas för att fylla rapporten med XML-innehåll som tidigare har tagits emot och lagrats i systemet. Till exempel kanske XML-svaret som har skapats innehåller en XML-begäran som har skickats tidigare.
- Ingen annan metod kan användas för att infoga tecken i det skapade dokumentet utifrån deras numeriska koder. För vissa språk och tecken existerar inte den här typen av koder. Exempel inkluderar den grekiska bokstaven rho (ρ) och HTML-koder såsom \&eacute; för ett *e* med akut accent (é).

> [!NOTE]
> Tänk på att ramverket inte kontrollerar om XML-innehållet som placeras i det skapade dokumentet med hjälp av formatelementet **RÅA XML** är korrekt.

Om du vill veta mer om den här funktionen kan du spela upp uppgiftsguiderna **Rapporterna ER använda råa XML-data för att skapa XML (Del 1: Designa datamodell)** och **Rapporterna ER använda råa XML-data för att skapa XML (Del 2: Designa och köra rapport)** som ingår i affärsprocessen **7.5.4.3 hämta/utveckla fram IT-tjänst/komponenter (10677)** och kan hämtas från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Dessa uppgiftsguider förklarar processen att konfigurera ett ER-format för att infoga råa XML-data i skapade filer.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
