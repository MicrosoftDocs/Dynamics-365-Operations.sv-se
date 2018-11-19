---
title: Skapa en processmall i Attract
description: "Det här avsnittet ger information om hur du skapar processmallar i Attract."
author: hasrivas
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 54c80f3d785ba7a7e0158c51201468f45796c193
ms.contentlocale: sv-se
ms.lasthandoff: 10/22/2018

---

# <a name="create-a-process-template-in-attract"></a>Skapa en processmall i Attract

[!include [banner](includes/banner.md)]

A *mall för nyanställning* innehåller de aktiviteter som ska ingå i anställningsprocessen för ett jobb. Det här avsnittet beskriver elementen i en processmall i Microsoft Dynamics 365 for Talent: Attract. Här förklaras också hur du skapar en mall.

> [!NOTE]
> Mallen är en del av tillägg för Comprehensive Hiring för Attract.

## <a name="template-management"></a>Mallhantering

Organisationer kan bestämma om teammedlemmar eller endast administratörer kan skapa processmallar i Attract. Konfigurera mallhantering genom att gå till **Administratörscenter** \> **Mallhantering**. Aktivera mallhantering för att skapa deras egna mallar. Om du inte aktiverar mallhantering kan endast administratörer skapa mallar.

## <a name="default-template"></a>Standardmall

Endast administratörer kan ange standardmallen. Standardmallen används om en mall inte markerats när ett jobb skapas. För att konfigurera standardmallen, gå till **Administratörscenter** \> **Mallhantering**. Markera knappen med tre punkter på kortet för mallen som bör vara standardmallen (**...**) och välj sedan **ange som standard**.

## <a name="create-a-process-template"></a>Skapa en processmall

Administratörer, rekryterare och anställningschefer kan skapa processmallar. En processmall består av *faser* och *aktiviteter*. Faser grupperar en eller flera aktiviteter. Som standard har varje processmall aktiviteterna potentiell kandidat, ansökan och erbjudanden. Faserna som innehåller dessa aktiviteter kan döpas om. Du kan lägga till fler faser genom att markera **+ Ny fas**. Du kan ta aktiviteter till en fas antingen genom att dra dem till lämplig fas eller genom att dubbelklicka på dem i aktivitetslistan.

> [!NOTE]
> Fasnamn visas för kandidater på sidan **Ansökningsstatus**. Du bör tänka på detta när du väljer namn för faser.

FÖr mer information om aktiviteter, se [Aktiviteter vid anställningsprocess i Attract](./activities-attract.md).

Följ dessa steg om du vill skapa en mall för anställningsprocesser.

1. Gå till **Mallar**.
2. Välj **Nytt**.
3. I fältet **mallnamn**, ange ett namn för mallen och välj sedan **Skapa**.
4. I lista **Välj godkännandeprocessen** väljer du **standard** för att begära godkännande för ett jobb.
5. Välj om du vill aktivera eller inaktivera potentiella kandidater.
6. Valfritt: Lägg till eller ta bort faser.

    - Lägg till en fas genom att markera **+ Ny fas**.
    - Om du vill ta bort en fas, för pekaren över fasen och välj knappen för papperskorgen som visas.

        > [!NOTE]
        > Faserna potentiell kandidat, ansökan och erbjudanden kan inte tas bort, men kan ändra namn.

7. Valfritt: Lägg till eller ta bort aktiviteter.

    - Om du vill lägga till en aktivitet, drar du den från listan till höger till lämplig fas. Du kan också dubbelklicka på aktiviteten och sedan välja fasen som den ska läggas till i.
    - Om du vill ta bort en aktivitet, expandera den och välj sedan knappen för papperskorgen i aktivitetshuvudet.

8. Välj **Spara**.

