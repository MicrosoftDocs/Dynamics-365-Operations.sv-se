---
title: Utfall kontra budget Power BI-innehåll
description: Det här avsnittet beskriver Utfall kontra budget Power BI-innehåll. Här förklaras hur du kommer åt rapporterna och ger information om datamodellen.
author: panolte
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 9cc52f4cdab3084c9ac43078b0b0d534119ab514
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744249"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]