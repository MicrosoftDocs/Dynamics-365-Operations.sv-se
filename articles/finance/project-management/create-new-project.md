---
title: Skapa ett nytt projekt
description: Denna artikel innehåller information om hur du skapar och ett nytt projekt.
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
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760663"
---
# <a name="create-a-new-project"></a>Skapa ett nytt projekt

[!include [banner](../includes/banner.md)]

Gör på följande sätt om du vill skapa ett nytt projekt.

1. På sidan **Projekthantering** markerar du **Nytt projekt** och anger sedan följande värden:

    - **Projekttyp:** tid och material
    - **Projektnamn:** XYZ uppgraderingsfas 2
    - **Projektgrupp:** TM\_WIP
    - **Projektkontrakt-ID:** 00000002

2. Markera **Skapa projekt**.

## <a name="assign-a-resource-to-a-project"></a>Tilldela en resurs till ett projekt

1. På sidan **Arbetare**, på listan **Arbetare**, markerar du posten för den medarbetare som du tidigare angett kompetenser för, och öppnar sedan arbetarposten.
2. I Åtgärdsfönstret, på fliken **Projekt**, i gruppen **Inställningar**, markerar du **Tilldela projekt**.
3. På sidan **Projekttilldelningar för resursvalidering**, på fliken **Projekt**, i fältet **Lägg till projektet bland valda projekt**, filtrera projektet **XYZ-uppgradering fas 2**.
4. I fönstret **Återstående projekt**, markera ett projekt och markera sedan pilknappen för att lägga till det i fönstret **Valda projekt**.

Du kan vid behov också tilldela kategorier för en resurs. Kategoritypen är antingen **Kostnad** eller **Intäkt**. Kategoritypen bestäms av din organisation. Om det inte finns några tilldelade kategorier för en resurs, slår Finance upp standardkategorin på timpriser för kostnader och intäkter.

## <a name="set-up-project-resource-and-role-characteristics"></a>Ställ in projektresurs och rollegenskaper

En projektledare kan använda projektresurshanteringsfunktionen för att skapa roller som krävs för projektet. Roller kan användas om bekräftade resurser fortfarande är okända när resurser reserveras. Roller kan tillfälligt reserveras som planerade resurser, så att du kan fortsätta projektplanläggningsfaserna.

[![Exempel på en roll](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scenario:** Contoso anlitades för att slutföra ett tids- och materialprojekt som har ett godkänt projektramverk. Juniorprojektledaren avslutar fortfarande omfånget för projektet. Den resursansvarige identifierar för närvarande specifika resurser som ska reserveras för arbete på det nya projektet. På grund av projektets vitala natur har projektets sponsor begärt rollen som ledande projektchef som en av sina roller. Resursansvarig måste anskaffa den nya resursen och definiera rollen i systemet om biträdande projektledare behöver resursinformationen i samband med projektplaneringen.

Följande steg visar hur resursansvarig kan ställa in rollen Seniorprojektledare och associera resursegenskaper med den. Senare rollen kan användas för att söka efter tillgängliga resurser som matchar de nödvändiga resurskompetenserna.

1. På sidan **Konfigurera roller** markerar du **Nytt** och anger sedan följande värden:

    - **Roll ID:** Senior projektledare
    - **Beskrivning:** Senior projektledare

2. Markera **Skapa**.
3. Markera rollen **Senior Project Manager** och markera sedan **Konfigurera egenskaper**.
4. I fältet **Egenskapstyp**, välj **Kompetens**.
5. I fältet **Tillgängliga egenskaper** anger du den kompetens som du söker efter.
6. I fältet **Egenskapstyp**, välj **Certifikat**.
7. I fältet **Tillgängliga egenskaper**, ange den certifikattyp som du söker efter.

## <a name="assign-a-project-resource-to-a-project"></a>Tilldela en projektresurs till ett projekt

1. På sidan **Alla projekt** markerar du projektet **XYZ-uppgradering fas 2**.
2. På fliken **Projektteam och tidsplanering** markerar du **Lägg till**.
3. I fältet **Roll**, välj **Teammedlem**.
4. Markera **Boka via kalender**.
5. På sidan **Resurstillgänglighet** markerar du **Visa inställningar**.
6. På sidan **Justera visningsinställningar**, ange följande värden:

    - **Vy för format för datumintervall:** Dag
    - **Visa beskrivningar av tillgänglighet:** Ja
    - **Visa resterande kapacitet:** Ja

7. Välj en resurs i listan över resurser.
8. Markera **Fast bokning** och **Full kapacitet**.

## <a name="assign-a-resource-to-a-default-role"></a>Tilldela en resurs till en standardroll

Om du vill hjälpa projektledare eller resursansvariga kan du ytterligare fördjupa dig i resurserna som kan reserveras för ett projekt. Du kan associera en standardroll med en befintlig resurs eller en nyligen anskaffad resurs. Exempelvis när Daniel anställdes hade han erfarenhet och sakkunskap som passade för rollen Affärsanalytiker. Resursansvarige tilldelade den här rollen som Daniels standardroll. Därefter lade resursansvarige till Daniel i en pool med affärsanalytiker som är tillgängliga för arbete i projekt.

Under resursreserveringen kan projektledare filtrera rollresurserna som är tillgängliga för arbete i projekt. De kan använda den här informationen som ett villkor när de använder beslutsanalys för flera kriterier under resursuppfyllelse. De kan också lägga till andra resursegenskaper till filtret om du vill söka efter resurser som har specifika färdigheter, utbildning och erfarenheter för ett visst projekt.

**Scenario:** Ett godkänt projekt har startat och den seniora projektledarrollen reserverades som en planerad resurs under projektplanläggningsfasen. Resurschefen har nu fått en resurs för att uppfylla den seniora rollen som projektledare.

1. På sidan **Resurslista** markerar du **Daniel Goldschmidt**.
2. På sidan **Resursroll** markerar du **Nytt** och anger sedan följande värden:

    - **Giltighet:** Ange aktuellt datum.
    - **Utgår:** Ange **Aldrig**.
    - **Roll:** Ange **Senior Project Manager**.

3. Markera **Spara** och stäng sedan sidan.
4. På fliken **Kompetenser**, lägg till färdigheten **ProjectMgmt** och **PMP**.
