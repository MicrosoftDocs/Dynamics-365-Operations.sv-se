---
title: Schemalagt utförande
description: I det här avsnittet beskrivs schemalagt utförande i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 976155b685498456952f7d715779d20191712103
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437698"
---
# <a name="scheduled-execution"></a>Schemalagt utförande

[!include [banner](../../includes/banner.md)]

 

Du kan använda servicenivåer för arbetsorder när du vill ange schemalagt utförande. (Mer information om servicenivåer för arbetsorder finns i [Servicenivå och beskrivning](service-level-and-description.md).) Schemalagt utförande ger flexibilitet vid arbetsplanering av underhållsarbetare, eftersom du kan ange mer detaljerade eller mindre detaljerade krav för intervallet som en arbetsorder ska slutföras under. En underhållsarbetare som utför jobbet snabbare än väntat i en produktionsanläggning kan till exempel gå vidare till ett annat närliggande jobb som har planerats för den aktuella veckan men inte nödvändigt vis för den aktuella dagen. På så sätt kan du optimera planeringen av arbetare och jobbslutförande.

Den schemalagda utförandeinställningen, som är relaterad till arbetsorder, kan vara allmän eller specifik. Du kan ställa in allmänna rader som inte är begränsade till specifika arbetsordertyper, tillgångstyper och så vidare. Du kan också skapa planerade körningsrader som gäller för en specifik arbetsordertyp, tillgångstyp, underhållsjobbtyp och så vidare.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Schemalagt utförande**.
2. Klicka på **Ny** för att skapa en schemalagd utföranderad.
3. I fälten **Funktionsplats**, **Arbetsordertyp**, **Tillgångstyp**, **Tillverkare**, **Modell**, **Kategori av underhållsjobbtyp**, **Underhållsjobbtyp**, **Variant av underhållsjobbtyp** och **Yrkesgren** väljer du värden efter behov.
4. Välj en servicenivå för arbetsorder i fältet **Servicenivå**. Om du lämnar det här fältet tomt skapar du den mest allmänna typen av schemalagd utföranderad. Ett exempel på en allmän rad finns i den första posten i illustrationen nedan. Den raden aktiverar alla arbetsorder som inte har någon servicenivå för arbetsorder som ska schemaläggas för ett visst datum och en viss tid.
5. Välj tidsintervall i fältet **Schemalagt utförande**.
6. Välj **Spara**.

![Schemalagt utförande](media/20-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]