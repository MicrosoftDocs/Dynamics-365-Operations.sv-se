---
title: "Faktiskt kontra Power BI-innehåll för budget"
description: "Det här avsnittet beskriver faktiskt Power BI-innehåll kontra Power BI-innehåll. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: ryansandness
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5d52cce3cccb16f0645d9de1832ebeffbfaf3a09
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# Faktiskt kontra Power BI-innehåll för budget
<a id="actual-vs-budget-power-bi-content" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Detta avsnitt beskriver **Faktiskt kontra budget**-Microsoft Power BI-innehåll. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet. 

# Översikt
<a id="overview" class="xliff"></a>

**Faktiskt kontra budget**-Power BI-innehållet skapades för personer som ansvarar att övervaka faktiskt kontra budget-prestanda i sina respektive organisationer. **Faktiskt kontra budget**-Power BI-innehåll ger insyn i dina budgetavvikelser. Du kan analysera budgeten för aktuellt år efter kontokategori, budgetkod, huvudkonto, huvudkontobeskrivningar eller räkenskapsperiod för att få en bättre förståelse för orsaken till eventuella avvikelser. 

# Åtkomst till Power BI-innehåll
<a id="accessing-the-power-bi-content" class="xliff"></a>
Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (uppdatering juli 2017) visas rapporter från Power BI-innehållet **Faktisk kontra budget** i arbetsytorna **Redovisningsbudget och prognoser** samt **Ekonomichef**.

# Rapporter som ingår i Power BI-innehållet
<a id="reports-that-are-included-in-the-power-bi-content" class="xliff"></a>
I följande tabell finns information om mått som finns på varje enskild rapportsida i Power BI-innehållet för **Faktiskt kontra budget**.

| Rapport                      | Mätvärden |
|-----------------------------|---------|
| Utgifter - Utfall kontra budget | <ul><li>Totala utgifter i år</li><li>Totala budgetutgifter i år</li></ul> |
| Intäkt - utfall kontra budget  | <ul><li>Totala intäkter i år</li><li>Totala budgetintäkter i år</li><ul> |
| Utgift                     | <ul><li>Totala utgifter i år</li><li>Målet för utgifter som baseras på budgeten </li><ul> |
| Intäkt                     | <ul><li>Totala intäkter i år</li><li>Målet för intäkter som baseras på budgeten </li><ul> |
| Nettoinkomst                  | <ul><li>Nettoinkomst i år</li><li>Målet för nettoutgifter som baseras på budgeten </li><ul> |

## Utöka Power BI-innehåll
<a id="extending-the-power-bi-content" class="xliff"></a>
Genom att använda innehållspaket som är tillgängliga i Microsoft Dynamics Lifecycle Services (LCS) kan du ge bra analyser till människor som inte är inloggade i Microsoft Dynamics 365. Du kan ändra dessa innehållspaket så att de innehåller andra rapporter och modeller och publicera innehållspaket till din Power BI.com-innehavare för analys. 

Du hittar Power BI-innehåll för **Faktisk kontra budget** i det delade resursbiblioteket i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

# Förstå datamodellen och enheterna
<a id="understanding-the-data-model-and-entities" class="xliff"></a>

| Enhet                    | Innehåll |
|---------------------------|----------|
| Redovisningsaktiviteter | Transaktionsbelopp för redovisningen |
| Budgetaktiviteter         | Transaktionsbelopp för budgetregistret |
| Huvudkonton             | Huvudkonton att för rapportfiltrering |
| Räkenskapskalendrar          | Räkenskapskalendrar för rapportfiltrering |
| Redovisningar                   | Redovisningar som kan användas för att filtrera rapporten till den aktuella redovisningen |
| Budgetkoder              | Budgetkoder att filtrera rapporter efter |
| Juridiska personer            | Juridiska personer som kan användas för att filtrera rapporten till den aktuella juridiska personen |

