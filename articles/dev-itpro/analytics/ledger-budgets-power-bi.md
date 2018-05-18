---
title: "Faktiskt kontra Power BI-innehåll för budget"
description: "Det här avsnittet beskriver faktiskt Power BI-innehåll kontra Power BI-innehåll. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: aac6439bb54b3b9cab066b06c01763e880efef8e
ms.openlocfilehash: fa0c56f4773b9062d616772e2bca9a576ad37ce2
ms.contentlocale: sv-se
ms.lasthandoff: 12/18/2017

---

# <a name="actual-vs-budget-power-bi-content"></a>Faktiskt kontra Power BI-innehåll för budget

[!include [banner](../includes/banner.md)]

Detta avsnitt beskriver **Faktiskt kontra budget**-Microsoft Power BI-innehåll. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet. 

## <a name="overview"></a>Översikt

**Faktiskt kontra budget**-Power BI-innehållet skapades för personer som ansvarar att övervaka faktiskt kontra budget-prestanda i sina respektive organisationer. **Faktiskt kontra budget**-Power BI-innehåll ger insyn i dina budgetavvikelser. Du kan analysera budgeten för aktuellt år efter kontokategori, budgetkod, huvudkonto, huvudkontobeskrivningar eller räkenskapsperiod för att få en bättre förståelse för orsaken till eventuella avvikelser. 

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Rapporter från Power BI-innehållet **Utfall kontra budget** visas i arbetsytorna **Redovisningsbudget och prognoser** samt **Ekonomichef**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet
I följande tabell finns information om mått som finns på varje enskild rapportsida i Power BI-innehållet för **Faktiskt kontra budget**.


|           Rapport            |                                       Mätvärden                                        |
|-----------------------------|--------------------------------------------------------------------------------------|
| Utgifter - Utfall kontra budget |  <ul><li>Totala utgifter i år</li><li>Totala budgetutgifter i år</li></ul>  |
| Intäkt - utfall kontra budget  |   <ul><li>Totala intäkter i år</li><li>Totala budgetintäkter i år</li><ul>    |
|           Utgift           | <ul><li>Totala utgifter i år</li><li>Målet för utgifter som baseras på budgeten </li><ul> |
|           Intäkt           |  <ul><li>Totala intäkter i år</li><li>Målet för intäkter som baseras på budgeten </li><ul>  |
|         Nettoinkomst          |  <ul><li>Nettoinkomst i år</li><li>Målet för nettoutgifter som baseras på budgeten </li><ul>  |

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

|          Enhet           |                                     Innehåll                                     |
|---------------------------|----------------------------------------------------------------------------------|
| Redovisningsaktiviteter |                    Transaktionsbelopp för redovisningen                    |
|     Budgetaktiviteter     |                   Transaktionsbelopp för budgetregistret                    |
|       Huvudkonton       |                        Huvudkonton att för rapportfiltrering                        |
|     Räkenskapskalendrar      |                      Räkenskapskalendrar för rapportfiltrering                       |
|          Redovisningar          |       Redovisningar som kan användas för att filtrera rapporten till den aktuella redovisningen        |
|       Budgetkoder        |                        Budgetkoder att filtrera rapporter efter                         |
|      Juridiska personer       | Juridiska personer som kan användas för att filtrera rapporten till den aktuella juridiska personen |


