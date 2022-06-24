---
title: Utgiftshantering Power BI-innehåll
description: Den här artikeln beskriver vad som ingår i Power BI-innehållspaketet för utläggshantering.
author: panolte
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 78ae444c1c9803ed3708d71da7a359667df0252f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878325"
---
# <a name="expense-management-power-bi-content"></a>Utgiftshantering Power BI-innehåll

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver vad som ingår i Power BI-innehållet för utläggshantering. 

## <a name="overview"></a>Översikt
Två Power BI-innehållspaket är tillgängliga för användning med utgiftshantering i version 8.1 eller senare. 
- Det finns en personlig instrumentpanel som har utformats för anställda som skickar utgiftsrapporter. 

  Instrumentpanelen är skräddarsydd för att tillhandahålla nyckelinformationen för personer som inte har skickats och överförda belopp, samt historik och insyn i transaktionshistoriken för utgiften. Den personliga instrumentpanelen är en sida som innehåller den viktigaste informationen för användaren.

- Det finns en administratörsinstrumentpanel för leverantörsreskontraansvariga och chefer. Instrumentpanelen är anpassad för spårning och rapportering av medarbetares totala kostnader. Den ger viktiga utgiftsmått såsom inte skickade utgifter, körsträcka och genomsnittliga utgiftsrapportbelopp. Den använder transaktionsdata och ger aggregerade vyer av utgiftshantering över alla företag. Den innehåller även en uppdelning per medarbetare med möjlighet att lägga till ekonomiska dimensionsdata. Innehållet i administrationsutgiftsanalysen innehåller: 
  - En översiktssida med nyckelvärden om utgiftsbelopp och insyn i utkast, pågående och slutförda utgiftsrapporter. 
  - En medarbetares statistiksida granskar enskild information om en anställd efter tid, kostnadstyp och statistikgrupp. 
  - En medarbetares jämförelsesida för att jämföra flera medarbetare med tiden. 

Alla belopp visas i företagsvalutan. Data för alla företag visas, men om det behövs kan du lägga till ett företagsfilter. 

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll
Du hittar innehåll för Expense Admin Dashboard.pbix och Expense Personal Dashboard.pbix Power BI i det deladeresursbiblioteket i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](/archive/blogs/dynamicsaxbi/power-bi-content-from-microsoft-and-your-partners).
Innehållet finns tillgängligt från arbetsytan utgiftshantering som inbäddat Power Bi-innehåll. Varje utgiftsägare kan komma åt privata utgifter för dem själva, medan endast leverantörsreskontraansvariga och chefer har åtkomst till administratörsinnehållet för att visa användares utgiftsdata.

## <a name="refreshing-the-power-bi-content"></a>Uppdatera Power BI-innehållet
Utläggshantering för Power BI-innehållet kräver att TrvBiExpenseMeasurement-mått och BudgetActivityMeasure uppdateras från Enhetslagring. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mätvärden som ingår i Power BI-innehållet
Innehållet omfattar en uppsättning rapportsidor. Sidorna består av en uppsättning mått som visualiseras som diagram, brickor och tabeller. Nedanstående tabell ger en översikt över de visualiseringar som används i Power BI-innehållet.

**Analys av privata utgifter**

| Rapportsida | Visualisering                             |
|-------------|-------------------------------------------|
| Mina utgifter | Belopp för milkostnad                         |
|             | Pågående utgiftsrapporter                |
|             | Nr. för utgifter som inte har skickats               |
|             | Privata utgifter som ska betalas              |
|             | Belopp som inte har skickats                        |
|             | Skickat belopp                          |
|             | Belopp som avvaktar återbetalning             |
|             | Utgiftsrapporter med belopp och status   |
|             | Skickade men inte godkända utgiftsrapporter  |
|             | Utgifter per kostnadstyp                     |
|             | Utgifter per handlare                      |
|             | Utgifter per bearbetade utgifter            |
|             | Utgifter per projekt                       |
|             | Totalt transaktionsbelopp över tid        |

**Administrationsutgiftsanalys**

| Rapportsida         | Visualisering                           |           
|---------------------|-----------------------------------------|
| Utgiftsöversikt    | Belopp för utkastutgift                   |
|                     | Antal rader med utkastutgift           |
|                     | Utkastutgiftrader                     |
|                     | Regelöverträdelser för utgiftsrapport        |
|                     | Utestående huvudbelopp                      |
|                     | Skickade men inte godkända utgifter       |
|                     | Godkända utgifter                       |
|                     | Totalt utgiftsbelopp                    |
|                     | Sammanfattningar av utgiftsrapport                |
|                     | Utgifter per kostnadstyp                   |
|                     | Utgifter per handlare                    |
|                     | Utgifter av medarbetare                   |
|                     | Utgifter jämfört med projekt                     |
| Jämförelse av medarbetare | Utgiftsbelopp                         |
|                     | Utgiftsbelopp över tid efter medarbetare   |
| Statistik på medarbetare | Utgiftsrapporter per kostnadstyp            |
|                     | Privata utgifter                       |
|                     | Utgiftsrapporter enligt statistikgrupp     |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]