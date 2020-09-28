---
title: Ställ in projektresurser
description: Detta ämne innehåller information om hur du ställer in eller begär projektresurser.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760668"
---
# <a name="set-up-project-resources"></a>Ställ in projektresurser

[!include [banner](../includes/banner.md)]

Du måste ställa in en kalender och associera den till en medarbetare eller en arbetare. Kalendern används för att kunna tidsplanera projektet och arbetstiden för de resurser som har reserverats för projektet. Under kalenderinställningarna kan projektledare kan utföra resursutjämning som en del av resursoptimeringen. Baserat på kalendertidsplanen kan begränsningar tillämpas på resurser. Du kan ställa in en kalender på sidan **Kalendrar**.

När du konfigurerar en medarbetare som e projektresurs kan du välja bland medarbetare som arbetar på det företag som du konfigurerar resurser för. Alternativt kan du välja medarbetare från andra företag inom din organisation. Dessa medarbetare kallas även företagsinterna resurser.

Följande procedurer förklarar hur du konfigurerar en medarbetare som en projektresurs inom ditt företag samt hur du konfigurerar en företagsintern projektresurs.

## <a name="set-up-a-worker-as-a-project-resource"></a>Ställ in en arbetare som en projektresurs

1. På sidan **Arbetare**, i listan **Arbetare**, välj den arbetare som du lägger till som en projektresurs och öppna arbetarens post.
2. I åtgärdsfönstret markerar du **Projekt** &gt; **Inställningar** &gt; **Projektinställning**.
3. Välj en kalender och stäng sedan sidan.

Du kan även ange standardprojekt för en resurs som en typ av förtilldelning. Förtilldelningar kan användas när resurschefen eller projektledaren vet vilka projekt att resursen ska arbeta med i förväg. Förtilldelningar kan också baseras på en begäran av en projektsponsor eller kund. Du förtilldelar ett projekt genom att välja lämpligt projekt på sidan **Tilldela projekt**, på **Projekt** fliken, i listan **Resterande projekt**.

## <a name="set-up-an-intercompany-resource"></a>Ställa in en koncernintern resurs

När du ställer in en medarbetare som en företagsintern resurs måste du slutföra inställningarna i både det långivande företaget och det lånande företaget.

### <a name="in-the-lending-company"></a>I det långivande företaget

1. I Finance kontrollerar du att det långivande företaget har valts och slutför sedan proceduren i föregående avsnitt, "Ställ in en medarbetare som en projektresurs".
2. På sidan **Företagsintern redovisning** markerar du **Ny**.
3. I fältet **ID för juridisk person** markerar du det långivande företaget. Fyll i återstående fält efter behov och markera sedan **Spara**.
4. På sidan **Överföringspris** markerar du **Ny**.
5. I fältet **Lånande juridisk person** markerar du lämpligt företag.
6. Om du endast vill låna den resurs som du skapa de i början av detta avsnitt till det lånande företaget, markerar du namnet på den resurs som du skapat i fältet **Resurs**. Om du vill att alla resurser inom företaget som lånar ut ska vara tillgängliga för företaget som lånar, lämnar du fältet **Resurs** tomt.
7. På sidan **Projekthantering och redovisningsparametrar**, på fliken **Företagsintern**, anger du alternativet **Aktivera företagsintern resursplanering och tidrapporter** som **Ja**.

### <a name="in-the-borrowing-company"></a>I det lånande företaget

- I sökfiltret på sidan **Resurslista** anger du namnet på den resurs som du skapade för företaget som lånar ut, detta i syfte att bekräfta att namnet inkluderas i resurslistan för företaget som lånar.

## <a name="request-project-resources"></a>Förfrågningar om projektresurser
Schemaläggningsfunktionen för projektresurser låter endast resursansvariga distribuera bemannade resurser för åtaganden eller projekt. För att aktivera funktionen slutför du följande uppgifter eller bekräftar att de har slutförts:

- Ställa in nummerserier.
- Ställ in projekthanterings- och redovisningsarbetsflöden.
- Aktivera arbetsflödena för resursbegäran.

När föregående uppgifter har slutförts kan du slutföra följande uppgifter efter behov:

- Skapa en resursbegäran från en preliminärbokad bemannad resurs.
- Övervaka resursbegäranden.
- Uppfylla resursbegäranden.
- Begära en bemannad resurs från en struktur.
- Boka resurser till ett projekt utan någon begäran om en bemannad resurs.
