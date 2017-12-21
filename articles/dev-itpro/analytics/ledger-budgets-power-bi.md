---
title: "Faktiskt kontra Power BI-innehåll för budget"
description: "Det här avsnittet beskriver faktiskt Power BI-innehåll kontra Power BI-innehåll. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: ryansandness
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 2a0ad5af4e4d7da09690331dc9d1a51d2e97a664
ms.contentlocale: sv-se
ms.lasthandoff: 12/01/2017

---

# <a name="actual-vs-budget-power-bi-content"></a>Faktiskt kontra Power BI-innehåll för budget

[!include[banner](../includes/banner.md)]


Detta avsnitt beskriver **Faktiskt kontra budget**-Microsoft Power BI-innehåll. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet. 

# <a name="overview"></a>Översikt

**Faktiskt kontra budget**-Power BI-innehållet skapades för personer som ansvarar att övervaka faktiskt kontra budget-prestanda i sina respektive organisationer. **Faktiskt kontra budget**-Power BI-innehåll ger insyn i dina budgetavvikelser. Du kan analysera budgeten för aktuellt år efter kontokategori, budgetkod, huvudkonto, huvudkontobeskrivningar eller räkenskapsperiod för att få en bättre förståelse för orsaken till eventuella avvikelser. 

# <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Rapporter från Power BI-innehållet **Utfall kontra budget** visas i arbetsytorna **Redovisningsbudget och prognoser** samt **Ekonomichef**.

# <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet
I följande tabell finns information om mått som finns på varje enskild rapportsida i Power BI-innehållet för **Faktiskt kontra budget**.

| Rapport                      | Mätvärden |
|-----------------------------|---------|
| Utgifter - Utfall kontra budget | <ul><li>Totala utgifter i år</li><li>Totala budgetutgifter i år</li></ul> |
| Intäkt - utfall kontra budget  | <ul><li>Totala intäkter i år</li><li>Totala budgetintäkter i år</li><ul> |
| Utgift                     | <ul><li>Totala utgifter i år</li><li>Målet för utgifter som baseras på budgeten </li><ul> |
| Intäkt                     | <ul><li>Totala intäkter i år</li><li>Målet för intäkter som baseras på budgeten </li><ul> |
| Nettoinkomst                  | <ul><li>Nettoinkomst i år</li><li>Målet för nettoutgifter som baseras på budgeten </li><ul> |

## <a name="extending-the-power-bi-content"></a>Utöka Power BI-innehåll
Genom att använda innehållspaket som är tillgängliga i Microsoft Dynamics Lifecycle Services (LCS) kan du ge bra analyser till människor som inte är inloggade i Microsoft Dynamics 365. Du kan ändra dessa innehållspaket så att de innehåller andra rapporter och modeller och publicera innehållspaket till din Power BI.com-innehavare för analys. 

Du hittar Power BI-innehåll för **Faktisk kontra budget** i det delade resursbiblioteket i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

# <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

| Enhet                    | Innehåll |
|---------------------------|----------|
| Redovisningsaktiviteter | Transaktionsbelopp för redovisningen |
| Budgetaktiviteter         | Transaktionsbelopp för budgetregistret |
| Huvudkonton             | Huvudkonton att för rapportfiltrering |
| Räkenskapskalendrar          | Räkenskapskalendrar för rapportfiltrering |
| Redovisningar                   | Redovisningar som kan användas för att filtrera rapporten till den aktuella redovisningen |
| Budgetkoder              | Budgetkoder att filtrera rapporter efter |
| Juridiska personer            | Juridiska personer som kan användas för att filtrera rapporten till den aktuella juridiska personen |

