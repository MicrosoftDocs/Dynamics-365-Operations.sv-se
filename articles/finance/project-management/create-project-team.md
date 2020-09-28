---
title: Skapa ett projektteam
description: Denna artikel innehåller information om hur du skapar och hanterar projektteam.
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
ms.openlocfilehash: 834a6c0a4fcc32a955c1feddf0a6cbbb1f16b869
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760664"
---
# <a name="create-a-project-team"></a>Skapa ett projektteam

[!include [banner](../includes/banner.md)]

Om du vill använda de roller som redan har ställts in i ett projekt, måste en projektledare associera rollerna med projektet. Flera roller kan tilldelas för ett projekt. I syfte att undvika förvirring märks dessa roller automatiskt under reservation. Om till exempel projektledaren kräver tre programingenjörer, genereras automatiskt tre roller för programingenjör som har etiketterna **programingenjör 1**, **programingenjör 2** och **programingenjör 3**. Om rollen tidigare fått egenskaper, används de som ett filter för sökningar efter en resurs. Ytterligare egenskaper kan läggas till som krävs för att begränsa sökningen.

Visningsinställningar kan också anpassas för att ge en bättre vy av resurstillgänglighet. Det finns alternativ för att visa tim, dag, vecka, månad, kvartalsvis och årlig tillgänglighet. Det finns även alternativ för att visa återstående och tillgänglig kapacitet för resurser. Det här alternativet är användbart för tidsadministration, när du vill beräkna tillgänglig tid för aktiviteter eller resurstillgänglighet.

Projektledaren kan välja en roll på sidan och sedan, om det finns en tillgänglig resurs som passar behovet, välja att reservera en resurs för att fylla rollen. Observera att resurserna inte måste reserveras vid denna tidpunkt i planeringsfasen. När du skapar en struktur kan du ersätta roller med bemannade resurser för projektet. Om roller ersättas med bemannade resurser i strukturen uppdaterar inställningen av resursen automatiskt projektteamslistan och tidsplaneringen.

[![Projektteam som innehåller både roller och faktiska resurser](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Projektchefen har olika alternativ för att boka resurser för ett projekt, till exempel **Resterande kapacitet**, **Total kapacitet**, **Kapacitet i procent** och **Ange timmar**. Dessa bokningsalternativ kan annulleras när som helst om resurstilldelningen ändras. Två typer av bokningar stöds:

- **Fast bokning** – Resursreservationen godkändes och bekräftades för att arbeta på engagemanget under den angivna varaktigheten.
- **Preliminär bokning** – Resursreservationerna godkändes preliminärt för att arbeta på engagemanget för den angivna varaktigheten.

Följande procedur förklarar hur du skapar ett projektteam.

## <a name="create-a-project-team"></a>Skapa ett projektteam

1. På listsidan **Alla projekt**, markera ett projekt och markera sedan **Redigera**.
2. På fliken **Projektteam och tidsplanering**, i fältet **Schemalagt slutdatum**, ange schemastartdatumet plus en månad. Om till exempel schemastartdatumet är 24 juni 2017 (24/06/2017), ange **24/07/2017**.
3. Markera **Lägg till**.
4. I **Lägg till roller i projektet**-fönstret, i **Roll**-fältet, välj **Senior projektledare**.
5. Markera **Erforderliga kompetenser**.
6. På **Välj egenskaper**-sidan markeras de egenskaper som du tidigare angett för rollen senior projektledare som standard. Välj **OK**.
7. På **Lägg till roller i projektet**-sidan i **Antal resurser**-fältet, ange **1**.
8. I **Resurs**-fältet visar sökningen alla resurser som har begärt kompetenserna. Markera **Daniel Goldschmidt** och markera sedan **Skapa**.
9. På sidan **Projekt** markerar du **Lägg till**.
10. I **Lägg till roller i projektet**-fönstret, i **Roll**-fältet, välj **Teammedlem**. I fältet **Antal resurser**, ange **5**.
11. Markera **Skapa**.
12. På sidan **Projekt** markerar du **Uppfyll resurs**.

## <a name="monitor-project-teams"></a>Övervaka projektteam
1. På sidan **Alla projekt**, markera länken **Projekt-ID** för projektet **XYZ-uppgradering fas 2**.
2. På snabbfliken **Projektteam och tidsplanering**, verifiera att de listade projektresurserna är korrekta.
