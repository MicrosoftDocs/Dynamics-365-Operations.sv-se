---
title: Utfall kontra budget Power BI-innehåll
description: Det här avsnittet beskriver Utfall kontra budget Power BI-innehåll. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a577ab24aaf86c1f7a22953e03f397a2e8213c78
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184403"
---
# <a name="actual-vs-budget-power-bi-content"></a>Utfall kontra budget Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver **Utfall kontra budget** Microsoft Power BI-innehåll. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="overview"></a>Översikt

**Utfall kontra budget** Power BI-innehållet skapades för personer som ansvarar att övervaka faktiskt kontra budget-prestanda i sina respektive organisationer. **Utfall kontra budget** Power BI-innehåll ger insyn i dina budgetavvikelser. Du kan analysera budgeten för aktuellt år efter kontokategori, budgetkod, huvudkonto, huvudkontobeskrivningar eller räkenskapsperiod för att få en bättre förståelse för orsaken till eventuella avvikelser.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll
Rapporter från **Utfall kontra budget** Power BI-innehåll visas i arbetsytorna **Redovisningsbudget och prognoser** och **Ekonomichef**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet
I följande tabell finns information om mått som finns på varje enskild rapportsida i **Utfall kontra budget** Power BI-innehåll.

| Rapport                      | Mätvärden                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| Utgifter - Utfall kontra budget | <ul><li>Totala utgifter i år</li><li>Totala budgetutgifter i år</li></ul>  |
| Intäkt - utfall kontra budget  | <ul><li>Totala intäkter i år</li><li>Totala budgetintäkter i år</li><ul>     |
| Utgift                     | <ul><li>Totala utgifter i år</li><li>Målet för utgifter som baseras på budgeten</li><ul> |
| Intäkt                     | <ul><li>Totala intäkter i år</li><li>Målet för intäkter som baseras på budgeten</li><ul>   |
| Nettoinkomst                  | <ul><li>Nettoinkomst i år</li><li>Målet för nettoutgifter som baseras på budgeten</li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

| Enhet                    | Innehåll                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| Redovisningsaktiviteter | Transaktionsbelopp för redovisningen                                       |
| Budgetaktiviteter         | Transaktionsbelopp för budgetregistret                                      |
| Huvudkonton             | Huvudkonton att för rapportfiltrering                                               |
| Räkenskapskalendrar          | Räkenskapskalendrar för rapportfiltrering                                            |
| Redovisningar                   | Redovisningar som kan användas för att filtrera rapporten till den aktuella redovisningen              |
| Budgetkoder              | Budgetkoder att filtrera rapporter efter                                                |
| Juridiska personer            | Juridiska personer som kan användas för att filtrera rapporten till den aktuella juridiska personen |
