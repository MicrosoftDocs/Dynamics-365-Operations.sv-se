---
title: Skapa serviceavtal
description: I denna artikel beskrivs hur du använder funktioner i modulerna för Servicehantering och Projekthantering samt redovisning för att skapa serviceavtal.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d18d279cd437e98cad6495def953978cb78e723e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901775"
---
# <a name="create-service-agreements"></a>Skapa serviceavtal

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du använder funktioner i modulerna för Servicehantering och Projekthantering samt redovisning för att skapa serviceavtal.

## <a name="create-a-service-agreement-from-service-management"></a>Skapa en serviceorder från ett serviceavtal

1. Gå till **servicehantering**.
2. Klicka på **serviceavtal** om du vill skapa en ny serviceavtalsrad i sidhuvudet. 
3. Välj **Ny**. Ange en beskrivning, välj en referens till ett projekt i fältet **projekt-ID** och fyll i resten av fälten och raderna för serviceavtalet. Välj **Spara**.
4. I fliken **relationer** välj **serviceobjekt** eller **serviceuppgifter** när du vill skapa relationer för serviceobjekt eller serviceuppgifter i serviceavtalet. Serviceobjekten och uppgifterna som du har skapat relationer för, kan kopplas till rader för serviceavtalet.
5. Skapa serviceavtalsrader på den nedre halvan av sidan genom att kopiera rader från en servicemall, ett annat serviceavtal eller genom att skapa serviceavtalsraderna manuellt.

> [!NOTE]
> Om du kopierar rader till serviceavtalet från ett annat serviceavtal kan du ange om du även vill kopiera serviceobjekt- och serviceuppgiftsrelationer. Om du kopierar dessa relationer läggs de till i eventuella befintliga relationer i serviceavtalet. Om du kopierar serviceavtalsrader från en servicemall kopieras serviceobjekt- och serviceuppgiftsrelationerna automatiskt i form av serviceobjektrelationer och serviceuppgiftsrelationer till de nya serviceavtalsraderna.

## <a name="create-service-agreement-lines-manually"></a>Skapa serviceavtalsrader manuellt

1. Från sidan för **serviceavtal** kan du lägga till en serviceavtalsrad i rutnätet. 
2. Ange önskad information för serviceavtalsraden. 
3. Tryck på **Spara** för att spara raden och stäng sedan sidan.

## <a name="create-a-service-agreement-from-project"></a>Skapa ett serviceavtal från Projekt

1. Välj **Projekthantering och redovisning**.
2. Markera **Alla projekt**.
3. Välj projekt i listan.
4. I **åtgärdsfönstret** klicka på **Hantera**. I den **nya** åtgärdsgruppen, klickar du på **service** och markerar **serviceavtal**.
5. Följ anvisningarna i avsnittet **Skapa ett serviceavtal** som beskrevs tidigare i denna artikel om du vill ange projektreferensen.


## <a name="related-articles"></a>Relaterade artiklar

[Ta fram och upprätta avtal – översikt](service-agreements.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]