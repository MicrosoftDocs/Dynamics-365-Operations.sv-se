---
title: Lägga till typer av betalningsbelopp
description: Det här avsnittet beskriver hur du konfigurerar betalningsbeloppet i Leasing av tillgångar.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 037afa458277a3a07bcb937c6ec4d961d0dd5ca9
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968329"
---
# <a name="add-payment-amount-types"></a>Lägga till typer av betalningsbelopp

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du konfigurerar betalningsbeloppet i Leasing av tillgångar. På det här sättet kan du specificera leasingbetalningsbeloppet i stället för att lägga till klumpsummabeloppet på raderna i betalningsplanen.

Om du vill lägga till typer av betalningsbelopp gör du följande.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Typer av betalningsbelopp**.
2. Välj **Ny**.
3. Ange den nya betalningstypen och en beskrivning.

> [!NOTE]
> För omvärdering av IFRS 16-index måste du skapa en betalningsbeloppstyp och markera den som **Använd för omvärdering av IR IFRS 16-index**.  Denna betalningsbeloppstyp kommer att användas när indexomvärderingsprocessen körs mot IFRS 16 bok, och den kommer att beakta de förändringar som inträffade på grund av indexomvärderingsprocessen.
>
> När alternativet **Betalningsfördelningstypen** i leasingen anges till **Ja**, om indexomvärderingen för IFRS 16 körs, men det inte finns någon betalningstyp för IFRS 16, slutförs inte processen.

Endast en post kan markeras som **Använd för omvärdering av IFRS 16-index**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
