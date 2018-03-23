---
title: "Utöka funktionerna i Microsoft Dynamics 365 for Talent"
description: "Om du har skapat några Microsoft-PowerApps kan du starta programmen från länkar i Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 51eb4288f5b6c732755007c1dcd8c4db090ccc0a
ms.contentlocale: sv-se
ms.lasthandoff: 03/08/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a>Utöka funktionerna i Microsoft Dynamics 365 for Talent

[!include[banner](includes/banner.md)]

Om du har skapat några Microsoft-PowerApps kan du starta programmen från länkar i Microsoft Dynamics 365 for Talent. Om du vill konfigurera åtkomsten till dina program måste du ange viss information i Talent på en konfigurationssida som kan öppnas från arbetsytan **Systemadministration**.

## <a name="configuring-embedded-powerapps-within-talent"></a>Konfigurera inbäddade PowerApps i Talent
Använd sidan **Ange inbäddade Microsoft PowerApps** för att konfigurera Talent-sidor så att dessa startar PowerApps-program. För att öppna sidan **Ange inbäddade Microsoft PowerApps**, öppna arbetsytan **Systemadministration** och öppna sedan fliken **Länkar**. Välj **Microsoft PowerApps** i gruppen **Konfiguration**. 

Följande information anges eller konfigureras på den här sidan: 

> - Ett beskrivande namn eller ID för respektive PowerApps-program.
> - En unik identifierare (GUID) för respektive program som du lägger till på en Talent-sida. Program-ID:t finns på PowerApps-webbplatsen [powerapps.com](http://powerapps.com/). 
> - Sidan där användare öppnar ett program eller en rapport. Inte alla Talent-sidor stöder inbäddade PowerApps- och Power BI-rapporter. 

 > [!NOTE]
 >  Ange det interna namnet på sidan i stället för det namn som visas överst på sidan. För att hitta det interna namnet, öppna sidan för vilken du behöver det interna namnet och klicka var som helst på sidan. När menyn öppnas, för då muspekaren över artikeln **Formulärinformation**. Det interna formulärnamnet visas bredvid menyalternativet **Formulärinformation**.
 
> - Ange den formulärstyrning varifrån programmet hämtar kontextdata. Ett program kan till exempel använda data om en arbetare. Om du anger sidan **Arbetare** i fältet **Kontext** kommer sidan **Arbetare** att öppnas när du startar programmet. En post i **kontextfältet** är valfritt. 
> - Ange storleken på dialogrutan där PowerApps-programmet ska köras. Dialogrutorna betecknas som ”liten” eller ”stor” i syfte att optimera användargränssnittet när programmet körs på en telefon respektive en större enhet. 

Du kan även ange vilka juridiska personer som ett program blir tillgängligt för, eller också kan du göra det tillgängligt för alla dina juridiska personer. Som standard är dina PowerApps-program tillgängliga för alla juridiska personer.

## <a name="opening-an-application"></a>Öppna ett program
När du har konfigurerat inbäddade PowerApps-program läggs länkar till angivna program till på sidorna i Talent. Klicka på en länk för att öppna ett program. 



