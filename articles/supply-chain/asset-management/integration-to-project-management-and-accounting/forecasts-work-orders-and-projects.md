---
title: Prognoser, arbetsorder och projekt
description: Denna artikel förklarar prognoser och arbetsorderintegrering med modulerna Projekthantering och redovisning i Tillgångshantering.
author: johanhoffmann
ms.date: 08/29/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: df1e1fe352add8361309df54b2178ec27752466d
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016809"
---
# <a name="forecasts-work-orders-and-projects"></a>Prognoser, arbetsorder och projekt

[!include [banner](../../includes/banner.md)]

 

I Tillgångshantering görs integrering med modulen **Projekthantering och redovisning** för att optimera kostnadskontrollen, vilket gör att användarna kan spåra kostnader för underhållsjobb av typen prognoser och arbetsorderjobb.

Om du vill spåra underhållsjobbtypen prognoser måste två inställningar göras:

1. Välj ett projekt i **resurshanterings** > **inställningar** > **parametrar för tillgångs hantering** och sedan på fliken **tillgångar** > på snabbfliken **projekt** i fältet **Underhållsprognosprojekt**, älj ett projekt.

2. När du skapar en standardrad för underhållsjobbstyp skapas automatiskt ett aktivitetsnummer för raden på sidan **Standardvärden för underhållsjobbtyp** (**Tillgångshantering** > **Inställningar** > **Jobb** > **Standardvärden för underhållsjobbtyp**).

Prognoser för underhållsjobbtyp har två funktioner: 

- Du kan spåra kostnader i prognoser för underhållsjobbtyp i modulen **Projekthantering och redovisning**. 
- Prognoser överförs automatiskt till ett jobbprojekt för arbetsorder när du väljer en underhållsjobbtyp för ett arbetsorderjobb.

Om du vill spåra kostnader för arbetsorderjobb måste du först konfigurera arbetsorderprojekt. Mer information finns i [Projektinställningar för arbetsorder](../setup-for-work-orders/work-order-project-setup.md).

## <a name="work-order-job-projects"></a>Jobbprojekt för arbetsorder

När du skapar ett arbetsorderjobb på en arbetsorder, bestäms arbetsorderprojektet av inställningen för det överordnade projektet för arbetsorder i **Projektinställningar för arbetsorder** (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Projektinställningar**).

Jobbprojekt för arbetsorder skapas genom att du använder en kombination av följande information om arbetsorder:

- Arbetsordertypen som har valts på arbetsordern 
- Funktionsplatsen som är relaterad till tillgången i arbetsorderjobbet
- Tillgångstypen som är relaterad till tillgången i arbetsorderjobbet  
- Den förväntade start- och sluttiden som angetts för arbetsordern  

En del av den här informationen kanske inte finns på en arbetsorder. Därför görs sökningen efter ett överordnat arbetsorderprojekt genom att använda den tillgängliga kombinationen av data och välja det projekt-ID som motsvarar arbetsorderdata.

Till exempel i följande illustration på grund av det sätt som tillgångstypen **lastbilsmotor** är inställd på kommer varje arbetsorderjobb som skapas med tillgångstypen **lastbilsmotor** att vara ett delprojekt för projekt ID 000186.

![Figur 1.](media/01-integration-to-pma.png)

Syftet med projekt-ID på arbetsorderjobbet och det relaterade aktivitetsnumret är att spåra kostnader som är relaterade till arbetsorderjobbet och tillgången som är vald i modulen **Projekthantering och redovisning**. (Om du vill visa projekt-ID och aktivitetsnummer väljer du **Tillgångshantering** > **arbetsorder** > **alla arbetsorder** och väljer sedan arbetsordern. På snabbfliken **Raddetaljer** visar fältet **Projekt-ID** projekt-ID och fältet **aktivitetsnummer** visar aktivitetsnummer.) Mer information om kostnadskontroll i tillgångs hantering finns [Kostnad- och datumkontroll](../controlling-and-reporting/cost-and-date-control.md).

Följande bild visar en grafisk översikt över arbetsorderprojekt och relaterade projektaktiviteter.

![Figur 2.](media/02-integration-to-pma.png)

När ett nytt arbetsorderjobb skapas på en arbetsorder skapas ett arbetsorderprojekt automatiskt för jobbet. De ekonomiska dimensionerna för tillgången relaterad till arbetsorderjobbet överförs automatiskt till arbetsorderprojektet.

Projektaktiviteten som skapas för ett arbetsorderjobb har relaterad information kopplad till sig. Den här informationen handlar om underhållsjobbtyp, variant av underhållsjobbtyp och handel. Detta är användbart om du t.ex. skapar en inköpsorder från en arbetsorder (se [Anskaffning](../work-orders/procurement.md)), eller om du använder modulen **Projekthantering och redovisning** för tidsregistrering.

Om tillgången har installerats på en funktionsplats och denna tillgång senare installeras på en annan funktionsplats, uppdateras de ekonomiska dimensionerna som hör till den nya funktionsplatsen automatiskt för tillgången. När du sedan skapar ett arbetsorderjobb för tillgången hämtar arbetsorderprojektet för arbetsorderjobbet automatiskt de ekonomiska dimensioner som nu är relaterade till tillgången. Det innebär att när du använder funktionsplatser kan kostnader alltid spåras på de funktionsplatser där en tillgång installerades vid en given tidpunkt. Den automatiska uppdateringen av ekonomiska dimensioner säkerställer en fullständig spårning av kostnaderna för projektstyrning och rapportering.

## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Arbetsorderprojekt, arbetsorders livscykeltillgång, projektfaser och projekttyper

För att säkerställa korrekt användning av livscykeltillstånd för arbetsorder och relaterade projektfaser på arbetsorder måste du ta hänsyn till beroendena i relation till modulen **Projekthantering och redovisning**:

- I modulen **Projekthantering och redovisning** ställs projektfaser in för projekttyper på sidan **Parametrar för projekthantering och redovisning**.  
- På sidan **Parametrar för projekthantering och redovisning**, använd kryssrutorna för att markera relevanta projektfaser för alla projekttyper som du kommer att använda. I bilden nedan har fem faser (**Skapat**, **Uppskattat**, **Tidsplanerat**, **Pågår** och **Slutfört**) valts för projekttyperna **Tid och material** och **Internt**. De fem faserna är relevanta för både interna underhållsjobb och serviceunderhållsjobb.
- I modulen **Tillgångshantering** definieras projekt typerna av projektgrupperna som du konfigurerar på sidan **Projektinställningar för arbetsorder** > fliken **Projektgrupp**(**Tillgångshantering** > **inställningar** > **arbetsorder** > **projektinställningar**).  
- Projektgrupperna som ställs in på sidan **Projektinställningar för arbetsorder** används när du skapar arbetsorder. När en arbetsorder skapas, skapas automatiskt ett arbetsorderprojekt för arbetsordern.  
- Varje arbetsorders livscykeltillstånd måste ha en relaterad projektfas.  
- Projektfasen som är relaterad till en arbetsorders livscykeltillstånd måste definieras som en aktiv fas för projektgruppen som definieras i arbetsorderprojektet. Arbetsorderprojektet skapas automatiskt på en arbetsorder.
- När du skapar en ny arbetsorder baseras den automatiska allokeringen av arbetsorderprojektet på inställningen på sidan **Projektinställningar för arbetsorder**.  

Följande bild visar kopplingar mellan projektgrupper i arbetsorder, relaterade projekttyper, projektfaser och livscykeltillstånd för arbetsorder.

![Figur 3.](media/03-integration-to-pma.png)

![Figur 4.](media/04-integration-to-pma.png)

![Figur 5.](media/05-integration-to-pma.png)

För mer information om hur du konfigurerar arbetsorderprojekt, se [Inställningar av arbetsorderprojekt](../setup-for-work-orders/work-order-project-setup.md). Mer information om hur du skapar livscykeltillstånd för arbetsorder finns i [Livscykeltillstånd för arbetsorder](../setup-for-work-orders/work-order-lifecycle-states.md).

Följande illustration visar en grafisk översikt över de olika projekt som skapas i modulen **Tillgångshantering** för att aktivera integrering med modulen **Projekthantering och redovisning**. Det visar även de arbetsprocesser som projekten är relaterade till.

![Figur 6.](media/06-integration-to-pma.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]