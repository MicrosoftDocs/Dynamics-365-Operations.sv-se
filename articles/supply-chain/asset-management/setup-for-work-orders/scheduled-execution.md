---
title: Schemalagt utförande
description: I denna artikel beskrivs schemalagd körning i Tillgångshantering.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e9d6af5c224f683481378da57708fda3c1b7207
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848061"
---
# <a name="scheduled-execution"></a>Schemalagt utförande

[!include [banner](../../includes/banner.md)]

 

Du kan använda servicenivåer för arbetsorder när du vill ange schemalagt utförande. (Mer information om servicenivåer för arbetsorder finns i [Servicenivå och beskrivning](service-level-and-description.md).) Schemalagt utförande ger flexibilitet vid arbetsplanering av underhållsarbetare, eftersom du kan ange mer detaljerade eller mindre detaljerade krav för intervallet som en arbetsorder ska slutföras under. En underhållsarbetare som utför jobbet snabbare än väntat i en produktionsanläggning kan till exempel gå vidare till ett annat närliggande jobb som har planerats för den aktuella veckan men inte nödvändigt vis för den aktuella dagen. På så sätt kan du optimera planeringen av arbetare och jobbslutförande.

Den schemalagda utförandeinställningen, som är relaterad till arbetsorder, kan vara allmän eller specifik. Du kan konfigurera allmänna rader som inte är begränsade till specifika arbetsordertyper, tillgångstyper och så vidare. Du kan också skapa planerade körningsrader som gäller för en specifik arbetsordertyp, tillgångstyp, underhållsjobbtyp och så vidare.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Schemalagt utförande**.
2. Klicka på **Ny** för att skapa en schemalagd utföranderad.
3. I fälten **Funktionsplats**, **Arbetsordertyp**, **Tillgångstyp**, **Tillverkare**, **Modell**, **Kategori av underhållsjobbtyp**, **Underhållsjobbtyp**, **Variant av underhållsjobbtyp** och **Yrkesgren** väljer du värden efter behov.
4. Välj en servicenivå för arbetsorder i fältet **Servicenivå**. Om du lämnar det här fältet tomt skapar du den mest allmänna typen av schemalagd utföranderad. Ett exempel på en allmän rad finns i den första posten i illustrationen nedan. Den raden aktiverar alla arbetsorder som inte har någon servicenivå för arbetsorder som ska schemaläggas för ett visst datum och en viss tid.
5. Välj tidsintervall i fältet **Schemalagt utförande**.
6. Välj **Spara**.

![Schemalagd körning.](media/20-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]