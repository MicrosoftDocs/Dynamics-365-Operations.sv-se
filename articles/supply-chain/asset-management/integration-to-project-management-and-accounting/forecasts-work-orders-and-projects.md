---
title: Prognoser, arbetsorder och projekt
description: Det här avsnittet innehåller information om prognoser och arbetsorderintegration med modulen Projekthantering och redovisning i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e986d139ac9d0a7729bb9787f05332bcc09f59b
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886826"
---
# <a name="forecasts-work-orders-and-projects"></a>Prognoser, arbetsorder och projekt

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I Tillgångshantering görs integrering i modulen **Projekthantering och redovisning** för att optimera kostnadskontrollen, vilket gör att användarna kan spåra kostnader för underhållsjobb av typen prognoser och arbetsorderjobb.

Om du vill spåra underhållsjobbtypen prognoser måste två inställningar göras:

1. Välj ett projekt i **Tillgångshantering** > **Inställningar** > **Parametrar för tillgångshantering** >  länken **Tillgångar** > snabbfliken **Projekt** > fältet **Underhållsprognosprojekt**.

2. I **Standardvärden för underhållsjobbtyp**, när du skapar en standardrad för en underhållsjobbtyp, skapas ett aktivitetsnummer automatiskt för raden (**Tillgångshantering** > **Inställningar** > **Jobb** > **Standardvärden för underhållsjobbtyp**).

Underhållsjobbtypen prognoser har två syfte: du kan spåra kostnader för underhållsjobbprognoser i modulen **Projekthantering och redovisning**. Dessutom överförs prognoser automatiskt till ett jobbprojekt för arbetsorder när du väljer en underhållsjobbtyp för ett arbetsorderjobb.

Om du vill spåra kostnader för arbetsorderjobb måste du först ställa in arbetsorderprojekt. Se avsnittet [Projektinställningar för arbetsorder](../setup-for-work-orders/work-order-project-setup.md) för en beskrivning av proceduren.

## <a name="work-order-job-projects"></a>Jobbprojekt för arbetsorder

När du skapar ett arbetsorderjobb på en arbetsorder, bestäms arbetsorderprojektet av inställningen för det överordnade projektet för arbetsorder i **Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Projektinställningar**.

Jobbprojekt för arbetsorder skapas genom att du använder en kombination av följande information om arbetsorder:

- Arbetsordertypen som har valts på arbetsordern 
- Funktionsplatsen som är relaterad till tillgången i arbetsorderjobbet
- Tillgångstypen som är relaterad till tillgången i arbetsorderjobbet  
- Den förväntade start- och sluttiden som angetts för arbetsordern  

Det är möjligt att viss information som nämns ovan inte finns på en arbetsorder. Därför görs sökningen efter ett överordnat arbetsorderprojekt genom att använda den tillgängliga kombinationen av data och välja det projekt-ID som motsvarar arbetsorderdata.

Exempel: inställningarna av tillgångstypen "Lastbilsmotor" i bilden nedan innebär att varje arbetsorderjobb som har skapats med denna tillgångstyp blir ett delprojekt med projekt-ID "000186".

![Figur 1](media/01-integration-to-pma.png)

Syftet med projekt-ID: t för arbetsorderjobbet och det relaterade aktivitetsnumret (**Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** > välj arbetsorder i listan > snabbfliken **Radinformation** > fältet **Projekt-ID** och fältet **Aktivitetsnummer**) är att spåra kostnader som är relaterade till arbetsorderjobbet, och tillgången som valts i arbetsorderjobbet i modulen **Projekthantering och redovisning**. 

I bilden nedan visas en grafisk översikt över arbetsorderprojekt och relaterade projektaktiviteter.

![Figur 2](media/02-integration-to-pma.png)

När ett nytt arbetsorderjobb skapas på en arbetsorder skapas ett arbetsorderprojekt automatiskt för jobbet. De ekonomiska dimensionerna för tillgången relaterad till arbetsorderjobbet överförs automatiskt till arbetsorderprojektet. Projektaktiviteten som har skapats för ett arbetsorderjobb har relaterad information kopplad till sig om underhållsjobbtyp, variant av underhållsjobbtyp och yrkesgren. Dessa data är användbara om du t.ex. skapar en inköpsorder från en arbetsorder (se [Anskaffning](../work-orders/procurement.md)), eller om du använder modulen **Projekthantering och redovisning** för tidsregistrering.  

Om tillgången har installerats på en funktionsplats och denna tillgång senare installeras på en annan funktionsplats, uppdateras de ekonomiska dimensionerna som hör till den nya funktionsplatsen automatiskt för tillgången. När du sedan skapar ett arbetsorderjobb för tillgången hämtar arbetsorderprojektet för arbetsorderjobbet automatiskt de ekonomiska dimensioner som nu är relaterade till tillgången. Det innebär att när du använder funktionsplatser kan kostnader alltid spåras på de funktionsplatser där en tillgång installerades vid en given tidpunkt. Den automatiska uppdateringen av ekonomiska dimensioner säkerställer en fullständig spårning av kostnaderna för projektstyrning och rapportering.  


## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Arbetsorderprojekt, arbetsorders livscykeltillgång, projektfaser och projekttyper

För att säkerställa korrekt användning av livscykeltillstånd för arbetsorder och relaterade projektfaser på arbetsorder måste du ta hänsyn till beroendena i relation till modulen **Projekthantering och redovisning**:

- I modulen **Projekthantering och redovisning** ställs projektfaser in för projekttyper i **Parametrar för projekthantering och redovisning**.  
- I **Parametrar för projekthantering och redovisning** måste du komma ihåg att markera relevanta kryssrutor för projektfaser för alla projekttyper som du ska använda. I bilden nedan har fem faser **Skapat** - **Uppskattat** - **Tidsplanerat** - **Pågår** - **Slutfört** valts för projekttyperna "Tid och material" och "Internt". De fem faserna är relevanta för både interna underhållsjobb och serviceunderhållsjobb.  
- I **Tillgångshantering** definieras projekttyper av projektgrupperna som du ställer in i formuläret **Projektinställningar för arbetsorder** > länken **Projektgrupp**.  
- Projektgrupperna som ställs in i **Projektinställningar för arbetsorder** används när du skapar arbetsorder. När en arbetsorder skapas, skapas automatiskt ett arbetsorderprojekt för arbetsordern.  
- Arbetsorderns livscykeltillstånd måste ha en relaterad projektfas.  
- Projektfasen som är relaterad till en arbetsorders livscykeltillstånd måste definieras som en aktiv fas för projektgruppen som definieras i arbetsorderprojektet. Arbetsorderprojektet skapas automatiskt på en arbetsorder.  
- När du skapar en ny arbetsorder baseras den automatiska allokeringen av arbetsorderprojektet på inställningen i **Projektinställningar för arbetsorder** (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Projektinställningar**).  

Kopplingar mellan projektgrupper i arbetsorder, relaterade projekttyper, projektfaser och livscykeltillstånd för arbetsorder visas i bilderna nedan.  

![Figur 3](media/03-integration-to-pma.png)

![Figur 4](media/04-integration-to-pma.png)

![Figur 5](media/05-integration-to-pma.png)

Se [Projektinställningar för arbetsorder](../setup-for-work-orders/work-order-project-setup.md) för att ställa in arbetsorderprojekt samt [Livscykeltillstånd för arbetsorder](../setup-for-work-orders/work-order-lifecycle-states.md) för hur du skapar livscykeltillstånd för arbetsorder.

I bilden nedan visas en grafisk översikt över de olika projekten som skapas i modulen **Tillgångshantering** för att möjliggöra integration med modulen **Projekthantering och redovisning**, samt de arbetsprocesser som projekten är relaterade till.

![Figur 6](media/06-integration-to-pma.png)

